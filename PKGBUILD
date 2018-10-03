# Maintainer: Yoshua Wuyts (yoshuawuyts@gmail.com)
pkgname=brother-hll2310d
pkgver=4.0.0_1
pkgrel=1
pkgdesc="Brother HL-L2310D CUPS driver"
url="http://www.brother.com"
arch=('x86_64' 'i686')
depends=('perl' 'bash')
license=('custom:Brother')
source=(
  http://download.brother.com/welcome/dlf103531/hll2310dpdrv-${pkgver//_/-}.i386.rpm
)
md5sums=(
  '786ededd9b19d559dcb49160bb81c8a2'
)

if [[ "$CARCH" == "x86_64" ]]; then
  depends+=('lib32-glibc')
fi

package() {
  mkdir -p "${pkgdir}/opt"
  cp -R "${srcdir}/opt/brother" "${pkgdir}/opt/brother"

  mkdir -p "${pkgdir}/usr/lib/cups/filter"
  echo "#! /usr/lib/cups/filter/brother_lpdwrapper_HLL2310D" > "${srcdir}/filter-shim"
  install -m 0755 -o root -g root "${srcdir}/filter-shim" "${pkgdir}/usr/lib/cups/filter/brother_lpdwrapper_HLL2310D"

  mkdir -p "${pkgdir}/usr/share/ppd/cupsfilters"
  install -m 0644 -o root -g root \
    "${pkgdir}/opt/brother/Printers/HLL2310D/cupswrapper" \
    "${pkgdir}/usr/share/ppd/cupsfilters"
}
