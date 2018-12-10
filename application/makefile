################################################################################
#by: androdrigue2
#version: 12/10/2018
################################################################################

RM := rm -rf
CC := gcc

# Name of the application ------------------------------------------------------------
APP_NAME = Test_GCC

#Path --------------------------------------------------------------------------------
SRC = src/
OBJ = obj/
BIN = bin/

#Source names ------------------------------------------------------------------------
MAIN = Test.c

#rebuild target ----------------------------------------------------------------------
rebuild: clean all

# All Target -------------------------------------------------------------------------
all: $(APP_NAME).o
Linux: $(APP_NAME).o $(APP_NAME).deb
Windows: $(APP_NAME).o $(APP_NAME).exe

# Tool invocations ------------------------------------------------------------------
$(APP_NAME).deb: $(OBJ)$(APP_NAME).o
	@echo ****Build****
	-$(CC) -o $(BIN)$(APP_NAME).deb $(OBJ)$(APP_NAME).o
	
$(APP_NAME).exe: $(OBJ)$(APP_NAME).o
	@echo ****Build****
	-$(CC) -o $(BIN)$(APP_NAME).exe $(OBJ)$(APP_NAME).o

$(APP_NAME).o: $(SRC)Test.c
	@echo ****Compile****
	-$(CC) -c $(SRC)$(MAIN) -o $(OBJ)$(APP_NAME).o
	
# Other Targets
clean:
	-$(RM) $(PCP_S)$(EXECUTABLES)$(OBJS)$(C_DEPS)$(CPCP_DEPS) $(BIN)$(APP_NAME).deb $(BIN)$(APP_NAME).exe
	-@echo **** Clean Complete ****

.PHONY: all clean dependents
.SECONDARY: