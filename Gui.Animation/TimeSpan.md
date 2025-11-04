# TimeSpan Class

## namespace Noesis

Represents a time interval.

The interval is expressed in days, hours, minutes, seconds and milliseconds, or in ticks (100-nanosecond units). TimeSpan is generally used from XAML files, parsing with the following signature: [ws][-]{ d | [d.]hh:mm[:ss[.ff]] }[ws]

ws: optional white space  
-: optional minus sign indicating a negative TimeSpan  
d: days, ranging from 0 to 10675199  
hh: hours, ranging from 0 to 23  
mm: minutes, ranging from 0 to 59  
ss: optional seconds, ranging from 0 to 59  
ff: optional fractional seconds, consisting of 1 to 7 decimal digits  

"1" and "1.0:0" represents 1 day  
"0:1" represents 1 minute  
"0:0:1" represents 1 second  
"0:0:0.1" represents 1 millisecond  
"-0:0:3" represents 3 seconds negative  

## Inheritance Hierarchy

- TimeSpan

## Properties

| Property | Description |
|----------|-------------|
| Days | Get the days component of the time interval |
| Hours | Get the hours component of the time interval |
| Milliseconds | Get the milliseconds component of the time interval |
| Minutes | Get the minutes component of the time interval |
| Seconds | Get the seconds component of the time interval |
| Ticks | Get total TimeSpan value in Ticks |
| TotalDays | Get total TimeSpan value in days |
| TotalHours | Get total TimeSpan value in hours |
| TotalMilliseconds | Get total TimeSpan value in milliseconds |
| TotalMinutes | Get total TimeSpan value in minutes |
| TotalSeconds | Get total TimeSpan value in seconds |

## Attached Properties

TimeSpan has no attached properties

## Methods

| Method | Description |
|--------|-------------|
| GetTimeInSeconds() | Get total TimeSpan value in seconds |
| ToString() | Returns a string representation of the TimeSpan instance |
| TryParse(str, result) | Tries to parse a TimeSpan from a string |
| Zero() | Gets Zero Timespan |

## Events

TimeSpan has no events