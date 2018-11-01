---
title: 配置受信任应用程序服务器
TOCTitle: 配置受信任应用程序服务器
ms:assetid: 20c3815f-3048-4940-8c0f-cdfcd0801d5d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204735(v=OCS.15)
ms:contentKeyID: 49312222
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 配置受信任应用程序服务器

 

_**上一次修改主题：** 2014-11-05_

在混合环境中，如果创建新的受信任的应用程序服务器，则必须将下一个跃点池设置为 Lync Server 2013 池。在混合环境中，旧 Lync Server 2010 池和 Lync Server 2013 池都显示在下拉列表中。此环境不支持选择旧池。

**创建受信任的应用程序服务器时选择 Lync Server 2013 作为下一个跃点**

1.  打开“拓扑生成器”。

2.  在左窗格中，右键单击“受信任的应用程序服务器”，然后单击“新建受信任的应用程序池”。

3.  输入受信任应用程序池的“池 FQDN”，选择该池是包含一台服务器还是多台服务器。

4.  单击“下一步”。

5.  在“选择下一个跃点”页上，从列表中选择 Lync Server 2013 前端池。

6.  单击“完成”。

7.  选择顶层节点“Lync Server”，然后从“操作”窗格中选择“发布”。
    
    确认“受信任应用程序池”已成功创建并且与正确的前端池关联。

