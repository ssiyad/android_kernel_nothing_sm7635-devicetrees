VOLCANO_BASE_DTB += ../qcom/volcano.dtb

# Frogger reuses Asteroids' qcom,board-id <11 0> and qcom,oem-id <1>, so the two
# overlays cannot coexist in one dtbo.img -- the bootloader would have no way to
# tell them apart. Nothing ships separate firmware per device and selects the
# device tree at build time; do the same here.
ifeq ($(CONFIG_NOTHING_IS_FROGGER),y)
NOTH_VOLCANO_BOARDS += \
	frogger-base-overlay.dtbo
else
NOTH_VOLCANO_BOARDS += \
	asteroids-base-overlay.dtbo \
	asteroids-pro-overlay.dtbo
endif

dtb-y += $(NOTH_VOLCANO_BOARDS) $(VOLCANO_BASE_DTB)

always-y	:= $(dtb-y)
subdir-y	:= $(dts-dirs)
clean-files	:= *.dtb *.dtbo
