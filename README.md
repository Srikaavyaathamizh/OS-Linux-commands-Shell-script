# OS-Linux-commands-Shell-scripting
Operating systems Lab exercise
# Linux commands-Shell scripting
Linux commands-Shell scripting

# AIM:
To practice Linux Commands and Shell Scripting

# DESIGN STEPS:

### Step 1:

Navigate to any Linux environment installed on the system or installed inside a virtual environment like virtual box/vmware or online linux JSLinux (https://bellard.org/jslinux/vm.html?url=alpine-x86.cfg&mem=192) or docker.

### Step 2:

Execute the following commands

### Step 3:

Testing the commands for the desired output. 

# COMMANDS:
### Create the following files file1, file2 as follows:
cat > file1
```
chanchal singhvi
c.k. shukla
s.n. dasgupta
sumit chakrobarty
^d
```
cat > file2
```
anil aggarwal
barun sengupta
c.k. shukla
lalit chowdury
s.n. dasgupta
^d
```
### Display the content of the files
cat < file1
## OUTPUT
![cat file1](./img/catfile1.png)



cat < file2
## OUTPUT
![cat file2](./img/catfile2.png)


# Comparing Files
cmp file1 file2
## OUTPUT
![cmp](./imgs/cmp.png)
 
comm file1 file2
 ## OUTPUT
 ![comm](./imgs/comm.png)

 
diff file1 file2
## OUTPUT
![diff](./imgs/diff.png)


#Filters

### Create the following files file11, file22 as follows:

cat > file11
```
Hello world
This is my world
^d
```
cat > file22
```
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
^d
```


cut -c1-3 file11
## OUTPUT
![catfile](./imgs/file11.png)



cut -d "|" -f 1 file22
## OUTPUT
![catfile22](./imgs/fil22.png)


cut -d "|" -f 2 file22
## OUTPUT
![catfile](./imgs/file221.png)

cat < newfile 
```
Hello world
hello world
^d
```
cat > newfile 
Hello world
hello world
 
grep Hello newfile 

## OUTPUT

![catnewfile](./imgs/newfile.png)

grep hello newfile 
## OUTPUT
![catnewfile](./imgs/newfile1.png)



grep -v hello newfile 
## OUTPUT

![catfile4](./imgs/newfile2.png)

cat newfile | grep -i "hello"
## OUTPUT

![catfile5](./imgs/newfile3.png)


cat newfile | grep -i -c "hello"
## OUTPUT

![catfile3](./imgs/newfile4.png)


grep -R ubuntu /etc
## OUTPUT
![catfile2](./imgs/newfile5.png)


grep -w -n world newfile   
## OUTPUT
![catfile1](./imgs/newfile6.png)

cat < newfile 
```
Hello world
hello world
Linux is world number 1
Unix is predecessor
Linux is best in this World
^d
```

cat > newfile
```
Hello world
hello world
Linux is world number 1
Unix is predecessor
Linux is best in this World
^d
 ```
egrep -w 'Hello|hello' newfile 
## OUTPUT
![cat](./imgs/n.png)


egrep -w '(H|h)ello' newfile 
## OUTPUT
![cat1](./imgs/n1.png)


egrep -w '(H|h)ell[a-z]' newfile 
## OUTPUT
![cat2](./imgs/n2.png)



egrep '(^hello)' newfile 
## OUTPUT
![cat3](./imgs/n3.png)


egrep '(world$)' newfile 
## OUTPUT

![cat4](./imgs/n4.png)

egrep '(World$)' newfile 
## OUTPUT
![cat5](./imgs/n5.png)

egrep '((W|w)orld$)' newfile 
## OUTPUT

![cat7](./imgs/n6.png)

egrep '[1-9]' newfile 
## OUTPUT

![cat8](./imgs/n7.png)

egrep 'Linux.*world' newfile 
## OUTPUT
![cat9](./imgs/n8.png)

egrep 'Linux.*World' newfile 
## OUTPUT
![cat](./imgs/n9.png)

egrep l{2} newfile
## OUTPUT

![cat](./imgs/a1.png)

egrep 's{1,2}' newfile
## OUTPUT 
![cat0](./imgs/a2.png)

cat > file23
```
1001 | Ram | 10000 | HR
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
1003 | Joe |  7000 | Developer
1001 | Ram | 10000 | HR
^d
```


sed -n -e '3p' file23
## OUTPUT
![cat23](./imgs/a3.png)


sed -n -e '$p' file23
## OUTPUT
![cat24](./imgs/a4.png)


sed  -e 's/Ram/Sita/' file23
## OUTPUT

![cat25](./imgs/a5.png)

sed  -e '2s/Ram/Sita/' file23
## OUTPUT
![cat26](./imgs/a6.png)


sed  '/tom/s/5000/6000/' file23
## OUTPUT
![cat27](./imgs/a7.png)


sed -n -e '1,5p' file23
## OUTPUT

![cat](./imgs/b1.png)

sed -n -e '2,/Joe/p' file23
## OUTPUT
![cat](./imgs/b2.png)



sed -n -e '/tom/,/Joe/p' file23
## OUTPUT
![cat2](./imgs/b3.png)


seq 10 
## OUTPUT
![cat3](./imgs/b4.png)



seq 10 | sed -n '4,6p'
## OUTPUT
![cat4](./imgs/b5.png)


seq 10 | sed -n '2,~4p'
## OUTPUT
![cat](./imgs/b6.png)


seq 3 | sed '2a hello'
## OUTPUT

![cat1](./imgs/c1.png)

seq 2 | sed '2i hello'
## OUTPUT
![cat](./imgs/c2.png)

seq 10 | sed '2,9c hello'
## OUTPUT
![cat4](./imgs/c3.png)

sed -n '2,4{s/^/$/;p}' file23
## OUTPUT

![cat](./imgs/c4.png)

sed -n '2,4{s/$/*/;p}' file23
## Output
![cat](./imgs/c5.png)
#Sorting File content
cat > file21
```
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
``` 
sort file21
## OUTPUT
![cat](./imgs/c7.png)

cat > file22
```
1001 | Ram | 10000 | HR
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
``` 
uniq file22
## OUTPUT

![cat12](./imgs/c8.png)

#Using tr command

cat file23 | tr [:lower:] [:upper:]
 ## OUTPUT
![cat11](./imgs/c9.png)
cat < urllist.txt
```
www. yahoo. com
www. google. com
www. mrcet.... com
^d
 ```
cat > urllist.txt
```
www. yahoo. com
www. google. com
www. mrcet.... com
 ```
cat urllist.txt | tr -d ' '
 ## OUTPUT
![cate](./imgs/d1.png)

 
cat urllist.txt | tr -d ' ' | tr -s '.'
## OUTPUT
![cats](./imgs/d2.png)


#Backup commands
tar -cvf backup.tar *
## OUTPUT
![catse](./imgs/d3.png)

	mkdir backupdir
 
mv backup.tar backupdir
 
tar -tvf backup.tar
## OUTPUT
![image](https://github.com/user-attachments/assets/998f10e4-48c1-451d-a51c-38157f5f154a)


tar -xvf backup.tar
## OUTPUT
![image](https://github.com/user-attachments/assets/4f04dfd9-b2ca-4e8d-96ba-8329a5e209f5)


gzip backup.tar

ls .gz
## OUTPUT
![image](https://github.com/user-attachments/assets/4c78c297-88cc-4062-a9cd-4e22be960bad)

 
gunzip backup.tar.gz

 
# Shell Script
```
echo '#!/bin/sh' > my-script.sh
echo 'echo Hello World‘; exit 0 >> my-script.sh
```
chmod 755 my-script.sh
./my-script.sh
## OUTPUT
![image](https://github.com/user-attachments/assets/3f8f64d3-b62d-4e04-913d-8e9cc32d62db)


 
cat << stop > herecheck.txt
```
hello in this world
i cant stop
for this non stop movement
stop
```

cat herecheck.txt
## OUTPUT
![image](https://github.com/user-attachments/assets/75ff7434-f9ef-4b8f-b2d2-80a443d4e232)


cat < scriptest.sh 
```bash
\#!/bin/sh
echo “File name is $0 ”
echo "File name is " `basename $0`
echo “First arg. is ” $1
echo “Second arg. is ” $2
echo “Third arg. is ” $3
echo “Fourth arg. is ” $4
echo 'The $@ is ' $@
echo 'The $\# is ' $1#
echo 'The $$ is ' $$
ps
^d
 ```

cat scriptest.sh 
```bash
\#!/bin/sh
echo “File name is $0 ”
echo "File name is " `basename $0`
echo “First arg. is ” $1
echo “Second arg. is ” $2
echo “Third arg. is ” $3
echo “Fourth arg. is ” $4
echo 'The $@ is ' $@
echo 'The $\# is ' $\#
echo 'The $$ is ' $$
ps
```
 
chmod 777 scriptest.sh
 
./scriptest.sh 1 2 3

## OUTPUT
![image](https://github.com/user-attachments/assets/5718d594-4ec1-4648-a39c-67690dd00567)

 
ls file1
## OUTPUT
![image](https://github.com/user-attachments/assets/affd747d-5650-4646-bd10-6ed1f7710108)

echo $?
## OUTPUT 
![image](https://github.com/user-attachments/assets/27ff47c3-2875-4e67-8bac-983215f32d6b)

./one
bash: ./one: Permission denied
 
echo $?
## OUTPUT 
![image](https://github.com/user-attachments/assets/cf9065b7-fbcd-408d-ad8d-fb616be252cc)

 
abcd
 
echo $?
 ## OUTPUT

![image](https://github.com/user-attachments/assets/f139b97a-4b90-47bd-af8e-5bfc3a34ed48)

 
# mis-using string comparisons

cat < strcomp.sh 
```bash
\#!/bin/bash
val1=baseball
val2=hockey
if [ $val1 \> $val2 ]
then
echo "$val1 is greater than $val2"
else
echo "$val1 is less than $val2"
fi
^d
```

cat strcomp.sh 
```bash
\#!/bin/bash
val1=baseball
val2=hockey
if [ $val1 \> $val2 ]
then
echo "$val1 is greater than $val2"
else
echo "$val1 is less than $val2"
fi
```
## OUTPUT
![image](https://github.com/user-attachments/assets/82f45771-a052-4aad-a1e9-fb9a11d94447)



chmod 755 strcomp.sh
 
./strcomp.sh 
## OUTPUT
![image](https://github.com/user-attachments/assets/ad81df9c-ae61-4ec7-bd01-d912f53a1535)


# check file ownership
cat < psswdperm.sh 
```bash
\#!/bin/bash
if [ -O /etc/passwd ]
then
echo “You are the owner of the /etc/passwd file”
else
echo “Sorry, you are not the owner of the /etc/passwd file”
fi
^d
```

cat psswdperm.sh 
```bash
/#!/bin/bash
if [ -O /etc/passwd ]
then
echo “You are the owner of the /etc/passwd file”
else
echo “Sorry, you are not the owner of the /etc/passwd file”
fi
 ```
./psswdperm.sh
## OUTPUT
![image](https://github.com/user-attachments/assets/546b2fbb-5815-4def-a1c6-3257032f17fd)

# check if with file location
cat>ifnested.sh 
```bash
\#!/bin/bash
if [ -e $HOME ]
then
echo “$HOME The object exists, is it a file?”
if [ -f $HOME ]
then
echo “Yes,$HOME it is a file!”
else
echo “No,$HOME it is not a file!”
if [ -f $HOME/.bash_history ]
then
echo “But $HOME/.bash_history is a file!”
fi
fi
else
echo “Sorry, the object does not exist”
fi
^d
```
cat ifnested.sh 
```
\#!/bin/bash
if [ -e $HOME ]
then
echo “$HOME The object exists, is it a file?”
if [ -f $HOME ]
then
echo “Yes,$HOME it is a file!”
else
echo “No,$HOME it is not a file!”
if [ -f $HOME/.bash_history ]
then
echo “But $HOME/.bash_history is a file!”
fi
fi
else
echo “Sorry, the object does not exist”
fi
```



# using numeric test comparisons
cat > iftest.sh 
```bash
\#!/bin/bash
val1=10
val2=11
if [ $val1 -gt 5 ]
then
echo “The test value $val1 is greater than 5”
fi
if [ $val1 -eq $val2 ]
then
echo “The values are equal”
else
echo “The values are different”
fi
^d
```


cat iftest.sh 
```bash
\#!/bin/bash
val1=10
val2=11
if [ $val1 -gt 5 ]
then
echo “The test value $val1 is greater than 5”
fi
if [ $val1 -eq $val2 ]
then
echo “The values are equal”
else
echo “The values are different”
fi
```

$ chmod 755 iftest.sh
 
$ ./iftest.sh 
## OUTPUT
![image](https://github.com/user-attachments/assets/eed39845-c26d-4383-9a41-458a23c03c55)

# check if a file
cat > ifnested.sh 
```bash
\#!/bin/bash
if [ -e $HOME ]
then
echo “$HOME The object exists, is it a file?”
if [ -f $HOME ]
then
echo “Yes,$HOME it is a file!”
else
echo “No,$HOME it is not a file!”
if [ -f $HOME/.bash_history ]
then
echo “But $HOME/.bash_history is a file!”
fi
fi
else
echo “Sorry, the object does not exist”
fi
^d
```

cat ifnested.sh 
```bash
\#!/bin/bash
if [ -e $HOME ]
then
echo “$HOME The object exists, is it a file?”
if [ -f $HOME ]
then
echo “Yes,$HOME it is a file!”
else
echo “No,$HOME it is not a file!”
if [ -f $HOME/.bash_history ]
then
echo “But $HOME/.bash_history is a file!”
fi
fi
else
echo “Sorry, the object does not exist”
fi
```

$ chmod 755 ifnested.sh
 
$ ./ifnested.sh 
## OUTPUT
![image](https://github.com/user-attachments/assets/bcec3968-6d7e-4254-9835-4ac3adc01ccf)

# looking for a possible value using elif
cat elifcheck.sh 
```bash
\#!/bin/bash
if [ $USER = Ram ]
then
echo "Welcome $USER"
echo "Please enjoy your visit"
elif [ $USER = Rahim ]
then
echo "Welcome $USER"
echo "Please enjoy your visit"
elif [ $USER = Robert ]
then
echo "Special testing account"
elif [ $USER = gganesh ]
then
echo "$USER, Do not forget to logout when you're done"
else
echo "Sorry, you are not allowed here"
fi
```

$ chmod 755 elifcheck.sh
 
$ ./elifcheck.sh 
## OUTPUT
![image](https://github.com/user-attachments/assets/4c75f77c-12eb-40a0-beea-0b774b170bb6)


# testing compound comparisons
cat> ifcompound.sh 
```bash
\#!/bin/bash
if [ -d $HOME ] && [ -w $HOME ]
then
echo "The file exists and you can write to it"
else
echo "I cannot write to the file"
fi
```
$ chmod 755 ifcompound.sh
$ ./ifcompound.sh 
## OUTPUT
![image](https://github.com/user-attachments/assets/553fb669-109a-41b3-ad9d-fdf0f485a2b1)

# using the case command
cat >casecheck.sh 
```bash
case $USER in
Ram | Robert)
echo "Welcome, $USER"
echo "Please enjoy your visit";;
Rahim)
echo "Special testing account";;
gganesh)
echo "$USER, Do not forget to log off when you're done";;
*)
echo "Sorry, you are not allowed here";;
esac
```
$ chmod 755 casecheck.sh 
 
$ ./casecheck.sh 
![image](https://github.com/user-attachments/assets/ea145b3b-f2f9-4c92-8741-6440a8093121)

 
cat > whiletest
```bash
#!/bin/bash
#while command test
var1=10
while [ $var1 -gt 0 ]
do
echo $var1
var1=$[ $var1 - 1 ]
done
```
$ chmod 755 whiletest.sh
 
$ ./whiletest.sh
## output
![image](https://github.com/user-attachments/assets/f98ba547-361f-451e-b007-c29b26062b5f)

 
cat untiltest.sh 
```bash
\#using the until command
var1=100
until [ $var1 -eq 0 ]
do
echo $var1
var1=$[ $var1 - 25 ]
done
``` 
$ chmod 755 untiltest.sh
 
 ![image](https://github.com/user-attachments/assets/b5fcb56a-8af4-4396-949a-f5f134647cfd)

 
cat forin1.sh 
```bash
\#!/bin/bash
\#basic for command
for test in Alabama Alaska Arizona Arkansas California Colorado
do
echo The next state is $test
done
 ```
 
$ chmod 755 forin1.sh
 ![image](https://github.com/user-attachments/assets/83278ec9-12ce-43d8-9746-971897c7d0a8)

 
cat forin2.sh 
```bash
\#!/bin/bash
\# another example of how not to use the for command
for test in I don't know if this'll work
do
echo “word:$test”
done
 ```
 
$ chmod 755 forin2.sh
![image](https://github.com/user-attachments/assets/c644a916-39f5-453b-93b8-2f7f4f59b4cf)

 
cat forin2.sh 
```bash
\#!/bin/bash
\# another example of how not to use the for command
for test in I don't know if this'll work
do
echo “word:$test”
done
```
$ chmod 755 forin2.sh
 ![image](https://github.com/user-attachments/assets/e55f0a29-b3bf-432f-ae7e-9fd32de5f200)

$ ./forin2.sh 
 
cat forin3.sh 
```bash
\#!/bin/bash
\# another example of how not to use the for command
for test in I don\'t know if "this'll" work
do
echo "word:$test"
done
```
$ ./forin3.sh 
 
cat forin1.sh 
```bash
#!/bin/bash
# basic for command
for test in Alabama Alaska Arizona Arkansas California Colorado
do
echo The next state is $test
done
```
$ chmod 755 forin1.sh

## OUTPUT
![image](https://github.com/user-attachments/assets/56a43bdc-3b75-4c09-96b6-25925533e97c)

cat forinfile.sh 
```bash
#!/bin/bash
# reading values from a file
file="cities"
for state in `cat $file`
do
echo "Visit beautiful $file“
done
```
$ chmod 777 forinfile.sh

$ cat cities
Hyderabad
Alampur
Basara
Warangal
Adilabad
Bhadrachalam
Khammam

## OUTPUT
![image](https://github.com/user-attachments/assets/8ce5db94-ed36-4e6a-8cec-06a5e4908654)


cat forctype.sh 
```bash
#!/bin/bash
# testing the C-style for loop
for (( i=1; i <= 5; i++ ))
do
echo "The value of i is $i"
done
````
$ chmod 755 forctype.sh
$ ./forctype.sh 
## OUTPUT
![image](https://github.com/user-attachments/assets/8821be80-c09e-4b83-80c4-4fa2f52f0bda)


cat forctype1.sh 
```bash
#!/bin/bash
# multiple variables
for (( a=1, b=5; a <= 5; a++, b-- ))
do
echo "$a - $b"
done
```
$ chmod 755 forctype.sh
$ ./forctype1.sh 
## OUTPUT
![image](https://github.com/user-attachments/assets/ad08eee2-7676-47b3-8137-3c14e12b6d2a)

cat fornested1.sh 
```bash
#!/bin/bash
# nesting for loops
for (( a = 1; a <= 3; a++ ))
do
echo "Starting loop $a:"
for (( b = 1; b <= 3; b++ ))
do
echo " Inside loop: $b"
done
done
```
$ chmod 755 fornested1.sh
 
$ ./fornested1.sh 
 ## OUTPUT

 ![image](https://github.com/user-attachments/assets/0fef432f-8d70-49c3-a37d-dc97fcffb80b)

cat forbreak.sh 
```bash
#!/bin/bash
# breaking out of a for loop
for var1 in 1 2 3 4 5
do
if [ $var1 -eq 3 ]
then
break
fi
echo "Iteration number: $var1"
done
echo "The for loop is completed“
```
## OUTPUT
![image](https://github.com/user-attachments/assets/9472886d-037f-4adb-a26d-ab8c7028c719)


$ chmod 755 forbreak.sh
 
$ ./forbreak.sh 
 
cat forbreak.sh 
```bash
#!/bin/bash
# breaking out of a for loop
for var1 in 1 2 3 4 5
do
if [ $var1 -eq 3 ]
then
continue
fi
echo "Iteration number: $var1"
done
echo "The for loop is completed“
```

 
$ chmod 755 forcontinue.sh
 
$ ./forcontinue.sh 
## OUTPUT
![image](https://github.com/user-attachments/assets/74ec626b-e4e9-4982-b158-7c3e5c46ce74)

 
cat exread.sh 
```bash
#!/bin/bash
# testing the read command
echo -n "Enter your name: "
read name
echo "Hello $name, welcome to my program. "
 ```
 
$ chmod 755 exread.sh 
 
$ ./exread.sh 
## OUTPUT
![image](https://github.com/user-attachments/assets/cd131d14-4295-4fe5-9438-221894e2e703)


 cat exread1.sh
```bash
#!/bin/bash
# testing the read command
read -p "Enter your name: " name
echo "Hello $name, welcome to my program. “
``` 
$ chmod 755 exread1.sh 

## OUTPUT

![image](https://github.com/user-attachments/assets/f3b8d0c2-3820-4321-8581-6e5f581e50f1)


$ ./exread1.sh 
 
cat funcex.sh
```bash
#!/bin/bash
# trying to access script parameters inside a function
function func {
echo $[ $1 * $2 ]
}
if [ $# -eq 2 ]
then
value=`func $1 $2`
echo "The result is $value"
else
echo "Usage: badtest1 a b"
fi
```
## OUTPUT
![image](https://github.com/user-attachments/assets/3943d64f-0331-4e8c-98eb-494c6cd059c2)

 ./funcex.sh 

 
 ./funcex.sh 1 2

 
cat argshift.sh
```bash
#!/bin/bash 
 while (( "$#" )); do 
  echo $1 
  shift 
done
```
$ chmod 777 argshift.sh

## OUTPUT
![image](https://github.com/user-attachments/assets/1cd2af9b-fd3f-41bc-acfe-59cb5a27ff4a)

$ ./argshift.sh 1 2 3
 
 cat argshift1.sh
```bash
 #/bin/bash 
 # store arguments in a special array 
args=("$@") 
# get number of elements 
ELEMENTS=${#args[@]} 
 # echo each element in array  
# for loop 
for (( i=0;i<$ELEMENTS;i++)); do 
    echo ${args[${i}]} 
done
```
$ chmod 777 argshift.sh
## OUTPUT
![image](https://github.com/user-attachments/assets/2d324625-c1ab-48d3-9306-c8f702a08b76)

$ ./argshift.sh 1 2 3
 
cat argshift.sh
```bash
#!/bin/bash 
set -x 
while (( "$#" )); do 
  echo $1 
  shift 
done
set +x
```
## OUTPUT
![image](https://github.com/user-attachments/assets/610e7db8-c432-4c39-93d4-7641b2dd85d2)


 ./argshift.sh 1 2 3
 
 
cat > nc.awk
```bash
BEGIN{}
{
print len=length($0),"\t",$0 
wordcount+=NF
chrcnt+=len
}
END {
print "total characters",chrcnt 
print "Number of Lines are",NR
print "No of Words count:",wordcount
}
 ```
cat>data.dat
```bash
bcdfghj
abcdfghj
bcdfghj
ebcdfghj
bcdfghj
ibcdfghj
bcdfghj
obcdfghj
bcdfghj
ubcdfghj
```
awk -f nc.awk data.dat
## OUTPUT 
 ![image](https://github.com/user-attachments/assets/5ad3e36e-7651-43be-8746-95a2c65c81a5)

cat > palindrome.sh
```bash
#num=545
echo "Enter the number"
read num
s=0
rev=""
temp=$num
while [ $num -gt 0 ]
do
	# Get Remainder
	s=$(( $num % 10 ))
	# Get next digit
	num=$(( $num / 10 ))
	# Store previous number and
	# current digit in reverse
	rev=$( echo ${rev}${s} )
done
if [ $temp -eq $rev ];
then
	echo "Number is palindrome"
else
	echo "Number is NOT palindrome"
fi
```
## OUTPUT 

![image](https://github.com/user-attachments/assets/a8050af0-3fbc-45fa-b71d-443a25529df3)


# RESULT:
The Commands are executed successfully.
