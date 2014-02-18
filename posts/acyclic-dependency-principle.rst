.. title: 去除循環相依性
.. slug: acyclic-dependency-principle
.. date: 2014/02/08 22:13:00
.. tags: 物件導向,設計原則
.. link: 
.. description: 
.. type: text

模組間依賴關係應維持單向相依，若出現循環相依，會造成系統編譯建置上的困難。

如下圖，Ｄ是Ｂ的底層，Ｂ是Ａ和Ｃ的底層，Ｃ是Ａ的底層。底層若變動，依賴於它的模組可能要隨著調整並重新編譯。因此當Ｄ變動則調整Ａ、Ｂ、Ｃ並全部重新編譯; 當Ｃ異動，則只有Ａ受影響需要重新編譯; 如果只有Ａ異動，那很好，沒有模組受影響，只要編譯Ａ就好。如此，我們限縮了異動影響範圍。

.. image:: /img/img_adp_acycle0.png

.. TEASER_END: (繼續閱讀...)

| 
| 

但如果出現循環相依，就不是這樣了。如下圖，當Ａ異動，因為D依賴Ａ，因此Ｄ要調整並重新編譯，連帶的Ｂ、Ｃ也要一起調整並編譯。我只是改了Ａ，但整張圖都受影響，所有模組都需要重新編譯。系統建置變複雜了，可維護性變差了。

.. image:: /img/img_adp_cycle.png

| 
| 

如何消除循環相依？Robert Martin在其 `文章 <http://www.objectmentor.com/resources/articles/granularity.pdf>`_ 中給了建議：

1. **使用依賴反轉法則**。如下圖，模組Ｄ提出Interface規格，由Ａ實作，如此消除循環相依。

.. image:: /img/img_adp_acycle1.png

| 

2. **將被依賴的部分，分離出來成為新模組**。如下圖，將被依賴的部分從Ａ分離出來，成為Ｅ。現在，Ｅ成為Ａ和Ｄ的底層。如此消除循環相依。

.. image:: /img/img_adp_acycle2.png

