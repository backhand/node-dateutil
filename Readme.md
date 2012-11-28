Date formatting library (PHP style)
=========================

Usage:
------

var dateformat = require('dateformatter').format;

```
dateformat('Y-m-d H:i:s', 1355319420000);
> 2012-12-12 13:37:00 (If your timezone is GMT)
```  

Installation:
------------------------
npm install dateformatter

Formats:
--------
Should support most PHP date formats, see: http://php.net/manual/en/function.date.php