2025-10-15 10:25

Status: #teen 

Tags: [[University Activities]] [[Compilers]] [[X++ Grammar]]

# X++ First Set
**OBS**: The string **\[** corresponding to the left square bracket

First(Program) = First(ClassList) U {$\epsilon$} = {**class**, $\epsilon$}
First(ClassList) = First(ClassDecl) = {**class**}
First(ClassDecl) = {**class**}
First(ClassBody) = {**{**}
First(VarDeclListOpt) = First(VarDeclList) U {$\epsilon$} = {**int**, **string**, **ID**, $\epsilon$}
First(VarDeclList) = First(VarDecl) = {**int**, **string**, **ID**}
First(VarDeclList') = First(VarDecl) U {$\epsilon$} = {**int**, **string**, **ID**, $\epsilon$}
First(VarDecl) = First(Type) = {**int**, **string**, **ID**}
First(VarDeclOpt) = {**,**, $\epsilon$}
First(Type) = {**int**, **string**, **ID**}
First(ConstructDeclListOpt) = First(ConstructDeclList) U {$\epsilon$} = {**constructor**, $\epsilon$}
First(ConstructDeclList) = First(ConstructDecl) = {**constructor**}
First(ConstructDeclList') = First(ConstructDecl) U {$\epsilon$} = {**constructor**, $\epsilon$}
First(ConstructDecl) = {**constructor**}
First(MethodDeclListOpt) = First(MethodDeclList) U {$\epsilon$} = {**int**, **string**, **ID**, $\epsilon$}
First(MethodDeclList) = First(MethodDecl) = {**int**, **string**, **ID**}
First(MethodDeclList') = First(MethodDecl) U {$\epsilon$} = {**int**, **string**, **ID**, $\epsilon$}
First(MethodDecl) = First(Type) = {**int**, **string**, **ID**}
First(MethodBody) = {**(**}
First(ParamListOpt) = First(ParamList) U {$\epsilon$} = {**int**, **string**, **ID**, $\epsilon$}
First(ParamList) = First(Param) = {**int**, **string**, **ID**}
First(ParamList') = {**,**, $\epsilon$}
First(Param) = First(Type) = {**int**, **string**, **ID**}
First(StatementsOpt) = First(Statements) U {$\epsilon$}
First(Statements) = First(Statement) = {**int**, **string**, **ID**, **print**, **read**, **return**, **super**, **if**, **for**, **break**, **;**}
First(Statements') = First(Statement) U {$\epsilon$} = {**int**, **string**, **ID**, **print**, **read**, **return**, **super**, **if**, **for**, **break**, **;**, $\epsilon$}
First(Statement)= First(VarDeclList) U First(AtribStat) U First(PrintStat) U First(ReadStat) U First(ReturnStat) U First(SuperStat) U First(IfStat) U First(ForStat) U {**break**, **;**} = {**int**, **string**, **ID**, **print**, **read**, **return**, **super**, **if**, **for**, **break**, **;**}
First(AtribStat) = First(LValue) = {**ID**}
First(PrintStat) = {**print**}
First(ReadStat) = {**read**}
First(ReturnStat) = {**return**}
First(SuperStat) = {**super**}
First(IfStat) = {**if**}
First(ForStat) = {**for**}
First(AtribStatOpt) = First(AtribStat) U {$\epsilon$} = {**ID**, $\epsilon$}
First(ExpressionOpt) = First(Expression) U {$\epsilon$} = {**+**, **-**, $\epsilon$}
First(LValue) = {**ID**}
First(LValueComp) = {**.**, **\[**, $\epsilon$}
First(Expression) = First(NumExpression) = {**+**, **-**}
First(AllocExpression) = {**new**} U First(Type) = {**new**, **int**, **string**, **ID**}
First(NumExpression) = First(Term) = {**+**, **-**}
First(Term) = First(UnaryExpression) = {**+**, **-**}
First(UnaryExpression) = {**+**, **-**}
First(Factor) = {**INTEGER_LITERAL**, **STRING_LITERAL**} U First(LValue) U {**(**} = {**INTEGER_LITERAL**, **STRING_LITERAL**, **ID**, **(**}
First(ArgListOpt) = First(ArgList) U {$\epsilon$} = {**+**, **-**, $\epsilon$}
First(ArgList) = First(Expression) = {**+**, **-**}
First(ArgList') = {**,**, $\epsilon$}

# References

