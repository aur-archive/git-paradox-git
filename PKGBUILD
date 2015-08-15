# Maintainer: Brandon Kase <bkase at cmu dot edu>

pkgname=git-paradox-git
pkgver=20120406
pkgrel=1
pkgdesc='Add the `git paradox` command to your suite of `git` commands'
arch=('any')
url=(https://github.com/bkase/git-paradox)
license=('MIT') 
depends=(git)
source=()
md5sums=()
conflicts=()

_gitroot=https://github.com/bkase/git-paradox.git
_gitname=git-paradox

build() {
    cd ${srcdir}
    msg "Connecting to GIT server..."

    if [ -d $_gitname ] ; then
        cd $_gitname && git pull origin
        msg "The local files are updated."
    else
        git clone $_gitroot $_gitname
        cd $_gitname
    fi
    msg "GIT checkout done or server timeout"
    msg "Installing..."

    mkdir -p "$pkgdir/usr/bin/"
    install -Dm755 git-paradox "$pkgdir/usr/bin/"
}
