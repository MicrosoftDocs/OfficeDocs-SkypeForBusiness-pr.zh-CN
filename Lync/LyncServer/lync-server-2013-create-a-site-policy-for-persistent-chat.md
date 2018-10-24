---
title: Lync Server 2013：为持久聊天创建站点策略
TOCTitle: 为持久聊天创建站点策略
ms:assetid: 1327ff5c-b859-4010-a240-e0b2b084b5bd
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204693(v=OCS.15)
ms:contentKeyID: 49312068
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中为持久聊天创建站点策略

 

_**上一次修改主题：** 2012-10-06_

对于已部署的每个站点，可以分别创建站点特定的持久聊天策略。

站点策略中的配置将覆盖全局策略，但是仅限于站点策略所涉及的特定站点。

> [!NOTE]  
> 要配置和使用 持久聊天服务器，则必须先使用 拓扑生成器将 持久聊天服务器支持添加到拓扑，然后发布该拓扑。有关详细信息，请参阅部署文档中的 <a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">在 Lync Server 2013 中将持久聊天服务器添加到部署</a>。<br />
要配置持久聊天服务器配置设置，请参阅部署文档中的<a href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">在 Lync Server 2013 中全局或为持久聊天服务器池配置持久聊天服务器选项</a>。



## 创建站点的持久聊天策略

1.  从分配给 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  从“开始”菜单中选择 Lync Server 控制面板或打开浏览器窗口，然后输入管理 URL。有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“持久聊天”，然后单击“持久聊天策略”。
    
    > [!IMPORTANT]
    > 您还可以使用 Windows PowerShell cmdlet。有关详细信息，请参阅部署文档中的 <a href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">使用 Windows PowerShell Cmdlet 配置持久聊天服务器</a>。


4.  单击“新建”，然后单击“站点策略”。

5.  在“选择站点”中，单击要应用此策略的站点。

6.  在“新建 持久聊天策略”中，请执行以下操作：
    
      - 在“名称”中，指定新站点策略的名称（例如，Redmond）。
    
      - 在“说明”中，提供有关该站点策略内容的详细信息（例如，Redmond 的聊天室策略）。
    
      - 若要控制未通过站点策略明确控制的所有站点的 持久聊天，请选中或清除“启用 持久聊天”复选框。

7.  单击“提交”。

