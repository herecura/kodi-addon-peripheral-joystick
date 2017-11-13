# $Id$
# Maintainer: BlackEagle <ike.devolder@gmail.com>>

pkgname=kodi-addon-peripheral-joystick
pkgver=1.3.3
pkgrel=1
pkgdesc="Joystick support for Kodi"
arch=('i686' 'x86_64')
url='https://github.com/xbmc/peripheral.joystick'
license=('GPL')
groups=('kodi-addons' 'kodi-addons-peripheral')
depends=('kodi-platform')
makedepends=('cmake' 'kodi-dev')
source=("$pkgname-$pkgver.tar.gz::https://github.com/xbmc/peripheral.joystick/archive/v$pkgver.tar.gz")
sha512sums=('e566cfab838b471f4d5cd6d1bde48479868bf1e401e2d5512627f6cfad606c9ec359fade3612dc32424b4a5baffad82278d25906e59062bea9e8aea009754a78')

build() {
    cd "peripheral.joystick-$pkgver"
	cmake \
		-DCMAKE_INSTALL_PREFIX=/usr \
		-DCMAKE_BUILD_TYPE=Release \
		-DBUILD_SHARED_LIBS=1 \
		-DUSE_LTO=1
	make
}

package() {
    cd "peripheral.joystick-$pkgver"
	make DESTDIR="$pkgdir/" install
}

