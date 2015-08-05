# Reference: http://qt-project.org/doc/qt-5.0/qtdoc/cmake-manual.html

cmake_minimum_required(VERSION 2.8.12)
cmake_policy(SET CMP0020 NEW)
set(PROJECT "PRO")

project(${PROJECT})

set(CMAKE_INCLUDE_CURRENT_DIR ON)
set(CMAKE_AUTOMOC ON)

project(${PROJECT})

# set(CMAKE_PREFIX_PATH /Users/Me/Qt5.4.2/5.4/clang_64/lib/cmake/)
# set(CMAKE_BUILD_TYPE Debug)
# set(EMOTIENT_SDK_DIR /Users/Me/EmotientSDK)
# set(QT_PATH /Users/Me/Qt5.4.2/5.4/clang_64)

set(CMAKE_PREFIX_PATH, ${QT_PATH}/lib/cmake)
set(CMAKE_INCLUDE_CURRENT_DIR ON)
set(CMAKE_AUTOMOC ON)


find_package(Qt5Widgets REQUIRED)

set(SOURCE_FILES
    main.cpp
)

add_executable(${PROJECT} 
    ${SOURCE_FILES}
)

qt5_use_modules(${PROJECT} Widgets Core Gui )

if (MSVC)

    set_target_properties(${PROJECT} PROPERTIES
        WIN32_EXECUTABLE YES
        LINK_FLAGS "/ENTRY:mainCRTStartup"
    )
endif ()




