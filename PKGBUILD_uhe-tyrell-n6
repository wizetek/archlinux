# Maintainer: Tom Wizetek <tom@wizetek.com>

pkgname=uhe-tyrell-n6
_pkgname=TyrellN6
pkgver=3.0
pkgrel=1
pkgdesc="Freeware synthesizer VST plugin from u-he"
arch=('x86_64' 'i686')
url="https://www.amazona.de/freeware-synthesizer-tyrell-n6-plugin-vst-au-win-mac/"
license=('custom')
groups=('vst-plugins')
source=('https://www.amazona.de/wp-content/tyrell/TyrellN6_V303_Linux.tar.gz'
	'https://www.amazona.de/wp-content/uploads/2016/10/Tyrell-N6_v3.0.3898_manual_ENG_v1.1.pdf')
md5sums=('c4c833ddbff347127db94c740b83b6be'
         'f27a4ccf1b418ebf6a8e650b81103798')

package() {
  install -dm755 "${pkgdir}/usr/share"
  cd "${srcdir}/${_pkgname}-3898"
  cp -r "${_pkgname}" "${pkgdir}/usr/share"

  install -Dm644 LinuxChangeLog.txt -t "${pkgdir}/usr/share/doc/${_pkgname}"

  install -dm755 "${pkgdir}/usr/lib/vst"
  cd "${srcdir}/${_pkgname}-3898/${_pkgname}"
  for so_file in *.so; do
    ln -sf "/usr/share/${_pkgname}/${so_file}" "${pkgdir}/usr/lib/vst/"
  done

  install -dm755 "${pkgdir}/usr/share/licenses/${_pkgname}"
  ln -sf "/usr/share/${_pkgname}/license.txt" "${pkgdir}/usr/share/licenses/${_pkgname}/"

  install -Dm644 "${srcdir}/Tyrell-N6_v3.0.3898_manual_ENG_v1.1.pdf" -t "${pkgdir}/usr/share/doc/${_pkgname}"
}
