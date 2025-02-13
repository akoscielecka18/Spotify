#### Create a Calendar table 

````dax
Calendar = 
VAR Days = CALENDAR ( ( MIN(spotify_history[ts])), max(spotify_history[ts]))
RETURN ADDCOLUMNS (
    Days,
    "Year", YEAR ( [Date] ),
    "Month Number", MONTH ( [Date] ),
    "Month", FORMAT ( [Date], "mmmm" ),
    "Year Month Number", YEAR ( [Date] ) * 12 + MONTH ( [Date] ) - 1,
    "Year Month", FORMAT ( [Date], "mmm yy" ),
    "Week Number", WEEKNUM ( [Date] ),
     "Day of Month", DAY ( [Date] ), 
    "Day of Week Number", WEEKDAY( [Date], 2 ), 
    "Day of Week", FORMAT ( [Date], "dddd" )
)
````


