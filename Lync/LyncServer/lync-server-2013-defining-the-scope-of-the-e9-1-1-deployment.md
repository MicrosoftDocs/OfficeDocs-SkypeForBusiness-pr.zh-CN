---
title: 'Lync Server 2013: 定义 E9 的范围-1-1 部署'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining the scope of the E9-1-1 deployment
ms:assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425775(v=OCS.15)
ms:contentKeyID: 48183707
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff32a71ec9b724bad9efee68784d284a71b8f385
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830693"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-the-scope-of-the-e9-1-1-deployment-in-lync-server-2013"></a>在 Lync Server 2013 中定义 E9 部署的范围

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-06-06_

在将 Microsoft Lync Server 2013 配置为 E9-1 之前, 你需要规划 E9-1-1 部署。 要考虑的一些问题包括：

  - **贵组织关于 E9-1-1 的策略和法律义务是什么？**  
    E9-1-1 针对 PBX（在 E9-1-1 用语中，称为多路电话系统或 MLTS）的法律要求因州/省而异。 您应咨询您的法律团队, 了解在相关地区的您的 Lync Server 部署中可能会收取的义务。

<!-- end list -->

  - **需要在企业内部的哪些区域启用 E9-1-1？**  
    可以为整个企业或选定位置启用 E9-1-1。例如，您可能对位于不同州/省的机构有不同的 E9-1-1 要求，您也可能要排除美国之外的站点。

<!-- end list -->

  - **如何为分支站点部署 E9-1-1？**  
    语音复原是在分支站点部署 E9-1-1 时需要理解的一个重要概念。 如果您有集中式电子 9-1-1 SIP 中继并且发生 WAN 中断, 则登录的客户可能无法从位置信息服务获取位置或连接到紧急服务服务提供商。 Lync 服务器提供了多个用于处理分支机构中的语音复原的策略, 包括: 具有弹性数据网络、在每个分支处部署 SIP 主干或在中断期间将紧急呼叫推送到本地网关。 有关详细信息, 请参阅[在 Lync Server 2013 中规划分支站点语音复原](lync-server-2013-planning-for-branch-site-voice-resiliency.md)。

<!-- end list -->

  - **是否为在网络外部工作的用户启用 E9-1-1？**  
    自动位置获取仅适用于组织网络内的客户端, 因此你的组织需要确定它是否支持 E9 从 Lync 客户端 (非本地) 拨打的 1-1。 例如，如果用户在家里或客户站点中工作，您是否允许这些用户进行紧急呼叫？ 如果客户端位于企业网络外部，则可将客户端配置为提示用户输入位置。 但由于无法根据主街道地址指南 (MSAG) 预先验证这些用户提供的位置，因此，紧急服务的服务提供商调度程序将需要在将呼叫路由至公共安全应答点 (PSAP) 之前向呼叫者口头确认该位置的有效性。
    
    <div>
    

    > [!NOTE]  
    > 通过使用 VPN 连接到组织网络的用户的 Lync 客户端可以获取内部 IP 地址信息, 但由于这些地址不能用于标识用户的实际位置, 因此必须将 VPN 子网排除在位置信息服务。

    
    </div>

<!-- end list -->

  - **是否向美国之外的站点提供紧急呼叫路由？**  
    您可能需要为贵公司所在的、紧急服务的服务提供商不提供服务的一些区域（例如，国际位置）提供紧急路由。为此，请创建新的站点，然后为涉及 PSTN 用法（可通过本地 PSTN 网关路由呼叫）的站点分配语音策略。

</div>

<span> </span>

</div>

</div>

</div>

