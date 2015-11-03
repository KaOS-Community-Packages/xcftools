pkgname=xcftools
pkgver=1.0.7
pkgrel=1
pkgdesc="Miscellaneous command line tools for use with the open XCF format used by The GIMP"
url="http://henning.makholm.net/software"
arch=('x86_64')
license=('GPL2' 'perl')
depends=('libpng' 'perl')
optdepends=('gimp')
makedepends=('libpng')
source=("http://henning.makholm.net/${pkgname}/${pkgname}-${pkgver}.tar.gz"
        "${pkgname}.patch")
sha512sums=('88af4791e18650562db259bd96bfd122364c21b7ea7a5692d4679e619667bdbcc179040a1d912c8fd623bc2d2735461da237ccde4646553b15d6072cc4493203'
            'd85529e77666b5453f61c6e48eaf5569b05ae6ab9eab5e549062385dcae67981a10efbbe4a69b9dc344daea34c5b424d6b4ac44430cf79268433da4be676bd10')

build() {
    cd "${srcdir}/${pkgname}-${pkgver}"
    patch -i ../${pkgname}.patch
    ./configure --prefix=/usr
    make
}

package() {
    cd "${srcdir}/${pkgname}-${pkgver}"
    make DESTDIR="${pkgdir}" install
}
