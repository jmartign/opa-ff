# BEGIN_ICS_COPYRIGHT8 ****************************************
# 
# Copyright (c) 2015, Intel Corporation
# 
# Redistribution and use in source and binary forms, with or without
# modification, are permitted provided that the following conditions are met:
# 
#     * Redistributions of source code must retain the above copyright notice,
#       this list of conditions and the following disclaimer.
#     * Redistributions in binary form must reproduce the above copyright
#       notice, this list of conditions and the following disclaimer in the
#       documentation and/or other materials provided with the distribution.
#     * Neither the name of Intel Corporation nor the names of its contributors
#       may be used to endorse or promote products derived from this software
#       without specific prior written permission.
# 
# THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS"
# AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE
# IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE
# DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT OWNER OR CONTRIBUTORS BE LIABLE
# FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL
# DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR
# SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER
# CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY,
# OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
# OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
# 
# END_ICS_COPYRIGHT8   ****************************************
# Makefile for MpiApps

# Include Make Control Settings
include $(TL_DIR)/$(PROJ_FILE_DIR)/Makesettings.project

DS_SUBPROJECTS	= 
DSP_SOURCES = Makefile

DIRS			= 

include $(TL_DIR)/$(PROJ_FILE_DIR)/Makerules.project

INSTALL_TEST_APPS_SRC =	$(TL_DIR)/ShmemApps/apps/shmem_apps.tgz
SHMEM_INSTALL_TESTS_DIR = $(PROJ_STAGE_DIR)/Tests/shmem

CLOBBER_EXTRA = \
	.ICSBOOTROMVERSIONSTRING \
	# add additional files here

.PHONEY: appl
appl $(TL_DIR)/ShmemApps/apps/shmem_apps.tgz:
	if [ -d apps ]; then \
		cd apps; $(MAKE) -f Makefile.package $(MFLAGS) ALL; \
	fi


cleandepend clean:: clobber

clobber::
	if [ -d apps ]; then \
		cd apps; $(MAKE) -f Makefile.package $(MFLAGS) CLOBBER; \
	fi
depend::
force::
ALL:: INCLUDES LIBS CMDS
INCLUDES::
LIBS::
# do the real work during CMDS
CMDS:: $(INSTALL_TEST_APPS_SRC)

STAGE::
	$(VS)if [ -d apps ]; then $(STAGE_INSTALL) $(STAGE_INSTALL_DIR_OPT) $(SHMEM_INSTALL_TESTS_DIR) $(INSTALL_TEST_APPS_SRC); fi
	$(VS)if [ -d apps ]; then $(STAGE_INSTALL) $(STAGE_INSTALL_DIR_OPT) $(PROJ_STAGE_SRC_DIR)/shmem/shmem_apps $(INSTALL_TEST_APPS_SRC); fi

INSTALL::
RUNTEST::
build_dsfiles::
clobber_dsfiles::
lint::
cflow::
