# Read csv file


## Setup:
 ```composer require baolq2020/rdcsv:dev-master```

## Example:
### We have 2 way for using this library:
#### #You can use function for convert csv to array.
##### Full option
````php
$Iacsv = Iacsv::start('path file')
	->setRowStart(2) // This is option( Default 0 )
	->setIsUTF8(true) // This is option( Will be auto detect if you don't set )
	->setDelimiter(';') // This is option( Will be auto detect if you don't set )
	->all();
	
````

##### Short way with auto detect (slow performance)
````php
$Iacsv = Iacsv::start('path file')->all();
````
---
#### #You can loop csv file and get single row content for improve performance
````php
$Iacsv = new Iacsv($pathFile);
$Iacsv->setRowStart(11); // This is option( Default 0 )
$Iacsv->setIsUTF8(true); // This is option( Will be auto detect if you don't set )
$Iacsv->setDelimiter(';'); // This is option( Will be auto detect if you don't set )
$Iacsv->openSingleRow();
while ($Iacsv->checkIsNotEof()) {
	$singleRow = $Iacsv->getSingleRow(); // You can get your single row data here.
	print_r($singleRow);
}
````
