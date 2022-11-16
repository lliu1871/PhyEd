---
layout: markdown
title: Shell script tutorial
permalink: /code/shell
author: "Liang Liu"
output: html_document
date: 2021-04-16
---

## Shell script tutorial

A shell script is a series of [bash commands](https://ss64.com/bash/) that can be executed by shell. A nice tutorial for shell scripting is available at [the shell tutorial](https://www.tutorialspoint.com/unix/shell_scripting.htm) and [Bash scripting cheatsheet](https://devhints.io/bash).

#### The first shell script "Hello World" using *echo*.
```shell
#!/bin/sh
echo "Hello World"
```

#### Read input from screen
```shell
#!/bin/sh
echo "What is your name?"
read NAME
echo "Hello, $NAME"
```

#### Read parameters from command lines: ./script.sh 3 alpha
```shell
#!/bin/sh
echo $1 $2
echo $@
```

#### Array variables. All shell variables should be capitalized
```shell
#!/bin/sh
NAME[0]="Zara"
NAME[1]="Qadir"
NAME[2]="Mahnaz"
NAME[3]="Ayan"
NAME[4]="Daisy"
echo "names: ${NAME[*]}"
for I in ${NAME[*]}
do
        echo $I
done
```

#### Math expression using \`expr\`
```shell
#!/bin/sh
val=`expr 2 + 2`
echo "Total value : $val"
```

#### Flow: make a decision if, elif, else

```shell
#!/bin/sh
NAME[0]="Zara"
NAME[1]="Qadir"
NAME[2]="Mahnaz"
NAME[3]="Ayan"
NAME[4]="Daisy"
echo "names: ${NAME[*]}"

for I in ${NAME[*]}
do
        echo $I
        if [ $I == "Ayan" ] 
        then
            break
        fi
done
```

#### Loop: for, until, while
```shell
#!/bin/sh
a=0
while [ $a -lt 10 ]
do
   echo $a
   if [ $a -eq 5 ]
   then
      break
   fi
   a=`expr $a + 1`
done
```

#### Define a function
```shell
#!/bin/sh
Hello () {
   echo "Hello World $1 $2"
}
Hello Zara Ali
```


