# 一级标题   
[主题](https://vscodethemes.com/)
## 二级标题
*斜体*
_斜体_
**粗体**
***粗斜体***
分行
***
- - - 
~~删除~~
<u>下划线</u>
[^脚注]：这样
- - -
- 第一
- 第二
* 第一
* 第二
- - -
1. 第一
2. 第二
- - - 
3. 第一
   - 嵌套
- - - 
> 区块
> > 嵌套区块
> > > 再嵌套区块
- - - 
> 区块中列表
> 1. 第一
> 2. 第二
- - -
- 列表中区块
  > 区块
- - -
`引用高亮`
```java
代码块
```
- - -
[链接名](地址)
<https://www.runoob.com>
高级链接 1 作为变量 [Runoob][1]

[1]: https://www.runoob.com
- - -
![Runoob 图标](http://static.runoob.com/images/runoob-logo.png)

也可以用 2 作为变量 [Runoob][2].

[2]: http://static.runoob.com/images/runoob-logo.png

指定高度与宽度
<img src="http://static.runoob.com/images/runoob-logo.png" width="50%">
- - -
|第一个表头|第二个表头|
| ---- |----|
|单元格|单元格|
- - -
|左对齐|右对齐|居中对齐|
|:---|--:|:--:|
|单元格|单元格|单元格|
- - -
<kbd>方框</kbd>
\*\* 转义 \*\*
- - -
公式
$f(x)=sin(x)+12$
$$\sum_{n=1}^{100} n$$
$\begin{matrix}
    a & b \\
    c & d
\end{matrix}$
$$\begin{matrix}
    a & b \\
    c & d
\end{matrix}$$
- - -
[mermaid](https://mermaid-js.github.io/mermaid/#/)

```mermaid
graph LR
A[方的] -->B(圆的)
B -->C{条件a}
C -->|a=1| D[结果]
C -->|a=2| E[结果]
F[横向流程图]
```
```mermaid
graph TD
A[方形] --> B(圆角)
    B --> C{条件a}
    C --> |a=1| D[结果1]
    C --> |a=2| E[结果2]
    F[竖向流程图]
```
> * TB - top to bottom
> * TD - top-down/ same as top to bottom
> * BT - bottom to top
> * RL - right to left
> * LR - left to right

[**flowcharts**](https://mermaid-js.github.io/mermaid/#/flowchart?id=special-characters-that-break-syntax)
```mermaid
flowchart TB
    c1-->a2
    subgraph 第一个框
    a1-->a2
    end
    subgraph 第二个框
    b1
    end
    subgraph 第三个框
    c1-->c2
    end
    第一个框 --> 第二个框
    第三个框 --> 第二个框
    第二个框 --> c2
```
[**Sepuence diagram**](https://mermaid-js.github.io/mermaid/#/sequenceDiagram?id=syntax)
```mermaid
sequenceDiagram
    participant Alice
    participant Bob
    Alice->>John: Hello John, how are you?
    loop Healthcheck
        John->>John: Fight against hypochondria
    end
    Note right of John: Rational thoughts <br/>prevail!
    John-->>Alice: Great!
    John->>Bob: How about you?
    Bob-->>John: Jolly good!
```
```mermaid
gantt
dateFormat  YYYY-MM-DD
title Adding GANTT diagram to mermaid
excludes weekdays 2014-01-10

section A section
Completed task            :done,    des1, 2014-01-06,2014-01-08
Active task               :active,  des2, 2014-01-09, 3d
Future task               :         des3, after des2, 5d
Future task2               :         des4, after des3, 5d
```
```mermaid
classDiagram
Class01 <|-- AveryLongClass : Cool
Class03 *-- Class04
Class05 o-- Class06
Class07 .. Class08
Class09 --> C2 : Where am i?
Class09 --* C3
Class09 --|> Class07
Class07 : equals()
Class07 : Object[] elementData
Class01 : size()
Class01 : int chimp
Class01 : int gorilla
Class08 <--> C2: Cool label
```
```mermaid
gitGraph:
options
{
    "nodeSpacing": 150,
    "nodeRadius": 10
}
end
commit
branch newbranch
checkout newbranch
commit
commit
checkout master
commit
commit
merge newbranch
```

```mermaid
erDiagram
    CUSTOMER ||--o{ ORDER : places
    ORDER ||--|{ LINE-ITEM : contains
    CUSTOMER }|..|{ DELIVERY-ADDRESS : uses

```
```mermaid
journey
    title My working day
    section Go to work
      Make tea: 5: Me
      Go upstairs: 3: Me
      Do work: 1: Me, Cat
    section Go home
      Go downstairs: 5: Me
      Sit down: 5: Me
```
```mermaid
pie showData
    title Key elements in Product X
    "Calcium" : 42.96
    "Potassium" : 50.05
    "Magnesium" : 10.01
    "Iron" :  5
```
test
test