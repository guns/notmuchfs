# Maintainer: Sung Pae <self@sungpae.com>
pkgname=notmuchfs-nerv
pkgver=
pkgrel=1
pkgdesc="Custom notmuchfs build"
arch=('x86_64')
url="https://github.com/guns/notmuchfs"
license=('GPL')
groups=('nerv')
depends=('notmuch-runtime' 'fuse')
makedepends=('git')
provides=('notmuchfs')
conflicts=('notmuchfs')
replaces=('notmuchfs-guns')

pkgver() {
    printf %s.%s "$(git rev-parse --abbrev-ref HEAD)" "$(git rev-list HEAD --count)"
}

build() {
    cd "$startdir"
    make -j $(grep -c ^processor /proc/cpuinfo)
}

package() {
    cd "$startdir"
    DESTDIR="$pkgdir/" PREFIX=/usr make -e install
}
