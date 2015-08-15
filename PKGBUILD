# Maintainer: Janne Nykanen <janne dot nykanen at gmail dot com>
# Contributor: Alessio Biancalana <dottorblaster@gmail.com>
# Contributor: Dylan D'Arcy <dylan.somebody@gmail.com>

pkgname=firefox-xmarks
pkgver=4.3.5
pkgrel=1
pkgdesc="plugin for firefox which synchronizes bookmarks and passwords"
arch=('i686' 'x86_64')
url="http://www.xmarks.com/"
license=('custom')
depends=(firefox)
makedepends=('unzip')
source=("https://static.xmarks.com/clients/firefox/xmarks-$pkgver-release.xpi")
md5sums=('d7eccd480c261065e9130d273aee0acb')

package() {
    cd $srcdir
    #this method comes from gentoo (http://kambing.ui.edu/gentoo-portage/eclass/mozextension.eclass):
    local emid=$(sed -n -e '/<\?em:id>\?/!d; s/.*\([\"{].*[}\"]\).*/\1/; s/\"//g; p; q' install.rdf)
    #updated version
    local dstdir=$pkgdir/usr/lib/firefox/browser/extensions/${emid}
    install -d $dstdir		|| return 1
    cp -R * $dstdir		|| return 1
    #changed to reflect actual file name
    #rm $dstdir/xmarks-$pkgver.xpi
}
