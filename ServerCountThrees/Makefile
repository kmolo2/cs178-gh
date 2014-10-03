# target ... : prerequisites ...0
# 	recipe
# 	...

SRCDIR = src
TESTDIR = test
PWD = `pwd`
	
objects = ServerCountThrees.o readInt32BitLE.o

ServerCountThrees : $(objects)
	cc -o ServerCountThrees $(objects)

ServerCountThrees.o : $(SRCDIR)/ServerCountThrees.c $(SRCDIR)/readInt32BitLE.h
	cc -c $(SRCDIR)/ServerCountThrees.c
readInt32BitLE.o : $(SRCDIR)/readInt32BitLE.c $(SRCDIR)/readInt32BitLE.h
	cc -c $(SRCDIR)/readInt32BitLE.c

	
test :
	mkdir $(TESTDIR)
	mv ServerCountThrees $(TESTDIR)
	cp -p $(SRCDIR)/threesData.bin $(TESTDIR)
	cd $(TESTDIR) && ./ServerCountThrees 
	cd $(PWD)

clean :
	rm $(objects)
	rm -rf $(TESTDIR)
	rm ServerCountThrees