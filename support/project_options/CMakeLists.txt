add_library(project_options INTERFACE)

include(CheckCXXCompilerFlag)
if(ENABLE_COVERAGE)
    check_cxx_compiler_flag("--coverage" COMPILER_SUPPORTS_COVERAGE)

    if(COMPILER_SUPPORTS_COVERAGE)
        target_compile_options(project_options INTERFACE --coverage -O0 -g)
        target_link_libraries(project_options INTERFACE --coverage)
    else()
        message(STATUS "Compiler does not support the coverage flag")
    endif()
endif()
