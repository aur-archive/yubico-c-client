# Maintainer: Christian Hesse <mail@eworm.de>

pkgname=yubico-c-client
pkgver=2.14
pkgrel=1
pkgdesc='Yubico YubiKey client C library'
arch=('i686' 'x86_64')
url='https://github.com/Yubico/yubico-c-client'
license=('BSD')
depends=('curl' 'yubico-c')
makedepends=('git' 'help2man')
provides=('ykclient')
conflicts=('ykclient' 'yubico-c-client-git')
source=("git://github.com/Yubico/yubico-c-client.git#tag=ykclient-${pkgver}")

build() {
	cd yubico-c-client/

	autoreconf -fi
	./configure --prefix=/usr
	make
}

check() {
	cd yubico-c-client/

	make check
}

package() {
	cd yubico-c-client/

	install -D -m0644 COPYING "${pkgdir}/usr/share/licenses/yubico-c-client/COPYING"
	install -D -m0644 README "${pkgdir}/usr/share/doc/yubico-c-client/README"
	make DESTDIR="${pkgdir}/" install
}

sha256sums=('SKIP')
