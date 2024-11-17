# Maintainer: George Rawlinson <george@rawlinson.net.nz>

pkgname=prometheus-bind-exporter
_pkgname=bind_exporter
pkgver=0.8.0 # renovate: datasource=github-releases depName=prometheus-community/bind_exporter
pkgrel=1
pkgdesc='Prometheus exporter for BIND metrics'
arch=('x86_64')
url='https://github.com/prometheus-community/bind_exporter'
license=('Apache')
optdepends=('bind: for monitoring a local BIND server')
options=('!lto')
source=(
  "$pkgname-$pkgver.tar.gz::$url/releases/download/v$pkgver/bind_exporter-$pkgver.linux-amd64.tar.gz"
  'systemd.service'
  'sysusers.conf'
)
sha512sums=('ef53c4c5b78e8018f7f528d415f7bb0c91197d951c1ea9fa00bcb44bc2fa18a0125f1dae56a54c661d564a5a617e9d90189c26e67e16ff5a22c091a4610ac61f'
            '8c22cfadddd8820258e02f53253de78cc1707f6220da13f36e682b79d58a3b59ef615b3f0c74ced01bcb6afb19c35414821575d265227512f5192182aca2d042'
            '143591ed6c2550085a2ab5c292aa57a6ab047826158270c630acaf1dd1afc9e3cbccb612f0b684206832c8d641eb432bf4f474dd07b9dc744cfd7174d320b552')
b2sums=('edee8966849d472bf602d35de93c53e00ba2e9ab57ea3e7c0b889383bb5bccc41ff7c83683d66ccd35ab5bf65244b300e962296498d7a9b4ee775cf786297676'
        '83ac2fb9b39f10f9eb130fc566887a5dc70447265d9d567221ceccf83a9fe7ad8035dfa751ecefe9681c64fd8ddb260b3e370f956350b9cab699eed507d9affc'
        '739b1e4e7ab277096d0875ed14d61f223e7b990e7081721e4638aebad9c3beccc270ce9944384784af8eab035dbb34a86badae687c065291bfb384abfb42573a')

package() {
  # systemd integration
  install -Dm644 systemd.service "$pkgdir/usr/lib/systemd/system/$pkgname.service"
  install -Dm644 sysusers.conf "$pkgdir/usr/lib/sysusers.d/$pkgname.conf"

  # binary
  install -Dm755 -t "$pkgdir/usr/bin" "$_pkgname-$pkgver.linux-amd64/$_pkgname"
}
