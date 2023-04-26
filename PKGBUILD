# Maintainer: Safwan Nayeem Yousuf <safwannayeemyousuf.com>
pkgname=ramallahos-tmux-config
pkgrel=1
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

pkgrel() {
  date +%S
}

package() {
    cd "$pkgname"
    install -d "${pkgdir}/etc/skel/.config/tmux/"
    install -Dm 644 "tmux.conf" "${pkgdir}/etc/skel/.config/tmux/tmux.conf"
}
