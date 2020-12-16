cmake_minimum_required (VERSION 3.4)

project(u8g2 C)

include_directories("u8g2/csrc/")

file(GLOB TARGET_SRC
        "csrc/*.c"
)

file(GLOB HEADER
        "csrc/*.h"
)

add_library(${PROJECT_NAME} ${TARGET_SRC} ${HEADER})

target_include_directories(${PROJECT_NAME}
	PUBLIC
		$<INSTALL_INTERFACE:include>
		$<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>
	PRIVATE
		${CMAKE_CURRENT_SOURCE_DIR}
)

