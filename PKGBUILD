pkgname=scarlett-dkms
pkgver=1.0.0
pkgrel=4
_commit=f496277bd7eb1977135c95ef7ae40b2852f0e263
pkgdesc="DKMS drivers for Focusrite Scarlett devices."
arch=('any')
url='https://github.com/geoffreybennett/scarlett-gen2/tree/scarlett-gen3'
license=('GPL2')
depends=('dkms')
options=('!strip')
source=(Makefile.patch
        dkms.conf
        "git://github.com/ricky26/linux.git#commit=$_commit")
md5sums=('5f318daa945e1a3b15a64e612148b899'
         '590c036d473073a66379ff77bc2bf32a'
         'SKIP')


prepare() {
  patch -p1 -d "$srcdir/linux/" -N -i "$srcdir/Makefile.patch"
}

package() {
  mkdir -p "${pkgdir}/usr/src"
  cp -r "$srcdir/linux/sound/usb" "${pkgdir}/usr/src/scarlett-${pkgver}"
  install -Dm644 "${srcdir}/dkms.conf" "${pkgdir}/usr/src/scarlett-${pkgver}/dkms.conf"
}
