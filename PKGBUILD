pkgname=python25-unittest2
pkgver=0.5.1
pkgrel=1
pkgdesc="The new features in unittest for Python 2.7 backported to Python 2.5+."
arch=('any')
url="http://www.voidspace.org.uk/python/articles/unittest2.shtml"
license=("BSD")
depends=("python25")
makedepends=("python2-distribute")
changelog=Changelog
install="python25-unittest2.install"
source=(http://pypi.python.org/packages/source/u/unittest2/unittest2-$pkgver.tar.gz
        LICENSE
        python25-unittest2.install)
md5sums=('a0af5cac92bbbfa0c3b0e99571390e0f'
         '0c162ecb7937c6a146e5b0457f0ccf1e'
         '8d0d5f3cf2bb0782edb346433f4fce43')
sha256sums=('aa5de8cdf654d843379c97bd1ee240e86356d3355a97b147a6f3f4d149247a71'
            'e0bfff5f29a59d078142b8b24b60b0105043057b9e238974d26ae778804ba9bc'
            'c0f9871ab3456e4c73f3eb8f896630ba4a8d03267844ee916c45194c34fc91b5')

build() {
  cd "$srcdir/unittest2-$pkgver"
  python2.5 setup.py install "--root=$pkgdir" --optimize=1

  # Leave /usr/bin/unit2 for unittest2 for Python 3
  # Switch to full removal when upstream adds /usr/bin/unit2-2[.py]
  mv "$pkgdir/usr/bin/unit2" "$pkgdir/usr/bin/unit2-25"
  mv "$pkgdir/usr/bin/unit2.py" "$pkgdir/usr/bin/unit2-25.py"
}

package() {
  install -Dm644 LICENSE $pkgdir/usr/share/licenses/$pkgname/LICENSE
}
