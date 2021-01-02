pkgname=scarlett-dkms
pkgver=1.0.0
pkgrel=1
_commit=4c8b43f358b96ba1c919afbc9d6f5952945eb56b
pkgdesc="DKMS drivers for Focusrite Scarlett devices."
arch=('any')
url='https://github.com/geoffreybennett/scarlett-gen2/tree/scarlett-gen3'
license=('GPL2')
depends=('dkms')
options=('!strip')
source=(Makefile.patch
        dkms.conf
        modprobe.conf
        "git://github.com/ricky26/linux.git#commit=$_commit")
md5sums=('5f318daa945e1a3b15a64e612148b899'
         '8952271791eb3c9cee39eaadeefe6b92'
         '5edf3d8707154c92c252f39dc9004e60'
         'SKIP')


prepare() {
  patch -p1 -d "$srcdir/linux/" -N -i "$srcdir/Makefile.patch"
}

package() {
  mkdir -p "${pkgdir}/usr/src"
  cp -r "$srcdir/linux/sound/usb" "${pkgdir}/usr/src/scarlett-${pkgver}"
  install -Dm644 "${srcdir}/dkms.conf" "${pkgdir}/usr/src/scarlett-${pkgver}/dkms.conf"
  install -Dm644 "${srcdir}/modprobe.conf" "${pkgdir}/usr/lib/modprobe.d/scarlett-dkms.conf"
}
