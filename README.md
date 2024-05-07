# DEVELOPED BY : DHIRAVIYA S
# REGISTER NO: 212223040041
# Ex-8-RECOGNITION-OF-THE-GRAMMAR-anb-where-n-10-USING-YACC
RECOGNITION OF THE GRAMMAR(anb where n>=10) USING YACC
# Date:22.03.2024
# AIM
To write a YACC program to recognize the grammar anb where n>=10.
# ALGORITHM
1.	Start the program.
2.	Write a program in the vi editor and save it with .l extension.
3.	In the lex program, write the translation rules for the variables a and b.
4.	Write a program in the vi editor and save it with .y extension.
5.	Compile the lex program with lex compiler to produce output file as lex.yy.c. eg $ lex filename.l
6.	Compile the yacc program with yacc compiler to produce output file as y.tab.c. eg $ yacc –d arith_id.y
7.	Compile these with the C compiler as gcc lex.yy.c y.tab.c
8.	Enter a string as input and it is identified as valid or invalid.
# PROGRAM
Program name: anb.l
```
%{

/*Lex Program for anb(n>=10)*/ #include "y.tab.h"
%}

%%

a {return A;} b {return B;}
. {return yytext[10];}

\n return('\n');

%%

int yywrap()

{

return 1;

}
```
Program name:anb.y
```
%{

/*YACC program for recognising anb(n>=10)*/

%}

%token A B

%%

stmt: A A A A A A A A A A anb '\n'{printf("\n Valid string"); return 0;
}

;

anb:A anb

|A B

;

%%

main()

{

printf("\nEnter some valid string\n"); yyparse();
}

int yyerror(char*s)

{

printf("\nInvalid string\n");

}
```
# OUTPUT

![image](https://github.com/DHIRAVIYASUNDARAM/Ex-8-RECOGNITION-OF-THE-GRAMMAR-anb-where-n-10-USING-YACC/assets/165143880/6b82416b-0258-4b81-ba14-1fda803cbf9c)

# RESULT
The YACC program to recognize the grammar anb where n>=10 is executed successfully and the output is verified.
 

