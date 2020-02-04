---
title: Lync Server 2013：启用或禁用与 Exchange 存储的集成
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling integration with Exchange storage
ms:assetid: c08b9ba5-04f6-452a-b44c-c130f1564a34
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205228(v=OCS.15)
ms:contentKeyID: 48185295
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c5c8a52aabb504ce63ef6e340b5a68e9e8c4c0e7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735662"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-integration-of-lync-server-2013-with-exchange-storage"></a>启用或禁用 Lync Server 2013 与 Exchange 存储的集成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-09_

在 Lync Server 2013 "控制面板" 中，使用存档配置启用和禁用与 Exchange 存储的集成。 这包括以下存档配置：

  - 部署 Lync Server 2013 时默认创建的全局配置。

  - 可创建和使用的可选网站级和池级配置，用于指定如何为特定网站或池实现存档。

有关如何实现存档配置的详细信息，包括你可以指定哪些选项和存档配置的层次结构，请参阅规划文档、部署文档或操作文档中的[存档在 Lync Server 2013 中的工作原理](lync-server-2013-how-archiving-works.md)。

<div>

## <a name="to-enable-or-disable-integration-with-microsoft-exchange-storage"></a>启用或禁用与 Microsoft Exchange 存储的集成

1.  使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“监控和存档”****，然后单击“存档配置”****。

4.  单击存档配置列表中相应的全局、站点或池配置的名称，单击“**编辑**”，再单击“**显示详细信息**”，然后执行以下操作：
    
      - 若要启用与 Exchange 2013 存储的集成，请选中 " **Microsoft Exchange 集成**" 复选框。
    
      - 若要禁用与 Exchange 2013 存储的集成，请清除 " **Microsoft Exchange 集成**" 复选框。

5.  单击“**提交**”。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中存档的工作方式](lync-server-2013-how-archiving-works.md)  


[管理您的组织、网站和池的 Lync Server 2013 中的存档配置选项](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

