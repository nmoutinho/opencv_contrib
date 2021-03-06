cmake_minimum_required(VERSION 2.8)
SET(CMAKE_CXX_FLAGS_DEBUG "$ENV{CXXFLAGS} -O0 -Wall -g -ggdb ")
SET(CMAKE_CXX_FLAGS_RELEASE "$ENV{CXXFLAGS} -O3 -Wall")
project(cnn_3dobj)
find_package(OpenCV REQUIRED)
set(SOURCES_generator demo_sphereview_data.cpp)
include_directories(${OpenCV_INCLUDE_DIRS})
add_executable(sphereview_test ${SOURCES_generator})
target_link_libraries(sphereview_test opencv_core opencv_imgproc opencv_highgui opencv_cnn_3dobj opencv_xfeatures2d)

set(SOURCES_classifier demo_classify.cpp)
add_executable(classify_test ${SOURCES_classifier})
target_link_libraries(classify_test opencv_core opencv_imgproc opencv_highgui opencv_cnn_3dobj opencv_xfeatures2d)

set(SOURCES_modelanalysis demo_model_analysis.cpp)
add_executable(model_test ${SOURCES_modelanalysis})
target_link_libraries(model_test opencv_core opencv_imgproc opencv_highgui opencv_cnn_3dobj opencv_xfeatures2d)

set(SOURCES_video demo_video.cpp)
add_executable(video_test ${SOURCES_video})
target_link_libraries(video_test opencv_core opencv_imgproc opencv_highgui opencv_cnn_3dobj opencv_xfeatures2d)
