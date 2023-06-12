# needed since we skip the main jsoncpp cmake file that defines this
set(ARCHIVE_INSTALL_DIR lib)
add_subdirectory(${at_media_deps_dir}/jsoncpp/src ${at_media_deps_dir}/jsoncpp/src)
set(jsoncpp_includes ${at_media_deps_dir}/jsoncpp/include)
target_include_directories(jsoncpp_lib PUBLIC ${jsoncpp_includes})
add_library(at_jsoncpp INTERFACE)
target_include_directories(at_jsoncpp INTERFACE ${jsoncpp_includes})
target_link_libraries(at_jsoncpp INTERFACE jsoncpp_lib)