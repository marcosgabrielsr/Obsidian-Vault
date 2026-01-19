Decl2025-10-19 11:28

Status: #teen 

Tags: [[University Activities]] [[Compilers]] [[X++ Grammar]]

# X++ First+ Set

1. First+(Program -> ClassList) = First(ClassList) = {**class**}
2. First+(Program -> $\epsilon$) = {$\epsilon$} U Follow(Program) = {$\epsilon$, **$**}
3. First+(ClassList -> ClassDecl ClassList) = First(ClassDecl) = {**class**}
4. First+(ClassList -> ClassDecl) = First(ClassDecl) = {**class**}
5. First+(ClassDecl -> **class ID** ClassBody) = {**class**}
6. First+(ClassDecl -> **class ID extends ID** ClassBody) = {**class**}
7. First+(ClassBody -> **{** VarDeclListOpt ConstructDeclListOpt MethodDeclListOpt **}**) = {**{**}
8. First+(VarDeclListOpt -> VarDeclList) = First(VarDeclList) = {**int**, **string**, **ID**}
9. First+(VarDeclListOpt -> $\epsilon$) = {$\epsilon$} U Follow(VarDeclListOpt) = {$\epsilon$, **constructor**, **int**, **string**, **ID**, **print**, **read**, **return**, **super**, **if**, **for**, **break**, **;**, **}**}
10. First+(VarDeclList -> VarDecl VarDeclList') = First(VarDecl) = {**int**, **string**, **ID**}
11. First+(VarDeclList' -> VarDecl VarDeclList') = First(VarDecl) = {**int**, **string**, **ID**}
12. First+(VarDeclList' -> $\epsilon$) = {$\epsilon$} U Follow(VarDeclList') = {$\epsilon$, **constructor**, **int**, **string**, **ID**, **print**, **read**, **return**, **super**, **if**, **for**, **break**, **;**, **}**}
13. First+(VarDecl -> Type **ID** VarDeclOpt ;) = First(Type) = {**int**, **string**, **ID**}
14. First+(VarDecl -> Type **[] ID** VarDeclOpt ;) = First(Type) = {**int**, **string**, **ID**}
15. First+(VarDeclOpt -> **, ID** VarDeclOpt) = {**,**}
16. First+(VarDeclOpt -> $\epsilon$) = {$\epsilon$} U Follow(VarDeclOpt) = {$\epsilon$, **;**}
17. First+(Type -> **int**) = {**int**}
18. First+(Type -> **string**) = {**string**}
19. First+(Type -> **ID**) = {**ID**}
20. First+(ConstructDeclListOpt -> ConstructDeclList) = First(ConstructDeclList) = {**constructor**}
21. First+(ConstructDeclListOpt -> $\epsilon$) = {$\epsilon$} U Follow(ConstructDeclListOpt) = {$\epsilon$, **int**, **string**, **ID**, **}**}
22. First+(ConstructDeclList -> ConstructDecl ConstructDeclList') = First(ConstructDecl) = {**constructor**}
23. First+(ConstructDeclList' -> ConstructDecl ConstructDeclList') = First(ConstructDecl) = {**constructor**}
24. First+(ConstructDeclList' -> $\epsilon$) = {$\epsilon$} U Follow(ConstructDeclList') = {$\epsilon$, **int**, **string**, **ID**, **}**}
25. First+(ConstructDecl -> **constructor** MethodBody) = {**constructor**}
26. First+(MethodDeclListOpt -> MethodDeclList) = First(MethodDeclList) = {**int**, **string**, **ID**}
27. First+(MethodDeclListOpt -> $\epsilon$) = {$\epsilon$} U Follow(MethodDeclListOpt) = {$\epsilon$, **}**}
28. First+(MethodDeclList -> MethodDecl MethodDeclList') = First(MethodDecl) = {**int**, **string**, **ID**}
29. First+(MethodDeclList' -> MethodDecl MethodDeclList') = First(MethodDecl) = {**int**, **string**, **ID**}
30. First+(MethodDeclList' -> $\epsilon$) = {$\epsilon$} U Follow(MethodDeclList') = {$\epsilon$, **}**}
31. First+(MethodDecl -> Type **ID** MethodBody) = First(Type) = {**int**, **string**, **ID**}
32. First+(MethodDecl -> Type **[] ID** MethodBody) = First(Type) = {**int**, **string**, **ID**}
33. First+(MethodBody -> **(** ParamListOpt **)** **{** StatementsOpt **}**) = {**(**}
34. First+(ParamListOpt -> ParamList) = First(ParamList) = {**int**, **string**, **ID**}
35. First+(ParamListOpt -> $\epsilon$) = {$\epsilon$} U Follow(ParamListOpt) = {$\epsilon$, **)**}
36. First+(ParamList -> Param ParamList') = First(Param) = {**int**, **string**, **ID**}
37. First+(ParamList' -> **,** Param ParamList') = {**,**}
38. First+(ParamList' -> $\epsilon$) = {$\epsilon$} U Follow(ParamList') = {$\epsilon$, **)**}
39. First+(Param -> Type **ID**) = First(Type) = {**int**, **string**, **ID**}
40. First+(Param -> Type **[] ID**) = First(Type) = {**int**, **string**, **ID**}
41. First+(StatementsOpt -> Statements) = First(Statements) =  {**int**, **string**, **ID**, **print**, **read**, **return**, **super**, **if**, **for**, **break**, **;**}
42. First+(StatementsOpt -> $\epsilon$) = {$\epsilon$} U Follow(StatementsOpt) = {$\epsilon$, **}**}
43. First+(Statements -> Statement Statements') = First(Statement) = {**int**, **string**, **ID**, **print**, **read**, **return**, **super**, **if**, **for**, **break**, **;**}
44. First+(Statements' -> Statement Statements') = First(Statement) = {**int**, **string**, **ID**, **print**, **read**, **return**, **super**, **if**, **for**, **break**, **;**}
45. First+(Statements' -> $\epsilon$) = {$\epsilon$} U Follow(Statements') = {$\epsilon$, **}**}
46. First+(Statement -> VarDeclList) = First(VarDeclList) = {**int**, **string**, **ID**}
47. First+(Statement -> AtribStat **;**) = First(AtribStat) = {**ID**}
48. First+(Statement -> PrintStat **;**) = First(PrintStat) = {**print**}
49. First+(Statement -> ReadStat **;**) = First(ReadStat) = {**read**}
50. First+(Statement -> ReturnStat **;**) = First(ReturnStat) = {**return**}
51. First+(Statement -> SuperStat **;**) = First(SuperStat) = {**super**}
52. First+(Statement -> IfStat) = First(IfStat) = {**if**}
53. First+(Statement -> ForStat) = First(ForStat) = {**for**}
54. First+(Statement -> **break ;**) = {**break**}
55. First+(Statement -> **;**) = {**;**}
56. First+(AtribStat -> LValue = Expression) = First(LValue) = {**ID**}
57. First+(AtribStat -> LValue = AllocExpression) = First(LValue) = {**ID**}
58. First+(PrintStat -> **print** Expression) = {**print**}
59. First+(ReadStat -> **read** LValue) = {**read**}
60. First+(ReturnStat -> **return** Expression) = {**return**}
61. First+(SuperStat -> **super** **(** ArgListOpt **)**) = {**super**}
62. First+(IfStat -> **if** **(** Expression **)** **{** Statements **}**) = {**if**}
63. First+(IfStat -> **if** **(** Expression **)** **{** Statements **}** **else {** Statements **}**) = {**if**}
64. First+(ForStat -> **for (** AtribStatOpt **;** ExpressionOpt **;** AtribStatOpt **)** **{** Statements **}**) = {**for**}
65. First+(AtribStatOpt -> AtribStat) = First(AtribStat) = {**ID**}
66. First+(AtribStatOpt -> $\epsilon$) = {$\epsilon$} U Follow(AtribStatOpt) = {$\epsilon$, **;**, **)**}
67. First+(ExpressionOpt -> Expression) = First(Expression) = {**+**, **-**}
68. First+(ExpressionOpt -> $\epsilon$) = {$\epsilon$} U Follow(ExpressionOpt) = {$\epsilon$, **;**}
69. First+(LValue -> **ID** LValueComp) = {**ID**}
70. First+(LValueComp -> **.ID** LValueComp) = {**.**}
71. First+(LValueComp -> **.ID \[** Expression **\]** LValueComp) = {**.**}
72. First+(LValueComp -> **.ID** **(** ArgListOpt **)** LValueComp) = {**.**}
73. First+(LValueComp -> **\[** Expression **\]** LValueComp) = { **\[** }
74. First+(LValueComp -> $\epsilon$) = {$\epsilon$} U Follow(LValueComp) = {$\epsilon$, **=**, _*_, **/**, **%**, **+**, **-**, **RelOp**, **;**, **)**, **]**, **,**}
75. First+(Expression -> NumExpression) = First(NumExpression) = {**+**, **-**}
76. First+(Expression -> NumExpression **RelOp** NumExpression) = First(NumExpression) = {**+**, **-**}
77. First+(AllocExpression -> **new ID** **(** ArgListOpt **)**) = {**new**}
78. First+(AllocExpression -> Type **\[** Expression **\]**) = First(Type) = {**int**, **string**, **ID**}
79. First+(NumExpression -> Term **+** Term) = First(Term) = {**+**, **-**}
80. First+(NumExpression -> Term **-** Term) = First(Term) = {**+**, **-**}
81. First+(NumExpression -> Term) = First(Term) = {**+**, **-**}
82. First+(Term -> UnaryExpression  _*_  UnaryExpression) = First(UnaryExpression) = {**+**, **-**}
83. First+(Term -> UnaryExpression  _/_  UnaryExpression) = First(UnaryExpression) = {**+**, **-**}
84. First+(Term -> UnaryExpression _%_ UnaryExpression) = First(UnaryExpression) = {**+**, **-**}
85. First+(Term -> UnaryExpression) = First(UnaryExpression) = {**+**, **-**}
86. First+(UnaryExpression -> **+** Factor) = {**+**}
87. First+(UnaryExpression -> **-** Factor) = {**-**}
88. First+(Factor -> **INTEGER_LITERAL**) = {**INTEGER_LITERAL**}
89. First+(Factor -> **STRING_LITERAL**) =  {**STRING_LITERAL**}
90. First+(Factor -> LValue) = First(LValue) = {**ID**}
91. First+(Factor -> **(** Expression **)**) = {**(**}
92. First+(ArgListOpt -> ArgList) = First(ArgList) = {**+**, **-**}
93. First+(ArgListOpt -> $\epsilon$) = {$\epsilon$} U Follow(ArgListOpt) = {$\epsilon$, **)**}
94. First+(ArgList -> Expression ArgList') = First(Expression) = {**+**, **-**}
95. First+(ArgList' -> **,** Expression ArgList') = {**,**}
96. First+(ArgList' -> $\epsilon$) = {$\epsilon$} U Follow(ArgList') = {$\epsilon$, **)**}
# References

