project(prayer_unit)

find_package(Catch2 REQUIRED)

add_executable(unit main.cpp)
target_link_libraries(unit PRIVATE project_options project_warnings Catch2::Catch2)

add_test(NAME unit_test COMMAND unit)
