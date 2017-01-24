# HolidaysCalendar-Brazil
This is a library for retrieving the Brazilian Holidays' Calendar. 

You can use it as a Node.js module or in browser.

## Instalation

If you use NPM, then you can install it with ```npm install holidays-calendar-brazil```. Othewise, you can download the latest release and use it in your browser or in other Javascript-based projects.

## Usage

### Node.js
```javascript
var calendar = require("holidays-calendar-brazil");
console.log('The total number of holidays in 2020 is '+calendar.Year(2020).total);
```

### Browser
```html
<script src="../node_modules/holidays-calendar/dist/HolidaysCalendar.js"></script>
<script src="HolidaysCalendar-brazil.js" charset="utf-8"></script>
<script>
console.log('The total number of holidays in 2020 is '+HolidaysCalendar.Year(2020).total);
</script>
```

## API Reference

### Year(year)

Retrieves information about holidays in year.

**year**: integer, required. Year reference.

***return***: Mixed. *Object* with structure: ```{total: integer, months: array of integer}``` when there are holidays within that year; *False* when there are no holidays in the given year.

#### Example

```bash
 var calendar = require("holidays-calendar-brazil");
 var data = calendar.Year(2020);
 \\data equals { months: [ 1, 2, 4, 5, 6, 9, 10, 11, 12 ], total: 11 }
```

### Month(year, month)

Retrieves information about holidays in a specific month.

**year**: integer, required. Year reference.

**month**: integer, required. Month reference (January=1).

***return***: Mixed. *Object* with structure: ```{total: integer, days: array of integer}``` when there are holidays within that month; *False* when there are no holidays in the given month.

#### Example

```bash
 var calendar = require("holidays-calendar-brazil");
 var data = calendar.Month(2020, 2);
 \\data equals { days: [ 24, 25 ], total: 2 }
```

### Day(year, month, day)

Retrieves information about a holiday in a specific date.

**year**: integer, required. Year reference.

**month**: integer, required. Month reference (January=1).

**day**: integer, required. Day reference.

***return***: Mixed. *String* representing the holiday name if the given date corresponds to a holiday according to the calendar in use; *False* when the date isn't a holiday.

#### Example
```bash
 var calendar = require("holidays-calendar-brazil");
 var data = calendar.Day(2020, 2, 25);
 \\data equals 'Carnaval'
```
