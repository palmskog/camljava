include ../Makefile.config

JAVAFILES = Test.java Testcb.java
CLASSFILES = $(JAVAFILES:.java=.class)

all: jnitest $(CLASSFILES)
	CLASSPATH=../lib:. ./jnitest

jnitest: jnitest.ml
	ocamlc -ccopt -g -o jnitest -I ../lib jni.cma jnitest.ml

clean::
	rm -f jnitest

.SUFFIXES: .java .class

$(CLASSFILES):
	$(JAVAC) -classpath ../lib:. $(JAVAFILES)

clean::
	rm -f *.cm?
	rm -f *.class
