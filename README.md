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
ajay
arya
sanjai
surya
^d

```
cat > file2
```
avi 
anjana
kaviya
swetha
^d

```
### Display the content of the files
cat < file1
## OUTPUT
~~~
ajay
arya
sanjai
surya
~~~


cat < file2
## OUTPUT


# Comparing Files
cmp file1 file2
## OUTPUT
 ~~~
avi 
anjana
kaviya
swetha
~~~
comm file1 file2
 ## OUTPUT

 
diff file1 file2
## OUTPUT
~~~
file1 file2 differ: byte 2, line 1
~~~
##output
~~~
ajay
arya
	avi
	anjana
	kaviya
sanjai
surya
	swetha
~~~

##OUTPUT
~~~
1,4c1,4
< ajay
< arya
< sanjai
< surya
---
> avi
> anjana
> kaviya
> swetha
~~~

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




cut -d "|" -f 1 file22
## OUTPUT
~~~
Hel
Thi
~~~


cut -d "|" -f 2 file22
## OUTPUT
~~~
1001 
1002 
1003
~~~

cat < newfile 
```
Hello world
hello world
^d
````
cat > newfile 
~~~
Hello world
hello world
 ~~~
grep Hello newfile 
## OUTPUT

<img width="140" height="50" alt="image" src="https://github.com/user-attachments/assets/3899502e-cef2-4af0-93fd-37298302dfcd" />


grep hello newfile 
## OUTPUT

<img width="136" height="25" alt="image" src="https://github.com/user-attachments/assets/1ee9d449-4b6a-4a8d-92b6-18180ce688c7" />



grep -v hello newfile 
## OUTPUT
~~~
Hello world
~~~


cat newfile | grep -i "hello"
## OUTPUT

<img width="136" height="25" alt="image" src="https://github.com/user-attachments/assets/a8d9373d-0b49-4e0b-b5a5-7bf50e5b85f5" />



cat newfile | grep -i -c "hello"
## OUTPUT
~~~
2
~~~


grep -R ubuntu /etc
## OUTPUT
<img width="1283" height="623" alt="image" src="https://github.com/user-attachments/assets/a4a7c851-ed90-4914-b1fc-eeeed956f3f7" />



grep -w -n world newfile   
## OUTPUT
<img width="161" height="43" alt="image" src="https://github.com/user-attachments/assets/d0eea93f-3976-43e8-84b3-1b371321de57" />


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

<img width="161" height="43" alt="image" src="https://github.com/user-attachments/assets/469872bb-60e9-4ff6-b9f6-264cc36a488c" />


egrep -w '(H|h)ello' newfile 
## OUTPUT
<img width="161" height="43" alt="image" src="https://github.com/user-attachments/assets/581d5f58-2649-48c1-b0db-548b7c3e9c1e" />



egrep -w '(H|h)ell[a-z]' newfile 
## OUTPUT

<img width="161" height="43" alt="image" src="https://github.com/user-attachments/assets/59a0f28e-cc35-4790-9e39-f13ec325a2a3" />



egrep '(^hello)' newfile 
## OUTPUT

<img width="161" height="28" alt="image" src="https://github.com/user-attachments/assets/f05e1b00-7d7e-4152-8b8e-d069d408ad1c" />


egrep '(world$)' newfile 
## OUTPUT

<img width="162" height="44" alt="image" src="https://github.com/user-attachments/assets/7c2caa6b-4ae7-46d3-8e7c-369585a960aa" />


egrep '(World$)' newfile 
## OUTPUT

<img width="162" height="44" alt="image" src="https://github.com/user-attachments/assets/a1dc86b2-47f1-4b39-b833-882f9cb87aac" />

egrep '((W|w)orld$)' newfile 
## OUTPUT

<img width="316" height="69" alt="image" src="https://github.com/user-attachments/assets/fb9e0440-8600-45f1-8c6c-b7ca976d8c1b" />


egrep '[1-9]' newfile 
## OUTPUT

<img width="317" height="28" alt="image" src="https://github.com/user-attachments/assets/ce7be1ee-c135-4986-a577-31094fde904e" />


