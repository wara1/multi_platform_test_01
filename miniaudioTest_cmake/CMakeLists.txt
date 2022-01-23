# CMakeList.txt : miniaudioTest_cmake の CMake プロジェクト。ソースを含めて、次を定義します:
# プロジェクト専用ロジックはこちらです。
#
cmake_minimum_required (VERSION 3.8)

# ソースをこのプロジェクトの実行可能ファイルに追加します。
add_executable (
  miniaudioTest_cmake
  src/main.cpp
)

# インクルードするファイル
target_include_directories(
  miniaudioTest_cmake
  PRIVATE
    "${CMAKE_SOURCE_DIR}/miniaudioTest_cmake/inc/"
)

if(WIN32)
  message("Windows OS!!!!!")
else (UNIX)
  message("Linux OS!!!!!")

  target_link_libraries(
    miniaudioTest_cmake
    dl
    pthread
  )
endif()
