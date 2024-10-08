## Задание 1

Код:

```
pip3 show matplotlib
```
Вывод:

```
Name: matplotlib
Version: 3.9.2
Summary: Python plotting package
Home-page: 
Author: John D. Hunter, Michael Droettboom
Author-email: Unknown <matplotlib-users@python.org>
License: License agreement for matplotlib versions 1.3.0 and later
=========================================================

1. This LICENSE AGREEMENT is between the Matplotlib Development Team
("MDT"), and the Individual or Organization ("Licensee") accessing and
otherwise using matplotlib software in source or binary form and its
associated documentation.

2. Subject to the terms and conditions of this License Agreement, MDT
hereby grants Licensee a nonexclusive, royalty-free, world-wide license
to reproduce, analyze, test, perform and/or display publicly, prepare
derivative works, distribute, and otherwise use matplotlib
alone or in any derivative version, provided, however, that MDT's
License Agreement and MDT's notice of copyright, i.e., "Copyright (c)
2012- Matplotlib Development Team; All Rights Reserved" are retained in
matplotlib  alone or in any derivative version prepared by
Licensee.

3. In the event Licensee prepares a derivative work that is based on or
incorporates matplotlib or any part thereof, and wants to
make the derivative work available to others as provided herein, then
Licensee hereby agrees to include in any such work a brief summary of
the changes made to matplotlib .

4. MDT is making matplotlib available to Licensee on an "AS
IS" basis.  MDT MAKES NO REPRESENTATIONS OR WARRANTIES, EXPRESS OR
IMPLIED.  BY WAY OF EXAMPLE, BUT NOT LIMITATION, MDT MAKES NO AND
DISCLAIMS ANY REPRESENTATION OR WARRANTY OF MERCHANTABILITY OR FITNESS
FOR ANY PARTICULAR PURPOSE OR THAT THE USE OF MATPLOTLIB
WILL NOT INFRINGE ANY THIRD PARTY RIGHTS.

5. MDT SHALL NOT BE LIABLE TO LICENSEE OR ANY OTHER USERS OF MATPLOTLIB
 FOR ANY INCIDENTAL, SPECIAL, OR CONSEQUENTIAL DAMAGES OR
LOSS AS A RESULT OF MODIFYING, DISTRIBUTING, OR OTHERWISE USING
MATPLOTLIB , OR ANY DERIVATIVE THEREOF, EVEN IF ADVISED OF
THE POSSIBILITY THEREOF.

6. This License Agreement will automatically terminate upon a material
breach of its terms and conditions.

7. Nothing in this License Agreement shall be deemed to create any
relationship of agency, partnership, or joint venture between MDT and
Licensee.  This License Agreement does not grant permission to use MDT
trademarks or trade name in a trademark sense to endorse or promote
products or services of Licensee, or any third party.

8. By copying, installing or otherwise using matplotlib ,
Licensee agrees to be bound by the terms and conditions of this License
Agreement.

License agreement for matplotlib versions prior to 1.3.0
========================================================

1. This LICENSE AGREEMENT is between John D. Hunter ("JDH"), and the
Individual or Organization ("Licensee") accessing and otherwise using
matplotlib software in source or binary form and its associated
documentation.

2. Subject to the terms and conditions of this License Agreement, JDH
hereby grants Licensee a nonexclusive, royalty-free, world-wide license
to reproduce, analyze, test, perform and/or display publicly, prepare
derivative works, distribute, and otherwise use matplotlib
alone or in any derivative version, provided, however, that JDH's
License Agreement and JDH's notice of copyright, i.e., "Copyright (c)
2002-2011 John D. Hunter; All Rights Reserved" are retained in
matplotlib  alone or in any derivative version prepared by
Licensee.

3. In the event Licensee prepares a derivative work that is based on or
incorporates matplotlib  or any part thereof, and wants to
make the derivative work available to others as provided herein, then
Licensee hereby agrees to include in any such work a brief summary of
the changes made to matplotlib.

4. JDH is making matplotlib  available to Licensee on an "AS
IS" basis.  JDH MAKES NO REPRESENTATIONS OR WARRANTIES, EXPRESS OR
IMPLIED.  BY WAY OF EXAMPLE, BUT NOT LIMITATION, JDH MAKES NO AND
DISCLAIMS ANY REPRESENTATION OR WARRANTY OF MERCHANTABILITY OR FITNESS
FOR ANY PARTICULAR PURPOSE OR THAT THE USE OF MATPLOTLIB
WILL NOT INFRINGE ANY THIRD PARTY RIGHTS.

5. JDH SHALL NOT BE LIABLE TO LICENSEE OR ANY OTHER USERS OF MATPLOTLIB
 FOR ANY INCIDENTAL, SPECIAL, OR CONSEQUENTIAL DAMAGES OR
LOSS AS A RESULT OF MODIFYING, DISTRIBUTING, OR OTHERWISE USING
MATPLOTLIB , OR ANY DERIVATIVE THEREOF, EVEN IF ADVISED OF
THE POSSIBILITY THEREOF.

6. This License Agreement will automatically terminate upon a material
breach of its terms and conditions.

7. Nothing in this License Agreement shall be deemed to create any
relationship of agency, partnership, or joint venture between JDH and
Licensee.  This License Agreement does not grant permission to use JDH
trademarks or trade name in a trademark sense to endorse or promote
products or services of Licensee, or any third party.

8. By copying, installing or otherwise using matplotlib,
Licensee agrees to be bound by the terms and conditions of this License
Agreement.
Location: /Users/nikitatisenko/Desktop/KonfUpr/pythonProject1/.venv/lib/python3.12/site-packages
Requires: contourpy, cycler, fonttools, kiwisolver, numpy, packaging, pillow, pyparsing, python-dateutil
```

