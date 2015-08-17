# Maintainer: psi23 <killerpsi23 at gmail dot com>

pkgname=ttf-adobe-fonts-cjkext
pkgver=11.0.09
pkgrel=1
pkgdesc="Adobe Asian and Extended Language Fonts from Adobe Reader XI"
arch=('any')
url='http://www.adobe.com/support/downloads/detail.jsp?ftpID=5508'
license=('custom')
makedepends=('p7zip')
optdepends=('ttf-adobe-fonts: Adobe Core Fonts from Adobe Reader XI')
conflicts=('acroread-fonts-systemwide')
install=${pkgname}.install
changelog=
source=("http://ardownload.adobe.com/pub/adobe/reader/win/${pkgver/.*/.x}/${pkgver}/misc/FontPack${pkgver//./}_XtdAlf_Lang.msi"
        "LICENSE")
md5sums=('51c08dd56aaec1999f27de05e118127f'
         '143d2b79910b40039aacd09fb165d974')

build() {
	cd ${srcdir}
	7z e $(basename ${source[0]}) -ir\!*.otf
}

package() {
	cd ${srcdir}
	mkdir -p ${pkgdir}/usr/share/fonts/OTF
	mkdir -p ${pkgdir}/usr/share/licenses/${pkgname}
	install -m 644 LICENSE ${pkgdir}/usr/share/licenses/${pkgname}
	install -m 644 *.otf ${pkgdir}/usr/share/fonts/OTF
}
