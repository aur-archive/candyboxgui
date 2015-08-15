# Maintainer: Yann Gauthier elril0000@gmail.com
pkgname=candyboxgui

pkgrel=1
pkgver=1.4.3
pkgdesc="A gui interface for the web browser game : Candy Box by aniwey"
arch=(any)
url="http://www.github.com/elril0000/candyboxgui"
license=('MIT')
depends=('qt5-base' 'qt5-webkit')
makedepends=('cmake>=2.8' 'git' 'qt5-tools')
source=('candyboxgui::git://github.com/elril0000/CandyBoxGUI.git' 'candyboxgui.desktop')
md5sums=('SKIP' 'SKIP')

build() {
  cd "$srcdir/$pkgname/"
  if [ ! -d "$DIRECTORY" ]; then
  echo 'creating the build directory'
  mkdir build
  fi
  
  cd build
  cmake .. -G "Unix Makefiles" -DCMAKE_BUILD_TYPE:STRING=Release -DCMAKE_INSTALL_PREFIX:STRING=/usr -DAPP_DIRECTORY:STRING=/usr/share/candyboxgui/
  make

}

package() {
  cd "$srcdir/$pkgname/build"

  make DESTDIR="$pkgdir/" install
  
  install -D -m 644 $srcdir/../candyboxgui.desktop $pkgdir/usr/share/applications/candyboxgui.desktop
}
