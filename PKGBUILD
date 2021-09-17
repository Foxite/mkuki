# Maintainer: Foxite <the@dirkkok.nl>
pkgname=mkuki
pkgver=0.1.0
pkgrel=1
epoch=0
pkgdesc='Build and sign a Unified Kernel Image'
url='https://github.com/Foxite/mkuki'
arch=('any')
license=('MIT')
changelog=CHANGELOG
source=("https://github.com/Foxite/mkuki/releases/download/v$pkgver/v$pkgver.tar.gz"{,.gpg})
depends=('binutils')
makedepends=('perl')
optdepends=('sbsigntools: for signing EFI images')
md5sums=('2288302db03e8f002c7e31d53cd5b3ec'
         'cc4df7bd56fefab2125a56e1a75cfedf')
sha256sums=('719046c211b653b1d2597f6c9aa362ca2a2b191a1efa3ddf4f26d3e0f00d6daf'
            '5a0229f250a31029a1c8193baf05e13cd1e00cd5c20d29b629d3b6153b48b2b3')
validpgpkeys=('EE05738A0F76012F5CF673DF60BD929EFA66E01F') # Foxite <the@dirkkok.nl>

build() {
	pod2man --section=1 --release="$pkgver" mkuki.pod | gzip > mkuki.1.gz
}

package() {
	install -Dm755 $pkgname $pkgdir/usr/bin/$pkgname
	install -Dm744 $pkgname.1.gz $pkgdir/usr/share/man/man1/mkuki.1.gz
}

