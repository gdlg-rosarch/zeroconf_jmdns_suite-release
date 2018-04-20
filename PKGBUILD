# Script generated with Bloom
pkgdesc="ROS - An implementation of zeroconf in pure java."
url='http://ros.org/wiki/zeroconf_jmdns_suite'

pkgname='ros-kinetic-zeroconf-jmdns-suite'
pkgver='0.3.0_1'
pkgrel=1
arch=('any')
license=('Apache 2.0'
)

makedepends=('ros-kinetic-catkin'
'ros-kinetic-rosjava-bootstrap'
'ros-kinetic-rosjava-build-tools'
)

depends=('ros-kinetic-rosjava-bootstrap'
'ros-kinetic-rosjava-build-tools'
)

conflicts=()
replaces=()

_dir=zeroconf_jmdns_suite
source=()
md5sums=()

prepare() {
    cp -R $startdir/zeroconf_jmdns_suite $srcdir/zeroconf_jmdns_suite
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/kinetic/setup.bash ] && source /opt/ros/kinetic/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/kinetic \
        -DPYTHON_EXECUTABLE=/usr/bin/python2 \
        -DPYTHON_INCLUDE_DIR=/usr/include/python2.7 \
        -DPYTHON_LIBRARY=/usr/lib/libpython2.7.so \
        -DPYTHON_BASENAME=-python2.7 \
        -DSETUPTOOLS_DEB_LAYOUT=OFF
  make
}

package() {
  cd "${srcdir}/build"
  make DESTDIR="${pkgdir}/" install
}

