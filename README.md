# DAX_Functions
DAX for time intelligence and more




Last 7 days =
CALCULATE (
    SUM ( 'DataTable'[Sost] ),
    DATESINPERIOD ( 'Datetable'[date], LASTDATE ( 'Datetable'[date] ), -7, DAY )
)


Last 30 days =
CALCULATE (
    SUM ( 'DataTable'[Sost] ),
    DATESINPERIOD ( 'Datetable'[date], LASTDATE ( 'Datetable'[date] ), -30, DAY )
)


Cumulative Quantity =
CALCULATE (
    SUM ( Transactions[Quantity] ),
    FILTER (
        ALL ( 'Date'[Date] ),
        'Date'[Date] <= MAX ( 'Date'[Date] )
    )
)
