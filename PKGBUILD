# Maintainer: Moritz Maxeiner <moritz@ucworks.org>
# Patch: Cedric Bellegarde <gnumdk@adishatz.org>
# Contributor: localizator <localizator@ukr.net>

pkgname=seafile-client-fdo
pkgver=3.0.4
pkgrel=1
pkgdesc="Seafile is an online file storage and collaboration tool. This is seafile client for synchronizing your local files with seafile server. Patched with FDO notifications"
arch=('i686' 'x86_64')
url="https://github.com/haiwen/seafile-client/"
license=('Apache')
depends=('qt4' 'seafile-shared>=3.0.4')
makedepends=('cmake')
optdepends=()
options=('!libtool' '!emptydirs')
install=seafile-client.install
source=("https://github.com/haiwen/seafile-client/archive/v${pkgver}.tar.gz" "notification.patch")

build ()
{
	cd "$srcdir/seafile-client-${pkgver}"
	patch -p1 < ../notification.patch
	cmake -DCMAKE_BUILD_TYPE=Release -DCMAKE_INSTALL_PREFIX=/usr .
	make
}

package ()
{
	cd "${srcdir}/seafile-client-${pkgver}"
	make DESTDIR="${pkgdir}/" install
}
sha256sums=('421933304e9c499d07471b8dc44186fba4959d30bc670d62d5c915897c213f82' 'a77f85718f7a51e80e68495812bc505237088ace0710785546772150b5b10f60')
