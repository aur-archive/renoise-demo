# Maintainer: Max Pray a.k.a. Synthead <synthead@gmail.com>
# Contributor: berkus <berkus@madfire.net>
# Contributor: hm_b <holger@music-nerds.net>

pkgname="renoise-demo"
pkgver="3.0.1"
pkgrel="1"
pkgdesc="A sophisticated music sequencer and audio processing application"
arch=("i686" "x86_64")
url="http://www.renoise.com"
license=("custom:renoise")
depends=("alsa-lib" "libx11" "gcc-libs")
optdepends=("jack: For JACK audio support")
makedepends=("xdg-utils")
install="renoise.install"
options=("!strip")

# This blurb checks if the host machine is x86 or x86_64,
# then declares the $md5sums and $source arrays accordingly.
if [[ $CARCH = "x86_64" ]]; then
  if64="_64"
  sha1sums=("89c216908e1fea4569cb6d34819a1597c9aeec0c")
else
  sha1sums=("3b73bb74e3a537317cb15edef24eb3f8b3f22e82")
fi
source=("http://files.renoise.com/demo/Renoise_${pkgver//./_}_Demo_x86$if64.tar.bz2")

package() {
  cd "$srcdir/Renoise_${pkgver//./_}_Demo_x86$if64"

  mkdir -p "$pkgdir/usr/share/renoise-$pkgver"
  cp -r "Resources"/* "$pkgdir/usr/share/renoise-$pkgver"

  install -Dm 755 "renoise" "$pkgdir/usr/bin/renoise"
  install -Dm 644 "Installer/renoise.png" "$pkgdir/usr/share/icons/hicolor/48x48/apps/renoise.png"
  install -Dm 644 "Installer/renoise.desktop" "$pkgdir/usr/share/applications/renoise.desktop"
  install -Dm 644 "Installer/renoise.1.gz" "$pkgdir/usr/share/man/man1/renoise.1.gz"
  install -Dm 644 "Installer/renoise-pattern-effects.5.gz" "$pkgdir/usr/share/man/man5/renoise-pattern-effects.5.gz" 
  install -Dm 644 "License.txt" "$pkgdir/usr/share/licenses/$pkgname/License.txt"
}
