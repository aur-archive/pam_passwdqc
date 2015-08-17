# $Id: PKGBUILD 356 2008-04-18 22:56:27Z aaron $
# Maintainer: Miah Johnson <miah (at) chia-pet dot org>
# Contributor: juergen <juergen@archlinux.org>
# Contributor: Manolis Tzanidakis
# Contributor: Viaken <viaken@gmail.com>

pkgname=pam_passwdqc
pkgver=1.0.5
pkgrel=4
pkgdesc="A password strength checking module for PAM-aware password changing programs."
arch=(i686 x86_64 armv6h)
url="http://www.openwall.com/passwdqc"
depends=('pam')
license=('custom')
source=(http://www.openwall.com/pam/modules/${pkgname}/${pkgname}-${pkgver}.tar.gz)
md5sums=('cd9c014f736158b1a60384a8e2bdc28a')

build() {
  cd ${startdir}/src/${pkgname}-${pkgver}
  make || return 1
}

package() {
  cd ${startdir}/src/${pkgname}-${pkgver}
  make SECUREDIR="/usr/lib/security" DESTDIR="${pkgdir}" MANDIR="/usr/man" install || return 1
  install -d ${pkgdir}/usr/share/licenses/${pkgname}
  install ${srcdir}/${pkgname}-${pkgver}/LICENSE ${pkgdir}/usr/share/licenses/$pkgname/
}
# vim: ts=2 sw=2 et ft=sh
