# Maintainer: jfperini <@jfperini>
# Contributor: jfperini <@jfperini>

pkgname=flattr-icons-kde-kaosx-git
pkgver=20140408.3c4b091
pkgrel=1
pkgdesc="Flattr is an icon theme for Linux desktops, the set is inspired by the latest flat design trend."
arch=('any')
url="https://github.com/KaOSx/flattr-icons-kde"
license=('CC BY-NC-SA 4.0')
depends=()
makedepends=('git')
conflicts=('flattr-icons','flattr-icon-theme','flattr-icon-theme-git')
provides=('flattr-icon-theme')
source=("$pkgname"::'git+https://github.com/KaOSx/flattr-icons-kde.git')
# Because the sources are not static, skip Git checksum:
md5sums=('SKIP')

pkgver() {
  cd "$srcdir/$pkgname"
  # Use the tag of the last commit
  git log -1 --date=short --format="%cd.%h" | tr -d '-'
}

package() {
  cd "$srcdir/$pkgname"
  install -d -m 755 "$pkgdir"/usr/share/icons/Flattr
  rm -rf {.git,.gitignore,CONTRIBUTORS,COPYING,CREDITS,LICENSE.txt,README.md}
  cp -r . "$pkgdir"/usr/share/icons/Flattr/
}
