---
title: 验证试点池与旧池的共存情况
TOCTitle: 验证试点池与旧池的共存情况
ms:assetid: 597d0fa6-ca04-4521-b1c2-72d7f35ecd08
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204914(v=OCS.15)
ms:contentKeyID: 49312944
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 验证试点池与旧池的共存情况

 

_**上一次修改主题：** 2012-09-28_

## 在 Office Communications Server 2007 R2 管理工具中验证池

1.  打开 Office Communications Server 2007 R2 管理工具。

2.  展开“林”节点，展开“Standard Edition 服务器”或“企业版池”节点，然后展开池或服务器名称。

3.  确保 Office Communications Server 2007 R2 服务正在池中运行。
    
    ![Office Communications Server 2007 R2 管理控制台](images/JJ204914.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office Communications Server 2007 R2 管理控制台")  

## 在 Lync Server 2013 控制面板中验证试用池

1.  使用具有 CsAdministrator 角色成员身份的用户帐户登录到 Lync Server 2013 前端服务器。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  单击“拓扑”。

4.  验证您部署的服务器是否在试用池中。
    
    ![“Lync Server 控制面板拓扑”页](images/JJ204914.a3d1ba5f-c1a7-45e8-b9a5-7cb07b01af8c(OCS.15).jpg "“Lync Server 控制面板拓扑”页")  

## 验证是否已启动 Lync Server 2013 服务

1.  在 Lync Server 2013 前端服务器上，从“管理工具”组中打开“服务”小程序。

2.  验证列出的服务是否与下图中的列表匹配。
    
    ![显示 Lync 服务已启动的服务页](images/JJ204914.fd35d54a-2ab6-4c09-b5e9-fd5bf10f6f51(OCS.15).jpg "显示 Lync 服务已启动的服务页")

