# Maintainer: Safwan Nayeem Yousuf <safwannayeemyousuf.com>
pkgname=ramallahos-tmux-config
local pkgver
local pkgrel
pkgdesc="TMUX config for RamallahOS"
arch=('any')
url="https://github.com/ramallahos/$pkgname"
license=('GPL3')
depends=('tmux' 'tmux-plugin-manager')
makedepends=('coreutils')
source=("$pkgname::git+$url.git")
sha256sums=('SKIP')

pkgver() {
  date +%Y%m%d
}

data=$( curl https://github.com/ramallahos/ramallahos-repo/tree/main/x86_64 | grep ".tar.zst" | grep $pkgname | awk '{ print $NF }' | awk -F ">" '{ print $2 }' | awk -F "." '{ print $1 }' )
uppkgverdate=$( echo $data | awk -F "-" '{ print $2}' )
uppkgrel=$( echo $data | awk -F "-" '{ print $3 }' )

if [ $pkgverdate == $(date +%Y%m%d) ];
then
    pkgrel=$( echo "$uppkgrel + 1 " | bc )
else
    pkgrel=1
fi

package() {
    cd "$pkgname"
    install -d "${pkgdir}/etc/skel/.config/tmux/"
    install -Dm 644 "tmux.conf" "${pkgdir}/etc/skel/.config/tmux/tmux.conf"
}
