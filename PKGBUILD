# Maintainer: Antonio Rojas <nqn1976 @ gmail.com>
# Contributor: Andrea Scarpino <andrea@archlinux.org>

pkgname=libmm-qt5-git
pkgver=r166.7370207
pkgrel=1
pkgdesc='Qt-only wrapper for ModemManager DBus API'
arch=('i686' 'x86_64')
url='https://projects.kde.org/projects/extragear/libs/libnm-qt'
license=('LGPL')
depends=('modemmanager' 'qt5-base')
makedepends=('extra-cmake-modules' 'git')
conflicts=('libmm-qt5')
provides=('libmm-qt5')
source=("git://anongit.kde.org/libmm-qt.git")
sha256sums=('SKIP')

pkgver() {
  cd libmm-qt
  printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

prepare() {
  mkdir -p build
}

build() {
  cd build
  cmake ../libmm-qt \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_INSTALL_PREFIX=/usr \
    -DLIB_INSTALL_DIR=lib
  make
}

package() {
  cd build
  make DESTDIR="${pkgdir}" install
}
