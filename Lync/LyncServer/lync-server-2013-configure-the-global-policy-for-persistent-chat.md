---
title: Lync Server 2013：配置持久聊天的全局策略
TOCTitle: 配置持久聊天的全局策略
ms:assetid: 6176eb5c-19de-4c07-bcc0-2e38f8965966
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204951(v=OCS.15)
ms:contentKeyID: 49313011
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中配置持久聊天的全局策略

 

_**上一次修改主题：** 2012-10-06_

您可以使用默认全局策略本身来为您的部署中的所有用户启用 持久聊天设置。您还可以为站点和用户指定其他策略以控制是否对特定用户和站点启用或禁用 持久聊天。

无法删除全局策略。如果试图删除全局策略，配置将重置为默认值。

> [!NOTE]  
> 要配置和使用 持久聊天服务器，则必须先使用 拓扑生成器将 持久聊天服务器支持添加到拓扑，然后发布该拓扑。有关详细信息，请参阅部署文档中的 <a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">在 Lync Server 2013 中将持久聊天服务器添加到部署</a>。<br />
要配置 持久聊天服务器配置设置，请参阅部署文档中的 <a href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">在 Lync Server 2013 中全局或为持久聊天服务器池配置持久聊天服务器选项</a>。



## 为 持久聊天配置全局策略

1.  从分配给 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  从“开始”菜单中，选择 Lync Server 控制面板或打开浏览器窗口，然后输入管理 URL。有关可用于启动 Lync Server 控制面板的各种方法的详细信息，请参阅操作文档中的[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。
    
    > [!IMPORTANT]  
    > 您还可以使用 Windows PowerShell cmdlet。有关详细信息，请参阅部署文档中的 <a href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">使用 Windows PowerShell Cmdlet 配置持久聊天服务器</a>。


3.  在 Lync Server 控制面板中，单击“持久聊天”，然后单击“持久聊天策略”。

4.  单击策略列表中的“全局”，再单击“编辑”，然后单击“显示详细信息”。

5.  在“编辑 持久聊天策略 - 全局”中，执行下列操作：
    
      - 在“名称”中，如果不想使用全局策略的默认名称 Global，可以为其指定新名称。
    
      - 在“说明”中，提供有关该用户策略内容（例如，*centralSiteName* 的全局策略）的详细信息。
    
      - 若要控制未通过站点策略或用户策略明确控制的所有站点和用户的 持久聊天，请选中或清除“启用 持久聊天”复选框。

6.  单击“提交”。

