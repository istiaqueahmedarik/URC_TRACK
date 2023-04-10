##basic of bash

**echo**

```bash
echo "hello world"
```

this will print "hello world" on the screen

**variable**

```bash
var="hello world"
echo $var
```

this will print "hello world" on the screen, here we use $ to call the variable and bash is dynamic type language, so we don't need to declare the type of the variable.

**read**

```bash
read var
echo $var
```

this will read the input from the keyboard and print it on the screen

**condition**

```bash
if [ $var == "hello world" ]
then
    echo "hello world"
else
    echo "not hello world"
fi
```

here we use [ ] to judge the condition, and we use == to compare the variable and the string, and we use && to connect two conditions, and we use || to connect two conditions, and we use ! to reverse the condition and fi to end the condition.

**loop**

```bash
for i in {1..10}
do
    echo $i
done
```

this will print 1 to 10 on the screen

**function**

```bash
function hello()
{
    echo "hello world"
}
hello
```

this will print "hello world" on the screen

**array**

```bash
array=(1 2 3 4 5)
echo ${array[0]}
```

this will print 1 on the screen

**file**

```bash
touch test.txt
echo "hello world" > test.txt
cat test.txt
```

this will create a file named test.txt and write "hello world" in it and print "hello world" on the screen

**command**

```bash
ls
```

this will list all the files in the current directory

**command with parameter**

```bash
ls -l
```

this will list all the files in the current directory with detail information

**command with variable**

```bash
ls -l $var
```

this will list all the files in the directory named by the variable var

**command with array**

```bash
ls -l ${array[0]}
```

this will list all the files in the directory named by the first element of the array

**command with function**

```bash
ls -l `hello`
```

this will list all the files in the directory named by the return value of the function hello

**command with file**

```bash
ls -l < test.txt
```

this will list all the files in the directory named by the content of the file test.txt

**command with pipe**

```bash
ls -l | grep test
```

this will list all the files in the current directory and filter the files which contain the string "test"

\*\*command with redirection

```bash
ls -l > test.txt
```

this will list all the files in the current directory and write the result to the file test.txt

\*\*command with redirection and pipe

```bash
ls -l | grep test > test.txt
```

this will list all the files in the current directory and filter the files which contain the string "test" and write the result to the file test.txt

\*\*command with redirection and pipe and variable

```bash
ls -l | grep $var > test.txt
```

this will list all the files in the current directory and filter the files which contain the string named by the variable var and write the result to the file test.txt

\*\*command with redirection and pipe and array

```bash
ls -l | grep ${array[0]} > test.txt
```

this will list all the files in the current directory and filter the files which contain the string named by the first element of the array and write the result to the file test.txt

\*\*command with redirection and pipe and function

```bash
ls -l | grep `hello` > test.txt
```

this will list all the files in the current directory and filter the files which contain the string named by the return value of the function hello and write the result to the file test.txt

\*\*command with redirection and pipe and file

```bash
ls -l | grep < test.txt > test.txt
```

this will list all the files in the current directory and filter the files which contain the string named by the content of the file test.txt and write the result to the file test.txt
