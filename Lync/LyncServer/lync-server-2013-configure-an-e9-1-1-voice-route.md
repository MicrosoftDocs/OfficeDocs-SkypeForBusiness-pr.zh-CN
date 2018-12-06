---
title: 在 Lync Server 2013 中配置 E9-1-1 语音路由
TOCTitle: 在 Lync Server 2013 中配置 E9-1-1 语音路由
ms:assetid: 6933b840-0e7b-4509-ae43-bc9065677547
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398496(v=OCS.15)
ms:contentKeyID: 49313145
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中配置 E9-1-1 语音路由

 

_**上一次修改主题：** 2012-09-17_

若要部署 E9-1-1，首先需配置紧急呼叫语音路由。有关创建语音路由的详细信息，请参阅[在 Lync Server 2013 中创建语音路由](lync-server-2013-create-a-voice-route.md)。例如，如果部署包括主要 SIP 中继和辅助 SIP 中继，则可定义多个路由。

> [!NOTE]  
> 若要在 E9-1-1 INVITE 中包含位置信息，您需要配置连接到 E9-1-1 服务提供商的 SIP 中继以便通过网关路由紧急呼叫。为此，请在 <strong>Set-CsTrunkConfiguration</strong> cmdlet 上将 EnablePIDFLOSupport 标志设置为 True。EnablePIDFLOSupport 的默认值为 False。例如：<code>Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.</code><br />
无需为回退公用电话交换网 (PSTN) 网关和紧急位置标识号 (ELIN) 网关启用接收位置。



有关使用语音路由的详细信息，请参阅 Lync Server 命令行管理程序文档中的以下 cmdlet：

  - **Set-CsPstnUsage**

  - **Get-CsPstnUsage**

  - **New-CsVoiceRoute**

  - **Get-CsVoiceRoute**

  - **Set-CsVoiceRoute**

  - **Remove-CsVoiceRoute**

## 配置 E9-1-1 语音路由

1.  使用 RTCUniversalServerAdmins 组成员或 CsVoiceAdministrator 管理角色成员帐户登录计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  运行以下 cmdlet 以创建新的 PSTN 用法记录。
    
    该名称必须与将用于位置策略中的 **PSTN** 设置的名称相同。尽管部署中将具有多个电话用法记录，但以下示例将“紧急用法”添加到可用 PSTN 用法的当前列表。有关详细信息，请参阅[在 Lync Server 2013 中配置语音策略和 PSTN 用法记录以授权呼叫功能和权限](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)。
    
        Set-CsPstnUsage -Usage @{add='EmergencyUsage'}

4.  运行以下 cmdlet 以使用上一步中创建的 PSTN 用法记录来创建新的语音路由。
    
    该号码模式必须与位置策略中的“紧急拨号字符串”设置中使用的号码模式相同。由于 Lync 已将“+”添加到紧急呼叫，因此需要“+”符号。“Co1-pstngateway-1”是用于 E9-1-1 服务提供商或 ELIN 网关服务 ID 的 SIP 中继服务 ID。以下示例将“EmergencyRoute”用作语音路由的名称。
    
        New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}

5.  （可选）对于 SIP 中继连接，建议运行以下 cmdlet 为由 E9-1-1 服务提供商的 SIP 中继不处理的呼叫创建本地路由。如果 E9-1-1 服务提供商的连接不可用，则使用此路由。
    
    以下示例假定用户的语音策略中具有“本地”用法。
    
        New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}

