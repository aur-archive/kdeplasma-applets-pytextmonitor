# Maintainer: Evgeniy "arcanis" Alexeev <arcanis.arch at gmail dot com>

pkgname=kdeplasma-applets-pytextmonitor
_pkgname=pytextmonitor
pkgver=1.10.2.7fa541b
_pkgver=1.11.0
pkgrel=1
pkgdesc="Minimalistic Plasmoid script written on Python2. It looks like widgets in Awesome WM"
arch=('i686' 'x86_64')
url="http://arcanis.name/projects/pytextmonitor"
license=('GPL3')
depends=('kdebase-workspace' 'kdebindings-python2' 'lm_sensors')
optdepends=("amarok: for music player monitor"
            "clementine: for music player monitor"
            "catalyst: for GPU monitor"
            "hddtemp: for HDD temperature monitor"
            "mpd: for music player monitor"
            "net-tools: for popup messages"
            "nvidia-utils: for GPU monitor"
            "qmmp: for music player monitor"
            "sysstat: for popup messages")
makedepends=('automoc4' 'cmake')
source=(https://github.com/arcan1s/pytextmonitor/releases/download/V.${_pkgver}/${_pkgname}-${_pkgver}-src.tar.xz)
install=${pkgname}.install
md5sums=('b5f8383c198e7059f463678f84a16273')
backup=('usr/share/config/extsysmon.conf')

prepare() {
  rm -rf "${srcdir}/build"
  mkdir "${srcdir}/build"
}

build () {
  cd "${srcdir}/build"
  cmake -DCMAKE_BUILD_TYPE=Release \
        -DCMAKE_INSTALL_PREFIX=$(kde4-config --prefix) \
        "../${_pkgname}"
  make
}

package() {
  cd "${srcdir}/build"
  make DESTDIR="${pkgdir}" install
}
