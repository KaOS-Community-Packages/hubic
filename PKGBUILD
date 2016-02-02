pkgname=hubic
pkgver=2.1.0
pkgrel=1
pkgdesc="Synchronization service provided by OVH."
arch=("x86_64")
url="https://hubic.com/"
license=('custom')
depends=('mono>=2.10')
install=hubic.install
changelog=CHANGELOG
source=(http://mir7.ovh.net/ovh-applications/hubic/hubiC-Linux/${pkgver}/hubiC-Linux-${pkgver}.${_pkgbuildver}-linux.tar.gz)
sha1sums=('8bc1d8dadcdfa44016440cdf6c3b0b87d403d7a5)

package() {
  cd "$pkgname"
  make PREFIX="$pkgdir/usr" RUNTIME_PREFIX="/usr" DBUSSERVICE_DIR="$pkgdir/usr/share/dbus-1/services" install
  install -dm 755 $pkgdir/usr/share/licenses/hubic
  mv $pkgdir/usr/share/doc/hubic/copyright $pkgdir/usr/share/licenses/hubic/LICENSE
  install -Dm 644 doc/Contrat_hubiC_2013.pdf $pkgdir/usr/share/licenses/hubic/CGU-fr_FR.pdf
}
