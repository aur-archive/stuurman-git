#Maintainer : Vadim Ushakov <igeekless [at] gmail [dot] com>

pkgname=stuurman-git
pkgver=201507291347
pkgrel=1
pkgdesc="A fast and feature-rich file manager with tabbed browsing and advanced file searching. Based on PCManFM."
arch=('i686' 'x86_64')
url="http://make-linux.org/"
license=('GPL')
depends=('libsmfm-gtk2-git' 'sde-reverse-meta-git')
makedepends=('git' 'intltool' 'pkg-config' 'automake')
provides=('stuurman')
conflicts=('stuurman')
install=stuurman.install

source=('git+git://make-linux.org/sde/stuurman.git')
md5sums=('SKIP')

_gitname="stuurman"

pkgver() {
  date +%Y%m%d%H%M
}

build() {
    cd "${_gitname}"

    ./autogen.sh
    ./configure \
        --prefix=/usr \
        --sysconfdir=/etc \
        --enable-silent-rules
    make
}

package() {
    cd "${_gitname}"
    make DESTDIR="$pkgdir" install
}