egrep 'Linux.*world' newfile 
## OUTPUT

<img width="317" height="28" alt="image" src="https://github.com/user-attachments/assets/94932205-9388-4326-9330-d481f6ffa686" />

egrep 'Linux.*World' newfile 
## OUTPUT
<img width="317" height="28" alt="image" src="https://github.com/user-attachments/assets/8a2122b4-e18b-42f6-9665-ebd3d7b2e2c8" />


egrep l{2} newfile
## OUTPUT
<img width="378" height="92" alt="image" src="https://github.com/user-attachments/assets/567eafa9-3091-4c28-8192-62c71833707b" />



egrep 's{1,2}' newfile
## OUTPUT 


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
~~~
1001 | Ram | 10000 | HR
~~~


sed -n -e '$p' file23
## OUTPUT
~~~
1001 | Sita | 10000 | HR
1001 | Sita | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
1003 | Joe |  7000 | Developer
1001 | Sita | 10000 | HR
~~~


sed  -e 's/Ram/Sita/' file23
## OUTPUT

~~~
1001 | Ram | 10000 | HR
1001 | Sita | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
1003 | Joe |  7000 | Developer
1001 | Ram | 10000 | HR
~~~

sed  -e '2s/Ram/Sita/' file23
## OUTPUT
~~~
1001 | Ram | 10000 | HR
1001 | Sita | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
1003 | Joe |  7000 | Developer
1001 | Ram | 10000 | HR
~~~


sed  '/tom/s/5000/6000/' file23
## OUTPUT
~~~
1001 | Ram | 10000 | HR
1001 | Ram | 10000 | HR
1002 | tom |  6000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
1003 | Joe |  7000 | Developer
1001 | Ram | 10000 | HR
~~~


sed -n -e '1,5p' file23
## OUTPUT
~~~
1001 | Ram | 10000 | HR
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
~~~


sed -n -e '2,/Joe/p' file23
## OUTPUT
~~~
1001 | Ram | 10000 | HR
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
~~~



sed -n -e '/tom/,/Joe/p' file23
## OUTPUT
~~~
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
~~~


seq 10 
## OUTPUT
~~~
1
2
3
4
5
6
7
8
9
10
~~~


seq 10 | sed -n '4,6p'
## OUTPUT
~~~
4
5
6
~~~


seq 10 | sed -n '2,~4p'
## OUTPUT
~~~
2
3
4
~~~


seq 3 | sed '2a hello'
## OUTPUT
~~~
1
2
hello
3
~~~


seq 2 | sed '2i hello'
## OUTPUT
~~~
1
2
hello
3
~~~

seq 10 | sed '2,9c hello'
## OUTPUT
~~~
1
hello
2
~~~

sed -n '2,4{s/^/$/;p}' file23
## OUTPUT
~~~
1
hello
10
~~~


sed -n '2,4{s/$/*/;p}' file23

~~~
$1001 | Ram | 10000 | HR
$1001 | Ram | 10000 | HR
$1002 | tom |  5000 | Admin
~~~

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
~~~
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1004 | Sit |  7000 | Dev
1005 | Sam |  5000 | HR
~~~

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
~~~
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
~~~


#Using tr command

cat file23 | tr [:lower:] [:upper:]
 ## OUTPUT

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
~~~
www.yahoo.com
www.google.com
www.mrcet....com
~~~

 
cat urllist.txt | tr -d ' ' | tr -s '.'
## OUTPUT
~~~
www.yahoo.com
www.google.com
www.mrcet.com
~~~


#Backup commands
tar -cvf backup.tar *
## OUTPUT

<img width="946" height="1005" alt="image" src="https://github.com/user-attachments/assets/434c2f43-66c3-4073-b4de-622f6b8ab499" />

mkdir backupdir
 
mv backup.tar backupdir

cd backupdir
 
tar -tvf backup.tar
## OUTPUT
<img width="946" height="1005" alt="image" src="https://github.com/user-attachments/assets/6d6f5f3b-0d9b-43da-be7b-268a6ea036f2" />


