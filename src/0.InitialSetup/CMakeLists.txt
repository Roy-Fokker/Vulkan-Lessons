# create executable for initial setup
add_executable(vkl_0_initialsetup)

# ensure it's Standard C++ 20
target_compile_features(vkl_0_initialsetup PRIVATE cxx_std_20)

# set preprocessor defines
target_compile_definitions(vkl_0_initialsetup
	PRIVATE 
		UNICODE _UNICODE
		_CRT_SECURE_NO_WARNINGS
		NOMINMAX
		WIN32_LEAN_AND_MEAN)

# source files for this application
target_sources(vkl_0_initialsetup
	PRIVATE
		main.cpp)

# libraries used by this application
target_link_libraries(vkl_0_initialsetup
	PRIVATE
		vkl::common)