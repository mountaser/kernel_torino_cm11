#/*******************************************************************************************
#Copyright 2010 Broadcom Corporation.  All rights reserved.
#
#Unless you and Broadcom execute a separate written software license agreement
#governing use of this software, this software is licensed to you under the
#terms of the GNU General Public License version 2, available at
#http://www.gnu.org/copyleft/gpl.html (the "GPL").
#
#Notwithstanding the above, under no circumstances may you combine this software
#in any way with any other Broadcom software provided under a license other than
#the GPL, without Broadcom's express prior written consent.
#*******************************************************************************************/

#
## Makefile for ALSA BRCM OMX
#
# -D USE_HAL_AUDIO_THREAD

#EXTRA_CFLAGS := -Wno-error -D USE_HAL_AUDIO_THREAD -D FUSE_DUAL_PROCESSOR_ARCHITECTURE -D FUSE_APPS_PROCESSOR -U FUSE_COMMS_PROCESSOR -D _BCM21553_ -D CHIP_REVISION=51

#ifeq ($(CONFIG_ARCH_BCM2157), y)
#EXTRA_CFLAGS += -D BCM2153_FAMILY_BB_CHIP_BOND -I$(src)/hal2157 -I$(src)
#ifeq ($(CONFIG_BOARD_BONDRAY),y)
#EXTRA_CFLAGS += -D BUILD_BONDRAY
#endif
#else
#EXTRA_CFLAGS += -I$(src)/hal2153 -I$(src)
#endif


#EXTRA_CFLAGS += -DUNDER_LINUX
#EXTRA_CFLAGS += -DRPC_INCLUDED
#EXTRA_CFLAGS += -DSTACK_wedge

#EXTRA_CFLAGS += -Idrivers/staging/bcm21553/drivers/char/brcm/fuse_ril/CAPI2/inc/
#EXTRA_CFLAGS += -Idrivers/staging/bcm21553/drivers/char/brcm/fuse_rpc/rpc/inc/
#EXTRA_CFLAGS += -Idrivers/staging/bcm21553/drivers/char/brcm/fuse_ipc/ipc/Implementation/Headers/
#EXTRA_CFLAGS += -Idrivers/staging/bcm21553/drivers/char/brcm/fuse_ipc/inc/

EXTRA_CFLAGS += -DUNDER_LINUX
EXTRA_CFLAGS += -D _ATHENA_  -D MSP -D FUSE_DUAL_PROCESSOR_ARCHITECTURE -D FUSE_APPS_PROCESSOR -D PMU_MAX8986 -D CHAL_NDEBUG_BUILD -D CHIP_REVISION=20 -D VPU_INCLUDED -D ATHENA_INCLUDE_VOIP -DENABLE_GPIO -DENABLE_VOIF
#EXTRA_CFLAGS += -D NO_SYSPARAM -D NO_PMU


ifeq ($(CONFIG_BOARD_TOTORO), y)
EXTRA_CFLAGS += -DAUDIO_GPIO_TOTORO
endif
ifeq ($(CONFIG_BOARD_LUISA), y)
EXTRA_CFLAGS += -DAUDIO_GPIO_LUISA
endif
ifeq ($(CONFIG_BOARD_TASSVE), y)
EXTRA_CFLAGS += -DAUDIO_GPIO_TASSVE
endif
ifeq ($(CONFIG_BOARD_COOPERVE), y)
EXTRA_CFLAGS += -DAUDIO_GPIO_COOPERVE
endif

