# How-to-change-the-make-file-in-NS2

download goi ns-allinone-2.30.tar.gz, extract ra thu muc /home/ns2/ns-allinone-2.30



cai dat ns2 bang lenh ./install
============> muon cai ns2 all inone bang lenh install 
1/ chu y phai phan lai quyen cho cac file configure bang lenh ( chmod +x configure )  trong cac file tuong ung moi khi no bao loi
2/
============end=================


cd ns-2.30, ./configure
Copy de folder ns-2.30 cua thay Tien len folder trong ns-allinone-2.30
5. cd ns-2.30

	./configure 

-thay doi 6 dong:
Ln203:
	queue/queue.o queue/drop-tail.o queue/drop-all.o queue/videoqueue.o \

Ln257:
thay 	aodv/aodv_logs.o aodv/aodv.o \
	aodv/aodv_rtable.o aodv/aodv_rqueue.o \
boi:
	fiboro/aodv_logs.o fiboro/aodv.o \
	fiboro/aodv_rtable.o fiboro/aodv_rqueue.o \
	myevalvid/OLSR.o myevalvid/OLSR_state.o myevalvid/OLSR_rtable.o myevalvid/OLSR_printer.o \
	myevalvid/myudp.o myevalvid/myevalvid_sink.o myevalvid/myevalvid.o \
	fishingboat/gps_tp.o fishingboat/gps_app_sink.o fishingboat/gps_app_source.o \

//doi ten trong myevalvid/:  olsr.cc, olsr.h. olsr.o -> OLSR.cc, OLSR.h, OLSR.o

-	make
-	make install




	export PATH=$PATH:/home/ns-allinone-2.30/bin:/home/ns-allinone-2.30/tcl8.4.13/unix:/home/ns-allinone-2.30/tk8.4.13/unix
	export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/home/ns-allinone-2.30/otcl-1.12:/home/ns-allinone-2.30/lib 
	export TCL_LIBRARY=$TCL_LIBRARY:/home/ns-allinone-2.30/tcl8.4.13/library

-tien hanh add cac command tren chay luc khoi dong:
	cd /etc/
	gedit ~/.bash_profile

export PATH=$PATH:/home/ns-allinone-2.30/bin:/home/ns-allinone-2.30/tcl8.4.13/unix:/home/ns-allinone-2.30/tk8.4.13/unix
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/home/ns-allinone-2.30/otcl-1.12:/home/ns-allinone-2.30/lib 
export TCL_LIBRARY=$TCL_LIBRARY:/home/ns-allinone-2.30/tcl8.4.13/library

=====================================

Please put /home/ns-allinone-2.30/bin:/home/ns-allinone-2.30/tcl8.4.13/unix:/home/ns-allinone-2.30/tk8.4.13/unix
into your PATH environment; so that you'll be able to run itm/tclsh/wish/xgraph.

IMPORTANT NOTICES:

(1) You MUST put /home/ns-allinone-2.30/otcl-1.12, /home/ns-allinone-2.30/lib, 
    into your LD_LIBRARY_PATH environment variable.
    If it complains about X libraries, add path to your X libraries 
    into LD_LIBRARY_PATH.
    If you are using csh, you can set it like:
                setenv LD_LIBRARY_PATH <paths>
    If you are using sh, you can set it like:
                export LD_LIBRARY_PATH=<paths>

(2) You MUST put /home/ns-allinone-2.30/tcl8.4.13/library into your TCL_LIBRARY environmental
    variable. Otherwise ns/nam will complain during startup.
