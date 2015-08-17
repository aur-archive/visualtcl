# Contributor: Arnold Perne <aperne@home.nl>

pkgname=visualtcl
pkgver=1.6.1
_ver=a1
pkgrel=1
arch=('any')
pkgdesc="Visual Tcl is a high-quality application development environment for theUNIX platform. Visual Tcl is written entirely in Tcl/Tk and generates pure Tcl/Tk code."
url="http://vtcl.sourceforge.net/"
license=('GPL')
depends=('tk' )
makedepends=('') 
#source=("http://kent.dl.sourceforge.net/project/vtcl/vtcl/$pkgver$pkgrel/vtcl-$pkgver$_ver.tar.gz")
source=("http://kent.dl.sourceforge.net/project/vtcl/files/vtcl/$pkgver.$ver/vtcl-$pkgver$_ver.tar.gz" vtcl.desktop)
#md5sums=('3aaa2fbca871e3d474ce17346dade438')
md5sums=('7bbef6c371b65c19530c46417f0f578f'
	 'd2a8b655d9495f027eea24ab084a017d')

build() {
  cd $startdir/src/vtcl-$pkgver$_ver
  sed -i '43s/package require -exact Tk $tcl_version/package require Tk $tcl_version/' $startdir/src/vtcl-$pkgver$_ver/lib/tkcon.tcl
  mkdir -p $startdir/pkg/usr/{bin,share}
  cp -R $startdir/src/vtcl-$pkgver$_ver/ $startdir/pkg/usr/share/
  install $startdir/vtcl $startdir/pkg/usr/share/vtcl-$pkgver$_ver/
  install -D -m644 ${srcdir}/vtcl.desktop ${pkgdir}/usr/share/applications/vtcl.desktop
  ln -sf /usr/share/vtcl-$pkgver$_ver/vtcl $startdir/pkg/usr/bin/vtcl
  ln -s "/usr/bin/wish8.5" "$pkgdir/usr/bin/wish8.4"
}
