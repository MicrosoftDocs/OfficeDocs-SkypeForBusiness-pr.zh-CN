---
title: 配置各种策略
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Configuring the Various Policies
ms:assetid: e3b3cbda-7c17-470b-acb0-82fdcc473184
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945610(v=OCS.15)
ms:contentKeyID: 51541436
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6316a1027de963cefea6c0c76051f09cb5d33538
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727682"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-various-policies"></a>配置各种策略

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-24_

<div>

## <a name="configuring-the-various-policies"></a>配置各种策略

下面是在运行 Lync Server 2013 应力和性能工具之前，您可以在 Lync Server 2013 拓扑中配置的各种策略。

<div>

## <a name="configuring-the-archiving-policy"></a>配置存档策略

请参阅脚本 ArchivingPolicy 示例。 只有在拓扑中部署了存档服务器时，才需要使用此脚本。 有关详细信息，请参阅 Lync server 2013 文档和 cmdlet 有关[在 Lync Server 2013 中存档和监视 cmdlet](https://technet.microsoft.com/en-us/library/gg415629\(v=ocs.15\))的帮助。

</div>

<div>

## <a name="configuring-the-conferencing-policy"></a>配置会议策略

请参阅脚本 MeetingPolicy 示例。 有关详细信息，请参阅 lync server 2013 文档和[Lync server 2013 中的 Web 会议](https://technet.microsoft.com/en-us/library/gg415675\(v=ocs.15\))Cmdlet cmdlet 帮助。

</div>

<div>

## <a name="configuring-the-contacts-policy"></a>配置联系人策略

请参阅示例 ContactsPolicy。 有关详细信息，请参阅 Lync server 2013 文档以及[Lync server 2013 中的 IM 和状态 cmdlet](https://technet.microsoft.com/en-us/library/gg398611\(v=ocs.15\))的 cmdlet 帮助。

</div>

<div>

## <a name="configuring-the-federation-policy"></a>配置联合身份验证策略

请参阅示例 FederationPolicy。 有关详细信息，请参阅 lync server 2013 文档和 lync server 2013 中的[Edge 服务器 cmdlet](https://technet.microsoft.com/en-us/library/gg415635\(v=ocs.15\))以及[lync server 2013 中的联盟和外部访问 cmdlet](https://technet.microsoft.com/en-us/library/gg415651\(v=ocs.15\))中的 cmdlet 帮助。

</div>

<div>

## <a name="configuring-the-call-admission-control-policy"></a>配置呼叫许可控制策略

请参阅示例 BandwidthPolicy。 有关详细信息，请参阅 lync server 2013 文档[概述 lync server 2013 中的呼叫许可控制](https://technet.microsoft.com/en-us/library/gg398529\(v=ocs.15\))和[lync server 2013 中的呼叫许可控制 Cmdlet](https://technet.microsoft.com/en-us/library/gg415676\(v=ocs.15\))的 cmdlet 帮助。

</div>

<div>

## <a name="configuring-the-voice-routing-rules"></a>配置语音路由规则

请参阅示例 RoutingRules。 配置语音路由规则时，请注意手机上下文（即/Location 配置文件或/SimpleName）和内部/外部区域代码，以便你可以在创建用户时以及在 LyncPerfTool 配置期间指定它们（特别是针对 PSTN-UC 和 UC）。 例如，RoutingRules 中的**CsDialPlan** Cmdlet 调用示例中的 SimpleName 参数应用于 UserProfileGenerator 下图中的 LocationProfile 值的值。

![示例语音路由规则。](images/JJ945610.9f34d971-4ed0-4a4c-b101-086a91c4578c(OCS.15).jpg "示例语音路由规则。")

有关详细信息，请参阅 lync server 2013 文档和适用于[Lync server 2013 中的企业语音 cmdlet](https://technet.microsoft.com/en-us/library/gg415658\(v=ocs.15\))的 cmdlet 帮助。

</div>

<div>

## <a name="configuring-conferencing-attendant-application"></a>配置会议助理应用程序

请参阅示例 ConferenceAutoAttendantConfiguration。 记下 ConferencingAutoAttendant 电话号码（默认情况下为1121111111），以便你可以将其键入到 LyncPerf 工具配置工具中，以便进行配置生成。

![配置会议助理应用程序](images/JJ945610.0618a22f-27a9-423a-9085-d2bf71e82db6(OCS.15).jpg "配置会议助理应用程序")

有关详细信息，请参阅 lync server 2013 文档和 lync server 2013 中的[Web 会议](https://technet.microsoft.com/en-us/library/gg415675\(v=ocs.15\))Cmdlet 和[lync server 2013 中的电话拨入式会议 cmdlet](https://technet.microsoft.com/en-us/library/gg415630\(v=ocs.15\))中的 cmdlet 帮助。

</div>

<div>

## <a name="configuring-lync-server-call-park-service"></a>配置 Lync Server 呼叫寄存服务

默认情况下，通话寄存处于禁用状态。 请参阅示例 CallParkConfiguration。 有关详细信息，请参阅 Lync server 2013 文档和 cmdlet 帮助，了解如何[在 Lync server 2013 中调用寄存应用程序 cmdlet](https://technet.microsoft.com/en-us/library/gg415639\(v=ocs.15\))。

</div>

<div>

## <a name="configuring-emergency-calls"></a>配置紧急呼叫

执行以下步骤来配置紧急呼叫的压力和性能测试。

1.  设置紧急呼叫的语音路线。 有关设置此语音路由的示例，请参阅注释 "将 E911 路由到 PSTN" 下的 RoutingRules 脚本。
    
    <div>
    

    > [!WARNING]  
    > RoutingRules 中的示例命令具有数字模式，其中包含数字119而不是911。 应避免使用911（或实际的本地紧急号码），以防止在负载测试期间意外呼叫本地紧急操作员。 此配置仅供模拟之用。

    
    </div>

2.  通过填写 UserProvisioningTool 中的 " **iis** " 选项卡上的值来配置地址，如下图所示。
    
    ![配置位置信息服务。](images/JJ945610.8ac1faa1-e9f9-40d0-b8b7-b159f4f459f7(OCS.15).jpg "配置位置信息服务。")  

3.  单击 "**生成 .Lis 配置文件**"。

4.  将生成用于端口、子网、开关和无线访问点（WAPs）和适用于 Lync Server 2013 应力和性能工具的 XML 文件的 CSV 文件。 当使用 LisConfiguration 脚本配置位置信息服务（.LIS）时，CSV 文件将用作输入（位于同一文件夹中）。 将生成的 Locations0 文件移动到 Lync Server 2013 应力和性能工具可执行文件（LyncPerfTool）所在的文件夹中，该文件将运行位置配置文件（拨号计划）方案。

</div>

<div>

## <a name="creating-enabling-configuring-and-disabling-users"></a>创建、启用、配置和禁用用户

在运行以下脚本之前，应创建所有用户。 按照[创建用户和联系人](create-users-and-contacts.md)中的说明创建用户。 有关详细信息，请参阅[move-csuser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\))、 [move-csuser](https://technet.microsoft.com/en-us/library/gg398510\(v=ocs.15\))和[Disable-move-csuser](https://technet.microsoft.com/en-us/library/gg398747\(v=ocs.15\)) cmdlet 的 Lync Server 2013 cmdlet 文档。

</div>

<div>

## <a name="configuring-response-group-application"></a>配置响应组应用程序

请参阅示例 ResponseGroupConfiguration。 有关详细信息，请参阅 Lync server 2013 文档和 cmdlet 帮助，了解[Lync server 2013 中的响应组应用程序 cmdlet](https://technet.microsoft.com/en-us/library/gg415654\(v=ocs.15\))。若要查看响应组应用程序配置， `https://<poolfqdn>/RgsConfig/`请参阅，如下图所示。

![响应组配置工具。](images/JJ945610.480a9440-2283-4533-98f8-86daaab4781c(OCS.15).jpg "响应组配置工具。")

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

