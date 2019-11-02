# 视觉组代码规范  
<font size=5>**在代码文件中，不要出现任何中文字符！！！！！！！！**</font>  
<font size=5>**代码的所有变量名和注释必须使用英文描述，不能使用拼音和拼音缩写！！！！！**</font>  
<font size=5>**写代码的标准是能让刚接手项目的人很快看懂你的代码**</font>  
**多学点英语单词吧pong友，不会的单词自己查**   
**所有文件中的字符都要是ASCII字符表中有的**  

## 格式规范  
#### 对齐  
相同层次的代码必须对齐  

#### 缩进  
缩进使用Tab键而不是空格  
```Cpp
for(int i; i<UPPER_LIMIT; i++)
{
    cnt ++;
}
```
#### 大括号
大括号需要换行  
使用for、if、while等条件语句时，必须使用大括号，不管执行多少语句  
```Cpp
int main()
{
    for(int i; i<UPPER_LIMIT; i++)
    {
        cnt ++;
    }
    if(i < 1)
    {
        i++;
    }
    return 0;
}
```
#### 空格
逗号和分号必后加空格，运算符和变量之间也要用空格隔开  
```Cpp
int front, back;
sum = front + back;
div = (first+second) / content;
return end_time - start_time;

if(/*one condition*/ && /*another condition*/)
{
    ...
}

for(int i; i<UPPER_LIMIT; i++)
{
    cnt++;
}
```
*注：在多运算符表达式时，要根据具体情况省略空格达到突出运算先后等效果，如上第三式。*  
  
函数名和它后面的()之间不留空格  
if，while，for它后面的()之间不留空格  
#### 指针  
定义指针时，星号*紧跟变量而非类型  
使用指针时，*和&都要紧跟变量，不留空格  
```Cpp
char *p;
float *p_matrix;

x = *p;
p = &x;
x = r.y;
x = r->y;
```
#### 头文件定义  
定义头文件时在尖括号或者双引号之前加空格  
```Cpp
#include <iostream>
#include "miku.h"
```
#### 宏定义  
宏定义不管上下文缩进，一定顶格写  
宏定义#后不留空格  
```Cpp
int MakeDecision()
{
    if (lopsided_score) 
    {
#if DISASTER_PENDING      // Correct -- Starts at beginning of line
        DropEverything();
#if NOTIFY
        NotifyClient();
        while(flag)
        {
            CatchFlag(&flag);
#ifdef DEBUG
            WarnUsers();
#endif
        }
#endif
#endif
        BackToNormal();
    }
    return 0;
}
```
#### 函数定义  
函数定义紧追宏定义之后  
函数定义完后是main函数  
main函数之后才是其他函数  
函数内部定义变量之后空一行  
宏定义和函数定义之间空一行  
函数与函数之间空一行  
```Cpp
#include <iostream>

int Add(int first_num, int second_num);

int main()
{
    int apple, banana, cnt;
    
    cin >> apple >> banana;
    cnt = Add(apple, banana);
    cout << cnt;
    return 0;
}

int Add(int first_num, int second_num)
{
    return first_num + second_num;
}
```
*注：在定义头文件后和主函数之前，用空行隔开函数定义区，定义多个函数时，在主函数后用空行隔开各个函数主体*

#### 空行  
头文件include和宏定义的define用空行分隔开  
宏定义和全局变量、函数定义用空行分隔开  
同类定义之间不留空行  
函数与函数之间留空行  
```Cpp
#include <iostream>
#include <time.h>

#define UTC 8
#define ARRAY_LENTH 300

float array[ARRAY_LENTH] = {0.0};
char  message_buf[100];

int Add(int first_num, int second_num);
int Multiply(int first_num, int second_num);

int main()
{
    return 0;
}

int Add(int first_num, int second_num)
{
    ...
}

int Multiply(int first_num, int second_num)
{
    ...
}
```

## 注释规范  
#### 文件注释
在文件开头要写明以下详细信息：
```Cpp
/*
File name: robomaster
Author: Guoqian Ma
Version: V1.0
Date: 2019-10-31
Description: This file is about how to write the normalize code. The vision code must achieve these rules.

Modification: (not necessary)
    Modifier: Guoqian Ma
    Date: 2019-11-01
    Description: Record the changes you had made.
*/
```
#### 代码注释
当你写一段代码时，一定要有注释，注释可以在语句后，也可以在代码段落之前用多行描述，单行注释用空格隔开注释符和源代码，多行注释与上一段代码用空行隔开，与要注释的代码紧紧相连。  
示例：
```Cpp
#include <iostream>

int Add(int first_num, int second_num);

int main()
{
    int apple, banana, cnt;
    
    cin >> apple >> banana;
    cnt = Add(apple, banana);
    cout << cnt;
    return 0;
}

/*
This function sums up a and b.
*/
int Add(int first_num, int second_num) //This function sums up a and b
{
    return first_num + second_num;
}
```
## 命名规范
**命名遵循“自解释”的原则**  
变量要尽量使用完整的单词来描述变量的功能  
坚决杜绝胡乱使用诸如a，aa，aaa，ab之类无脑命名的行为  

*像for循环使用的临时变量i、j、k，计数用的n、cnt之类的例外*  
*不会起名了就用几个英语词简要描述一下功能*  

#### 文件命名  
文件命名统统小写，如有必要使用下划线或减号分隔开，推荐使用下划线
```Cpp
//files
my_useful_class.cc
my-useful-class.cc
myusefulclass.cc
myusefulclass_test.cc
```
#### 类、结构、函数命名  
类、结构、函数的名称中，每个单词首字母大写
```Cpp
//classes and structs
class UrlTable { ...
class UrlTableTester { ...
struct UrlTableProperties { ...

//typedefs
typedef hash_map<UrlTableProperties *, std::string> PropertiesMap;

//using aliases
using PropertiesMap = hash_map<UrlTableProperties *, std::string>;

//enums
enum UrlTableErrors { ...

//functions
AddTableEntry()
DeleteUrl()
OpenFileOrDie()
```
#### 变量命名  
普通变量全部小写  
const变量以小写字母k开头  
指针变量以小写字母p开头  
```Cpp
//variable names are lowercase with underscore.
std::string table_name;
int i, j, k;
int cnt;
float gradian;

//constant name start with lowercase 'k'
const int k_days_in_a_week = 7;
const int k_android8_0_0 = 24;

//pointer name  start with lowercase 'p'
int *p_table;
char *p_message_buf;
```
#### 宏定义命名  
宏定义中的变量全部大写，单词与单词之间下划线分隔  
```Cpp
//macro defines are all uppercase
#define ROUND(x) ...
#define PI_ROUNDED 3.0

#ifndef FOO_BAR_BAZ_H_
#define FOO_BAR_BAZ_H_
...
#endif  // FOO_BAR_BAZ_H_
```
