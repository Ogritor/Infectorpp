#=============================================================================
# Welcome to Infectorpp2 Build system.
#=============================================================================
cmake_minimum_required( VERSION 2.8)
project( Infectorpp2)

#-----------------------------------CONFIGURE---------------------------------
#-----------------------------------------------------------------------------
set( CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/cmake")
include( OutOfSourceBuild)
include( EnableCpp11)
include( SuperStrictWarnings)

#Target name is used so that you can build a different binary for each
#target you maintain (Linux, Win32, Win64, Win64 +SSE,  whatever)
set(INFECTORPP2_TARGET_NAME "bin" CACHE STRING
    "Give the name you like most to a logical target")

include( AddLibraryType)

set(SHARED_BUILD false )
add_library_type( libInfectorpp2 STATIC)


# = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = 
#---------------------------------- COMPILE ----------------------------------
# = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = = 
	
include( AddUnityObjectLibrary)

add_unity_object_library( infectorObj)


enable_testing()
add_subdirectory( tests)

	