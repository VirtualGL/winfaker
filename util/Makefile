include ../Makerules

##########################################################################
ifeq ($(platform), windows)
##########################################################################

TARGETS = $(LDIR)/rrutil.lib \
          $(LDIR)/fbx.lib \
          $(EDIR)/fbxtest.exe \
          $(EDIR)/threadtest.exe

OBJS = $(ODIR)/rrlog.obj \
       $(ODIR)/genericQ.obj \
       $(ODIR)/fbx.obj \
       $(ODIR)/fbxtest.obj \
       $(ODIR)/threadtest.obj

all: $(TARGETS)

clean:
	-$(RM) $(TARGETS) $(OBJS)

HDRS := $(wildcard ../include/*.h)
$(OBJS): $(HDRS)

$(LDIR)/rrutil.lib: $(ODIR)/rrlog.obj $(ODIR)/genericQ.obj
	$(AR) -OUT:$@ $^

$(EDIR)/fbxtest.exe: $(ODIR)/fbxtest.obj $(LDIR)/fbx.lib
	$(LINK) $(LDFLAGS) $< -out:$@ $(FBXLIB)

$(EDIR)/threadtest.exe :$(ODIR)/threadtest.obj
	$(LINK) $(LDFLAGS) $< -out:$@

##########################################################################
endif
##########################################################################
