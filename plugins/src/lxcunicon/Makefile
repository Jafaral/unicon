# Makefile example for a Unicon plugin
#
# Look for @Replace and change the line(s) that follow(s)  
#

# @Replace: What is the name of this library?
LNAME=lxcunicon

# @Replace: add any additionl (non-standard name) c source files here
COBJ = $(LNAME).o 
CSRC = $(LNAME).c

# @Replace: If additinal libraries need to be linked in append them here:
MYLIBS=$(LIBS) -llxc

# 
BASE=../../..

# lib relative to top
TDIR=../..

include ../Makedefs

default:	 $(LIBD)/$(LNAME).u

