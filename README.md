# CSV Reader

CSV file reader

## Read CSV file with headers

Example file `test.csv`:

```csv
id;name;value
1;test1;value1
2;test2;value2
```

Read file (Example):

```php
<?

$resource = fopen('test.csv','r');
$csv = new csv_reader($resource, false, ';');

// Get headers array
$csv->getHeaders(); // []
$first_row = $csv->current();
echo $first_row[0]; echo "<br>" . "\n"; // Headers

$counter = 0;
foreach ($csv as $row) {
    $counter++;
    if ($counter == 1) {
        continue;
    }
    echo $row[0]; echo "<br>" . "\n";
}

```
