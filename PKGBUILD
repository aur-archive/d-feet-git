pkgname=d-feet-git
pkgver=0.3.9.r10.rg589afec
pkgrel=1

pkgdesc='D-Bus debugger and inspector.'
url='https://wiki.gnome.org/action/show/Apps/DFeet'
arch=('i686' 'x86_64')
license=('GPL2')

depends=('gtk3' 'python-gobject' 'hicolor-icon-theme')
makedepends=('python-distribute' 'intltool' 'itstool' 'pep8-python3' 'git' 
             'gnome-common' 'yelp-tools')

provides=('d-feet')
conflicts=('d-feet')

install='d-feet-git.install'

source=('git://git.gnome.org/d-feet')

md5sums=('SKIP')

pkgver() {
    cd d-feet
    git describe | sed 's/^v//; s/-/.r/g; s/-/./'
}

prepare() {
    cd d-feet
    ./autogen.sh --prefix=/usr --sysconfdir=/etc --localstatedir=/var
}

build() {
    cd d-feet
    make
}

package() {
    cd d-feet
    make DESTDIR="$pkgdir" install
}
