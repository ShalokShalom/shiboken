pkgname=shiboken
_pkgname=Shiboken
pkgver=2.0
pkgrel=1
pkgdesc="Plugin (front-end) for Generator Runner. It generates bindings for C++ libraries using CPython source code"
arch=('x86_64')
license=('LGPL')
url="http://www.pyside.org"
depends=('python2' 'qt5-base' 'libxslt' 'python2-sphinx')
makedepends=('cmake')
source=(latest.tar.gz)
md5sums=('c284197d06ad25d78009ff55f18dd512')


build(){
    cd ${_pkgname}-${pkgver}
    mkdir -p build
    cd build
    
    cmake ../ -DCMAKE_INSTALL_PREFIX=/usr  \
              -DCMAKE_BUILD_TYPE=Release   \
              -DBUILD_TESTS=OFF            \
              -DPYTHON_EXECUTABLE=/usr/bin/python2 \
              -DPYTHON_LIBRARY=/usr/lib/libpython2.7.so \
              -DPYTHON_INCLUDE_DIR=/usr/include/python2.7 
    make
}

package(){
    cd ${_pkgname}-${pkgver}/build
    
    make DESTDIR="$pkgdir" install
}

