cmake_minimum_required(VERSION 3.15)

# Переменные
set(CMAKE_CXX_STANDARD 17)

# Расположение файлов библиотеки
FILE(GLOB_RECURSE INCLUDES ${ENGINE_SOURCE}/*.h)
FILE(GLOB_RECURSE SOURCES ${ENGINE_SOURCE}/*.cpp)
source_group(TREE ${ENGINE_SOURCE} TREE PREFIX "" FILES ${INCLUDES} ${SOURCES})

# Расположение заголовочных файлов
include_directories(${GAME_SOURCE})

# ThirdPathy
include_directories(${GLM_INCLUDES})
include_directories(${JSONCPP_INCLUDES})
include_directories(${GLFW_INCLUDES})
include_directories(${GLEW_INCLUDES})
include_directories(${FREEIMAGE_INCLUDES})
include_directories(${PHYSX_INCLUDES})
include_directories(${PHYSX_INCLUDES_PXSHARED})
include_directories(${FREETYPE2_INCLUDES})

# Создание статической библиотеки
add_library(${ENGINE_NAME} STATIC ${INCLUDES} ${SOURCES})

