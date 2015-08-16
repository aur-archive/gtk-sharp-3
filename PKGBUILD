# Contributor: Lex Black <autumn-wind at web dot de>

_pkgname=gtk-sharp
pkgname=gtk-sharp-3
pkgver=2.99.2
pkgrel=1
pkgdesc="Mono/.NET binding to the cross platform Gtk+ GUI toolkit"
arch=('i686' 'x86_64')
url="https://github.com/mono/gtk-sharp"
license=('LGPL')
depends=('mono' 'gtk3')
#makedepends=('git' 'gtk2')
options=('!libtool')
source=("$pkgname-$pkgver.tar.gz::https://github.com/mono/gtk-sharp/archive/$pkgver.tar.gz")
md5sums=('1ce7abcb1899f91e5acc0fc4c93c92c2')


build() {
	cd "$srcdir/$_pkgname-$pkgver"

	./autogen.sh --prefix=/usr --sysconfdir=/etc --localstatedir=/var \
		--disable-static
	make
}

package() {
	cd "$srcdir/$_pkgname-$pkgver"

	make DESTDIR="$pkgdir/" install
	rm -r "$pkgdir"/usr/lib/monodoc
}
