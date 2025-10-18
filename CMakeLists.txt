if(APPLE)

    cmake_minimum_required(VERSION 3.16)
    project(dictionary VERSION 5.7.1)

    find_package(Albert REQUIRED)
    find_package(QCoro6 REQUIRED COMPONENTS Coro)

    albert_plugin(
        LINK PRIVATE "-framework CoreServices"
        QT Core
        LINK PRIVATE QCoro6::Coro
    )

    target_compile_options(${PROJECT_NAME} PRIVATE "-fobjc-arc")

endif()
