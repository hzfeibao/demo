EXECUTABLE = demo


SOURCES = main.cpp \
        ../Classes/AppDelegate.cpp \
        ../Classes/HelloWorldScene.cpp\
	../Classes/controller.cpp\
	../Classes/testBasic.cpp\
	../Classes/VisibleRect.cpp\
	../Classes/ActionsProgressTest/ActionsProgressTest.cpp\


#COCOS_ROOT = ../../..
#include $(COCOS_ROOT)/cocos2dx/proj.linux/cocos2dx.mk

COCOS_ROOT = ../../..
include $(COCOS_ROOT)/cocos2dx/proj.linux/cocos2dx.mk
##INCLUDES = -I.. -I../Classes\
##	   -I$(COCOS_ROOT)/external

SHAREDLIBS += -lcocos2d -lcocosdenshion -lcurl
COCOS_LIBS = $(LIB_DIR)/libcocos2d.so $(LIB_DIR)/libcocosdenshion.so

INCLUDES += -I$(COCOS_ROOT)/CocosDenshion
INCLUDES += -I$(COCOS_ROOT)/CocosDenshion/include
INCLUDES += -I$(COCOS_ROOT)/extensions
INCLUDES += -I$(COCOS_ROOT)/external
INCLUDES += -I$(COCOS_ROOT)/external/chipmunk/include/chipmunk

$(TARGET): $(OBJECTS) $(STATICLIBS) $(COCOS_LIBS) $(CORE_MAKEFILE_LIST)
	@mkdir -p $(@D)
	$(LOG_LINK)$(CXX) $(CXXFLAGS) $(OBJECTS) -o $@ $(SHAREDLIBS) $(STATICLIBS)

$(OBJ_DIR)/%.o: %.cpp $(CORE_MAKEFILE_LIST)
	@mkdir -p $(@D)
	$(LOG_CXX)$(CXX) $(CXXFLAGS) $(INCLUDES) $(DEFINES) $(VISIBILITY) -c $< -o $@

$(OBJ_DIR)/%.o: ../%.cpp $(CORE_MAKEFILE_LIST)
	@mkdir -p $(@D)
	$(LOG_CXX)$(CXX) $(CXXFLAGS) $(INCLUDES) $(DEFINES) $(VISIBILITY) -c $< -o $@
