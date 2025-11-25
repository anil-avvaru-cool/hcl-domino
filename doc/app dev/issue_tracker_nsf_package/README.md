Issue Tracker (Domino) - Import Package
=============================================

What this package contains:
- IssueForm.dxl            -> DXL representation of the IssueForm (paste/import via Designer DXL Import)
- AllIssuesView.dxl       -> DXL representation of the AllIssues view
- CreateIssueAgent.lss    -> LotusScript agent to create an issue
- IssuesJSONAgent.lss     -> LotusScript web agent returning JSON
- import_instructions.md  -> Step-by-step import instructions

Important:
- I cannot directly create a .nsf file in this environment. Domino .nsf requires Domino Designer or server APIs.
- The files here are intended to be imported into Domino Designer (File -> Application -> New or existing db, then File -> Export/Import -> DXL Import or create agents and paste code).
- After import, sign agents with an ID that has the required rights.

If you want, I can also generate a single DXL file containing the entire database (more complex).