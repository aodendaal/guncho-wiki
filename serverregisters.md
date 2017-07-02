# Server registers
Server registers are named channels that a realm can use to receive information from the server. Several registers are used internally; the ones documented below are meant for public use.

## Numeric registers
```
[ To read... ]
let val be server register "name";
```
* __timehm__: Gets the current time of day, as (Hour * 100) + Minute on a 24 hour clock. For example, if it's 2:15 PM on the server (US central time), this register contains the number 1415.
* __times__: Gets the seconds part of the current time of day, from 0 to 59.
* __datemd__: Gets the current date, as (Month * 100) + Day. For example, on November 24th, this register contains the number 1124.
* __datey__: Gets the current year.
* __datedow__: Gets the current day of the week, from 0 (Sunday) to 6 (Saturday).