cmake_minimum_required(VERSION 3.0.0)
project(yolov5onnex VERSION 0.1.0)

include(CTest)
enable_testing()

find_package( OpenCV REQUIRED )
include_directories( ${OpenCV_INCLUDE_DIRS} )
include_directories (${CMAKE_CURRENT_BINARY_DIR})

add_executable(yolov5onnex yolov5onnex.cpp)
target_link_libraries(yolov5onnex ${OpenCV_LIBS} )
target_link_libraries(yolov5onnex ${CMAKE_CURRENT_BINARY_LIBS})


add_executable(nms nms.cpp)
target_link_libraries(nms ${OpenCV_LIBS} )
target_link_libraries(nms ${CMAKE_CURRENT_BINARY_LIBS})

add_executable(nmsfuntion nmsfuntion.cpp)
target_link_libraries(nmsfuntion ${OpenCV_LIBS} )
target_link_libraries(nmsfuntion ${CMAKE_CURRENT_BINARY_LIBS})



add_executable(objectdetection objectdetection.cpp)
target_link_libraries(objectdetection ${OpenCV_LIBS} )
target_link_libraries(objectdetection ${CMAKE_CURRENT_BINARY_LIBS})




add_executable(vector vector.cpp)
target_link_libraries(vector ${OpenCV_LIBS} )
target_link_libraries(vector ${CMAKE_CURRENT_BINARY_LIBS})



add_executable(nmscpp nmscpp.cpp)
target_link_libraries(nmscpp ${OpenCV_LIBS} )
target_link_libraries(nmscpp ${CMAKE_CURRENT_BINARY_LIBS})


set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
set(CMAKE_INCLUDE_CURRENT_DIR ON)
include(CPack)
