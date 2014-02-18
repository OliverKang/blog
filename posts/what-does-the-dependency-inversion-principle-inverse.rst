.. title: 依賴"反轉"，反轉了什麼？
.. slug: what-does-the-dependency-inversion-principle-inverse
.. date: 2014/02/07 23:34:30
.. tags: 物件導向,設計原則
.. link: 
.. description: 
.. type: text

依賴反轉是物件導向原則之一，維基 [1]_ 上說這個原則有兩項要求：

- 高層次的模組不應該依賴於低層次的模組，兩者都應該依賴於抽象介面。*(High level modules should not depend upon low level modules. Both should depend upon abstractions.)*
- 抽象介面不應該依賴於具體實現。而具體實現則應該依賴於抽象介面。*(Abstractions should not depend upon details. Details should depend upon abstractions.)*

只是...究竟是什麼東西被“**反轉**”了？

.. TEASER_END: (繼續閱讀...)

讓我們來看圖。

| 
| **這是DI之前：**
|   高層次的模組依賴於低層次的模組。

.. image:: /img/img_dip_before.png

|
| **這是有DI之後：**
|   箭頭方向反轉了，現在是低層次模組依賴于高層次模組所定義的抽象界面。

.. image:: /img/img_dip_after.png

|

將將～是不是一目瞭然了呢？

|
|
|

*參考資料*

.. [1] `維基百科-依賴反轉原則 <http://zh.wikipedia.org/wiki/%E4%BE%9D%E8%B5%96%E5%8F%8D%E8%BD%AC%E5%8E%9F%E5%88%99>`_

|
|
|




