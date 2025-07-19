# Maintainer: sahandlinux <your-email@example.com>
pkgname=basteh
pkgver=1.0
pkgrel=1
pkgdesc="GTK GUI frontend for pacman"
arch=('x86_64')
url="https://github.com/sahandlinux/basteh"
license=('GPL3')
depends=('gtk3' 'pacman' 'pkexec')
makedepends=('gcc')
source=("install.sh")
sha256sums=('SKIP')

package() {
  install -Dm755 "$srcdir/install.sh" "$pkgdir/usr/bin/basteh-install"
  cd "$pkgdir/usr/bin"
  chmod +x basteh-install
  ./basteh-install
}