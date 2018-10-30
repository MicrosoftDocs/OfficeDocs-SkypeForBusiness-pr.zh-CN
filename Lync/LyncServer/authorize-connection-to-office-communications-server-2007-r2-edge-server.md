---
title: 授权连接到 Office Communications Server 2007 R2 边缘服务器
TOCTitle: 授权连接到 Office Communications Server 2007 R2 边缘服务器
ms:assetid: 14f6798a-28d6-4b3d-8734-942192e1bbf5
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204702(v=OCS.15)
ms:contentKeyID: 49312093
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 授权连接到 Office Communications Server 2007 R2 边缘服务器

 

_**上一次修改主题：** 2012-09-28_

对于试点池中的每个 Lync Server 2013 前端服务器或标准版服务器，您必须更新已获准连接到 Office Communications Server 2007 R2 边缘服务器的内部服务器的列表。如果不进行这些更新，则用户使用旧边缘服务器加入的外部音频/视频 (A/V) 会议将不起作用。

## 授权连接到 Office Communications Server 2007 R2 边缘服务器

1.  从 Office Communications Server 2007 R2 边缘服务器中的“管理工具”组中，打开“计算机管理”管理单元。

2.  在控制台树中，展开“服务和应用程序”。

3.  右键单击“Office Communications Server 2007 R2”，然后单击“属性”。

4.  单击“内部”选项卡。

5.  在“添加服务器”下，单击“添加”。

6.  在“添加 Office Communications Server”对话框中，输入相应的信息：
    
      - 指定每个 Lync Server 2013 前端服务器或标准版服务器以及 Lync Server 2013 池的完全限定的域名 (FQDN)。
    
      - 如果在用 Lync Server 2013 控制器的 FQDN 指定下一个跃点计算机的池中已配置静态路由，则指定该控制器的 FQDN。

7.  为每个 Lync Server 2013 前端服务器、标准版服务器、池和控制器添加条目后，单击“**应用**”，然后单击“确定”关闭属性页。