#Audio Controller header files
EXTRA_CFLAGS += -I$(src)
EXTRA_CFLAGS += -I$(src)/common -I$(src)/audio/audio_controller -I$(src)/audio/audio_controller/public
EXTRA_CFLAGS += -I$(src)/audio/audio_vdriver/public/
EXTRA_CFLAGS += -I$(src)/audio/public/
EXTRA_CFLAGS += -I$(src)/audio/audio_datadriver/public/
#CSL header files
EXTRA_CFLAGS += -I$(src)/soc/csl/audio/public/
EXTRA_CFLAGS += -I$(src)/soc/csl/dsp/public/
EXTRA_CFLAGS += -I$(src)/soc/csl/bsp/public/
#CHAL header files
EXTRA_CFLAGS += -I$(src)/soc/chal/modules/audio/inc/
#EXTRA_CFLAGS += -I$(src)/soc/chal/athena/bsp/inc/
#EXTRA_CFLAGS += -I$(src)/soc/chal/os_adaptation/linux/inc/
#RDB header files
#EXTRA_CFLAGS += -I$(src)/rdb/athena/A0
EXTRA_CFLAGS += -I$(src)/rdb/athena/B0
#DSP header files
EXTRA_CFLAGS += -I$(src)/dsp/public/
#EXTRA_CFLAGS += -I$(src)/dsp/athena/A0/include/
EXTRA_CFLAGS += -I$(src)/dsp/athena/B0/include/
#SYSPARM Header files
#EXTRA_CFLAGS += -I$(src)/sysinterface/sysparms/
#RPC Header files

# _BSDTYPES_DEFINED needed so uchar doesn't get redefined in CAPI2 headers
EXTRA_CFLAGS += -D_BSDTYPES_DEFINED
EXTRA_CFLAGS += -Idrivers/staging/bcm21553/drivers/char/brcm/fuse_rpc/rpc_CIB/public/
EXTRA_CFLAGS += -Idrivers/staging/bcm21553/drivers/char/brcm/fuse_rpc/rpc_CIB/arpc/inc/
EXTRA_CFLAGS += -Idrivers/staging/bcm21553/drivers/char/brcm/fuse_rpc/rpc_CIB/srpc/inc/
EXTRA_CFLAGS += -Idrivers/staging/bcm21553/drivers/char/brcm/fuse_rpc/rpc_CIB/xdr/inc/
include drivers/staging/bcm21553/drivers/char/brcm/fuse_ril/CAPI2_CIB/capi2_include_paths.gmk

#LOG Header files
EXTRA_CFLAGS += -I$(src)/soc/debug/public
EXTRA_CFLAGS += -Idrivers/staging/bcm21553/drivers/char/brcm/fuse_log

#PMU Header files
#EXTRA_CFLAGS += -I$(src)/peripherals/pmu/public
#EXTRA_CFLAGS += -I$(src)/sysinterface/hal/pmu/public

#VOIF Handler Header files
EXTRA_CFLAGS += -I$(src)/audio/voif_handler/public

#GPIO Handler Header files
EXTRA_CFLAGS += -I$(src)/audio/gpio_handler/public

#Platform header files
EXTRA_CFLAGS += -I./arch/arm/plat-bcmap/include/
EXTRA_CFLAGS += -I./arch/arm/plat-bcmap/include/plat/
EXTRA_CFLAGS += -I./drivers/char/broadcom/
EXTRA_CFLAGS += -I./arch/arm/mach-bcm215xx/include/
EXTRA_CFLAGS += -I./arch/arm/plat-bcmap/include/plat/chal/
EXTRA_CFLAGS += -I./arch/arm/plat-bcmap/include/plat/osabstract/

obj-$(CONFIG_BRCM_SOUND_ATHENA_ALSA) += snd-brcm-omx.o
snd-brcm-omx-objs := brcm_alsa_dev.o
snd-brcm-omx-objs += brcm_alsa_pcm.o
snd-brcm-omx-objs += brcm_alsa_ctl.o
snd-brcm-omx-objs += brcm_audio_thread.o
#snd-brcm-omx-objs += audio_stubs.o
snd-brcm-omx-objs += brcm_auddrv_test.o
snd-brcm-omx-objs += brcm_audio_policy.o
snd-brcm-omx-objs += audio/audio_controller/src/audio_controller_audvoc.o
snd-brcm-omx-objs += audio/audio_controller/src/audio_controller_common.o
snd-brcm-omx-objs += audio/audio_controller/src/audio_gain_table.o
snd-brcm-omx-objs += audio/audio_datadriver/src/audio_ddriver.o

