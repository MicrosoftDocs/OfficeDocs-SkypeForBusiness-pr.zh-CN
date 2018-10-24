---
title: Lync Server 2013：会议的基于位置的路由的配置
TOCTitle: 会议的基于位置的路由的配置
ms:assetid: d8c708cc-a1b1-48b1-808c-a64df15f7701
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Dn362846(v=OCS.15)
ms:contentKeyID: 56271209
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中会议的基于位置的路由的配置

 

_**上一次修改主题：** 2016-12-08_

基于位置的路由会议应用程序依赖于 Lync Server 2013 基于位置的路由的配置。主要配置如下：

  - 加入会议的参与者的位置基于其网络站点进行确定。网络站点及其相关联的网络子网必须在 Lync Server 中定义，以便强制实施基于位置的路由。

  - 要对会议强制实施基于位置的路由，Lync 参与者必须启用基于位置的路由。

  - 要对加入会议的 PSTN 终结点强制实施基于位置的路由，用于连接 PSTN 终结点的 SIP 中继必须配置基于位置的路由。

有关部署和配置 Lync Server 2013 基于位置的路由的详细信息，请参阅[配置基于位置的路由](lync-server-2013-configuring-location-based-routing.md)。

## 配置基于位置的路由会议应用程序

基于位置的路由会议应用程序默认情况下处于禁用状态。在启用此应用程序之前，您需要确定要为该应用程序分配的适当优先级。要确定此优先级，请在 Lync Server 命令行管理程序 中运行以下 cmdlet：

Get-CsServerApplication -Identity Service:Registrar:\<Pool FQDN\>

在此 cmdlet 中，\<池 FQDN\> 是指要在其中启用基于位置的路由会议应用程序的池。

此 cmdlet 将返回 Lync Server 托管的应用程序列表和每个应用程序的优先级值。为基于位置的路由会议应用程序分配的优先级值需要大“UdcAgent”应用程序，而小于“DefaultRouting”、“ExumRouting”和“OutboundRouting”应用程序。建议为基于位置的路由会议应用程序分配的优先级值高于“UdcAgent”应用程序的优先级值。

例如，如果“UdcAgent”应用程序的优先级值为“2”，“DefaultRouting”应用程序的优先级值为“8”，“ExumRouting”应用程序的优先级值为“9”，并且“OutboundRouting”应用程序的优先级值为“10”，那么应为基于位置的路由会议应用程序分配优先级值“3”。这样做将按以下顺序设定应用程序的优先级：其他应用程序（优先级：0 到 1）、“UdcAgent”（优先级：2）、基于位置的路由会议应用程序（优先级：3）、其他应用程序（优先级：4 到 8）、“DefaultRouting”（优先级：9）、“ExumRouting”（优先级：10）和“OutboundRouting”（优先级：11）。

在为基于位置的路由会议应用程序找到正确的优先级值只会，请对托管启用了基于位置的路由的用户的各个前端池或 Standard Edition Server 键入以下 cmdlet：

New-CsServerApplication -Identity Service:Registrar:\<Pool FQDN\>/LBRouting -Priority \<Application Priority\> -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting

例如：

New-CsServerApplication -Identity Service:Registrar:LS2013CU2LBRPool.contoso.com/LBRouting -Priority 3 -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting

使用此 cmdlet 之后，请重新启动池中的所有前端服务器或者启用了基于位置的路由会议应用程序的 Standard Edition Server。

> [!IMPORTANT]  
> 在合适池中的所有前端服务器或 Standard Edition Server 重新启动之后，才会对会议或咨询呼叫转接强制实施基于位置的路由限制。如果在上述 cmdlet 中将 <strong>–Critical</strong> 设置为 <strong>$true</strong>，您的 Lync 服务将立即重新启动。如果不希望这些服务立即重新启动，请到现在为止将 <strong>–Critical</strong> 设置为 <strong>$false</strong>，然后在服务重新启动之后，以后使用 <strong>Set-CsServerApplication</strong> 将 <strong>-Critical</strong> 更改为 <strong>$true</strong>。


一旦成功启用基于位置的路由会议应用程序，并且所有适用的 Lync 服务器已重新启动，由启用了基于位置的路由的 Lync 用户组织的所有会议将受到监视以防止 PSTN 收费绕路情形。

