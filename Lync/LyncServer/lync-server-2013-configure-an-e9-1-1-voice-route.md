---
title: Lync Server 2013：配置 E9-1-1 语音路由
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure an E9-1-1 voice route
ms:assetid: 6933b840-0e7b-4509-ae43-bc9065677547
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398496(v=OCS.15)
ms:contentKeyID: 48184384
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e0a14c540ca8d9a8655f215449d90716cf6834f3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146555"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-an-e9-1-1-voice-route-in-lync-server-2013"></a>在 Lync Server 2013 中配置 E9-1-1 语音路由

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-17_

若要部署 E9-1-1，首先需配置紧急呼叫语音路由。 有关创建语音路由的详细信息，请参阅[在 Lync Server 2013 中创建语音路由](lync-server-2013-create-a-voice-route.md)。 例如，如果部署包括主要 SIP 中继和辅助 SIP 中继，则可定义多个路由。

<div>


> [!NOTE]  
> 若要在 E9-1-1 INVITE 中包含位置信息，您需要配置连接到 E9-1-1 服务提供商的 SIP 中继以便通过网关路由紧急呼叫。 为此，请在 <STRONG>Set-CsTrunkConfiguration</STRONG> cmdlet 上将 EnablePIDFLOSupport 标志设置为 True。 EnablePIDFLOSupport 的默认值为 False。 例如：<CODE>Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.</CODE><BR>无需为回退公用电话交换网 (PSTN) 网关和紧急位置标识号 (ELIN) 网关启用接收位置。



</div>

有关使用语音路由的详细信息，请参阅 Lync Server 命令行管理程序文档中的以下 cmdlet：

  - **CsPstnUsage**

  - **CsPstnUsage**

  - **新 CsVoiceRoute**

  - **CsVoiceRoute**

  - **CsVoiceRoute**

  - **CsVoiceRoute**

<div>

## <a name="to-configure-an-e9-1-1-voice-route"></a>配置 E9-1-1 语音路由

1.  使用 RTCUniversalServerAdmins 组成员或 CsVoiceAdministrator 管理角色成员帐户登录计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

3.  运行以下 cmdlet 以创建新的 PSTN 用法记录。
    
    该名称必须与将用于位置策略中的 **PSTN** 设置的名称相同。 尽管部署中将具有多个电话用法记录，但以下示例将“紧急用法”添加到可用 PSTN 用法的当前列表。 有关详细信息，请参阅[在 Lync Server 2013 中配置语音策略和 PSTN 用法记录以授权呼叫功能和权限](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)。
    
        Set-CsPstnUsage -Usage @{add='EmergencyUsage'}

4.  运行以下 cmdlet 以使用上一步中创建的 PSTN 用法记录来创建新的语音路由。
    
    该号码模式必须与位置策略中的“紧急拨号字符串”**** 设置中使用的号码模式相同。 "+" 符号是必需的，因为 Lync 将 "+" 添加到紧急呼叫中。 “Co1-pstngateway-1”是用于 E9-1-1 服务提供商或 ELIN 网关服务 ID 的 SIP 中继服务 ID。 以下示例将“EmergencyRoute”用作语音路由的名称。
    
        New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}

5.  （可选）对于 SIP 中继连接，建议运行以下 cmdlet 为由 E9-1-1 服务提供商的 SIP 中继不处理的呼叫创建本地路由。如果 E9-1-1 服务提供商的连接不可用，则使用此路由。
    
    以下示例假定用户的语音策略中具有“本地”用法。
    
        New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}

</div>

</div>

<span> </span>

</div>

</div>

</div>

