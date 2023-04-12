# Maintainer: Robotic-Brain <archaur@roboticbrain.de>
pkgname=openldap-rfc2307bis-git
pkgver=r3
pkgrel=1
pkgdesc="OpenLDAP schema for the official RFC2307bis draft LDAP schema."
arch=('any')
url="https://github.com/jtyr/rfc2307bis"
license=('MIT')
depends=('openldap')
makedepends=('git')
provides=("${pkgname%-git}")
conflicts=("${pkgname%-git}")
source=('git+https://github.com/jtyr/rfc2307bis.git')
sha256sums=('SKIP')
pkgver() {
	cd "${srcdir}/${pkgname%-git}"
	printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

package() {
	cd "${srcdir}/${pkgname%-git}"
	install -Dm444 rfc2307bis.schema "${pkgdir}/etc/openldap/schema/rfc2307bis.schema"
	install -Dm444 LICENSE "${pkgdir}/usr/shar/licenses/${pkgname%-git}/LICENSE"
}
