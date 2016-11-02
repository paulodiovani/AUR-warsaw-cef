# Maintainer: Paulo Diovani <paulo@diovani.com>
# Debian Package Maintainer: GAS Tecnologia <info@gastecnologia.com.br>

pkgname=warsaw
pkgver=1.3.0
pkgrel=1
pkgdesc=""
arch=('x86_64')
url="https://internetbanking.caixa.gov.br/sinbc/nb/login/redirecionaDispSeguranca"
license=('unknown')
depends=('openssl>=1.0' 'curl' 'nss')
provides=('warsaw')
source=(
    "https://cloud.gastecnologia.com.br/cef/$pkgname/install/GBPCEFwr64.deb"
    'warsaw.service'
)
md5sums=(
    '723eb9b0a3a3f514b8c1f6b3dcc958eb'
    'd91d3c6778de9dc5aea73e97a2d365bb'
)

package() {
    msg2 "Extracting the data.tar.xz..."
    bsdtar -xf data.tar.xz -C "$pkgdir/"

    msg2 "Removing unnecessary files (e.g. systemv init)..."
    rm -r "$pkgdir/etc/init.d"

    msg2 "Adding systemd unit file..."
    mkdir -p "$pkgdir/usr/lib/systemd/system"
    cp warsaw.service "$pkgdir/usr/lib/systemd/system/"

    msg2 "Fix file permissions..."
    chmod 0755  "$pkgdir/etc/" \
                "$pkgdir/etc/xdg/" \
                "$pkgdir/etc/xdg/autostart/" \
                "$pkgdir/usr/" \
                "$pkgdir/usr/local/" \
                "$pkgdir/usr/share/" \
                "$pkgdir/usr/share/fonts/" \
                "$pkgdir/usr/share/fonts/truetype/" \
                "$pkgdir/usr/local/bin/" \
                "$pkgdir/usr/local/etc/" \
                "$pkgdir/usr/local/lib/" \
                "$pkgdir/usr/local/bin/warsaw/" \
                "$pkgdir/usr/local/etc/warsaw/" \
                "$pkgdir/usr/local/lib/warsaw/"

    chmod 0644  "$pkgdir/etc/xdg/autostart/warsaw.desktop" \
                "$pkgdir/usr/local/etc/warsaw/openssl.conf" \
                "$pkgdir/usr/local/etc/warsaw/features.dat" \
                "$pkgdir/usr/local/etc/warsaw/config.cfg" \
                "$pkgdir/usr/share/fonts/truetype/Warsaw Bold.ttf"

    chmod 0755  "$pkgdir/usr/local/bin/warsaw/core" \
                "$pkgdir/usr/local/bin/warsaw/uninstall_core" \
                "$pkgdir/usr/local/lib/warsaw/wsbrmu.so" \
                "$pkgdir/usr/local/lib/warsaw/wsftbco.so" \
                "$pkgdir/usr/local/lib/warsaw/wsftdl.so" \
                "$pkgdir/usr/local/lib/warsaw/wsftev.so" \
                "$pkgdir/usr/local/lib/warsaw/wsftuan.so" \
                "$pkgdir/usr/local/lib/warsaw/wsftup.so" \
                "$pkgdir/usr/local/lib/warsaw/wslbmid.so"
}
