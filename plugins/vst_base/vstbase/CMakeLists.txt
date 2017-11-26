BUILD_PLUGIN(vstbase
	../vst_base.cpp ../VstPlugin.cpp ../VstPlugin.h ../communication.h 
	MOCFILES ../VstPlugin.h 
	EXPORT_BASE_NAME vstbase
	LINK SHARED
)

TARGET_INCLUDE_DIRECTORIES(vstbase
	PUBLIC ../
)

IF(LMMS_BUILD_LINUX AND WANT_QT5)
	TARGET_LINK_LIBRARIES(vstbase qx11embedcontainer)
ENDIF()
