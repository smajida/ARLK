CMAKE_MINIMUM_REQUIRED(VERSION 2.8)

IF(${CMAKE_SYSTEM_NAME} MATCHES "Windows")

	SET( SRCS
		stdafx.h
		resource.h
		MyDebug.h
		SkeletonPlayer.h
		SkeletonPlayer.cpp
		ConsoleWindowsApp.cpp
		SkeletonPlayer.rc
		)
	
	ADD_DEFINITIONS(-D_AFXDLL -DUNICODE -D_UNICODE)
	SET(CMAKE_MFC_FLAG 0)
	
	#Absolute path of ARLK include directory
	INCLUDE_DIRECTORIES("E:/ustc/CS/HI/kinect/GradPaper/ARLK_LIB/include")
	
	#Absolute path of Microsoft Kinect SDK inc directory
	INCLUDE_DIRECTORIES("C:/Program Files/Microsoft SDKs/Kinect/v1.6/inc")
	
	#Absolute path of ARLK lib directory
	LINK_DIRECTORIES("E:/ustc/CS/HI/kinect/GradPaper/ARLK_LIB/win32/lib")
	
	#Absolute path of Microsoft Kinect SDK lib directory
	LINK_DIRECTORIES("C:/Program Files/Microsoft SDKs/Kinect/v1.6/lib/x86")
	
	ADD_EXECUTABLE(SkeletonPlayer WIN32 ${SRCS})
	
	#Link the lib files
	TARGET_LINK_LIBRARIES(SkeletonPlayer SkeData Kinect10 Shlwapi)

ENDIF(${CMAKE_SYSTEM_NAME} MATCHES "Windows")