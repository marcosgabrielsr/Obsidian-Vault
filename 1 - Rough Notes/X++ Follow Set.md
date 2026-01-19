2025-10-19 09:30

Status: #teen 

Tags: [[University Activities]] [[Compilers]] [[X++ Grammar]]
# X++ Follow Set

Follow(Program) = {**$**}
Follow(ClassList) = Follow(Program) = {**$**}
Follow(ClassDecl) = First(ClassList) U Follow(ClassList) = {**class**, **$**}
Follow(ClassBody) = Follow(ClassDecl) = {**class**, **$**}
Follow(VarDeclListOpt) = First(ConstructDeclListOpt) - {$\epsilon$} U First(MethodDeclListOpt) - {$\epsilon$} U {**}**} = {**constructor**, **int**, **string**, **ID**, **}**}
Follow(VarDeclList) = Follow(VarDeclListOpt) U Follow(Statement) = {**constructor**, **int**, **string**, **ID**, **int**, **string**, **ID**, **print**, **read**, **return**, **super**, **if**, **for**, **break**, **;**, **}**}
Follow(VarDeclList') = Follow(VarDeclList) = {**constructor**, **int**, **string**, **ID**, **int**, **string**, **ID**, **print**, **read**, **return**, **super**, **if**, **for**, **break**, **;**, **}**}
Follow(VarDecl) = First(VarDeclList') - {$\epsilon$} U Follow(VarDeclList) U Follow(VarDeclList') = {**constructor**, **int**, **string**, **ID**, **int**, **string**, **ID**, **print**, **read**, **return**, **super**, **if**, **for**, **break**, **;**, **}**}
Follow(VarDeclOpt) = {**;**}
Follow(Type) = {**ID**, **\[** }
Follow(ConstructDeclListOpt) = First(MethodDeclListOpt) - {$\epsilon$} U {**}**} = {**int**, **string**, **ID**, **}**}
Follow(ConstructDeclList) = Follow(ConstructDeclListOpt)  = {**int**, **string**, **ID**, **}**}
Follow(ConstructDeclList') = Follow(ConstructDeclList) = {**int**, **string**, **ID**, **}**}
Follow(ConstructDecl) = First(ConstructDeclList') - {$\epsilon$} U Follow(ConstructDeclList) U Follow(ConstructDeclList') = {**constructor**, **int**, **string**, **ID**, **}**}
Follow(MethodDeclListOpt) = {**}**}
Follow(MethodDeclList) = Follow(MethodDeclListOpt) = {**}**}
Follow(MethodDeclList') = Follow(MethodDeclListOpt) = {**}**}
Follow(MethodDecl) = First(MethodDeclList') - {$\epsilon$} U Follow(MethodDeclList) U Follow(MethodDeclList') = {**int**, **string**, **ID**, **}**}
Follow(MethodBody) = Follow(MethodDecl) = {**int**, **string**, **ID**, **}**} 
Follow(ParamListOpt) = {**)**}
Follow(ParamList) = Follow(ParamListOpt) = {**)**}
Follow(ParamList') = Follow(ParamList) = {**)**}
Follow(Param) = First(ParamList') - {$\epsilon$} U Follow(ParamList) U Follow(ParamList') = {**,**, **)**}
Follow(StatementsOpt) = {**}**}
Follow(Statements) = Follow(StatementsOpt) = {**}**}
Follow(Statements') = Follow(Statements) = {**}**}
Follow(Statement) = First(Statements') - {$\epsilon$} U Follow(Statements) U  Follow(Statements') = {**int**, **string**, **ID**, **print**, **read**, **return**, **super**, **if**, **for**, **break**, **;**, **}**}
Follow(AtribStat) = {**;**} U Follow(AtribStatOpt) = {**;**, **)**}
Follow(PrintStat) = {**;**}
Follow(ReadStat) = {**;**}
Follow(ReturnStat) = {**;**}
Follow(IfStat) = Follow(Statement) = {**int**, **string**, **ID**, **print**, **read**, **return**, **super**, **if**, **for**, **break**, **;**, **}**}
Follow(ForStat) = Follow(Statement) = {**int**, **string**, **ID**, **print**, **read**, **return**, **super**, **if**, **for**, **break**, **;**, **}**}
Follow(AtribStatOpt) = {**;**, **)**}
Follow(ExpressionOpt) = {**;**}
Follow(LValue) = {**=**} U Follow(ReadStat) U Follow(Factor) = {**=**, _*_, **/**, **%**, **+**, **-**, **RelOp**, **;**, **)**, **]**, **,**}
Follow(LValueComp) = Follow(LValue) = {**=**, _*_, **/**, **%**, **+**, **-**, **RelOp**, **;**, **)**, **]**, **,**}
Follow(Expression) = Follow(AtribStat) U Follow(PrintStat) U Follow(ReturnStat) U {**)**} U Follow(ExpressionOpt) U {**]**} U {**)**} U First(ArgList')  -  {$\epsilon$}  U Follow(ArgList) U Follow(ArgList') = {**;**, **)**, **]**, **,**}
Follow(AllocExpression) = Follow(AtribStat) = {**;**, **)**}
Follow(NumExpression) = {**RelOp**} U Follow(Expression) = {**RelOp**, **;**, **)**, **]**, **,**}
Follow(Term) = {**+**, **-**} U Follow(NumExpression) = {**+**, **-**, **RelOp**, **;**, **)**, **]**, **,**}
Follow(UnaryExpression) = {_*_, **/**, **%**} U Follow(Term) = {_*_, **/**, **%**, **+**, **-**, **RelOp**, **;**, **)**, **]**, **,**}
Follow(Factor) = Follow(UnaryExpression) = {_*_, **/**, **%**, **+**, **-**, **RelOp**, **;**, **)**, **]**, **,**}
Follow(ArgListOpt) = {**)**}
Follow(ArgList) = Follow(ArgListOpt) = {**)**}
Follow(ArgList') = Follow(ArgList) = {**)**}

# References

