cmake_minimum_required(VERSION 3.4.1)

set(GNUSTL_BASE_DIR ${CMAKE_CURRENT_LIST_DIR})
set(GNUSTL_SHARED_LIBS
    "${GNUSTL_BASE_DIR}/libs/${ANDROID_ABI}/libgnustl_static.a"
    "${GNUSTL_BASE_DIR}/libs/${ANDROID_ABI}/libsupc++.a")
set(GNUSTL_INCLUDE_DIRS
    "${GNUSTL_BASE_DIR}/include"
    "${GNUSTL_BASE_DIR}/libs/${ANDROID_ABI}/include"
    "${GNUSTL_BASE_DIR}/include/backward")

set(CMAKE_CXX_STANDARD_INCLUDE_DIRECTORIES "${CMAKE_CXX_STANDARD_INCLUDE_DIRECTORIES}" ${GNUSTL_INCLUDE_DIRS})
string(REPLACE ";" "\" \"" GNUSTL_LIBS "\"${GNUSTL_SHARED_LIBS}\"")
set(CMAKE_CXX_STANDARD_LIBRARIES "${CMAKE_CXX_STANDARD_LIBRARIES} ${GNUSTL_LIBS}")
