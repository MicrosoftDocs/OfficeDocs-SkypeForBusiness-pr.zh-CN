---
title: 将 Lync Server 存档策略应用于用户
TOCTitle: 将 Lync Server 存档策略应用于用户
ms:assetid: a23e4876-aa8d-4f49-a3bd-3696616e8290
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205143(v=OCS.15)
ms:contentKeyID: 49313804
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 将 Lync Server 存档策略应用于用户

 

_**上一次修改主题：** 2012-10-10_

创建 Lync Server 用户策略后，必须将其应用于驻留在 Lync Server 2013 上的特定用户或用户组，然后它才会生效。有关为特定用户创建用户策略的详细信息，请参阅部署文档中的[在 Lync Server 中创建和配置存档的用户策略](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md)。

有关存档策略（包括全局策略、站点策略和用户策略的层次结构）的工作方式的详细信息，请参阅规划文档、部署文档或操作文档中的[Lync Server 2013 的存档工作原理](lync-server-2013-how-archiving-works.md)。

> [!NOTE]  
> 为了配置和使用存档，您必须首先部署存档。有关详细信息，请参阅部署文档中的<a href="lync-server-2013-deploying-archiving.md">在 Lync Server 2013 中部署存档</a>。<br />
> 如果为部署启用 Microsoft Exchange 集成，Exchange 就地保留策略将控制是否为驻留在 Exchange 2013 上且其邮箱使用就地保留的用户启用存档。有关详细信息，请参阅部署文档中的<a href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">使用 Exchange 服务器集成设置存档的策略</a>。<br />
> 您应在存档配置中指定所有适当的选项，然后再启用存档。有关详细信息，请参阅部署文档中的<a href="lync-server-2013-configuring-archiving-options.md">配置存档选项</a>。



## 将 Lync Server 存档策略应用于用户

1.  使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 2013 控制面板。有关可用于启动 Lync Server 2013 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“用户”，然后搜索要配置的用户帐户。

4.  在列出搜索结果的表中，单击相应的用户帐户，再单击“编辑”，然后单击“显示详细信息”。

5.  在“编辑 Lync Server 用户”中的“存档策略”下，选择要应用的存档用户策略。
    
    > [!NOTE]  
    > “&lt;自动&gt;”设置将应用默认服务器安装设置。服务器将自动应用这些设置。
    


6.  单击“提交”。

