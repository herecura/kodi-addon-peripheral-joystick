# Maintainer: BlackEagle <ike.devolder@gmail.com>>

pkgname=kodi-addon-peripheral-joystick
pkgver=1.4.7
pkgrel=18
pkgdesc="Joystick support for Kodi"
arch=('x86_64')
url='https://github.com/xbmc/peripheral.joystick'
license=('GPL')
groups=('kodi-addons' 'kodi-addons-peripheral')
depends=('kodi-platform')
makedepends=('cmake' 'kodi-dev')
source=("$pkgname-$pkgver.tar.gz::https://github.com/xbmc/peripheral.joystick/archive/v$pkgver.tar.gz")
sha512sums=('89d9c993f598f7660fccfcc1926ad3b944d88586b0399b3e47524fe5a68665eec8fc7b196acd6d59e36488f830afef50c402ecd05d69cee75c21a69c538e9acd')

build() {
    cd "peripheral.joystick-$pkgver"
    cmake \
        -DCMAKE_INSTALL_PREFIX=/usr \
        -DCMAKE_BUILD_TYPE=Release \
        -DBUILD_SHARED_LIBS=1 \
        -DUSE_LTO=1 \
        .
    make
}

package() {
    cd "peripheral.joystick-$pkgver"
    make DESTDIR="$pkgdir/" install
}

