all: unittest

unittest: tmp/timetable.dat unittest1 unittest2 

unittest1:
	cd tmp ; ../../../testerrrr --depart -D 2014-01-01T00:01:00 --from-idx 0 --to-idx 1 -T timetable.dat -g ../gtfs-rt/3b.pb

unittest2:
	cd tmp ; ../../../testerrrr --depart -D 2014-01-01T00:11:00 --from-idx 0 --to-idx 1 -T timetable.dat -g ../gtfs-rt/3b.pb

tmp/gtfsdb: gtfs/*
	mkdir -p tmp
	../../gtfsdb.py gtfs tmp/gtfsdb

tmp/timetable.dat: tmp/gtfsdb
	cd tmp ; ../../../timetable.py gtfsdb

clean:
	rm -r tmp

