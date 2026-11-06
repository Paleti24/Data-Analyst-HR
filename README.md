AtliQ HR Analytics – Presence Insights

A Power BI report that analyses employee attendance at AtliQ using monthly attendance sheets from April–June 2022. It shows how often employees are present, working from home (WFH) or on sick leave (SL), and how those patterns change over time and by day of the week.

Repository contents
File	Description
HR-Analytics-Atliq.pbix	Power BI report (one page: Presence Insights)
Attendance-Sheet-2022-2023.xlsx	Source data: monthly attendance registers plus a legend sheet
Source data (Attendance-Sheet-2022-2023.xlsx)
Sheet	Contents
Apr 2022	Daily attendance register, one row per employee
May 2022	Same layout
June 2022	Same layout
Attendance Key	Legend of attendance codes

Each monthly sheet has:

Employee Code and Name
One column per calendar day, holding an attendance code (see below)
Summary columns per employee: TPD (Total Present Days), P, WFH, PL, SL, BL, FFL, BRL, LWP, WO, HO, ML

Each month has roughly 80 employee rows. Despite the "2022-2023" file name, the data covers April to June 2022 only.

Attendance codes
Code	Meaning	Code	Meaning
P	Present	LWP / HLWP	Leave without pay / half day
WFH / HWFH	Work from home / half day	BRL / HBRL	Bereavement leave / half day
PL / HPL	Paid leave / half day	ML / HML	Menstrual leave / half day
SL / HSL	Sick leave / half day	WO	Weekly off
FFL / HFFL	Floating festival leave / half day	HO	Holiday off
BL	Birthday leave		

Half-day codes count as 0.5 in the summary columns (for example, 3 full PL days plus 1 HPL gives a PL total of 3.5).

Power BI report (HR-Analytics-Atliq.pbix)

Page: Presence Insights

Visual	Purpose
KPI cards	Overall Attendance %, WFH % and SL %
Employee table	Attendance %, present days and WFH % per Employee ID
Area charts	Attendance %, WFH % and SL % over time (by month and by week number)
Day-of-week tables	Attendance %, SL % and WFH % by weekday
Matrix	Employee × date view of the attendance value
Slicers	Filter by date and by month (MMM YY)

Data model

A fact table named Final Data, with fields such as Employee ID, Date, Value (the attendance code), MMM YY, WeekNo and day of week. This is the daily attendance data in long (unpivoted) form.
A Measures table with Attendace % (spelled this way in the report), Present Days, WFH % and SL %.

The report uses a custom visual (wishyoulizationwalkers) and the AtliQ logo, both embedded in the file. It was created with Power BI Desktop (release 2022.08).

How to use
Install Power BI Desktop (Windows).
Open HR-Analytics-Atliq.pbix.
Use the date and month slicers to focus on a period, and click a bar or point to cross-filter the other visuals.
To refresh with new data, add the new month's sheet to the Excel file, then use Home > Transform data and Refresh. If the report's data source points to a different file path, update it under Data source settings.
Data notes
Some employee codes appear more than once in the same month, sometimes with different names (for example Atq -335). Check for duplicates before relying on per-employee figures.
Cells for dates that haven't happened yet (such as the last days of a partly filled month) are blank.
Weekly offs (WO) and holidays (HO) are not working days, so check how the percentage measures treat them before comparing them with external figures.
The employee names look like synthetic or sample data, so this project is best treated as a demo or portfolio project.
Suggested extensions
Add leave-type analysis (PL, FFL, BL, BRL, ML, LWP).
Add department or team breakdowns, if that data becomes available.
Add the remaining months to cover the full 2022–2023 year.
Add a drill-through page for individual employees.
