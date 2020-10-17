---
title: Lync Server 2013 支持托管 Exchange UM 集成
description: Lync Server 2013 支持托管 Exchange UM 集成。
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
ms.openlocfilehash: 88920667d703bc634921903e8e3995cb65db6873
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546317"
---
# <a name="support-for-hosted-exchange-um-integration-in-lync-server-2013"></a>在 Lync Server 2013 中支持托管 Exchange UM 集成

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-21_

Lync Server 2013 ExUM 路由应用程序支持与 Exchange 统一消息 (UM) 集成在本地环境中，其中 Lync Server 2013 和 Exchange UM 都安装在企业内部，或者在服务提供商托管的 Exchange UM 中，如下图所示。

![本地 Lync Server Exchange UM 部署](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "本地 Lync Server Exchange UM 部署")

支持以下模式：

  - **本地模式**    Lync Server 2013 和 Exchange UM 都部署在企业中的本地服务器上。

  - **跨界模式**    Lync Server 2013 部署在企业内的本地服务器上，Exchange UM 托管在联机服务提供商的设施中，如 Microsoft Exchange Online 数据中心。

  - **混合模式**    你的 Lync Server 2013 部署中的某些用户邮箱驻留在企业中的本地服务器上，并且某些邮箱驻留在托管 Exchange service 数据中心中。
    
    <div>
    

    > [!NOTE]  
    > 在评估和 stepwise 用户迁移到托管 Exchange UM 的过程中，混合模式可用作过渡解决方案，如果您选择在迁移其他用户之前将某些用户的 Exchange UM 服务保留在本地，则为永久解决方案。

    
    </div>

若要将 Lync Server 2013 与托管 Exchange UM 集成，您必须配置 *共享 SIP 地址空间* (也称为 " *拆分域*) "。 在此配置中，Lync Server 2013 和第三方托管 Exchange UM 服务提供商都可以访问相同的 SIP 域地址空间。 有关详细信息，请参阅规划文档中的在 [Lync Server 2013 中托管 EXCHANGE UM 集成体系结构](lync-server-2013-hosted-exchange-um-integration-architecture.md) 。

</div>

<span> </span>

</div>

</div>

</div>

