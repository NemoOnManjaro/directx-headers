# Maintainer: Jan Alexander Steffens (heftig) <heftig@archlinux.org>
# Maintainer: Laurent Carlier <lordheavym@archlinux.org>
# Contributor: Cyano Hao <c@cyano.cn>

pkgname=directx-headers
pkgver=1.618.2
pkgrel=1
pkgdesc="DirectX headers for using D3D12"
url="https://github.com/microsoft/DirectX-Headers"
arch=(x86_64)
license=(MIT)
depends=()
makedepends=(
  git
  meson
)
options=(!lto)
source=("directx-headers::git+$url#tag=v$pkgver")
b2sums=('SKIP')

build() {
  local meson_options=(
    -D build-test=false
  )

  arch-meson directx-headers build "${meson_options[@]}"
  meson compile -C build
}

package() {
  meson install -C build --destdir "$pkgdir"

  install -Dm644 directx-headers/LICENSE \
    -t "$pkgdir/usr/share/licenses/$pkgname"
}

# vim:set sw=2 sts=-1 et:
