# Useful Linux Commands

Get row and column number of a file
```
# delimeter is comma
awk -F',' ' { print NF }' emoji620vec-1.csv | uniq -c
# Output
731691 102
```

Replace One Char with another
```sed -i "s/\t/,/g" input_file # inplace
sed "s/\t/,/g" input_file.csv > output_file.csv # new file
sed "s/'//g" input_file.csv > output_file.csv # new file```

Insert a line at the beginning of a file 
```sed -i '1s/^/insert this\n/' file_name```
```sed -i '1s/^/1584755 621\n/' file_name```

Get rows that contains only 13 columns
```awk -F'\t' 'NF==13 {print}' infile  > newfile```

Remove first line of a file
```
# -i indicates inplace
sed -i '1d' file.txt```

Split a file
```
split -l 500 source.txt newfile # by line numbers
split -b 40k source.txt newFile # by file size
```

Copy specific column of a csv file
```
awk '{print $2}' 1.csv OR cut -d' ' -f2 1.csv
awk '{print $1,$2}' 1.csv
awk '{print $1,$2}' *.csv

```

Paste csv files side by side
```
paste {1..3}.csv # merge 1.csv, 2 .csv, 3.csv, default delimeter tab
paste -d' ' {1..3}.csv # merge 1.csv, 2 .csv, 3.csv seperated by space
paste -d' ' *.csv # merge all csv files side by side seperated by space
```