```
 git clone https://github.com/matplotlib/matplotlib.git
cd matplotlib
pip3 install .
pip3 show matplotlib
```
```
Вывод тот же что и выше
```

## Задание 2

Ввод 
```
npm view express
```

![image](https://github.com/user-attachments/assets/e5d9cb95-ec6f-4575-9c93-e3c853f81b6e)

```
git clone https://github.com/expressjs/express.git
cd express
npm install
npm link
```

```
Вывод прежний
```


## Задание 3 

Digraph код
```
digraph mpl {
    node [shape=box];

    "matplotlib" -> "contourpy";
    "matplotlib" -> "cycler";
    "matplotlib" -> "fonttools";
    "matplotlib" -> "kiwisolver";
    "matplotlib" -> "numpy";
    "matplotlib" -> "packaging";
    "matplotlib" -> "pillow";
    "matplotlib" -> "pyparsing";
    "matplotlib" -> "python-dateutil";
}
```
```
dot -Tpng matplotlib.dot -o result.png
```

```
 digraph ExpressDeps {
    node [shape=box];

    "express" -> "accepts";
    "express" -> "array-flatten";
    "express" -> "body-parser";
    "express" -> "content-disposition";
    "express" -> "content-type";
    "express" -> "cookie";
    "express" -> "cookie-signature";
    "express" -> "debug";
    "express" -> "depd";
    "express" -> "encodeurl";
    "express" -> "escape-html";
    "express" -> "etag";
    "express" -> "finalhandler";
    "express" -> "fresh";
    "express" -> "http-errors";
    "express" -> "merge-descriptors";
    "express" -> "methods";
    "express" -> "on-finished";
    "express" -> "parseurl";
    "express" -> "path-to-regexp";
    "express" -> "proxy-addr";
    "express" -> "qs";
    "express" -> "range-parser";
    "express" -> "safe-buffer";
    "express" -> "send";
    "express" -> "serve-static";
    "express" -> "setprototypeof";
    "express" -> "statuses";
    "express" -> "type-is";
    "express" -> "utils-merge";
    "express" -> "vary";
}
```
dot -Tpng exp.dot -o res2.png
```


```
## Задание 4

```
int: sum = 3;
var 0..9: a; 
var 0..9: b; 
var 0..9: c; 

include "alldifferent.mzn"; 

constraint a + b + c = sum;
constraint all_different([a, b, c]); 

solve satisfy; 
```
Вывод:
```

￼
Running untitled_model.mzn
80msec

a = 2;
b = 1;
c = 0;
----------
Finished in 80msec.

￼
Running untitled_model.mzn
67msec

a = 2;
b = 1;
c = 0;
----------
Finished in 67msec.
```

## Задание 5

```
int: mC = 6;
int: dC = 5;
int: iC = 2;
var 1..mC: m;
var 1..dC: d;
var 1..iC: i;

array[1..mC] of tuple(int, int, int): mV = 
  [(1,0,0), (1,1,0), (1,2,0), (1,3,0), (1,4,0), (1,5,0)];
array[1..dC] of tuple(int, int, int): dV = 
  [(1,8,0), (2,0,0), (2,1,0), (2,2,0), (2,3,0)];
array[1..iC] of tuple(int, int, int): iV = 
  [(1,0,0), (2,0,0)];

constraint (mV[m] == (1,0,0) \/ mV[m] == (1, 5, 0) /\ iV[i] == (1, 0, 0));
constraint (mV[m].2 >= 1 /\ mV[m].2 <= 5) -> (dV[d] == (2, 3, 0) \/ dV[d] == (2, 0, 0));
constraint mV[m] == (1, 0, 0) -> dV[d] == (1, 8, 0);
constraint (dV[d].2 >= 0 /\ dV[d].2 <= 3) -> iV[i] == (2, 0, 0);

solve satisfy;

output [
  "Menu version: ", show(mV[m]), "\n",
  "Dropdown version: ", show(dV[d]), "\n",
  "Icon version: ", show(iV[i]), "\n"
];

```

Вывод:
```

￼
Running untitled_model.mzn
52msec

Menu version: (1, 0, 0)
Dropdown version: (1, 8, 0)
Icon version: (1, 0, 0)
----------
Finished in 52msec.
```

## Задание 6

```
int: fC = 2;
int: lC = 1;
int: rC = 1;
int: shC = 2;
int: tC = 2;

var 1..fC: foo;
var 1..lC: left;
var 1..rC: right;
var 1..shC: shared;
var 1..tC: target;

array[1..fC] of tuple(int, int, int): fV = 
[(1,0,0), (1,1,0)];
array[1..lC] of tuple(int, int, int): lV = 
[(1,0,0)];
array[1..rC] of tuple(int, int, int): rV = 
[(1,0,0)];
array[1..shC] of tuple(int, int, int): shV = 
[(1,0,0), (2,0,0)];
array[1..tC] of tuple(int, int, int): tV = 
[(1,0,0), (2,0,0)];


constraint (fV[foo].1 == 1 /\ fV[foo].2 >= 0) 
/\ (tV[target].1 == 2 /\ tV[target].2 >= 0); 
constraint fV[foo] == (1, 1, 0) -> 
(lV[left].1 == 1 /\ lV[left].2 >= 0) 
/\ (rV[right].1 == 1 /\ rV[right].2 >= 0); 
constraint lV[left] == (1, 0, 0) ->
(shV[shared].1 >= 1);
constraint rV[right] == (1, 0, 0) ->
(shV[shared].1 < 2);
constraint shV[shared] == (1, 0, 0) ->
(tV[target].1 == 1 /\ tV[target].2 >= 0);

tuple(int, int, int): rootV = (1,0,0);

solve satisfy;

output [
"Root version: ", show(rootV), "\n",
"Foo version: ", show(fV[foo]), "\n",
"Left version: ", show(lV[left]), "\n",
"Right version: ", show(rV[right]), "\n",
"Shared version: ", show(shV[shared]), "\n",
"Target version: ", show(tV[target]), "\n"
];
```
Вывод:

```

￼
Running untitled_model.mzn
58msec

Root version: (1, 0, 0)
Foo version: (1, 0, 0)
Left version: (1, 0, 0)
Right version: (1, 0, 0)
Shared version: (1, 0, 0)
Target version: (2, 0, 0)
----------
Finished in 58msec.
```
