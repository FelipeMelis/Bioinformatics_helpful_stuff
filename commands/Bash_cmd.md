## Bash

**Create screen**
```
screen -S screen_name
```
**Enter the screen**
```
screen -r screen_name
```
**Convert _fastq_ to _fasta_**
```
sed -n '1~4s/^@/>/p;2~4p' file.fastq > file.fasta
```
**Rename files from different folders**
```
ls | while read line ; do cp ./${line}/file.fl ./${line} ; done
```
**Find files**
```
find / -name "file.txt"
```
**Find zero bytes files and erase them from the face of the earth!**
```
find . -type f -size 0 | while read line; do rm ${line} ; done
```
**Double loop**
```
for i in *.txt ; do cat file.txt  while read line ; do echo $i $line; done ; done
```

**List of the elements in file_1 but not in file_2**
```
comm -23 <(sort file_1) <(sort file_2)
```
**List of the elements in file_2 but not in file_1**
```
comm -13 <(sort file_1) <(sort file_2)
```
**Count number of forward reads from a folder**
```
ls *R1* |while read line ; do awk '{s++}END{print s/4}' ${line}; done
```
