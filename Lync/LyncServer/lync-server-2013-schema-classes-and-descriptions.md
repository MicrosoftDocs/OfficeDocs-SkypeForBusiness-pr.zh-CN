---
title: Lync Server 2013：架构类和说明
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Schema classes and descriptions
ms:assetid: 7d43b920-ac37-40cc-adfe-be289bda6e9e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398625(v=OCS.15)
ms:contentKeyID: 48184612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5080af0977457f5c4a75d2f121e75560b0f24524
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764930"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-classes-and-descriptions-in-lync-server-2013"></a>Lync Server 2013 中的架构类和说明

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-30_

本部分介绍 Lync Server 2013 使用的所有架构类。

<div>

## <a name="schema-classes-and-descriptions"></a>架构类和说明


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>种类</th>
<th>说明</th>
<th>备注</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>邮件-收件人</p></td>
<td><p>Exchange 统一消息（UM）电子邮件收件人。</p></td>
<td><p>此辅助类与 Exchange UM 共享。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationContacts</p></td>
<td><p>此类是多个应用程序联系人的容器，并且不包含任何属性本身。</p></td>
<td><p>Microsoft Office 通信服务器 2007 R2 中的新增项。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationServer</p></td>
<td><p>此类包含统一通信应用程序服务（UCAS）实例的服务控制点的条目。</p></td>
<td><p>Office 通信服务器 2007 R2 中的新增项。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationServerService</p></td>
<td><p>此类提供从特定池到其应用程序服务的关联。</p></td>
<td><p>通信服务器 2007 R2 中的新增项。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationServerSettings</p></td>
<td><p>此辅助类到 msRTCSIP-ApplicationServer 保留表示应用程序服务实例的设置的属性。</p></td>
<td><p>通信服务器 2007 R2 中的新增项。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-存档（已过时）</p></td>
<td><p>此辅助类到 msRTCSIP-GlobalContainer 保存与存档相关的所有设置。</p></td>
<td><p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchivingServer （已过时）</p></td>
<td><p>此类表示单个即时消息存档服务器。 在将计算机激活为即时消息存档服务器（如安装了即时消息存档服务的计算机）时，将创建此类的实例。</p></td>
<td><p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ConferenceDirectories</p></td>
<td><p>此类是多个会议目录实例的容器，并且不包含任何属性本身。</p></td>
<td><p>通信服务器 2007 R2 中的新增项。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ConferenceDirectory</p></td>
<td><p>此类包含表示特定会议目录的设置的属性。</p></td>
<td><p>通信服务器 2007 R2 中的新增项。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ConnectionPoint</p></td>
<td><p>通用服务控制点（SCP）将计算机指定为运行 Lync Server 的服务器。</p></td>
<td><p>Lync 2010 中的新增项。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultCWABank</p></td>
<td><p>此辅助类保留 Microsoft Lync Web App bank 的设置。</p></td>
<td><p>通信服务器 2007 R2 中的新增项。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-域</p></td>
<td><p>此类包含用于定义 SIP 注册机构配置的域的属性。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EdgeProxy</p></td>
<td><p>此类容器表示单个访问边缘服务。 由于在外围网络中部署了 Access Edge 服务，并且客户通常不允许从外围网络访问 Active Directory 域服务，因此 Access Edge 服务的实例未联接到 intranet 的 Active Directory 网络。 因此，访问代理服务器不会自动在 AD DS 中注册。 管理员必须手动配置 AD DS 中的每个 Access Edge 服务实例的存在。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnterpriseMCUSettings</p></td>
<td><p>MsRTCSIP 的此辅助类保留表示会议服务器设置的属性。</p></td>
<td><p>Microsoft Office 通信服务器2007中的新增新增服务。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EnterpriseMediationServerSettings</p></td>
<td><p>此辅助类到 msRTCSIP-MediationServer 包含表示中介服务器设置的属性。</p></td>
<td><p>Office 通信服务器2007中的新增项。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnterpriseServerSettings</p></td>
<td><p>此辅助类到 msRTCSIP-服务器保留表示 SIP 服务器设置的属性。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-联合</p></td>
<td><p>此辅助类到 msRTCSIP-GlobalContainer 保存与联盟相关的所有设置。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalContainer</p></td>
<td><p>此类包含适用于整个 Lync Server 部署的所有设置。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-GlobalUserPolicy （已过时）</p></td>
<td><p>此类表示单个 Office 通信服务器会议策略。</p></td>
<td><p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalTopologySetting</p></td>
<td><p>本地全局拓扑设置对象。</p></td>
<td><p>Lync Server 2010 中的新增新增服务。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-GlobalTopologySettings</p></td>
<td><p>用于保存全局拓扑设置对象的容器。</p></td>
<td><p>Lync Server 2010 中的新增新增服务。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocalNormalization</p></td>
<td><p>此类是表示位置规范化规则的实例的容器。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocationContactMapping</p></td>
<td><p>此类由会议助理应用程序创建，并保留用于按地区对会议电话号码进行分类的属性。</p></td>
<td><p>通信服务器 2007 R2 中的新增项。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationContactMappings</p></td>
<td><p>此类是位置联系人映射的多个实例的容器，并且不包含任何属性本身。</p></td>
<td><p>通信服务器 2007 R2 中的新增项。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocationProfile</p></td>
<td><p>此类是一个表示特定位置配置文件的容器。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationProfiles （已过时）</p></td>
<td><p>此类是多个位置配置文件的容器，并且不包含任何属性本身。</p></td>
<td><p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocalNormalizations （已过时）</p></td>
<td><p>此类是多个本地规范化规则的容器，并且不包含任何属性本身。</p></td>
<td><p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCU</p></td>
<td><p>此类表示单个会议服务器。</p></td>
<td><p>通信服务器2007中的新增项。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactories</p></td>
<td><p>此类保存多个 msRTCSIP MCUFactory 类，并且没有属性本身。</p></td>
<td><p>通信服务器2007中的新增项。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUFactory</p></td>
<td><p>此类是一个容器，表示适用于单个媒体类型的会议服务器工厂。 当激活此特定类型和供应商的第一个会议服务器时，将创建此类的实例。</p></td>
<td><p>通信服务器2007中的新增项。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactoryService</p></td>
<td><p>此类提供从特定池到其会议服务器工厂的关联。</p></td>
<td><p>通信服务器2007中的新增项。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MediationServer</p></td>
<td><p>此类包含用于中介服务器的服务控制点的条目。</p></td>
<td><p>通信服务器2007中的新增项。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-会议（已过时）</p></td>
<td><p>此辅助类到 msRTCSIP-GlobalContainer 包含表示可配置的会议设置的属性。</p></td>
<td><p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-移动性</p></td>
<td><p>存储全局移动设置的容器。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MonitoringServer</p></td>
<td><p>此类包含表示单个监视服务器的设置的属性。</p></td>
<td><p>通信服务器 2007 R2 中的新增项。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PhoneRoute （已过时）</p></td>
<td><p>此类是一个容器，表示指向网关或网关集的最低成本路线的实例。 此信息由运行标准版的所有企业池或服务器使用，以最经济高效的方式将传出呼叫路由到公共交换电话网络（PSTN）。</p></td>
<td><p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PhoneRoutes （已过时）</p></td>
<td><p>此类是多个最少的成本路由的容器，并且不包含任何属性本身。</p></td>
<td><p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-政策（已过时）</p></td>
<td><p>此类包含多个 Lync 服务器策略类，并且没有任何属性本身。</p></td>
<td><p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Pool</p></td>
<td><p>此类表示单个 Lync 服务器池。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-池</p></td>
<td><p>此类包含多个 Lync 服务器池，并且没有任何属性本身。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolService</p></td>
<td><p>此类表示池的服务控制 pointservice 控制点。 托管在池中的用户将其 msRTCSIP-PrimaryHomeServer 属性指向此类的实例。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-状态</p></td>
<td><p>存储全局状态设置的容器。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-注册机构</p></td>
<td><p>此辅助类到 msRTCSIP-GlobalContainer 包含表示 SIP 注册机构维护的用户设置的属性。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-RouteUsage （已过时）</p></td>
<td><p>此类是一个容器，表示手机路线使用情况的实例。 电话路由使用类包含一个属性字段和一个说明字段。 属性字段定义使用类型。 "说明" 域允许管理员在手机路线中描述此属性的用法。</p></td>
<td><p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-RouteUsages （已过时）</p></td>
<td><p>此类保留 msRTCSIP 类的多个实例，并且没有任何属性本身。</p></td>
<td><p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-搜索</p></td>
<td><p>此辅助类到 msRTCSIP-GlobalContainer 包含限制和控制搜索结果范围的属性。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-服务器</p></td>
<td><p>此类表示运行 Lync Server 的单个服务器。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-服务</p></td>
<td><p>此类包含全局设置容器和 msRTCSIP 域对象。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedMCU</p></td>
<td><p>此类包含表示受信任的会议服务器的设置的属性。</p></td>
<td><p>通信服务器2007中的新增项。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedMCUs</p></td>
<td><p>此类保留 msRTCSIP 类的多个实例，并且没有任何属性本身。</p></td>
<td><p>通信服务器2007中的新增项。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedProxies</p></td>
<td><p>此类包含多个 msRTCSIP TrustedProxy 类，并且不包含任何属性本身。</p></td>
<td><p>通信服务器2007中的新增项。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedProxy</p></td>
<td><p>此类是一个容器，表示运行代理服务器的服务器。 在加入到 AD DS 的计算机上激活新的代理服务器时，将创建此类的实例。</p></td>
<td><p>通信服务器2007中的新增项。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServer</p></td>
<td><p>此类包含表示受信任服务器的设置的属性。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedService</p></td>
<td><p>此类是一个容器，表示可通过全局可路由用户代理 URI （GRUU）地址进行路由的受信任的服务。 当激活由 Lync Server 信任的新服务器时，将创建此类的实例。 此受信任服务器必须加入 Active Directory 域。</p></td>
<td><p>通信服务器2007中的新增项。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServices</p></td>
<td><p>此类是多个 GRUU 服务器的容器，并且不包含任何属性本身。</p></td>
<td><p>通信服务器2007中的新增项。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedWebComponentsServer</p></td>
<td><p>此类包含表示受信任 web 组件的设置的属性。</p></td>
<td><p>通信服务器2007中的新增项。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedWebComponentsServers</p></td>
<td><p>此类保留 msRTCSIP 类的多个实例，并且没有任何属性本身。</p></td>
<td><p>通信服务器2007中的新增项。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UnifiedCommunications （已过时）</p></td>
<td><p>此辅助类到 msRTCSIP-GlobalContainer 保存与统一通信相关的属性。</p></td>
<td><p>在 Lync Server 2010 中已过时。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-WebComponents</p></td>
<td><p>此类包含 Internet information Server （IIS）的服务控制 pointservice 控制点。 它将服务器标识为 web 组件服务器。</p></td>
<td><p>通信服务器2007中的新增项。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-WebComponentsService</p></td>
<td><p>此类提供从特定池到该池将使用的 web 组件的关联。</p></td>
<td><p>通信服务器2007中的新增项。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-WebComponentSettings</p></td>
<td><p>此辅助类到 msRTCSIP-WebComponents 包含表示 web 组件的设置的属性。</p></td>
<td><p>通信服务器2007中的新增项。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

