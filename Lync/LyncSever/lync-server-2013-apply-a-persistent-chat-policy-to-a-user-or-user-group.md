---
title: Lync Server 2013：将持久聊天策略应用于用户或用户组
TOCTitle: 将持久聊天策略应用于用户或用户组
ms:assetid: 809ef4e0-8d42-4feb-b7c0-3995f39867a7
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205038(v=OCS.15)
ms:contentKeyID: 49313413
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中将持久聊天策略应用于用户或用户组

 

_**上一次修改主题：** 2012-10-06_

如果已经为用户启用 Lync Server 2013，则可以向特定用户应用适当的策略以便对其启用或禁用 持久聊天服务器。

> [!NOTE]  
> 要配置和使用 持久聊天服务器，则必须先使用 拓扑生成器将 持久聊天服务器支持添加到拓扑，然后发布该拓扑。有关详细信息，请参阅部署文档中的 <a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">在 Lync Server 2013 中将持久聊天服务器添加到部署</a>。<br />
> 要配置 持久聊天服务器配置设置，请参阅部署文档中的 <a href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">在 Lync Server 2013 中全局或为持久聊天服务器池配置持久聊天服务器选项</a>。



使用本主题中的过程将以前创建的 持久聊天用户策略应用于一个或多个用户帐户或用户组。

## 向用户帐户应用 持久聊天用户策略

1.  从分配给 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  从“开始”菜单中选择 Lync Server 控制面板或打开浏览器窗口，然后输入管理 URL。有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“用户”，然后搜索要配置的用户帐户。

4.  在列出搜索结果的表中，单击相应的用户帐户，再单击“编辑”，然后单击“显示详细信息”。

5.  在“编辑 Lync Server 用户”中的“持久聊天策略”下，选择要应用的持久聊天用户策略。
    
    > [!NOTE]  
    > “&lt;自动&gt;”设置将应用默认生效的策略。服务器将自动应用这些设置。
    


6.  单击“提交”。

