## Maintainer: Speykious <speykious@gmail.com>

pkgname=osu-lazer-bin
_pkgver=`cat current_version`
pkgver=`echo "$_pkgver" | tr '\\:/\- ' '_'`
pkgrel=1
pkgdesc="The future of osu! and the beginning of an open era! Commonly known by the codename osu!lazer. Pew pew."
arch=('x86_64')
url="https://osu.ppy.sh"
license=('MIT' 'custom:CC-BY-NC 4.0')
groups=()
depends=(ffmpeg zlib libgl sdl2 fuse2)
makedepends=()
checkdepends=()
optdepends=()
provides=(osu-lazer)
conflicts=(osu-lazer)
replaces=()
backup=()
options=(!strip)
install=
changelog=
source=("$pkgname-$_pkgver.AppImage::https://github.com/ppy/osu/releases/download/$_pkgver/osu.AppImage"
        "$pkgname.png::https://raw.githubusercontent.com/ppy/osu/master/assets/lazer.png"
        "$pkgname-LICENCE.md::https://raw.githubusercontent.com/ppy/osu-resources/master/LICENCE.md"
        "osu-lazer.desktop")
noextract=("$pkgname-$_pkgver.AppImage")
sha256sums=(`cat osu_sha256sum`
            "36f73cfe0a84cd65a8bb54fcde5a01c419b134bee4a88cc92eb4f33236343a10"
            "30b914824784b6ba6b30a44b22bea4f3c6fbc10f3f0e74fde5ca76a92ef57244"
            "0887ee7e6594abd1c067597316fdbaa8344077e23c4507258ef11ddf7c17cd09")
package() {
	 # Install image
	 install -Dm644 "$srcdir/$pkgname.png" "$pkgdir/usr/share/pixmaps/osu-lazer.png"

	 # Install license
	 install -Dm644 "$srcdir/$pkgname-LICENCE.md" "$pkgdir/usr/share/licenses/$pkgname/LICENCE.md"

	 # Install desktop file
	 install -Dm644 osu-lazer.desktop "$pkgdir/usr/share/applications/osu-lazer.desktop"

	 # Install binary
	 install -Dm755 "$srcdir/$pkgname-$_pkgver.AppImage" "$pkgdir/usr/bin/osu-lazer"
}
