# Contributor: Isaac Curtis <isaaccurtis1@gmail.com>
# Maintainer: Isaac Curtis <isaaccurtis1@gmail.com>

pkgname=zotero-beta
pkgver="5.0.35_beta.15+4add3ec44"
pkgrel=1
pkgdesc="Zotero Standalone. A free, easy-to-use tool to help you collect, organize, cite, and share your research sources."
arch=('i686' 'x86_64')
url="http://www.zotero.org/download"
license=('GPL3')
depends=('dbus-glib' 'gtk2' 'gtk3' 'gcc-libs' 'nss' 'libxt')
optdepends=('xpdf: PDF indexing')
conflicts=('zotero')
sha256sums=('8ec2a82b5c9b37e30cbe5ef968f5baa29e324a0e024a8cc28c38738ca3db7c7a')
sha256sums_i686=('961e1f47649a9634d2b21f8b046de35b41c1a9b717c40794ef3baf18b95a1380')
sha256sums_x86_64=('6caec085f860c14ce35378ec35bd3e810044ced2134457b8c48cc59352bf2770')

_ver=${pkgver//_/-}
_ver=${_ver//+/%2B}
install='zotero-beta.install'

source=("zotero-beta.desktop")
source_i686=("https://download.zotero.org/client/beta/${_ver}/Zotero-${_ver}_linux-i686.tar.bz2")
source_x86_64=("https://download.zotero.org/client/beta/${_ver}/Zotero-${_ver}_linux-x86_64.tar.bz2")

package() {
  mkdir -p "$pkgdir"/usr/{bin,lib/zotero}
  mv "$srcdir"/Zotero_linux-$CARCH/* "$pkgdir"/usr/lib/zotero
  ln -s /usr/lib/zotero/zotero "$pkgdir"/usr/bin/zotero
  install -Dm644 "$srcdir"/zotero-beta.desktop "$pkgdir"/usr/share/applications/zotero-beta.desktop
  # Copy zotero icons to a standard location
  install -Dm644 "$pkgdir"/usr/lib/zotero/chrome/icons/default/default16.png "$pkgdir"/usr/share/icons/hicolor/16x16/apps/zotero.png
  install -Dm644 "$pkgdir"/usr/lib/zotero/chrome/icons/default/default32.png "$pkgdir"/usr/share/icons/hicolor/32x32/apps/zotero.png
  install -Dm644 "$pkgdir"/usr/lib/zotero/chrome/icons/default/default48.png "$pkgdir"/usr/share/icons/hicolor/48x48/apps/zotero.png
}
