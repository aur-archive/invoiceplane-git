# Submitter: Jonas Heinrich <onny@project-insanity.org>
# Maintainer: Jonas Heinrich <onny@project-insanity.org>

pkgname=invoiceplane-git
_pkgname=InvoicePlane
pkgver=1.0.0.1.gdece25a
pkgrel=1
pkgdesc="Self hosted invoicing for freelancers and small businesses"
arch=(any)
url="https://invoiceplane.com/"
license=('MIT')
depends=('php')
optdepends=('php-mysql: for MySQL database support')
conflicts=('invoiceplane')
source=("git+https://github.com/InvoicePlane/InvoicePlane.git")
sha512sums=('SKIP')

pkgver() {
  cd "$SRCDEST/${_pkgname}"
  git describe --always | sed 's|-|.|g' | cut -f2 -d"v"
}

package() {
  cd ${srcdir}
  install -vdm0755 $pkgdir/usr/share/webapps
  mkdir -p $pkgdir/etc/webapps/invoiceplane
  cp -a "${_pkgname}" $pkgdir/usr/share/webapps/invoiceplane
  ln -s /usr/share/webapps/invoiceplane/application/config $pkgdir/etc/webapps/invoiceplane

  install -D "${_pkgname}/license.txt" "${pkgdir}/usr/share/licenses/${pkgname}/LICENSE"
}