tar -xvf backup.tar
## OUTPUT
<img width="946" height="1005" alt="image" src="https://github.com/user-attachments/assets/94684192-0a51-4794-803c-f80fb7f50344" />

gzip backup.tar

ls .gz

# Shell Script
```
echo '#!/bin/sh' > my-script.sh
echo 'echo Hello World‘; exit 0 >> my-script.sh
```
chmod 755 my-script.sh
./my-script.sh
## OUTPUT

 
cat << stop > herecheck.txt
```
hello in this world
i cant stop
for this non stop movement
stop
```

cat herecheck.txt
## OUTPUT
<img width="471" height="89" alt="image" src="https://github.com/user-attachments/assets/7717043f-9b3e-4f33-b93d-53107d3cc50f" />


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
<img width="650" height="418" alt="image" src="https://github.com/user-attachments/assets/3b61a9bb-fdf5-404d-a71d-55d87730bcc4" />

 
ls file1
## OUTPUT
~~~
file1
~~~
echo $?
## OUTPUT 
./one
bash: ./one: Permission denied
 
echo $?
## OUTPUT 
 ~~~
127
~~~
abcd
 
echo $?
 ## OUTPUT


 
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
##OUTPUT

<img width="646" height="250" alt="image" src="https://github.com/user-attachments/assets/ea7df5dd-77eb-439b-86ad-58fc4ee0db84" />


chmod 755 strcomp.sh
 
./strcomp.sh 
## OUTPUT


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
<img width="450" height="35" alt="image" src="https://github.com/user-attachments/assets/7991d9fc-9db8-4cac-95b4-1f35a817b838" />

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

./ifnested.sh 
## OUTPUT

<img width="449" height="69" alt="image" src="https://github.com/user-attachments/assets/93901fd5-6bd5-40dc-a79d-0e8f7fc9d6ae" />


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
##OUTPUT
<img width="448" height="40" alt="image" src="https://github.com/user-attachments/assets/a0e69e98-b94b-4159-ae11-6e3807403dcf" />

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
##OUTPUT
<img width="359" height="63" alt="image" src="https://github.com/user-attachments/assets/6ac9a537-d4fe-4857-ab4c-05bfad595368" />

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
<img width="459" height="45" alt="image" src="https://github.com/user-attachments/assets/37d5c8f7-5000-42d6-bec9-2e005491880c" />


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
<img width="301" height="35" alt="image" src="https://github.com/user-attachments/assets/5e0eae81-a598-4583-8a48-e3c56d228fb6" />

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
##OUTPUT
<img width="457" height="45" alt="544885663-4298bd19-dbac-42ab-bbdc-50732959c4e3" src="https://github.com/user-attachments/assets/3579bd84-f23f-4b01-9d17-e01cbde63393" />

 
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
##OUTPUT

 <img width="458" height="244" alt="544886644-c7d50257-b407-4c54-879a-e81860926d7a" src="https://github.com/user-attachments/assets/c5a1ff2e-7f4e-47b2-8254-d3c06787f78d" />

 
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
 
 ##OUTPUT
 <img width="554" height="141" alt="544887416-791a0897-e7f1-4114-8984-9a4897a9afa9" src="https://github.com/user-attachments/assets/db98b428-9048-4866-936c-280059a464ca" />

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
 ###OUTPUT
 <img width="629" height="198" alt="544888619-846aca77-c981-4b87-9918-428f202db6b1" src="https://github.com/user-attachments/assets/1aa63f9c-2f21-482b-a572-20dc0f3b0a99" />

 
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
 ##OUTPUT
 <img width="633" height="134" alt="544894641-409e7fe8-94ae-4ee2-8e0f-eae54ed0c8f0" src="https://github.com/user-attachments/assets/ffc6ea4c-f2d4-4c3b-83b6-87d5f2559f20" />

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
 
