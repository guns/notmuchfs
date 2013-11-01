# Maintainer: Sung Pae <self@sungpae.com>
pkgname=notmuchfs-guns
pkgver=commit.8
pkgrel=1
pkgdesc="Sung Pae's notmuchfs build"
arch=('x86_64')
url="https://github.com/guns/notmuchfs"
license=('GPL')
groups=('guns')
depends=('notmuch-runtime' 'fuse')
makedepends=('git')
provides=('notmuchfs')
conflicts=('notmuchfs')

pkgver() {
    printf commit.%s "$(git rev-list HEAD --count)"
}

build() {
    cd "$startdir"
    make -j $(grep -c ^processor /proc/cpuinfo)
}

package() {
    cd "$startdir"
    DESTDIR="$pkgdir/" PREFIX=/usr make -e install
}
