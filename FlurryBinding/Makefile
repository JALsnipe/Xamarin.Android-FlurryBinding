
EXTRA_DIST =  Makefile

# Warning: This is an automatically generated file, do not edit!

srcdir=.
top_srcdir=..

include $(top_srcdir)/config.make

ifeq ($(CONFIG),DEBUG)
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

ifeq ($(CONFIG),RELEASE)
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

FLURRYINTERFACEDEFS_DLL = $(BUILD_DIR)/FlurryInterfaceDefs.dll
FLURRYBINDING_PC = $(BUILD_DIR)/flurrybinding.pc

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

#Targets
all: $(ASSEMBLY) $(PROGRAMFILES) $(LINUX_PKGCONFIG)  $(top_srcdir)/config.make

include $(top_srcdir)/Makefile.include
#include $(srcdir)/custom-hooks.make



$(eval $(call emit-deploy-target,FLURRYINTERFACEDEFS_DLL))
$(eval $(call emit-deploy-target,FLURRYINTERFACEDEFS_DLL_MDB))
$(eval $(call emit-deploy-wrapper,FLURRYBINDING_PC,flurrybinding.pc))


$(eval $(call emit_resgen_targets))
$(build_xamlg_list): %.xaml.g.cs: %.xaml
	xamlg '$<'


$(ASSEMBLY_MDB): $(ASSEMBLY)
$(ASSEMBLY): $(build_sources) $(build_resources) $(build_datafiles) $(DLL_REFERENCES) $(PROJECT_REFERENCES) $(build_xamlg_list) $(build_satellite_assembly_list)
	make pre-all-local-hook prefix=$(prefix)
	mkdir -p $(shell dirname $(ASSEMBLY))
	make $(CONFIG)_BeforeBuild
	$(ASSEMBLY_COMPILER_COMMAND) $(ASSEMBLY_COMPILER_FLAGS) -out:$(ASSEMBLY) -target:$(COMPILE_TARGET) $(build_sources_embed) $(build_resources_embed) $(build_references_ref)
	make $(CONFIG)_AfterBuild
	make post-all-local-hook prefix=$(prefix)

install-local: $(ASSEMBLY) $(ASSEMBLY_MDB)
	make pre-install-local-hook prefix=$(prefix)
	make install-satellite-assemblies prefix=$(prefix)
	mkdir -p '$(DESTDIR)$(libdir)/$(PACKAGE)'
	$(call cp,$(ASSEMBLY),$(DESTDIR)$(libdir)/$(PACKAGE))
	$(call cp,$(ASSEMBLY_MDB),$(DESTDIR)$(libdir)/$(PACKAGE))
	$(call cp,$(FLURRYBINDING_DLL_MDB),$(DESTDIR)$(libdir)/$(PACKAGE))
	$(call cp,$(FLURRYINTERFACEDEFS_DLL),$(DESTDIR)$(libdir)/$(PACKAGE))
	$(call cp,$(FLURRYINTERFACEDEFS_DLL_MDB),$(DESTDIR)$(libdir)/$(PACKAGE))
	mkdir -p '$(DESTDIR)$(libdir)/pkgconfig'
	$(call cp,$(FLURRYBINDING_PC),$(DESTDIR)$(libdir)/pkgconfig)
	make post-install-local-hook prefix=$(prefix)

uninstall-local: $(ASSEMBLY) $(ASSEMBLY_MDB)
	make pre-uninstall-local-hook prefix=$(prefix)
	make uninstall-satellite-assemblies prefix=$(prefix)
	$(call rm,$(ASSEMBLY),$(DESTDIR)$(libdir)/$(PACKAGE))
	$(call rm,$(ASSEMBLY_MDB),$(DESTDIR)$(libdir)/$(PACKAGE))
	$(call rm,$(FLURRYBINDING_DLL_MDB),$(DESTDIR)$(libdir)/$(PACKAGE))
	$(call rm,$(FLURRYINTERFACEDEFS_DLL),$(DESTDIR)$(libdir)/$(PACKAGE))
	$(call rm,$(FLURRYINTERFACEDEFS_DLL_MDB),$(DESTDIR)$(libdir)/$(PACKAGE))
	$(call rm,$(FLURRYBINDING_PC),$(DESTDIR)$(libdir)/pkgconfig)
	make post-uninstall-local-hook prefix=$(prefix)

install: install-local
uninstall: uninstall-local
clean: clean-local

include $(top_srcdir)/rules.make
