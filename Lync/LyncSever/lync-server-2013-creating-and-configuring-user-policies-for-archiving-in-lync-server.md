---
title: 在 Lync Server 中创建和配置存档的用户策略
TOCTitle: 在 Lync Server 中创建和配置存档的用户策略
ms:assetid: 5af0e605-3563-4d6f-a3c6-511d204a3165
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204923(v=OCS.15)
ms:contentKeyID: 49312955
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 中创建和配置存档的用户策略

 

_**上一次修改主题：** 2012-10-09_

要为驻留在 Lync Server 上的特定用户启用或禁用存档，您必须首先创建用户策略，然后将该策略应用于一个或多个用户或者用户组。有关将用户策略应用于特定用户和用户组的详细信息，请参阅部署文档中的[将 Lync Server 存档策略应用于用户](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md)。

有关存档策略的工作方式的详细信息（包括全局、站点和用户策略的层次结构），请参阅规划文档、部署文档或操作文档中的[Lync Server 2013 的存档工作原理](lync-server-2013-how-archiving-works.md)。

> [!NOTE]  
> 如果为部署启用 Microsoft Exchange 集成，Exchange 就地保留策略将控制是否为驻留在 Exchange 2013 上且其邮箱使用就地保留的用户启用存档。有关详细信息，请参阅部署文档中的<a href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">使用 Exchange 服务器集成设置存档的策略</a>。<br />
您应在存档配置中指定所有适当的选项，然后再启用存档。有关详细信息，请参阅部署文档中的<a href="lync-server-2013-configuring-archiving-options.md">配置存档选项</a>。



## 为驻留在 Lync Server 上的用户配置存档策略

1.  使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 2013 控制面板。有关可用于启动 Lync Server 2013 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“监控和存档”，然后单击“存档策略”。

4.  单击“新建”，然后单击“用户策略”。

5.  在“新建存档策略”中，执行下列操作：
    
      - 在“名称”中，指定用户策略的名称。
    
      - 在“说明”中，提供有关该用户策略内容的信息（例如，法律部门的用户策略）。
    
      - 若要控制用户策略的内部通信存档，请选中或清除“存档内部通信”复选框。
    
      - 若要控制用户策略的外部通信存档，请选中或清除“存档外部通信”复选框。

6.  单击“提交”。

用户策略仅适用于为其分配策略的用户。有关将用户策略应用于特定用户的详细信息，请参阅部署文档中的[将 Lync Server 存档策略应用于用户](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md)。

