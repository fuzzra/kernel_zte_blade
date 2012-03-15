# bcm4330_b1_b2_zte

SRCBASE := $(shell /bin/pwd)/../..
DHDCFLAGS = -DLINUX -DSRCBASE=\"$(SRCBASE)\" -DBCMDRIVER -DBCMDONGLEHOST -DUNRELEASEDCHIP -DBCMDMA32 -DWLBTAMP \
			-DBCMFILEIMAGE  -DCONFIG_WIRELESS_EXT -DDHDTHREAD -DDHD_GPL -DDHD_SCHED -DDHD_DEBUG -DSDTEST \
			-DBDC -DTOE -DDHD_BCMEVENTS -DSHOW_EVENTS -DBCMSDIO -DDHD_GPL -DBCMLXSDMMC -DBCMPLATFORM_BUS \
			-DWIFI_ACT_FRAME -DOOB_INTR_ONLY -DCUSTOM_OOB_GPIO_NUM=19
						
DHDIFLAGS =	-Idrivers/net/wireless/bcm4330_b1_b2_zte -Idrivers/net/wireless/bcm4330_b1_b2_zte/include -Idrivers/net/wireless/bcm4330_b1_b2_zte/shared \
						-Idrivers/net/wireless/bcm4330_b1_b2_zte/sys -Idrivers/net/wireless/bcm4330_b1_b2_zte/dongle -Idrivers/net/wireless/bcm4330_b1_b2_zte/wl/sys

DHDOFILES = dhd_linux.o linux_osl.o bcmutils.o dhd_common.o dhd_custom_gpio.o \
	wl_iw.o siutils.o sbutils.o aiutils.o hndpmu.o bcmwifi.o dhd_sdio.o   \
	dhd_linux_sched.o dhd_cdc.o bcmsdh_sdmmc.o bcmsdh.o bcmsdh_linux.o    \
	bcmsdh_sdmmc_linux.o bcmutils.o bcmevent.o dhd_bta.o

obj-$(CONFIG_BCM4330_ZTE) += dhd.o
dhd-objs += $(DHDOFILES)
EXTRA_CFLAGS = $(DHDCFLAGS) $(DHDIFLAGS)
EXTRA_LDFLAGS += --strip-debug


