# Maintainer: Neil Hanlon <neil@neilhanlon.com> 

pkgname=battery_warning
pkgver=1.0
pkgrel=1
pkgdesc='Warn if the battery capacity drops too low, but for gnome'
arch=('x86_64')
url='https://github.com/NeilHanlon/battery_warning'
license=('MIT')
depends=('libnotify')
makedepends=('git')
source=("$pkgname-$pkgver::git+https://github.com/NeilHanlon/battery_warning.git")
sha256sums=('SKIP')

prepare() {
	cd "$pkgname-$pkgver"
	git checkout $pkgver
}

build() {
	cd "$pkgname-$pkgver"
	make prefix=/usr
}

package() {
	cd "$pkgname-$pkgver"
	make DESTDIR=$pkgdir prefix=/usr systemd_prefix=/usr/lib install
	install -D -m 644 LICENSE $pkgdir/usr/share/licenses/$pkgname/LICENSE
}
