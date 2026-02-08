# Maintainer: SSRVodka <sjtuxhw at gmail dot com>
# Contributor: FabioLolix
# Contributor: archplayer
# Contributor: RemiliaForever <remilia AT koumakan DOT cc>
# Contributor: Felix Yan <felixonmars@gmail.com>
# Contributor: Christoph Drexler <chrdr at gmx dot at>
# Contributor: Jelle van der Waa <jellevdwaa@gmail.com>

_pkgname=xmind
pkgname="$_pkgname-voxel2308"
_pkgver=23.08.02122-202308281754
pkgver=${_pkgver//-/.}
pkgrel=1
pkgdesc="Brainstorming and Mind Mapping Software"
arch=(x86_64)
url="https://www.xmind.net"
license=(unknown)
depends=(gtk3 alsa-lib libxkbfile nss)
options=(!strip)
provides=("$_pkgname")
conflicts=("$_pkgname")

source_x86_64=(
  "https://github.com/SSRVodka/xmind-aur-23.08/releases/download/23.08/Xmind-for-Linux-amd64bit-${_pkgver}.deb" 
  "${_pkgname}.desktop" 
  "${_pkgname}.sh"
)

sha256sums_x86_64=('403464a23c473796ad14d89b010504d7d4e9dec0a0f2a0752e1e2b61197d51a2'
                   '26e0a8e4c7e7bd7f9c46e52f5a80de808566d9619a3df1a83fb4dda916172bae'
                   '686e5f4c0f4b26c9e66903d18550730b7496a155cfe46e2361b7293dd20677eb')

package() {
  bsdtar -xf ${srcdir}/data.tar.xz -C ${pkgdir}/
  install -d "$pkgdir/usr/bin"

  # Add custom desktop file
  install -m644 "${srcdir}/${_pkgname}.desktop" "${pkgdir}/usr/share/applications/${_pkgname}.desktop"
  
  # Add custom launcher to allow passing user flags
  install -m755 "${srcdir}/${_pkgname}.sh" "${pkgdir}/usr/bin/${_pkgname}"
}