$ ./forin2.sh 
 ##OUTPUT
 <img width="633" height="134" alt="544895501-3226afca-47d8-4f6e-9101-f083d7470cf3" src="https://github.com/user-attachments/assets/11493965-d6e2-4cb4-a6d2-c35aebff078e" />

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
<img width="639" height="204" alt="544898433-86896796-56a8-4c68-bf96-3a59fe0b4de0" src="https://github.com/user-attachments/assets/989efbe3-ba53-42f6-ace6-763d6d9a61ed" />

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
<img width="637" height="161" alt="544905730-59324ddb-bafb-424f-bea8-f9c6238cbf29" src="https://github.com/user-attachments/assets/2c8d56e0-2332-48bd-a842-7737f4f7b6c0" />


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
## OUT<img width="636" height="178" alt="544908216-35ff652b-a692-4657-9d76-234d7d5d06b7" src="https://github.com/user-attachments/assets/c31e9185-a4a9-4e9e-b381-607b75a14279" />
PUT

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
<img width="626" height="138" alt="544909204-7f7c2fc1-fb12-417c-bccc-7cb83a46dad2" src="https://github.com/user-attachments/assets/c5829f3e-1ab0-45c8-bef4-28928d416d75" />

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
 ## OUTP
 <img width="626" height="138" alt="544909875-1076a656-e81c-4ce0-8ecf-06f0eabf0270" src="https://github.com/user-attachments/assets/e0a39a6a-4eac-4360-b78a-8ff76858edd6" />
UT

 
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
<img width="629" height="288" alt="544910645-0fb8dc58-0fff-450d-aac2-8c5e424d87c5" src="https://github.com/user-attachments/assets/6b4482c5-7924-4861-96d5-a025131bc26a" />

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
 <img width="656" height="78" alt="544912888-bab79c6c-e275-47ba-b486-1e8bc0773a2b" src="https://github.com/user-attachments/assets/7b17c27d-985e-4419-9348-90219aa23f63" />

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
<img width="457" height="45" alt="image" src="https://github.com/user-attachments/assets/49dc7428-b161-4743-a83a-9f7b2b6f3cdd" />


 cat exread1.sh
```bash
#!/bin/bash
# testing the read command
read -p "Enter your name: " name
echo "Hello $name, welcome to my program. “
``` 
$ chmod 755 exread1.sh 

## OUTPUT
<img width="653" height="70" alt="544914564-904a6359-f69a-4030-a0af-4a9404b1eae4" src="https://github.com/user-attachments/assets/7f054065-0985-48e3-a1b8-a65686c5f077" />



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
 ./funcex.sh 
<img width="653" height="49" alt="544915368-94684c33-174e-436f-9e15-de977e3002b5" src="https://github.com/user-attachments/assets/01b5d2d7-9921-433a-8ad4-cffaf412e6d0" />

 
 ./funcex.sh 1 2
<img width="653" height="49" alt="544915488-0543d9f8-24e6-4851-a0c9-1c5152b400fa" src="https://github.com/user-attachments/assets/db696a13-ed58-41a3-a743-366d571093d2" />

 
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
$ ./argshift.sh 1 2 3
 <img width="656" height="90" alt="544916451-006e3746-3597-4bba-9432-aa8611b3c63d" src="https://github.com/user-attachments/assets/d18886dd-6f78-40ea-8557-c436cefd1c4d" />

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
$ ./argshift.sh 1 2 3
 <img width="656" height="90" alt="544917167-b98ca80e-111b-47ae-bca4-6ee1e147dcaa" src="https://github.com/user-attachments/assets/66bf1bdd-7659-44dc-a357-4bede702189b" />

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
 ./argshift.sh 1 2 3
 <img width="656" height="330" alt="544917745-d130b65d-826e-48fe-a663-623f25ffe118" src="https://github.com/user-attachments/assets/2b601221-f206-431a-bb30-332498937739" />

 
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
 <img width="654" height="315" alt="544918614-b19c1410-1002-4743-b06f-165e0136bebd" src="https://github.com/user-attachments/assets/7f49cdef-8edd-416e-87a6-8e7e15d9423b" />

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
<img width="655" height="93" alt="544919910-25cd51b4-878f-43bc-b6b4-dc08e5ee0c57" src="https://github.com/user-attachments/assets/a93516cd-f186-46a3-88ca-a2e10991a73f" />


# RESULT:
The Commands are executed successfully.
