# Maintainer: Tomoyuki Harada <harada.tomoyuki03@gmail.com>

pkgname=poco-basic
pkgver=1.7.3
pkgrel=1
epoch=
pkgdesc="Cross-platform C++ libraries with a network/internet focus."
arch=('i686' 'x86_64')
url="http://www.pocoproject.org"
license=('custom:boost')
depends=('pcre' 'expat')
makedepends=('gcc' 'cmake')
provides=('poco')
conflicts=('poco' 'poco-dev')

source=(
	${url}/releases/poco-${pkgver}/poco-${pkgver}.tar.gz
)
sha256sums=('8bf7d8fbdcb0cf893fdc0bb064dd0b23d4d7f2c8ca2e54f1bd184f0ee0a9dd5a')

build() {
  mkdir -p poco-$pkgver/cmake_build
  cd poco-$pkgver/cmake_build
  cmake -DCMAKE_INSTALL_PREFIX=/usr -DENABLE_DATA=OFF -DENABLE_NETSSL=OFF -DENABLE_MONGODB=OFF -DENABLE_PAGECOMPILER=OFF -DENABLE_CRYPTO=OFF -DENABLE_PAGECOMPILER_FILE2PAGE=OFF -DENABLE_ZIP=OFF ..
  make
}

package() {
	cd poco-$pkgver/cmake_build
	make DESTDIR="$pkgdir/" install
}
