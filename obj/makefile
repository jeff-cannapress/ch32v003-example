################################################################################
# Automatically-generated file. Do not edit!
################################################################################

-include ../makefile.init

RM := rm -rf

# All of the sources participating in the build are defined here
-include sources.mk
-include User/subdir.mk
-include Startup/subdir.mk
-include Peripheral/src/subdir.mk
-include Debug/subdir.mk
-include Core/subdir.mk
-include subdir.mk
-include objects.mk

ifneq ($(MAKECMDGOALS),clean)
ifneq ($(strip $(ASM_UPPER_DEPS)),)
-include $(ASM_UPPER_DEPS)
endif
ifneq ($(strip $(ASM_DEPS)),)
-include $(ASM_DEPS)
endif
ifneq ($(strip $(S_DEPS)),)
-include $(S_DEPS)
endif
ifneq ($(strip $(S_UPPER_DEPS)),)
-include $(S_UPPER_DEPS)
endif
ifneq ($(strip $(C_DEPS)),)
-include $(C_DEPS)
endif
endif

-include ../makefile.defs

# Add inputs and outputs from these tool invocations to the build variables 
SECONDARY_FLASH += \
card-riscv.hex \

SECONDARY_LIST += \
card-riscv.lst \

SECONDARY_SIZE += \
card-riscv.siz \


# All Target
all: card-riscv.elf secondary-outputs

# Tool invocations
card-riscv.elf: $(OBJS) $(USER_OBJS)
	@	@	riscv-none-embed-gcc -march=rv32ecxw -mabi=ilp32e -msmall-data-limit=0 -msave-restore -Os -fmessage-length=0 -fsigned-char -ffunction-sections -fdata-sections -fno-common -Wunused -Wuninitialized  -g -T "C:\Users\jeffr\Documents\card-rv\card-riscv\Ld\Link.ld" -nostartfiles -Xlinker --gc-sections -Wl,-Map,"card-riscv.map" --specs=nano.specs --specs=nosys.specs -o "card-riscv.elf" $(OBJS) $(USER_OBJS) $(LIBS) -lprintf
	@	@
card-riscv.hex: card-riscv.elf
	@	riscv-none-embed-objcopy -O ihex "card-riscv.elf"  "card-riscv.hex"
	@	@
card-riscv.lst: card-riscv.elf
	@	riscv-none-embed-objdump --all-headers --demangle --disassemble -M xw "card-riscv.elf" > "card-riscv.lst"
	@	@
card-riscv.siz: card-riscv.elf
	@	riscv-none-embed-size --format=berkeley "card-riscv.elf"
	@	@
# Other Targets
clean:
	-$(RM) $(ASM_UPPER_DEPS)$(OBJS)$(SECONDARY_FLASH)$(SECONDARY_LIST)$(SECONDARY_SIZE)$(ASM_DEPS)$(S_DEPS)$(S_UPPER_DEPS)$(C_DEPS) card-riscv.elf
	-@
secondary-outputs: $(SECONDARY_FLASH) $(SECONDARY_LIST) $(SECONDARY_SIZE)

.PHONY: all clean dependents

-include ../makefile.targets
