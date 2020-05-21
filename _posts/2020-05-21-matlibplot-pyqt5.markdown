---
layout: post
title: matlibplot嵌入pyqt5
date: 2020-05-21T14:22:44.000Z
categories: update
---
<img src="/images/fulls/03.jpg" class="fit image"> 

个人使用方法技巧：  在QT Designer里面  用graphicsView里面占用界面
然后再code里面注释掉graphicsView，用Figure_Canvas替代，因为Figure_Canvas也是一个Widget, 可以直接添加
```python
self.verticalLayout_3.addLayout(self.horizontalLayout)
#self.graphicsView = QtWidgets.QGraphicsView(self.centralwidget)
#self.graphicsView.setObjectName("graphicsView")
#self.verticalLayout_3.addWidget(self.graphicsView)
#self.verticalLayout_3.setStretch(0, 2)
#self.verticalLayout_3.setStretch(1, 5)
self.dr = Figure_Canvas()
self.verticalLayout_3.addLayout(self.horizontalLayout)
self.verticalLayout_3.addWidget(self.dr)
self.verticalLayout_3.setStretch(0, 2)
self.verticalLayout_3.setStretch(1, 5)
self.addToolBar(NavigationToolbar(self.dr, self))
#self.dr = Figure_Canvas()
#self.graphicscene = QtWidgets.QGraphicsScene()
#self.graphicscene.addWidget(self.dr)
#self.graphicsView.setScene(self.graphicscene)
#Matplot自适应pyqt5
#self.qvbl = QtWidgets.QVBoxLayout(self.graphicsView)
#if self.qvbl.count() == 0:
#    self.qvbl.addWidget(self.dr)
#else:
#    # 先清空布局中的所有控件，再添加新控件
#    for i in range(self.qvbl.count()):
#        self.qvbl.itemAt(i).widget().deleteLater()
 #   self.qvbl.addWidget(self.dr)
```
详情可以点击[link]( https://matplotlib.org/gallery/user_interfaces/embedding_in_qt_sgskip.html?highlight=pyqt)
