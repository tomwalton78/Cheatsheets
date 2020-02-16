1. **cut** - remove sections from each line of files
  - E.g. Show fourth field from space separated file: `cut -f4 -d' ' file_name`
  - E.g. Show 2nd to last fields in tsv file: `cut -f2- file_name` 
2. **head** - output the first part of files
  - E.g. Show first 20 lines from file: `head -n 20 file_name`
  - E.g. Show first 20 chars from file: `head -c 20 file_name`
3. **tail** - output the last part of files
	- E.g. Show last 20 lines from file: `tail -n 20 file_name`
	- E.g. Show lines 12 to 22 inclusive from file: `head -n 22 file_name | tail -n 11`
	- E.g. Show tail of file, as it is updated: `tail -f file_name`
4. **tr** - translate or delete characters
	- E.g. Replace () with []: `tr "(" "[" | tr ")" "]"`
	- E.g. Delete lowercase charts `tr -d [a-z]`
	- E.g. Replace sequences of multiple spaces with one space: `tr -s " "`
5. **sort** - sort lines of text files
	- E.g. Sort file in lexicographical order: `sort file_name`
	- E.g. Sort file numerically: `sort -n file_name`
	- E.g. Sort file in ascending order of 2nd column: `sort -t $'\t' -k 2 -n file_name.tsv`
6. **uniq** - report or omit repeated lines
	- E.g. Remove consecutive repetitions of a line: `uniq file_name`
	- E.g. Remove duplicate lines: `sort file_name | uniq`
	- E.g. Count no. of times each line repeats itself (consecutively): `uniq -c file_name`
	- E.g. Show lines without consecutive repetitions: `uniq -u`
7. **paste** - merge lines of files
	- E.g. Replace new lines with tabs: `paste -s -d "\t" file_name`
	- E.g. Fold 3 consecutive rows into one, separating with semicolon: `paste -sd ";;\n" file_name`
8. **grep** - print lines matching a pattern
	- E.g. Show lines containing words the, that, then or those, case insensitive: `grep -iEw "the|that|then|those" file_name`
	- E.g. Omit lines containing 'that' (case insensitive): `grep -iwv that file_name` 
	- E.g. Show credit card no.s with 2 or more conesecutive occurrences of same digit: `grep -E "([0-9])\s?\1{1}"`
9. **sed** - stream editor for filtering and transforming text
	- E.g. Transform first occurrence of 'the' with 'this' (case sensitive): `sed -e "s/\bthe\b/this/"`
	- E.g. Transform all occurrences of 'thy' with 'your' (case insensitive): `sed -e "s/\bthy\b/your/gI"`
	- E.g. Wrap all occurrences of 'thy' in curly braces: `sed -e "s/thy/{&}/gI"`
10. **awk** - pattern scanning and text processing language
	- E.g. Print 3rd and 4th words on each line, tab separated: `awk '{print $3 "\t" $4}' file_name`
	- E.g. Print lines with more than 18 chars: `awk 'length($0) > 18' file_name`
11. **find** - search for files in a directory hierarchy
	- E.g. Find files named core in or below the directory /tmp and delete them: `find /tmp -name core -type f -print | xargs /bin/rm -f`
12. **ps** - report a snapshot of the current processes
