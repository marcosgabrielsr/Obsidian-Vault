2025-10-13 14:43

Status #child

Tags: [[University Activities]] [[ Compilers ]]

# X++ Grammar

### This is a grammar that will be use in the Pratical Activity of the Compilers subject.

### Gramática da Linguagem X++ (com remoção à esquerda)
1. Program -> ClassList
2. Program -> $\epsilon$
3. ClassList -> ClassDecl ClassList
4. ClassList -> ClassDecl
5. ClassDecl -> **class ID** ClassBody
6. ClassDecl -> **class ID extends ID** ClassBody
7. ClassBody -> **{** VarDeclListOpt ConstructDeclListOpt MethodDeclListOpt **}**
8. VarDeclListOpt -> VarDeclList
9. VarDeclListOpt -> $\epsilon$
10. VarDeclList -> VarDecl VarDeclList'
11. VarDeclList' -> VarDecl VarDeclList'
12. VarDeclList' -> $\epsilon$
13. VarDecl -> Type **ID** VarDeclOpt ;
14. VarDecl -> Type **[] ID** VarDeclOpt ;
15. VarDeclOpt -> **, ID** VarDeclOpt
16. VarDeclOpt -> $\epsilon$
17. Type -> **int**
18. Type -> **string**
19. Type -> **ID**
20. ConstructDeclListOpt -> ConstructDeclList
21. ConstructDeclListOpt -> $\epsilon$
22. ConstructDeclList -> ConstructDecl ConstructDeclList'
23. ConstructDeclList' -> ConstructDecl ConstructDeclList'
24. ConstructDeclList' -> $\epsilon$
25. ConstructDecl -> **constructor** Method Body
26. MethodDeclListOpt -> MethodDeclList
27. MethodDeclListOpt -> $\epsilon$
28. MethodDeclList -> MethodDecl MethodDeclList'
29. MethodDeclList' -> MethodDecl MethodDeclList'
30. MethodDeclList' -> $\epsilon$
31. MethodDecl -> Type **ID** MethodBody
32. MethodDecl -> Type **[] id** MethodBody
33. MethodBody -> **(** ParamListOpt **)** **{** StatementsOpt **}**
34. ParamListOpt -> ParamList
35. ParamListOpt -> $\epsilon$
36. ParamList -> Param ParamList'
37. ParamList' -> , Param ParamList'
38. ParamList' -> $\epsilon$
39. Param -> Type **ID**
40. Param -> Type **[] ID**
41. StatementsOpt -> Statements
42. StatementsOpt -> $\epsilon$
43. Statements -> Statement Statements'
44. Statements' -> Statement Statements'
45. Statements' -> $\epsilon$
46. Statement -> VarDeclList
47. Statement -> AtribStat **;**
48. Statement -> PrintStat **;**
49. Statement -> ReadStat **;**
50. Statement -> ReturnStat **;**
51. Statement -> SuperStat **;**
52. Statement -> IfStat
53. Statement -> ForStat
54. Statement -> **break ;**
55. Statement -> **;**
56. AtribStat -> LValue = Expression
57. AtribStat -> LValue = AllocExpression
58. PrintStat -> **print** Expression
59. ReadStat -> **read** LValue
60. ReturnStat -> **return** Expression
61. SuperStat -> **super** **(** ArgListOpt **)** 
62. IfStat -> **if** **(** Expression **)** **{** Statements **}**
63. IfStat -> **if** **(** Expression **)** **{** Statements **}** **else {** Statements **}**
64. ForStat -> **for (** AtribStatOpt **;** ExpressionOpt **;** AtribStatOpt **)** **{** Statements **}**
65. AtribStatOpt -> AtribStat
66. AtribStatOpt -> $\epsilon$
67. ExpressionOpt -> Expression
68. ExpressionOpt -> $\epsilon$
69. LValue -> **ID** LValueComp
70. LValueComp -> **.ID** LValueComp
71. LValueComp -> **.ID** **\[** Expression **]** LValueComp
72. LValueComp -> **.ID** **(** ArgListOpt **)** LValueComp
73. LValueComp -> **\[** Expression **]** LValueComp
74. LValueComp -> $\epsilon$
75. Expression -> NumExpression
76. Expression -> NumExpression **RelOp** NumExpression
77. AllocExpression -> **new ID** **(** ArgListOpt **)**
78. AllocExpression -> Type **\[** Expression **]**
79. NumExpression -> Term **+** Term
80. NumExpression -> Term **-** Term
81. NumExpression -> Term
82. Term -> UnaryExpression  _*_  UnaryExpression
83. Term -> UnaryExpression  _/_  UnaryExpression
84. Term -> UnaryExpression _%_ UnaryExpression
85. Term -> UnaryExpression
86. UnaryExpression -> **+** Factor
87. UnaryExpression -> **-** Factor
88. Factor -> **INTEGER_LITERAL**
89. Factor -> **STRING_LITERAL**
90. Factor -> LValue
91. Factor -> **(** Expression **)**
92. ArgListOpt -> ArgList
93. ArgListOpt -> $\epsilon$
94. ArgList -> Expression ArgList'
95. ArgList' -> , Expression ArgList'
96. ArgList' -> $\epsilon$


# References

