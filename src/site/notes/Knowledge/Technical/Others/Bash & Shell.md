---
{"dg-publish":true,"permalink":"/knowledge/technical/others/bash-and-shell/","noteIcon":""}
---

## Variables
- TEST_VAR=xyz
- echo $TEST_VAR
## Positional arguments
- example.sh FIRST SECOND
	- $1 = FIRST
	- $2 = SECOND
- $#
	- Show the number of arguments
## Stand Input
```sh
read test
echo $test
```
## Output/Input redirection (Streams)
- >
	- redirect standard out to a file
	- same as `1>`
- >>
	- Append to a file 
- 2>
	- redirect only standard error
- &>
	- redirect both standard out and error
- <
	- Input file
	- wc -w hello.txt
- <<
	- Input EOF
	- cat << EOF
- <<<
	- Feed string into the command, string needs to be in the double quote
	- wc -w <<< "Hello There"
- |
	- (piping) redirect output to be input for the right command
	- echo Hello there | grep there 
## Test operators
```sh
[ hello = hello ]
echo $? # 0

[ 1 = 0 ]
echo $? # 1

[ 1 -eq 1]
echo $? # 0

[ -f ~/.zshrc]

[ -d ~/.kube]
```
## If/Elif/Else
```sh
if [ ${1,,} = first ]; then
	echo "FIRST"
elif [ ${1,,} = second ]; then
	echo "SECOND"
else
	echo "NONE"
fi

# use the command to check the command exists
if command -v $command; then
	echo $command exists
else
	echo $command does not exists
fi
```

> ${1,,} is parameter expansion, allowing to ignore UPPER and lowercase when comparing the string

- $ AND
- | OR
## Case statements
```sh
case ${1,,} in
	first | second)
		echo "FIRST or SECOND"
		;;
	three)
		echo "THREE"
		;;
	*)
		echo "NONE"
esac
```
## Arrays
```sh
NUMBER_LIST=(one two three four five)

echo $NUMBER_LIST # one
echo ${NUMBER_LIST[@]} # one two three four five
echo ${NUMBER_LIST[0]} # one
```
## For Loop
```sh
for item in ${NUMBER_LIST[@]}; do
	echo -n $item;
done

for number in 1 2 3 4 5; do
	echo $number
done

for number in {1..10}; do
	echo $number
done

for file in logfiles/*.log; do
	echo $file
done
```
## While Loop
```sh
myvar=1

while [ $myvar -le 10]
do
	echo $myvar
	myvar=$(( $myvar +1))
	sleep 0.5
done
```
## Functions
```sh
# Basic function
show_uptime() {
	up=$(uptime -p | cut -c4-)
	since=$(uptime -s)
	cat << EOF
-----
This machine has been up for ${up}
It has been running since ${since}
----
EOF
}
show_uptime

# Function with args and return value
show_name(){
	echo hello $1
	if [ ${1,,} = true ]; then
		return 0
	else
		return 1
	fi
}
show_name $1
if [ $? = 0 ]; then
	echo "TRUE"
fi
```
## Exit Code
- status
	- 0 - success
	- 1 - false 
- $?
	- latest exit code from the previous command
- exit {CODE}
	- exit the bash script with a specific exit code
## Math
```sh
expr 30 + 10 # 40
expr 30 \* 10 # 300
```
## Scheduling Jobs
## Command-line tools
### Read
```sh
read test
echo $testt
```
### At
```sh
at 15:30 -f ./script.sh

# List the jobs in the queue
atq

# Remove the job
atrm $ID
```
### Date
```sh
date # Sun Jun 30 14:49:57 +07 2024
```
### Crontab
```sh
# edit the crontab file
crontab -e

# 0 5 * * 1 <command>
```
### Test
- Same as the bracket in the if statement
```sh
test 10 -eq 10
```
### Cut
```SH
echo "123456789" | cut -c2,7 # 27
echo "123456789" | cut -c2-7 # 234567
echo "123456789" | cut -c5- # 56789
echo "123456789" | cut -c-4 # 1234
```
### AWK
- Use to filter file contents or the output of a command
```sh
awk '{print $1}' file.txt # one
awk '{print $2}' file.txt # two

# read from csv
awk -F, '{print $1}' file.csv
```
### SED
```sh
sed 's/one/two/g' file.txt # replace "one" to "two"
sed -i.ORIGINAL 's/one/two/g' file.txt # save "file.txt.ORIGINAL" before change
```
## References
- https://www.youtube.com/watch?v=tK9Oc6AEnR4