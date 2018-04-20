# Script generated with Bloom
pkgdesc="ROS - depthimage_to_laserscan"
url='http://ros.org/wiki/depthimage_to_laserscan'

pkgname='ros-kinetic-depthimage-to-laserscan'
pkgver='1.0.7_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('gtest'
'ros-kinetic-catkin>=0.5.68'
'ros-kinetic-dynamic-reconfigure'
'ros-kinetic-image-geometry'
'ros-kinetic-image-transport'
'ros-kinetic-nodelet'
'ros-kinetic-roscpp'
'ros-kinetic-sensor-msgs'
)

depends=('ros-kinetic-dynamic-reconfigure'
'ros-kinetic-image-geometry'
'ros-kinetic-image-transport'
'ros-kinetic-nodelet'
'ros-kinetic-roscpp'
'ros-kinetic-sensor-msgs'
)

conflicts=()
replaces=()

_dir=depthimage_to_laserscan
source=()
md5sums=()

prepare() {
    cp -R $startdir/depthimage_to_laserscan $srcdir/depthimage_to_laserscan
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

