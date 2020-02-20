---
title: Lync Server 2013：配置位置数据库
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure the location database
ms:assetid: 8544be31-6958-47ef-b926-fdc80d56191c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398679(v=OCS.15)
ms:contentKeyID: 48184704
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b7bf02e809597092ca2212cacb3fd78336a0be2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145641"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-the-location-database-in-lync-server-2013"></a>在 Lync Server 2013 中配置位置数据库

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-17_

为使客户端能够自动检测其在网络中的位置，首先需要配置位置数据库。如果不配置位置数据库，且位置策略中的“所需位置”**** 设置为“是”**** 或“免责声明”****，则会提示用户手动输入位置。

要配置位置数据库，请执行下列任务：

1.  使用网络元素到位置的映射填充数据库。 如果您使用紧急位置标识号（ELIN）网关，则需要在 " \<公司名称\> " 字段中添加 ELIN。

2.  根据由 E9-1-1 服务提供商维护的主街道地址指南 (MSAG) 验证地址。

3.  发布更新的数据库。

<div>


> [!NOTE]  
> 另外，可以定义可用于代替位置数据库的辅助位置源数据库。 有关详细信息，请参阅<A href="lync-server-2013-configure-a-secondary-location-information-service.md">在 Lync Server 2013 中配置辅助位置信息服务</A>。



</div>

<div>

## <a name="in-this-section"></a>本部分内容

  - [在 Lync Server 2013 中填充位置数据库](lync-server-2013-populate-the-location-database.md)

  - [在 Lync Server 2013 中验证地址](lync-server-2013-validate-addresses.md)

  - [从 Lync Server 2013 发布位置数据库](lync-server-2013-publish-the-location-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

