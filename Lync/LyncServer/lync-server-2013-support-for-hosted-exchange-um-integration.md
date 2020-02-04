---
title: 托管 Exchange UM 集成的 Lync Server 2013 支持
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Support for hosted Exchange UM integration
ms:assetid: c7573ec3-013c-48d9-b59b-2a5427e6da35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398821(v=OCS.15)
ms:contentKeyID: 48185376
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 24139ad5294bf908a85b797300397fa8b2ac9140
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764378"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="support-for-hosted-exchange-um-integration-in-lync-server-2013"></a>Lync Server 2013 中的托管 Exchange UM 集成支持

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-21_

Lync Server 2013 ExUM 路由应用程序支持与 Exchange 统一消息（UM）在本地环境中进行集成，其中 Lync Server 2013 和 Exchange UM 都安装在您的企业内部，或者在托管的 Exchange UM 中由服务提供商，如下图所示。

![本地 Lync Server Exchange UM 部署](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "本地 Lync Server Exchange UM 部署")

支持下列模式：

  - **本地模式**   Lync Server 2013 和 Exchange UM 均部署在企业内的本地服务器上。

  - **跨平台模式**   Lync Server 2013 部署在你的企业内的本地服务器上，Exchange UM 托管在一个联机服务提供商的设备（如 Microsoft Exchange online 数据中心）中。

  - **混合模式**   您的 Lync Server 2013 部署在您的企业中的本地服务器上有一些用户邮箱，并且某些邮箱驻留在托管 Exchange 服务数据中心中。
    
    <div>
    

    > [!NOTE]  
    > 在评估和 stepwise 用户迁移到托管 Exchange UM 的过程中，混合模式可用作过渡式解决方案，如果你选择在迁移其他用户之后将某些用户的 Exchange UM 服务保留在本地，则为永久解决方案。

    
    </div>

若要将 Lync Server 2013 与托管 Exchange UM 集成，必须配置*共享 SIP 地址空间*（也称为*拆分域*）。 在此配置中，Lync Server 2013 和第三方托管 Exchange UM 服务提供商可以访问相同的 SIP 域地址空间。 有关详细信息，请参阅规划文档中的[Lync Server 2013 中的托管 EXCHANGE UM 集成体系结构](lync-server-2013-hosted-exchange-um-integration-architecture.md)。

</div>

<span> </span>

</div>

</div>

</div>

