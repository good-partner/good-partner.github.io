---
layout: post
title:  "sprintf,fprintf,sscanf,fscanf,printf"
date:   2017-05-17 12:00:10 +0800
categories: php
tags: php
---

### sprintf — Return a formatted string

```php

<?php
$num = 5;
$location = 'tree';

$format = 'There are %d monkeys in the %s';
echo sprintf($format, $num, $location);

```

### fprintf — Write a formatted string to a stream

```php

<?php
if (!($fp = fopen('date.txt', 'w'))) {
    return;
}

fprintf($fp, "%04d-%02d-%02d", $year, $month, $day);
// will write the formatted ISO date to date.txt

```

### sscanf — Parses input from a string according to a format

```php

<?php
// getting the serial number
list($serial) = sscanf("SN/2350001", "SN/%d");
// and the date of manufacturing
$mandate = "January 01 2000";
list($month, $day, $year) = sscanf($mandate, "%s %d %d");
echo "Item $serial was manufactured on: $year-" . substr($month, 0, 3) . "-$day\n";

```

### fscanf — Parses input from a file according to a format

```php
<?php
$handle = fopen("users.txt", "r");
while ($userinfo = fscanf($handle, "%s\t%s\t%s\n")) {
    list ($name, $profession, $countrycode) = $userinfo;
    //... do something with the values
}
fclose($handle);

```

### printf — Output a formatted string

```php
<?php
printf ("(9.95 * 100) = %d \n", (9.95 * 100)); 

```
Result:

(9.95 * 100) = 994

