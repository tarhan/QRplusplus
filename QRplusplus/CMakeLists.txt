cmake_minimum_required(VERSION 3.5)
project(QRplusplus
    VERSION 0.2.0.0
    LANGUAGES CXX
)

add_executable(QRplusplus "")

set(SOURCES
    main.cpp
    qrplusplus.h
    qrplusplus.cpp
    qrplusplus.qrc
    qrplusplus.ui

    BitBuffer.hpp
    BitBuffer.cpp

    QrCode.hpp
    QrCode.cpp

    QrSegment.hpp
    QrSegment.cpp
)

target_sources(QRplusplus
    PRIVATE ${SOURCES}
)

find_package(Qt5 COMPONENTS Core Gui Widgets REQUIRED)
target_link_libraries(QRplusplus
    PRIVATE
        Qt5::Core
        Qt5::Gui
        Qt5::Widgets
)

set_target_properties(QRplusplus PROPERTIES
    CXX_STANDARD 14
    CXX_STANDARD_REQUIRED ON
    AUTOUIC ON
    AUTOMOC ON
)
