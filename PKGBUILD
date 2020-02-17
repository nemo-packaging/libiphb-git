# $Id$
# Maintainer: TheKit <nekit1000 at gmail.com>
# Maintainer: James Kittsmiller (AJSlye) <james@nulogicsystems.com>

pkgname=libiphb-git
pkgver=1.2.5+git1.r0.g62091c5
pkgrel=1
pkgdesc="C API for using IP Heartbeat service"
arch=('x86_64' 'aarch64')
url="https://git.sailfishos.org/mer-core/libiphb"
license=('GPL')
depends=('dbus-glib' 'libdsme')
makedepends=('git' 'mce-headers-git')
provides=("${pkgname%-git}")
conflicts=("${pkgname%-git}")
source=('git+https://git.sailfishos.org/mer-core/libiphb.git')
md5sums=('SKIP')

pkgver() {
	cd "$srcdir/${pkgname%-git}"
	git describe --long --tags | sed 's/\([^-]*-g\)/r\1/;s/-/./g'
}

build() {
	cd "$srcdir/${pkgname%-git}"
    ./autogen.sh
    ./configure --prefix=/usr
    make
}

package() {
	cd "$srcdir/${pkgname%-git}"
	make DESTDIR="$pkgdir/" install
}
