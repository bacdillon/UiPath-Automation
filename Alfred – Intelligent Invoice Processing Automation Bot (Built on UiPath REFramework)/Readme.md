## Alfred – Intelligent Invoice Processing Automation Bot (Built on UiPath REFramework)
Alfred is an intelligent, attended automation bot built on UiPath REFramework (Robotic Enterprise Framework), designed to optimize end-to-end invoice processing with high reliability, modularity, and exception handling.
Watch Alfred in action 👇
[![Alfred in action](https://github.com/bacdillon/RPA-UiPath/raw/main/Alfred%20%E2%80%93%20Intelligent%20Invoice%20Processing%20Automation/img/alfred_action.png)](https://vimeo.com/1081363310?share=copy#t=0)

![alt_text](https://github.com/bacdillon/UiPath-Automation/blob/main/Alfred%20%E2%80%93%20Intelligent%20Invoice%20Processing%20Automation%20Bot%20(Built%20on%20UiPath%20REFramework)/img/Screen1.png)

**Process Flow Description**
1. REFramework Initiation -
Initializes configuration settings, opens required apps, and closes unnecessary ones. On error, exception handling ends the process.

2. Email Processing -
Monitoring incoming email with the subject "Invoice Entry Request for Processing - [Today’s Date]". Downloads attachments to Files\Invoice. Skips if no email or on failure.

3. Intelligent Document Processing -
Loads invoices, digitizes using OCR, classifies using Keyword Classifier, extracts data via ML Extractor. Sends to Validation Station if needed. Exports to Datasets_Extraction and readable format in Export folder.

4. Consolidate Export Invoice -
Reading exported files, creates headers, appends data into SummaryReport.xlsx in Summary folder. Deletes temporary formatted sheets.

5. REFramework Get Transaction Data -
Uses DataRow (not QueueItem) for transaction items. Retrieves rows from DataTable after app initialization.

6. REFramework Process Transaction -
Validates data. If Invoice No. or Bill To is missing, triggers Business Rule Exception and sends email notification. Enters data in CRM. Ends if no data remains.

7. REFramework Set Transaction Status -
Sets each transaction’s status (Success, Business, or System Exception). Logs status in Summary Report before moving to next item.

8. REFramework End Process -
Closes applications, moves SummaryReport.xlsx to archive with today's date, formats report, archives all files, and emails final report to relevant stakeholders.

![alt_text](https://github.com/bacdillon/RPA-UiPath/blob/main/Alfred%20%E2%80%93%20Intelligent%20Invoice%20Processing%20Automation/img/summary.jpg)




