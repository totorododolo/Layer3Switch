# Top-level Makefile for CLI Parser
# $Id: Makefile 132 2009-05-07 09:33:05Z henry $

# Copyright (c) 2008, Henry Kwok
# All rights reserved.
#
# Redistribution and use in source and binary forms, with or without
# modification, are permitted provided that the following conditions are met:
#     * Redistributions of source code must retain the above copyright
#       notice, this list of conditions and the following disclaimer.
#     * Redistributions in binary form must reproduce the above copyright
#       notice, this list of conditions and the following disclaimer in the
#       documentation and/or other materials provided with the distribution.
#     * Neither the name of the project nor the names of its contributors 
#       may be used to endorse or promote products derived from this software 
#       without specific prior written permission.
#
# THIS SOFTWARE IS PROVIDED BY HENRY KWOK ''AS IS'' AND ANY
# EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED
# WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE
# DISCLAIMED. IN NO EVENT SHALL HENRY KWOK BE LIABLE FOR ANY
# DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES
# (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES;
# LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND
# ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT
# (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS
# SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.

all:

MODULE_LIST = .

LIBRARY = libcparser.a

ifeq ("$(OUTDIR)", "")
OUTDIR = .
endif

DIR_LIST = $(patsubst %,%.PHONY,$(MODULE_LIST) $(BIN_LIST) $(LIB_LIST))

CLEAN_LIST = $(patsubst %,%.PHONY_CLEAN,$(MODULE_LIST))

$(DIR_LIST):
	@echo "MAKE $(basename $@)"
	$(MAKE) PLATFORM=$(PLATFORM) MODULE=$(basename $@) DEBUG="$(DEBUG)" LIBRARY=$(LIBRARY) -C $(basename $@)/src all

$(CLEAN_LIST):
	@echo "CLEAN $(basename $@)"
	$(MAKE) PLATFORM=$(PLATFORM) MODULE=$(basename $@) DEBUG="$(DEBUG)" LIBRARY=$(LIBRARY) -C $(basename $@)/src clean

bin: $(DIR_LIST)

all: bin $(TEST_LIST)

clean: $(CLEAN_LIST)
