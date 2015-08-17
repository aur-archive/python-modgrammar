# Maintainer: Hilton Medeiros <medeiros.hilton@gmail.com>

pkgname=python-modgrammar
_pkgname=modgrammar
pkgver=0.10
pkgrel=1
pkgdesc="A general-purpose library for constructing language parsers and interpreters."
arch=('any')
url="http://code.google.com/p/modgrammar/"
license=('BSD')
depends=('python')
makedepends=('python-distribute' 'python-sphinx')
source=("http://pypi.python.org/packages/source/m/$_pkgname/$_pkgname-$pkgver.tar.gz"
        LICENSE)
md5sums=('8d4b335a40fd88eef58dce32bb61e2f4'
         'eee8ddb26a25591f2b954b5e6da95480')

build() {
  cd "$srcdir/$_pkgname-$pkgver"
  sphinx-build doc build/html
}

package() {
  cd "$srcdir/$_pkgname-$pkgver"

  python3 setup.py install --prefix=/usr --root="$pkgdir" -O1

  install -d "$pkgdir/usr/share/doc"
  cp -rf build/html "$pkgdir/usr/share/doc/$pkgname"
  install -Dm644 "$srcdir/LICENSE" "$pkgdir/usr/share/licenses/$pkgname/LICENSE"
}
