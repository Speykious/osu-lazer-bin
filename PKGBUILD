## Maintainer: Speykious <speykious@gmail.com>

pkgname=osu-lazerious
_pkgver=`cat current_version`
pkgver=`echo "$_pkgver" | tr '\\:/\- ' '_'`
pkgrel=1
pkgdesc="The future of osu! and the beginning of an open era! Commonly known by the codename osu!lazer. Pew pew."
arch=('x86_64')
url="https://osu.ppy.sh"
license=('MIT' 'custom:CC-BY-NC 4.0')
depends=(ffmpeg zlib libgl sdl2 fuse2)
provides=(osu-lazer)
conflicts=(osu-lazer)
options=(!strip)
source=("$pkgname-$_pkgver.AppImage::https://github.com/ppy/osu/releases/download/$_pkgver/osu.AppImage"
        "$pkgname.png::https://raw.githubusercontent.com/ppy/osu/master/assets/lazer.png"
        "$pkgname-LICENCE.md::https://raw.githubusercontent.com/ppy/osu-resources/master/LICENCE.md"
        "$pkgname.xml"
        "$pkgname.desktop")
noextract=("$pkgname-$_pkgver.AppImage")
sha256sums=('4ccfb1f93dc42f6f04adae5e4519a19ee9c5f1aa09dabea84d3be3343d3ca7d2'
            '36f73cfe0a84cd65a8bb54fcde5a01c419b134bee4a88cc92eb4f33236343a10'
            '30b914824784b6ba6b30a44b22bea4f3c6fbc10f3f0e74fde5ca76a92ef57244'
            'fa5c5ebf1546e855103db2f97721448cb60c3cdf85c370e266c8a6eb0094e1b5'
            'af516b1ba81aa2203d0655a2721d3bd71ea79ef976bb6008def2ae69a9efd3e8')

package() {
	# Install image
	install -Dm644 "$pkgname.png" "$pkgdir/usr/share/pixmaps/osu-lazer.png"

    # Install mime types
	install -Dm644 "$pkgname.xml" "$pkgdir/usr/share/mime/packages/osu-lazer.xml"

	# Install license
	install -Dm644 "$pkgname-LICENCE.md" "$pkgdir/usr/share/licenses/$pkgname/LICENCE.md"

	# Install desktop file
	install -Dm644 "$pkgname.desktop" "$pkgdir/usr/share/applications/osu-lazer.desktop"

	# Install binary
	install -Dm755 "$pkgname-$_pkgver.AppImage" "$pkgdir/usr/bin/osu-lazer"
}
