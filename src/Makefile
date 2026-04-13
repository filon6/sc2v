LEX = flex
YACC = bison -y

CFLAGS = -std=gnu89 -m32 -fcommon \
-Wno-implicit-int \
-Wno-implicit-function-declaration \
-Wno-pointer-to-int-cast \
-Wno-int-to-pointer-cast

all: step1 step2 step3

step1:
	$(LEX) sc2v_step1.l
	$(YACC) -d sc2v_step1.y
	gcc $(CFLAGS) lex.yy.c y.tab.c sc2v_step1.c global_vars.c -Isrc -o ../bin/sc2v_step1 -lm

step2:
	$(LEX) sc2v_step2.l
	$(YACC) -d sc2v_step2.y
	gcc $(CFLAGS) lex.yy.c y.tab.c sc2v_step2.c global_vars.c -Isrc -o ../bin/sc2v_step2 -lm

step3:
	$(LEX) sc2v_step3.l
	$(YACC) -d sc2v_step3.y
	gcc $(CFLAGS) lex.yy.c y.tab.c global_vars.c -Isrc -o ../bin/sc2v_step3 -lm

clean:
	rm -f lex.yy.c y.tab.c y.tab.h
	rm -f *.o
	rm -f ../bin/sc2v_step1
	rm -f ../bin/sc2v_step2
	rm -f ../bin/sc2v_step3
