# Maintainer: Jacques-Pascal Deplaix <jp.deplaix@gmail.com>
# Contributor: Jacques-Pascal Deplaix <jp.deplaix@gmail.com>
pkgname=macaque
pkgver=0.6
pkgrel=1
pkgdesc="a DSL for SQL Queries in Caml"
arch=('i686' 'x86_64')
url="http://forge.ocamlcore.org/projects/macaque/"
license=('LGPL')
depends=('pgocaml')
makedepends=('ocaml-findlib')
source=(http://forge.ocamlcore.org/frs/download.php/1027/$pkgname-$pkgver.tar.gz)
sha512sums=('d4af100a6eb2529515b23aa5a5f975099c1b8bb9db46ac7280d59c6759c04a6fec98c30388fa2a8e46b90a3d4331608ae81d5d1cd5c2e053a502a3bd496058c8')

build() {
    cd "$srcdir/$pkgname/src"

    make -j1 || return 1
}

package() {
    cd "$srcdir/$pkgname/src"

    export OCAMLFIND_DESTDIR="$pkgdir$(ocamlfind printconf destdir)"
    mkdir -p "$OCAMLFIND_DESTDIR"
    make install || return 1
}
