pkgname=g923-dkms
pkgver=1.0.0
pkgrel=4
_commit=2519aceaf7f03d65da699fd9360f49e9ed740b41
pkgdesc="DKMS patched drivers for the G923 steering wheel"
arch=('any')
url='https://github.com/ricky26/linux/tree/g923'
license=('GPL2')
depends=('dkms')
options=('!strip')
source=("git://github.com/ricky26/linux.git#commit=$_commit"
        dkms.conf)
        
md5sums=('SKIP'
         '1e34b10d69f0cd255e707192225b5d30')

package() {
  mkdir -p "${pkgdir}/usr/src"
  cp -r "$srcdir/linux/drivers" "${pkgdir}/usr/src/g923-${pkgver}"
  install -Dm644 "${srcdir}/dkms.conf" "${pkgdir}/usr/src/g923-${pkgver}/dkms.conf"
}

