# һ������   
[����](https://vscodethemes.com/)
## ��������
*б��*
_б��_
**����**
***��б��***
����
***
- - - 
~~ɾ��~~
<u>�»���</u>
[^��ע]������
- - -
- ��һ
- �ڶ�
* ��һ
* �ڶ�
- - -
1. ��һ
2. �ڶ�
- - - 
3. ��һ
   - Ƕ��
- - - 
> ����
> > Ƕ������
> > > ��Ƕ������
- - - 
> �������б�
> 1. ��һ
> 2. �ڶ�
- - -
- �б�������
  > ����
- - -
`���ø���`
```java
�����
```
- - -
[������](��ַ)
<https://www.runoob.com>
�߼����� 1 ��Ϊ���� [Runoob][1]

[1]: https://www.runoob.com
- - -
![Runoob ͼ��](http://static.runoob.com/images/runoob-logo.png)

Ҳ������ 2 ��Ϊ���� [Runoob][2].

[2]: http://static.runoob.com/images/runoob-logo.png

ָ���߶�����
<img src="http://static.runoob.com/images/runoob-logo.png" width="50%">
- - -
|��һ����ͷ|�ڶ�����ͷ|
| ---- |----|
|��Ԫ��|��Ԫ��|
- - -
|�����|�Ҷ���|���ж���|
|:---|--:|:--:|
|��Ԫ��|��Ԫ��|��Ԫ��|
- - -
<kbd>����</kbd>
\*\* ת�� \*\*
- - -
��ʽ
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
A[����] -->B(Բ��)
B -->C{����a}
C -->|a=1| D[���]
C -->|a=2| E[���]
F[��������ͼ]
```
```mermaid
graph TD
A[����] --> B(Բ��)
    B --> C{����a}
    C --> |a=1| D[���1]
    C --> |a=2| E[���2]
    F[��������ͼ]
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
    subgraph ��һ����
    a1-->a2
    end
    subgraph �ڶ�����
    b1
    end
    subgraph ��������
    c1-->c2
    end
    ��һ���� --> �ڶ�����
    �������� --> �ڶ�����
    �ڶ����� --> c2
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