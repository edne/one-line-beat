#!/bin/sh

FOLDER=/tmp/oneliner
CFILE=$FOLDER/file.c
COMPILED=$FOLDER/compiled
PIDFILE=$FOLDER/pid

if [ $1 = "--kill" ] || [ $1 = "-k" ]; then
	PID=`cat $PIDFILE 2> /dev/null`
	if [ $? = 0 ]; then
		kill $PID
		rm $PIDFILE
	fi
else
	mkdir $FOLDER 2> /dev/null
	
	echo "main(i){for(i=0;;i++)putchar($1);}" > $CFILE

	gcc $CFILE -o$COMPILED
	if [ $? = 0 ]; then
		chmod +x $COMPILED
		
		$0 --kill
		$COMPILED | aplay - 2> /dev/null &
		echo $! > $PIDFILE
	fi
fi
