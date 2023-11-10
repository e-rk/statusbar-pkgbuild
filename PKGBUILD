pkgname=statusbar
pkgver=0.2.11.gcf34f07
pkgrel=1
arch=('i686' 'x86_64')
license=('MIT')
pkgdesc='Simple status bar.'
depends=('mpd')
makedepends=('git' 'make')

source=("$pkgname-$pkgver::git+https://github.com/e-rk/statusbar.git")
sha256sums=('SKIP')

pkgver()
{
    cd $pkgname-$pkgver
    git describe --tags | sed 's/-/./g'
}

build()
{
    cd $pkgname-$pkgver
    make
}

package()
{
    cd $pkgname-$pkgver
    
    make install DESTDIR=$pkgdir

    install -Dm644 LICENSE "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}
