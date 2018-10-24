---
title: Lync Server 2013：配置聊天室外接程序
TOCTitle: 配置聊天室外接程序
ms:assetid: 4eeaf19e-8369-4f6f-af65-a283cf7daa1c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204878(v=OCS.15)
ms:contentKeyID: 49312812
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中配置聊天室外接程序

 

_**上一次修改主题：** 2013-02-21_

在 Lync Server 2013 控制面板中，您可以使用“持久聊天”页的“外接程序”部分将 URL 与持久聊天关联。这些 URL 显示在聊天室的对话可扩展性窗格中的 Lync 2013 客户端中。管理员必须将外接程序添加到注册的外接程序列表中，并且聊天室管理员/创建者必须将聊天室与注册的外接程序之一相关联，用户才能在其 Lync 2013 客户端中看到此升级。

外接程序用于扩展聊天室内体验。典型的外接程序可能包括一个指向 Silverlight 应用程序的 URL，该应用程序在将股票报价发布到聊天室时实施拦截，并在可扩展性窗格中显示股票历史记录。其他示例包括将 OneNote 2013 URL 作为外接程序嵌入聊天室，以包括一些共享上下文，如“指导思想”或“今日主题”。

## 配置聊天室外接程序

1.  使用分配给 CsPersistentChatAdministrator 或 CsAdministrator 角色的用户帐户登录您的本地部署中的任一计算机。

2.  从“开始”菜单中选择 Lync Server 控制面板或打开浏览器窗口，然后输入管理 URL。有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。
    
    > [!IMPORTANT]  
    > 您还可以使用 Windows PowerShell cmdlet。有关详细信息，请参阅部署文档中的 <a href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">使用 Windows PowerShell Cmdlet 配置持久聊天服务器</a>。


3.  在左侧导航栏中，单击“持久聊天”，然后单击“外接程序”。
    
    对于多个 持久聊天服务器池部署，从下拉列表中选择相应的池。

4.  在“外接程序”页上，单击“新建”。

5.  在“选择服务”中，选择与其中需要创建外接程序的 持久聊天服务器池对应的服务。外接程序无法从一个池移到另一个池，或者在不同池之间共享。

6.  在“新建外接程序”中，执行下列操作：
    
      - 在“名称”中，指定新外接程序的名称。
    
      - 在“URL”中，指定与外接程序关联的 URL。URL 将限制为 http 和 https 协议。

7.  单击“提交”。

## 另请参阅

#### 任务

[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)  

#### 概念

[使用 Windows PowerShell Cmdlet 配置持久聊天服务器](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)

