---
title: 设置存档的站点策略
TOCTitle: 设置存档的站点策略
ms:assetid: dc2ea206-8b9c-44dd-a479-efb217593c89
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205325(v=OCS.15)
ms:contentKeyID: 49314448
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 设置存档的站点策略

 

_**上一次修改主题：** 2012-10-09_

您可通过为特定站点中的每个站点创建和配置存档策略来启用或禁用这些站点的存档。站点策略将覆盖全局策略，但用户策略将覆盖站点策略。仅当未使用 Microsoft Exchange 集成，或者使用 Microsoft Exchange 集成而某些用户未驻留在 Exchange 2013 上并且他们的邮箱置于就地保留状态时，存档策略才适用。

有关存档策略工作原理（包括全局、站点和用户策略的层次结构）的详细信息，请参阅规划文档、部署文档或操作文档中的[Lync Server 2013 的存档工作原理](lync-server-2013-how-archiving-works.md)。

> [!NOTE]  
> 如果为部署启用 Microsoft Exchange 集成，则 Exchange 就地保留策略将控制是否为驻留在 Exchange 2013 上且其邮箱处于就地保留状态的用户启用存档。有关详细信息，请参阅部署文档中的<a href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">使用 Exchange 服务器集成设置存档的策略</a>。<br />
在存档策略中启用内部或外部通信的存档之前，应在存档配置中指定所有适当选项。有关详细信息，请参阅部署文档中的<a href="lync-server-2013-configuring-archiving-options.md">配置存档选项</a>。



## 创建站点的存档策略

1.  使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 2013 控制面板。

3.  在左侧导航栏中，单击“监控和存档”，然后单击“存档策略”。
    
    有关存档策略工作原理（包括全局、站点和用户策略的层次结构）的详细信息，请参阅规划文档、部署文档或操作文档中的[Lync Server 2013 的存档工作原理](lync-server-2013-how-archiving-works.md)。

4.  单击“新建”，然后单击“站点策略”。

5.  在“选择站点”中，单击要应用此策略的站点。

6.  在“新建存档策略”中，执行下列操作：
    
      - 在“名称”中，指定站点策略的名称。
    
      - 在“说明”中，提供有关该站点策略内容的信息（例如，Redmond 的站点策略）。
    
      - 若要控制指定站点的内部通信存档，请选中或清除“存档内部通信”复选框。
    
      - 若要控制指定站点的外部通信存档，请选中或清除“存档外部通信”复选框。

7.  单击“提交”。

