# Maintainer: Simon Legner <Simon.Legner@gmail.com>
pkgname=esbuild
pkgver=0.8.12
pkgrel=1
pkgdesc="An extremely fast JavaScript/TypeScript bundler and minifier"
arch=(any)
url="https://github.com/evanw/esbuild"
license=('MIT')
depends=('nodejs')
makedepends=('npm')
optdepends=()
source=(https://registry.npmjs.org/$pkgname/-/$pkgname-$pkgver.tgz)
noextract=($pkgname-$pkgver.tgz)

package() {
  cd $srcdir
  local _npmdir="$pkgdir/usr/lib/node_modules/"
  mkdir -p $_npmdir
  cd $_npmdir
  npm install -g --prefix "$pkgdir/usr" $pkgname@$pkgver
  find "${pkgdir}"/usr -name package.json -exec sed -i '/"_where"/d' '{}' '+'
  find "${pkgdir}"/usr -type d -exec chmod 755 {} +
}

sha256sums=('8d6a645163344729e94afe6f9351b689473550e51bea9df57535ca095b0837ce')
