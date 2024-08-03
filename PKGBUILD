pkgname=kcoreaddons
pkgver=6.4.0
pkgrel=1
pkgdesc='Addons to QtCore'
arch=(x86_64)
url='https://github.com/LingmoOS/kcoreaddons'
license=(LGPL-2.0-only LGPL-3.0-only)
depends=(gcc-libs
         glibc
         qt6-base
         systemd-libs)
makedepends=(doxygen
             extra-cmake-modules
             qt6-declarative
             qt6-doc
             qt6-tools)
optdepends=('qt6-declarative: QML bindings')
groups=(kf6)
source=(git+$url)
sha256sums=('SKIP')
validpgpkeys=('41EF7182553A87AC18196A77F27F2FDA54F067D8') # Lingmo OS Team <team@lingmo.org>

build() {
  cmake -B build -S $pkgname \
    -DBUILD_TESTING=OFF \
    -DBUILD_QCH=ON
  cmake --build build -j12
}

package() {
  DESTDIR="$pkgdir" cmake --install build
}

