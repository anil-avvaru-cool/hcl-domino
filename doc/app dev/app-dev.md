## App Development

### New Application
#### New Form
    - Problem and Answers
    - Alias: PA (Used to access from program with rename issues)
    - Our First Form
- Typical path: C:\ibm\notes\data\ProblemsAnswers.nsf
- Change fonts: File->Preferences->Basic Notes Client Configuration->Default fonts
- Create table: Rows=10, Columns=2, Fixed width=6", Table Type: basic

| Problem & Answers| | ||
|---|---|---|---|
| Category: | Category Field |Author: |Author Field|
| Status: | Status Field| Created: | Created Field|
| Priority: | Priority Field | Date Completed |CompletedDate Field |
| (Blank) |  | 
| Title: | Title Field| 
| Problem |  | 
| Problem Field   | 
| Answers: | | 

- Create->Field->Type text
- Design->Preview Notes
- Title: Table-> insert row
- Title: Table-> Merge cells
- Add column: Right click-> append-> Column
- Adjust width: Right click -> Adjust width
- Remove border: Right click-> Border->Change border zero

#### New view
- Name: By Title
- Alias: Title
- Title Column->Field->Title
- Add Column->Author Field->Author
- Add Column->Create Date Field->CreatedDate
- Add Column->Status Field->Status
- Formula for Author Field-> @Name([CN]@UserName)
- CreateDate field->Change type to Date/Time->Second tab->Select date and time
- CreateDate field->Default value->@Now
- CompleteDate field->Change type to calender control
- Status field-> Change type to radio button
    - Provide below choices and make "Active" default
    - Active
    - Waiting for more info
    - Completed
- Priority field-> Change type to radio button-> Add options 1,2,3

### New View
- Name: By Category 
- Alias-> LKUP_Category
- Add Category column and drag to first column
- Category column value-> Select Category

### Problem and Answers form
- Category field->Change to Dialogbox
    - Add below options, Allow values not in list
    - R&D
    - Sales
    - Operational
    - IT
- Category field-> Change to Enter choice on formula
- Alias-> LKUP_Category
 - @DbColumn("";"":"";"LKUP_Category";1)

- Objects->Window Title
    - @If(@IsNewDoc,"P&A New Document","P&A"+Title)




