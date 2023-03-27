cmake_minimum_required(VERSION 3.24)

# Enable policy to make vcpkg copy dll/so to build directory
cmake_policy(SET CMP0087 NEW)

# include logic to build glsl files
# include(cmake/glsl_compiler.cmake)

# project and language to be used
project(vulkan-lessons
	LANGUAGES CXX
	HOMEPAGE_URL "https://www.swapbuffer.com/vulkan-lessons"
	DESCRIPTION "Series of Lessons in using Vulkan.")

# executable source folder
add_subdirectory(src/Common)
add_subdirectory(src/0.InitialSetup)