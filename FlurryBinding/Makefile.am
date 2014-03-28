
EXTRA_DIST =  

# Warning: This is an automatically generated file, do not edit!

if ENABLE_DEBUG
ASSEMBLY_COMPILER_COMMAND = smcs
ASSEMBLY_COMPILER_FLAGS =  -noconfig -codepage:utf8 -warn:4 -optimize- -debug "-define:DEBUG;__MOBILE__;__ANDROID__;"
ASSEMBLY = bin/Debug/FlurryBinding.dll
ASSEMBLY_MDB = $(ASSEMBLY).mdb
COMPILE_TARGET = library
PROJECT_REFERENCES =  \
	../FlurryInterfaceDefs/bin/Debug/FlurryInterfaceDefs.dll
BUILD_DIR = bin/Debug

FLURRYBINDING_DLL_MDB_SOURCE=bin/Debug/FlurryBinding.dll.mdb
FLURRYBINDING_DLL_MDB=$(BUILD_DIR)/FlurryBinding.dll.mdb
FLURRYINTERFACEDEFS_DLL_SOURCE=../FlurryInterfaceDefs/bin/Debug/FlurryInterfaceDefs.dll
FLURRYINTERFACEDEFS_DLL_MDB_SOURCE=../FlurryInterfaceDefs/bin/Debug/FlurryInterfaceDefs.dll.mdb
FLURRYINTERFACEDEFS_DLL_MDB=$(BUILD_DIR)/FlurryInterfaceDefs.dll.mdb

endif

if ENABLE_RELEASE
ASSEMBLY_COMPILER_COMMAND = smcs
ASSEMBLY_COMPILER_FLAGS =  -noconfig -codepage:utf8 -warn:4 -optimize+ "-define:__MOBILE__;__ANDROID__;"
ASSEMBLY = bin/Release/FlurryBinding.dll
ASSEMBLY_MDB = 
COMPILE_TARGET = library
PROJECT_REFERENCES =  \
	../FlurryInterfaceDefs/bin/Release/FlurryInterfaceDefs.dll
BUILD_DIR = bin/Release

FLURRYBINDING_DLL_MDB=
FLURRYINTERFACEDEFS_DLL_SOURCE=../FlurryInterfaceDefs/bin/Release/FlurryInterfaceDefs.dll
FLURRYINTERFACEDEFS_DLL_MDB=

endif

AL=al
SATELLITE_ASSEMBLY_NAME=$(notdir $(basename $(ASSEMBLY))).resources.dll

PROGRAMFILES = \
	$(FLURRYBINDING_DLL_MDB) \
	$(FLURRYINTERFACEDEFS_DLL) \
	$(FLURRYINTERFACEDEFS_DLL_MDB)  

LINUX_PKGCONFIG = \
	$(FLURRYBINDING_PC)  


RESGEN=resgen2
	
all: $(ASSEMBLY) $(PROGRAMFILES) $(LINUX_PKGCONFIG) 

FILES = \
	Properties/AssemblyInfo.cs 

DATA_FILES = 

RESOURCES = 

EXTRAS = \
	Additions/AboutAdditions.txt \
	Jars/AboutJars.txt \
	flurrybinding.pc.in 

REFERENCES =  \
	System \
	System.Xml \
	System.Core \
	Mono.Android

DLL_REFERENCES = 

CLEANFILES = $(PROGRAMFILES) $(LINUX_PKGCONFIG) 

include $(top_srcdir)/Makefile.include

FLURRYINTERFACEDEFS_DLL = $(BUILD_DIR)/FlurryInterfaceDefs.dll
FLURRYBINDING_PC = $(BUILD_DIR)/flurrybinding.pc

$(eval $(call emit-deploy-target,FLURRYINTERFACEDEFS_DLL))
$(eval $(call emit-deploy-target,FLURRYINTERFACEDEFS_DLL_MDB))
$(eval $(call emit-deploy-wrapper,FLURRYBINDING_PC,flurrybinding.pc))


$(eval $(call emit_resgen_targets))
$(build_xamlg_list): %.xaml.g.cs: %.xaml
	xamlg '$<'

$(ASSEMBLY_MDB): $(ASSEMBLY)

$(ASSEMBLY): $(build_sources) $(build_resources) $(build_datafiles) $(DLL_REFERENCES) $(PROJECT_REFERENCES) $(build_xamlg_list) $(build_satellite_assembly_list)
	mkdir -p $(shell dirname $(ASSEMBLY))
	$(ASSEMBLY_COMPILER_COMMAND) $(ASSEMBLY_COMPILER_FLAGS) -out:$(ASSEMBLY) -target:$(COMPILE_TARGET) $(build_sources_embed) $(build_resources_embed) $(build_references_ref)
