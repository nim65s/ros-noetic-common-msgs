# Maintainer: Hermann von Kleist (stertingen yahoo com)
pkgdesc="ROS - common_msgs contains messages that are widely used by other ROS packages."
url='https://wiki.ros.org/common_msgs'
pkgbase='ros-noetic-common-msgs'
pkgname=(
    ros-noetic-actionlib-msgs
    ros-noetic-common-msgs
    ros-noetic-diagnostic-msgs
    ros-noetic-geometry-msgs
    ros-noetic-nav-msgs
    ros-noetic-sensor-msgs
    ros-noetic-shape-msgs
    ros-noetic-stereo-msgs
    ros-noetic-trajectory-msgs
    ros-noetic-visualization-msgs
)
pkgver='1.12.7'
arch=('i686' 'x86_64' 'aarch64' 'armv7h' 'armv6h')
pkgrel=1
license=('BSD')

source=("${pkgbase}-${pkgver}.tar.gz"::"https://github.com/ros/common_msgs/archive/${pkgver}.tar.gz")
sha256sums=('a9d8c7655d426afe8bc2b021e0bc8ce25dae70ca35b985a0ec0b8b5768722bd4')

makedepends=(
	cmake
	ros-build-tools
	ros-noetic-catkin
    ros-noetic-message-generation
)

build() {
    # Use ROS environment variables.
    source /usr/share/ros-build-tools/clear-ros-env.sh
    [ -f /opt/ros/noetic/setup.bash ] && source /opt/ros/noetic/setup.bash

    catkin_make_isolated \
        --directory ${srcdir} \
        --source ${srcdir}/common_msgs-${pkgver} \
        --install-space /opt/ros/noetic \
        --cmake-args \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DPYTHON_EXECUTABLE=/usr/bin/python3 \
        -DSETUPTOOLS_DEB_LAYOUT=OFF
}

check() {
    catkin_make_isolated \
        --directory ${srcdir} \
        --source ${srcdir}/common_msgs-${pkgver} \
        --install-space /opt/ros/noetic \
        --catkin-make-args run_tests
}

package_ros-noetic-actionlib-msgs() {
    pkgdesc="ROS - actionlib_msgs defines the common messages to interact with an action server and an action client."
    url='https://wiki.ros.org/actionlib_msgs'
    depends=(
        ros-noetic-message-runtime
        ros-noetic-std_msgs
    )
    cd "${srcdir}/build_isolated/actionlib_msgs"
    make DESTDIR="${pkgdir}/" install
}

package_ros-noetic-common-msgs() {
    pkgdesc="ROS - common_msgs contains messages that are widely used by other ROS packages."
    url='https://wiki.ros.org/common_msgs'
    depends=(
        ros-noetic-actionlib-msgs
        ros-noetic-diagnostic-msgs
        ros-noetic-geometry-msgs
        ros-noetic-nav-msgs
        ros-noetic-sensor-msgs
        ros-noetic-shape-msgs
        ros-noetic-stereo-msgs
        ros-noetic-trajectory-msgs
        ros-noetic-visualization-msgs
    )
    cd "${srcdir}/build_isolated/common_msgs"
    make DESTDIR="${pkgdir}/" install
}

package_ros-noetic-diagnostic-msgs() {
    pkgdesc="ROS - This package holds the diagnostic messages which provide the standardized interface for the diagnostic and runtime monitoring systems in ROS."
    url='https://wiki.ros.org/diagnostic_msgs'
    depends=(
        ros-noetic-message-runtime
        ros-noetic-std_msgs
    )
    cd "${srcdir}/build_isolated/diagnostic_msgs"
    make DESTDIR="${pkgdir}/" install
}

package_ros-noetic-geometry-msgs() {
    pkgdesc="ROS - geometry_msgs provides messages for common geometric primitives such as points, vectors, and poses."
    url='https://github.com/ros/common_msgs'
    depends=(
        ros-noetic-message-runtime
        ros-noetic-std_msgs
    )
    cd "${srcdir}/build_isolated/geometry_msgs"
    make DESTDIR="${pkgdir}/" install
}

package_ros-noetic-nav-msgs() {
    pkgdesc="ROS - nav_msgs defines the common messages used to interact with the navigation stack."
    url='https://wiki.ros.org/nav_msgs'
    depends=(
        ros-noetic-actionlib-msgs
        ros-noetic-geometry-msgs
        ros-noetic-message-runtime
        ros-noetic-std_msgs
    )
    cd "${srcdir}/build_isolated/nav_msgs"
    make DESTDIR="${pkgdir}/" install
}

package_ros-noetic-sensor-msgs() {
    pkgdesc="ROS - This package defines messages for commonly used sensors, including cameras and scanning laser rangefinders."
    url='https://wiki.ros.org/sensor_msgs'
    depends=(
        ros-noetic-geometry-msgs
        ros-noetic-message-runtime
        ros-noetic-std_msgs
    )
    cd "${srcdir}/build_isolated/sensor_msgs"
    make DESTDIR="${pkgdir}/" install
}

package_ros-noetic-shape-msgs() {
    pkgdesc="ROS - This package contains messages for defining shapes, such as simple solid object primitives (cube, sphere, etc), planes, and meshes."
    url='https://wiki.ros.org/shape_msgs'
    depends=(
        ros-noetic-geometry-msgs
        ros-noetic-message-runtime
        ros-noetic-std_msgs
    )
    cd "${srcdir}/build_isolated/shape_msgs"
    make DESTDIR="${pkgdir}/" install
}

package_ros-noetic-stereo-msgs() {
    pkgdesc="ROS - stereo_msgs contains messages specific to stereo processing, such as disparity images."
    url='https://wiki.ros.org/stereo_msgs'
    depends=(
        ros-noetic-message-runtime
        ros-noetic-sensor-msgs
        ros-noetic-std_msgs
    )
    cd "${srcdir}/build_isolated/stereo_msgs"
    make DESTDIR="${pkgdir}/" install
}

package_ros-noetic-trajectory-msgs() {
    pkgdesc="ROS - This package defines messages for defining robot trajectories."
    url='https://wiki.ros.org/trajectory_msgs'
    depends=(
        ros-noetic-geometry-msgs
        ros-noetic-message-runtime
        ros-noetic-rosbag-migration-rule
        ros-noetic-std_msgs
    )
    cd "${srcdir}/build_isolated/trajectory_msgs"
    make DESTDIR="${pkgdir}/" install
}

package_ros-noetic-visualization-msgs() {
    pkgdesc="ROS - visualization_msgs is a set of messages used by higher level packages, such as rviz, that deal in visualization-specific data."
    url='https://wiki.ros.org/visualization_msgs'
    depends=(
	    ros-noetic-geometry-msgs
        ros-noetic-message-runtime
        ros-noetic-std_msgs
    )
    cd "${srcdir}/build_isolated/visualization_msgs"
    make DESTDIR="${pkgdir}/" install
}