#CHAL Source Files
snd-brcm-omx-objs += soc/chal/modules/audio/audvoc/src/chal_audiospeaker.o
snd-brcm-omx-objs += soc/chal/modules/audio/audvoc/src/chal_audioaipath.o
snd-brcm-omx-objs += soc/chal/modules/audio/audvoc/src/chal_audioaopath.o
snd-brcm-omx-objs += soc/chal/modules/audio/audvoc/src/chal_audiopopath.o
snd-brcm-omx-objs += soc/chal/modules/audio/audvoc/src/chal_audiovipath.o
snd-brcm-omx-objs += soc/chal/modules/audio/audvoc/src/chal_audiovopath.o
snd-brcm-omx-objs += soc/chal/modules/audio/audvoc/src/chal_audiopcmif.o
snd-brcm-omx-objs += soc/chal/modules/audio/audvoc/src/chal_audiomixertap.o
snd-brcm-omx-objs += soc/chal/modules/audio/audvoc/src/chal_audiomixer.o
snd-brcm-omx-objs += soc/chal/modules/audio/audvoc/src/chal_audiomic.o
snd-brcm-omx-objs += soc/chal/modules/audio/audvoc/src/chal_dsppcm.o

#CSL Source Files
snd-brcm-omx-objs += soc/csl/audio/src/csl_aud_drv_hw.o
snd-brcm-omx-objs += soc/csl/audio/src/csl_audvoc_render.o
snd-brcm-omx-objs += soc/csl/audio/src/csl_audvoc_capture.o
snd-brcm-omx-objs += soc/csl/audio/src/csl_aud_queue.o

#audio vdriver Source Files
snd-brcm-omx-objs += audio/audio_vdriver/src/audio_vdriver_audvoc.o
snd-brcm-omx-objs += audio/audio_vdriver/src/audio_vdriver_common.o
snd-brcm-omx-objs += audio/audio_vdriver/src/audio_rpc.o
snd-brcm-omx-objs += audio/audio_vdriver/src/ripisr_audio.o
snd-brcm-omx-objs += audio/audio_vdriver/src/dspif_voice_record.o
snd-brcm-omx-objs += audio/audio_vdriver/src/audio_ipc_ap.o
snd-brcm-omx-objs += audio/audio_vdriver/src/audio_vdriver_audlog.o
snd-brcm-omx-objs += audio/audio_vdriver/src/audio_vdriver_voif.o
snd-brcm-omx-objs += audio/audio_vdriver/src/audio_vdriver_gpio.o
#snd-brcm-omx-objs += audio/audio_vdriver/src/audio_vdriver_voice_play.o
#snd-brcm-omx-objs += audio/audio_vdriver/src/audio_vdriver_voice_record.o
#snd-brcm-omx-objs += audio/audio_vdriver/src/audio_vdriver_voicetap.o

#
#dsp source files
snd-brcm-omx-objs += dsp/audio/src/vpu.o
#snd-brcm-omx-objs += dsp/rip/ripisr_ap.o
#snd-brcm-omx-objs += dsp/rip/ripcmdq.o
#snd-brcm-omx-objs += dsp/rip/vpripcmdq.o
#snd-brcm-omx-objs += dsp/rip/vsharedmem.o
snd-brcm-omx-objs += soc/csl/dsp/src/sharedmem_ap.o
snd-brcm-omx-objs += soc/csl/dsp/src/csl_dsp.o
snd-brcm-omx-objs += soc/csl/dsp/src/csl_apcmd.o
snd-brcm-omx-objs += soc/csl/dsp/src/osdw_dsp_drv.o

#voif handler source files
snd-brcm-omx-objs += audio/voif_handler/src/voif_handler.o

#gpio handler source files
snd-brcm-omx-objs += audio/gpio_handler/src/gpio_handler.o
