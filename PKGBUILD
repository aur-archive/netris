
# Contributor: arjan <arjan@archlinux.org>
# Contributor: Tom Newsom <Jeepster@gmx.co.uk>
# Contributor: Łukasz Fidosz <virhilo@gmail.com>
# Contributor: J. W. Birdsong  <jwbirdsong AT gmail DOT com>
# Maintainer: DaZ <daz.root+arch@gmail.com>

pkgname=netris
pkgver=0.52
pkgrel=7
pkgdesc="This is an unfinished developmental version of Netris, a free networked version of T*tris"
arch=('i686' 'x86_64')
url="http://www.netris.org/"
license=('GPL')
depends=('ncurses')
source=(ftp://ftp.netris.org/pub/netris/$pkgname-$pkgver.tar.gz
	01_multi-games-with-scoring.patch
	02_line-count-patch.patch
	03_staircase-effect-fix.patch
	04_robot-close-fixup.patch
	05_init-static-vars.patch
	06_curses.c-include-term.h.patch
	07_curses.c-include-time.h.patch
	08_various-fixes.patch)

md5sums=('b55af5697175ee06f7c6e40101979c38'
	'7959a9d84a8f396cb1e751be66e54832'
	'65dcd6153cd80b5855eed19f7bc1fa12'
	'6eb7f804b821e5ca652d6ebe5f2f1d24'
	'265778ed08c9096f3f913fc411e5aa67'
	'dded6337946a878a1d29e3cc549bec3b'
	'ad2b0c0d298a24315423bd21851ab9d8'
	'32447539b9fcf13d33abf50d21833c8a'
	'ff2ecb51acebd5b89ec1e56c6d4e3e23')

build() {
cd ${srcdir}/${pkgname}-${pkgver}
for i in ${srcdir}/*.patch 
do
	patch -p1 < "$i"
done
./Configure  
make 
}


package() {
cd ${srcdir}/${pkgname}-${pkgver}
install -D -m755 netris  "${pkgdir}/usr/bin/netris"
}
