# Maintainer: Mic <nomaster@chaosdorf.de>

pkgname=batman-alfred
pkgver=2014.1.0
pkgrel=1
pkgdesc='Almighty Lightweight Fact Remote Exchange Daemon'
arch=('i686' 'x86_64')
url='http://www.open-mesh.net/'
license=('GPL')
source=(
  "http://downloads.open-mesh.net/batman/releases/batman-adv-${pkgver}/alfred-${pkgver}.tar.gz"
  "alfred@.service"
  "batadv-vis@.service"
  )
depends=('gpsd')

build(){
  cd "${srcdir}/alfred-${pkgver}"
  make
}
package() {
  cd "${srcdir}/alfred-${pkgver}"
  make DESTDIR="${pkgdir}"  PREFIX=/usr SBINDIR=/usr/bin install
  mkdir -p "${pkgdir}/usr/lib/systemd/system/"
  install -Dm644 "${srcdir}/alfred@.service" "${pkgdir}/usr/lib/systemd/system/"
  install -Dm644 "${srcdir}/batadv-vis@.service" "${pkgdir}/usr/lib/systemd/system/"
}

sha256sums=(
  'ed00ba9ab5acf1457a9e4d6f580d23df91b097f58f90f8d2c31dffb2cd4ce16a'
  '5059fb9e7ffdc9de65562a5def88e091df470be9191d66f092e98636419d5aac'
  '74d723d73e4ed750ed70b46bf892f153632d76ecfbcdf5e5cb6ba7ecc5bb383a'
  )
