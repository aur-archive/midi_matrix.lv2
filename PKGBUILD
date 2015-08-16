# This is an example PKGBUILD file. Use this as a start to creating your own,
# and remove these comments. For more information, see 'man PKGBUILD'.
# NOTE: Please fill out the license field for your package! If it is unknown,
# then please put 'unknown'.

# Maintainer: Hanspeter Portner <dev at open-music-kontrollers dot ch>
pkgname=midi_matrix.lv2
pkgver=0.1.1
pkgrel=2
pkgdesc="LV2 'Midi Matrix' plugin bundle: 'Channel Filter'"
arch=(i686 x86_64)
url="http://open-music-kontrollers.ch/lv2/midi_matrix"
license=('ZLIB')
groups=('lv2-plugins')
depends=('efl')
makedepends=('cmake' 'lv2')
checkdepends=()
optdepends=()
provides=()
conflicts=()
replaces=()
backup=()
options=()
install=
changelog=
source=(https://github.com/OpenMusicKontrollers/$pkgname/archive/$pkgver.tar.gz)
noextract=()
md5sums=('11f71e9504bfd7d0b6c8d088578a8d65')

prepare() {
	cd "$srcdir/$pkgname-$pkgver"
	mkdir -p build
}

build() {
	cd "$srcdir/$pkgname-$pkgver"/build
  cmake \
		-DCMAKE_INSTALL_PREFIX=/usr \
		-DCMAKE_C_FLAGS='-std=gnu99' \
		..
	make
}

check() {
	cd "$srcdir/$pkgname-$pkgver"/build
}

package() {
	cd "$srcdir/$pkgname-$pkgver"/build
	make DESTDIR="$pkgdir/" install

	install -d "$pkgdir/usr/share/licenses/$pkgname/"
	install ../COPYING "$pkgdir/usr/share/licenses/$pkgname/"
}
