# Script generated with Bloom
pkgdesc="ROS - This is an interface to the Ocean Server Technology Intelligent Battery and Power System."
url='http://www.ros.org/wiki/ocean_battery_driver'

pkgname='ros-kinetic-ocean-battery-driver'
pkgver='1.1.6_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('log4cxx'
'ros-kinetic-catkin'
'ros-kinetic-diagnostic-msgs'
'ros-kinetic-diagnostic-updater'
'ros-kinetic-pr2-msgs'
'ros-kinetic-roscpp'
)

depends=('log4cxx'
'ros-kinetic-diagnostic-msgs'
'ros-kinetic-diagnostic-updater'
'ros-kinetic-pr2-msgs'
'ros-kinetic-roscpp'
)

conflicts=()
replaces=()

_dir=ocean_battery_driver
source=()
md5sums=()

prepare() {
    cp -R $startdir/ocean_battery_driver $srcdir/ocean_battery_driver
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

