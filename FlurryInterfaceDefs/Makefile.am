
EXTRA_DIST =  

# Warning: This is an automatically generated file, do not edit!

if ENABLE_DEBUG
ASSEMBLY_COMPILER_COMMAND = smcs
ASSEMBLY_COMPILER_FLAGS =  -noconfig -codepage:utf8 -warn:4 -optimize- -debug "-define:DEBUG;__MOBILE__;__ANDROID__;"
ASSEMBLY = bin/Debug/FlurryInterfaceDefs.dll
ASSEMBLY_MDB = $(ASSEMBLY).mdb
COMPILE_TARGET = library
PROJECT_REFERENCES = 
BUILD_DIR = bin/Debug

FLURRYINTERFACEDEFS_DLL_MDB_SOURCE=bin/Debug/FlurryInterfaceDefs.dll.mdb
FLURRYINTERFACEDEFS_DLL_MDB=$(BUILD_DIR)/FlurryInterfaceDefs.dll.mdb

endif

if ENABLE_RELEASE
ASSEMBLY_COMPILER_COMMAND = smcs
ASSEMBLY_COMPILER_FLAGS =  -noconfig -codepage:utf8 -warn:4 -optimize+ "-define:__MOBILE__;__ANDROID__;"
ASSEMBLY = bin/Release/FlurryInterfaceDefs.dll
ASSEMBLY_MDB = 
COMPILE_TARGET = library
PROJECT_REFERENCES = 
BUILD_DIR = bin/Release

FLURRYINTERFACEDEFS_DLL_MDB=

endif

AL=al
SATELLITE_ASSEMBLY_NAME=$(notdir $(basename $(ASSEMBLY))).resources.dll

PROGRAMFILES = \
	$(FLURRYINTERFACEDEFS_DLL_MDB)  

LINUX_PKGCONFIG = \
	$(FLURRYINTERFACEDEFS_PC)  


RESGEN=resgen2
	
all: $(ASSEMBLY) $(PROGRAMFILES) $(LINUX_PKGCONFIG) 

FILES = \
	MainActivity.cs \
	Resources/Resource.designer.cs \
	Properties/AssemblyInfo.cs \
	IJavaObjectEx.cs 

DATA_FILES = 

RESOURCES = 

EXTRAS = \
	Resources/AboutResources.txt \
	Assets/AboutAssets.txt \
	Properties/AndroidManifest.xml \
	flurryinterfacedefs.pc.in 

REFERENCES =  \
	System \
	System.Xml \
	System.Core \
	Mono.Android

DLL_REFERENCES = 

CLEANFILES = $(PROGRAMFILES) $(LINUX_PKGCONFIG) 

include $(top_srcdir)/Makefile.include

FLURRYINTERFACEDEFS_PC = $(BUILD_DIR)/flurryinterfacedefs.pc

$(eval $(call emit-deploy-wrapper,FLURRYINTERFACEDEFS_PC,flurryinterfacedefs.pc))


$(eval $(call emit_resgen_targets))
$(build_xamlg_list): %.xaml.g.cs: %.xaml
	xamlg '$<'

$(ASSEMBLY_MDB): $(ASSEMBLY)

$(ASSEMBLY): $(build_sources) $(build_resources) $(build_datafiles) $(DLL_REFERENCES) $(PROJECT_REFERENCES) $(build_xamlg_list) $(build_satellite_assembly_list)
	mkdir -p $(shell dirname $(ASSEMBLY))
	$(ASSEMBLY_COMPILER_COMMAND) $(ASSEMBLY_COMPILER_FLAGS) -out:$(ASSEMBLY) -target:$(COMPILE_TARGET) $(build_sources_embed) $(build_resources_embed) $(build_references_ref)
