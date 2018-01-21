#
# make all cui applications by gcc
#

BINDIR = /usr/local/bin
DIRS   = pos2kml str2str rnx2rtkp convbin rtkrcv

all:
	@make -C ../lib/iers/gcc
	@for i in $(DIRS); do make -C $$i/gcc; done

install:
	@echo installing...
	@for i in $(DIRS); do cp $$i/gcc/$$i $(BINDIR); done
	@cp rtkrcv/gcc/rtkshut.sh /usr/local/bin/
	@chmod +x /usr/local/bin/rtkshut.sh
	@cp rtkrcv/gcc/rtkstart.sh /usr/local/bin/
	@chmod +x /usr/local/bin/rtkstart.sh
	@mkdir -p /usr/local/share/rtklib
	@cp -r ../data /usr/local/share/rtklib/

clean:
	@echo cleaning up...
	@for i in $(DIRS); do make -C $$i/gcc clean; done

