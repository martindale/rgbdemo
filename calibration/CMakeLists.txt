SET(common_sources calibration_common.h calibration_common.cpp)

ADD_EXECUTABLE(annotate_image annotate_image.cpp ${common_sources})
TARGET_LINK_LIBRARIES(annotate_image nestk)
#INSTALL(TARGETS annotate_image DESTINATION bin)

ADD_EXECUTABLE(calibrate_kinect calibrate_kinect.cpp ${common_sources})
TARGET_LINK_LIBRARIES(calibrate_kinect nestk)
#INSTALL(TARGETS calibrate_kinect DESTINATION bin)

ADD_EXECUTABLE(calibrate_kinect_ir MACOSX_BUNDLE calibrate_kinect_ir.cpp ${common_sources})
TARGET_LINK_LIBRARIES(calibrate_kinect_ir nestk)
INSTALL(TARGETS calibrate_kinect_ir DESTINATION bin)
SET(DIRS ${QT_LIBRARY_DIRS} ${CMAKE_BINARY_DIR}/lib ${CMAKE_BINARY_DIR}/bin)
INSTALL_STANDALONE_BUNDLE(calibrate_kinect_ir ${DIRS})
