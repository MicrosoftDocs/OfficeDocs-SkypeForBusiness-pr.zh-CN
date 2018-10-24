---
title: Lync Server 2013：为持久聊天创建用户策略
TOCTitle: 为持久聊天创建用户策略
ms:assetid: aa3774af-d442-4206-8a68-2fbb9102e9d6
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205170(v=OCS.15)
ms:contentKeyID: 49313876
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中为持久聊天创建用户策略

 

_**上一次修改主题：** 2012-10-06_

在 Lync Server 控制面板中，定义可分配给“用户”中的用户的用户策略。

用户策略将覆盖全局策略和站点策略，但是仅限于为其分配了该用户策略的特定用户。

> [!NOTE]  
> 要配置和使用 持久聊天服务器，则必须先使用 拓扑生成器将 持久聊天服务器支持添加到拓扑，然后发布该拓扑。有关详细信息，请参阅部署文档中的 <a href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">在 Lync Server 2013 中将持久聊天服务器添加到部署</a>。<br />
要配置 持久聊天服务器配置设置，请参阅部署文档中的 <a href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">在 Lync Server 2013 中全局或为持久聊天服务器池配置持久聊天服务器选项</a>。



## 为 持久聊天创建用户策略

1.  从分配给 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  从“开始”菜单中选择 Lync Server 控制面板或打开浏览器窗口，然后输入管理 URL。有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。
    
    > [!IMPORTANT]
    > 您也可以使用 Windows PowerShell cmdlet。请参阅部署文档中的 <a href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">使用 Windows PowerShell Cmdlet 配置持久聊天服务器</a>。


3.  在左侧导航栏中，单击“持久聊天”，然后单击“持久聊天策略”。

4.  单击“新建”，然后单击“用户策略”。

5.  在“新建 持久聊天策略”中，请执行以下操作：
    
      - 在“名称”中，指定新用户策略的名称。
    
      - 在“说明”中，提供有关用户策略（例如，特定用户的 持久聊天策略）的内容的详细信息。
    
      - 要控制未专门通过用户策略控制的所有用户的 持久聊天，请选中或清除“启用 持久聊天”复选框。

6.  单击“提交”。

