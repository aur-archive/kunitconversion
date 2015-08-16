# Maintainer: Andrea Scarpino <andrea@archlinux.org>

pkgname=kunitconversion
pkgver=4.99.0
pkgrel=1
pkgdesc='KUnitConversion'
arch=('i686' 'x86_64')
url='https://projects.kde.org/projects/frameworks/kunitconversion'
license=('LGPL')
depends=('kconfig' 'ki18n')
makedepends=('extra-cmake-modules')
groups=('kf5')
source=("http://download.kde.org/unstable/frameworks/${pkgver}/${pkgname}-${pkgver}.tar.xz")
md5sums=('7079e289918ac94c60fb29ea154b970e')

prepare() {
  mkdir -p build
}

build() {
  cd build
  cmake ../${pkgname}-${pkgver} \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_INSTALL_PREFIX=/opt/kf5 \
    -DLIB_INSTALL_DIR=lib \
    -DBUILD_TESTING=OFF
  make
}

package() {
  cd build
  make DESTDIR="${pkgdir}" install
}
