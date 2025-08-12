set(SOURCES  "main.cc"
            )

set(INCLUDE_DIRS "." )

# 添加板级公共文件
file(GLOB BOARD_COMMON_SOURCES ${CMAKE_CURRENT_SOURCE_DIR}/board/common/*.cc)
list(APPEND SOURCES ${BOARD_COMMON_SOURCES})
list(APPEND INCLUDE_DIRS ${CMAKE_CURRENT_SOURCE_DIR}/board/common)

idf_component_register(SRCS ${SOURCES}
                       INCLUDE_DIRS ${INCLUDE_DIRS}
                       WHOLE_ARCHIVE
                    )