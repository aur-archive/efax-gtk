# Maintainer: Giovanni Scafora <giovanni@archlinux.org>

pkgname=efax-gtk
pkgver=3.2.8
pkgrel=1
pkgdesc="A GUI front end for the 'efax' fax program"
arch=('i686' 'x86_64')
url="http://efax-gtk.sourceforge.net/"
license=('GPL')
depends=('dbus-glib' 'gtk3' 'ghostscript')
makedepends=('pkg-config')
optdepends=('heirloom-mailx: to use the mail_fax script')
backup=('etc/efax-gtkrc')
install=efax-gtk.install
source=("http://downloads.sourceforge.net/${pkgname}/${pkgname}-${pkgver}.src.tgz")
md5sums=('275ad1706e5c38e2b153dddd8a16724f')

build() {
  cd "${srcdir}/${pkgname}-${pkgver}"

  ./configure --prefix=/usr \
              --sysconfdir=/etc \
              --with-spooldir=/usr/bin
  make
}

package() {
  cd "${srcdir}/${pkgname}-${pkgver}"

  make DESTDIR="${pkgdir}" install
  install -m 755 mail_fax print_fax "${pkgdir}/usr/bin"
}
