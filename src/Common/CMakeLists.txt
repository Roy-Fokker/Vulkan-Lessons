# create Common library for platform stuff. As Static library
add_library(vkl_common STATIC)

# add alias for consumer
add_library(vkl::common ALIAS vkl_common)

# ensure it's Standard C++ 20
target_compile_features(vkl_common PRIVATE cxx_std_20)

# expose current source directory for consumer headers.
target_include_directories(vkl_common PUBLIC
	${CMAKE_CURRENT_SOURCE_DIR})

# set preprocessor defines
target_compile_definitions(vkl_common PRIVATE 
	UNICODE _UNICODE
	_CRT_SECURE_NO_WARNINGS
	NOMINMAX
	WIN32_LEAN_AND_MEAN)

# source files for the common library
target_sources(vkl_common PRIVATE
	common.cpp)

# identify which header is public
set_target_properties(vkl_common PROPERTIES
	PUBLIC_HEADER
		common.h)