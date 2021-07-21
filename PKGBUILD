# Maintainer:

pkgname=dmenu-aseem
_pkgname=dmenu
pkgver=5.0.r578.a22e2b0
pkgrel=1
epoch=1
pkgdesc="My build of dmenu."
url='https://github.com/mistersmee/dmenu'
arch=(any)
license=('GPL')
depends=('make')
makedepends=('git')
source=('git://github.com/mistersmee/dmenu')
sha1sums=('SKIP')

provides=("${_pkgname}")
conflicts=("${_pkgname}")

pkgver() {
	cd "${_pkgname}"
	printf "%s.r%s.%s" "$(awk '/^VERSION =/ {print $3}' config.mk)" \
		"$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

prepare() {
	cd $srcdir/${_pkgname}
}

build() {
	cd "${_pkgname}"
	make
}

package() {
	cd "${_pkgname}"
	make PREFIX=/usr DESTDIR="${pkgdir}" install
}
