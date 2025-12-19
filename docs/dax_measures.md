# DAX Measures – Attendance Analysis

This document lists the DAX measures used in Power BI to calculate attendance metrics.
All measures operate on sanitized, aggregated datasets.

DAX Formulas in Power BI: 
#To count all Absence records:
Total Absences =
CALCULATE(
    COUNTROWS(complete_dataframe),
    complete_dataframe[IsAbsent] = 1
)

#Weighted absence rate:
Absence Rate =
DIVIDE(
    SUM(summary_dataframe[Absent_Days]),
    SUM(summary_dataframe[Total_Days])
)

Homeless children vs Non-homeless children Absence rates:
Absence Rate by Housing Status =
DIVIDE(
    SUM(summary_dataframe[Absent_Days]),
    SUM(summary_dataframe[Total_Days])
)

#Missing Absence reason (Data Entry error):
Missing Reason Absence Rate =
DIVIDE(
    [Absences with Missing Reason],
    [Total Absences]
)


#Transportation Issue:
Transportation Absence Rate =
DIVIDE(
    [Transportation Absences],
    [Total Absences]
)
