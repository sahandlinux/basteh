# Maintainer: Aydin Rahbaran <codewizaard@proton.me>
pkgname=basteh
pkgver=0.0.2
pkgrel=1
pkgdesc="GTK GUI frontend for apt package manager"
arch=('x86_64')
url="https://github.com/sahandlinux/basteh"
license=('GPL3')
depends=('gtk3' 'apt' 'polkit')
makedepends=('gcc' 'git')
source=("$pkgname::git+https://github.com/sahandlinux/basteh.git")
sha256sums=('SKIP')

build() {
  cd "$srcdir/$pkgname/Basteh"
  gcc main.c -o basteh `pkg-config --cflags --libs gtk+-3.0`
}

package() {
  # Binary
  install -Dm755 "$srcdir/$pkgname/Basteh/basteh" "$pkgdir/usr/bin/basteh"

  # Icon
  install -Dm644 "$srcdir/$pkgname/icons/basteh_minimal.jpg" "$pkgdir/usr/share/icons/hicolor/128x128/apps/basteh.png"

  # Desktop Entry
  install -Dm644 /dev/stdin "$pkgdir/usr/share/applications/basteh.desktop" <<EOF
[Desktop Entry]
Version=0.0.2
Name=Basteh
Exec=$pkgdir/usr/bin/basteh
Icon=$srcdir/$pkgname/icons/basteh_minimal.jpg
Terminal=false
Type=Application
Categories=System;Utility;
EOF
}
