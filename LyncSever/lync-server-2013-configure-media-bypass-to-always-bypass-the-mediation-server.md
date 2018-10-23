---
title: 配置媒体绕过以始终绕过中介服务器
TOCTitle: 配置媒体绕过以始终绕过中介服务器
ms:assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425846(v=OCS.15)
ms:contentKeyID: 49312492
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 配置媒体绕过以始终绕过中介服务器

 

_**上一次修改主题：** 2013-02-25_

> [!NOTE]  
> 本主题假定，对于希望媒体绕过中介服务器的特定站点或特定服务，已为连接到对等方（Internet 电话服务提供商 (ITSP) 的公用电话交换网 (PSTN) 网关、IP-PBX 或会话边界控制器）的所有中继连接配置媒体旁路。<br />
如果启用了呼叫允许控制，则无法将媒体配置为始终绕过中介服务器。这些设置不兼容，因此在 Lync Server 控制面板用户界面中是相互排斥的设置。



除了为与中介服务器的对等方相关联的各个中继连接启用媒体旁路功能外，还必须配置全局媒体旁路设置。如果使用本主题中的步骤配置全局媒体旁路设置，则假定前提是 Lync 终结点与在中继连接上配置了媒体旁路的任何对等方之间的连接工作正常。

如果 Lync Server 终结点与中介服务器的所有对等方（已对其相应的中继连接启用媒体旁路）之间的连接工作不正常，则采用媒体旁路时必须配置全局媒体旁路设置以使用站点和区域信息。这可以在媒体绕过中介服务器时，提供更为细化的控制。为执行此操作，请改用[配置媒体绕过全局设置以使用站点和区域信息](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)和[在 Lync Server 2013 中将子网与网络站点相关联](lync-server-2013-associate-a-subnet-with-a-network-site.md)中的步骤。

## 在全局范围启用媒体旁路以始终绕过中介服务器

1.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

2.  在左侧导航栏中，单击“网络配置”。

3.  双击列表中的“全局”配置。

4.  在“编辑全局设置”页上，选中“启用媒体旁路”复选框。

5.  单击“始终绕过”。

6.  单击“提交”。

## 另请参阅

#### 概念

[在 Lync Server 2013 中配置媒体绕过](lync-server-2013-configure-media-bypass.md)  
[全局媒体绕过选项](lync-server-2013-global-media-bypass-options.md)  
[Lync Server 2013 中的媒体绕过和中介服务器](lync-server-2013-media-bypass-and-mediation-server.md)  

#### 其他资源

[在 Lync Server 2013 中规划媒体旁路](lync-server-2013-planning-for-media-bypass.md)

