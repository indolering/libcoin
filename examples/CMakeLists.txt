#######################################################
# this are setting used in SETUP_EXAMPLE macro
#######################################################
SET(TARGET_DEFAULT_PREFIX "example_")
SET(TARGET_DEFAULT_LABEL_PREFIX "Examples")

SET(TARGET_COMMON_LIBRARIES 
    coin
    coinHTTP
    coinChain
)

IF(ANDROID)
    # ADD_SUBDIRECTORY(coinandroidsimple)
ELSE(ANDROID)

IF(DYNAMIC_LIBCOIN)

ELSE(DYNAMIC_LIBCOIN)
    #needed on win32 or the linker get confused by _declspec declarations
    ADD_DEFINITIONS(-DLIBCOIN_LIBRARY_STATIC)
ENDIF(DYNAMIC_LIBCOIN)

    
ADD_SUBDIRECTORY(simplecoin)
ADD_SUBDIRECTORY(ponzicoin)
ADD_SUBDIRECTORY(extrawallet)

#    IF   (wxWidgets_FOUND)
#        ADD_SUBDIRECTORY(bitsimpleWX)
#    ENDIF(wxWidgets_FOUND)

ENDIF(ANDROID)

