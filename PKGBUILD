# Maintainer: Foxite <the@dirkkok.nl>
pkgname=mkuki
pkgver=0.1.0
pkgrel=1
epoch=0
pkgdesc="Build and sign a Unified Kernel Image"
arch=('any')
license=('MIT')
changelog=CHANGELOG
source=('mkuki' 'mkuki.pod')
depends=('binutils')
makedepends=('perl')
optdepends=('sbsigntools: for signing EFI images')
md5sums=('0a6500072f9ffa328a914a80542a266c'
         '2e717e04ee627fdac77454dfdf81ad25')
sha256sums=('56fa482837acb0d299d2fe173732966c49927882a477018b2833134622973fb1'
            '2bd06848879df23cbbb5f586cc18c034b8d359d31e9099090fa680a5f2c4711a')
validpgpkeys=('EE05738A0F76012F5CF673DF60BD929EFA66E01F')

build() {
	pod2man --section=1 --release="$pkgver" mkuki.pod | gzip > mkuki.1.gz
}

package() {
	install -Dm755 $pkgname $pkgdir/usr/bin/$pkgname
	install -Dm744 $pkgname.1.gz $pkgdir/usr/share/man/man1/mkuki.1.gz
}
