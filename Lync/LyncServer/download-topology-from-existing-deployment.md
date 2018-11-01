---
title: 从现有部署下载拓扑
TOCTitle: 从现有部署下载拓扑
ms:assetid: e39065a2-d4b0-4f27-8c49-f56be78fa55b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ721913(v=OCS.15)
ms:contentKeyID: 49888651
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 从现有部署下载拓扑

 

_**上一次修改主题：** 2012-09-29_

创建 Lync Server 2013 池时，将使用与 Lync Server 2010 关联的中央管理存储。因第一次使用而启动拓扑生成器并随后编辑会话时，系统会提示您要使拓扑生成器加载当前配置文档的位置。因为，您已定义了 Lync Server 2010 拓扑并建立了中央管理存储，所以，应选择从现有部署下载拓扑。拓扑生成器将读取数据库并检索当前的定义。

**从现有部署下载拓扑**

1.  打开“Lync Server 部署向导”。

2.  从“Lync Server 2013 – 部署向导”页面，单击“安装管理工具”。

3.  启动拓扑生成器：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 拓扑生成器”。

4.  选择 **从现有部署下载拓扑**。
    
    ![部署向导 - 拓扑生成器设置](images/JJ721913.d5b39fd9-3c13-422e-a06c-25d2568fe781(OCS.15).jpg "部署向导 - 拓扑生成器设置")

5.  使用默认的 .tbxml 文件类型选择文件名并保存该拓扑。

6.  展开 Lync Server 节点（如图所示），在部署中查看各种服务器角色。
    
    ![拓扑生成器 - 服务器角色常规属性](images/JJ721913.af99ead3-676b-47fd-8369-5a5f9717383f(OCS.15).jpg "拓扑生成器 - 服务器角色常规属性")

