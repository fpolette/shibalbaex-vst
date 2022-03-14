pkgname=shibalbaex-vst-bin
pkgver=1.0
pkgrel=1
pkgdesc="Shibalba Amp Sim base on Bogner Shiva"
arch=('x86_64')
url="https://audioassault.mx/collections/plugins/products/shibalba"
license=('EULA')
groups=('vst-plugins')
depends=('glibc')
makedepends=('xdg-user-dirs' 'unzip')

prepare () {
    _archive="`xdg-user-dir DOWNLOAD`/Shibalba_Ex_1_0.zip"
    ln -srf "${_archive}" "$srcdir/`basename "${_archive}"`"
    unzip "$srcdir/`basename "${_archive}"`"
    find $srcdir -name ".DS_Store" -delete
}

package() {
    ## Install Preset and Default Libraries
    mkdir -p "$pkgdir/opt/Audio Assault/Shibalba EX"
    cp -rf $srcdir/Shibalba\ EX\ Linux/Shibalba\ EX/{IRs,Presets} "$pkgdir/opt/Audio Assault/Shibalba EX"

    ## Install VST Plugin
    install -Dm755 "$srcdir/Shibalba EX Linux/Shibalba EX VST2.so" "$pkgdir/usr/lib/vst/shibalbaexvst2.so"
    install -Dm755 "$srcdir/Shibalba EX Linux/Shibalba EX.vst3/Contents/x86_64-linux/Shibalba EX.so" "$pkgdir/usr/lib/vst3/shibalbaexvst3.so"
}