# Let's-build-a-parser
Functional Programming project: Let's build a parser in Racket programming
Grammar:



program -> linelist $$ 
linelist -> line linelist | epsilon 
line -> idx stmt linetail* [EOL]
idx -> nonzero_digit digit* 
linetail -> :stmt | epsilon 
stmt -> id = expr | if expr then stmt | read id | write expr | goto idx | gosub idx | return
expr -> id etail | num etail | (expr)
etail -> + expr | - expr | = expr | epsilon
id -> [a-zA-Z]+
num -> numsign digit digit*
numsign -> + | - | epsilon 
nonzero_digit -> 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9
digit -> 0 | nonzero_digit 
