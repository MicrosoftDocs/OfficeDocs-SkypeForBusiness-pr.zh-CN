---
title: 配置存档的全局策略
TOCTitle: 配置存档的全局策略
ms:assetid: 58341d6b-c3ff-4dd9-b1c7-0048f33861ca
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204906(v=OCS.15)
ms:contentKeyID: 49312908
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 配置存档的全局策略

 

_**上一次修改主题：** 2012-10-09_

在部署前端服务器时，Lync Server 将创建用于存档的全局策略。默认情况下，将在全局策略中禁用存档。除非设置站点或用户策略（这将覆盖全局策略），或者如果您对部分或所有用户使用 Microsoft Exchange 集成，否则全局策略控制是否为您的整个部署的内部或外部通信启用存档。如果使用 Microsoft Exchange 集成，则全局策略不适用于驻留在 Exchange 2013 上且其邮箱已被置于就地保留状态的任何用户。

有关存档策略的工作方式的详细信息（包括全局、站点和用户策略的层次结构），请参阅规划文档、部署文档或操作文档中的[Lync Server 2013 的存档工作原理](lync-server-2013-how-archiving-works.md)。

> [!NOTE]  
> 如果为部署启用 Microsoft Exchange 集成，则 Exchange 就地保留策略将控制是否为驻留在 Exchange 2013 上且其邮箱处于就地保留状态的用户启用存档。有关详细信息，请参阅部署文档中的<a href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">使用 Exchange 服务器集成设置存档的策略</a>。<br />
您应在存档配置中指定所有适当的选项，然后再启用存档。有关详细信息，请参阅部署文档中的<a href="lync-server-2013-configuring-archiving-options.md">配置存档选项</a>。



## 配置使用 Lync Server 存档数据库时用于存档的全局策略

1.  使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 2013 控制面板。有关可用于启动 Lync Server 2013 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“监控和存档”，然后单击“存档策略”。

4.  在“存档策略”页上，单击“全局”，再单击“编辑”，然后单击“显示详细信息”。

5.  在“编辑存档策略 - 全局”中，执行下列操作：
    
      - 在“名称”中，如果不想使用全局策略的默认名称 Global，可以为其指定新名称。
    
      - 在“说明”中，提供有关该策略内容的信息（例如，*divisionName* 的全局策略）
    
      - 要控制未通过特定站点策略或用户策略控制的所有站点和用户的内部通信存档，请选中或清除“存档内部通信”复选框。
    
      - 要控制未通过特定站点策略或用户策略控制的所有站点和用户的外部通信存档，请选中或清除“存档外部通信”复选框。

6.  单击“提交”。

