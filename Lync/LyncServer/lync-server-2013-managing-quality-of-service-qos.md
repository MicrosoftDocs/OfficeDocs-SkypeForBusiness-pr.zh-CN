---
title: 在 Lync Server 2013 中管理服务质量 (QoS)
TOCTitle: 在 Lync Server 2013 中管理服务质量 (QoS)
ms:assetid: ab1051c3-8380-4d72-86df-37a61b1e4a41
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg405409(v=OCS.15)
ms:contentKeyID: 49313909
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中管理服务质量 (QoS)

 

_**上一次修改主题：** 2016-12-08_

服务质量 (QoS) 是某些组织中所使用的一种网络技术，目的是有助于针对音频和视频通信提供最佳的最终用户体验。QoS 最常用于带宽有限的网络上：其中大量的网络数据包争用相对数量较小的可用带宽。服务质量为管理员提供一种为承载音频或视频数据的数据包分配较高优先级的方法。通过为这些数据包提供较高的优先级，与涉及诸如文件传输、Web 浏览或数据库备份等内容的网络会话相比，音频和视频通信可能会以更快的速度完成，并且发生更少的中断。这是因为针对用于文件传输或数据库备份的网络数据包分配了“最佳效果”优先级。

> [!NOTE]  
> 一般而言，服务质量仅适用于内部网络上的通信会话。在实施 QoS 时，您可以将服务器和路由器配置为支持数据包标记；但是，应以特定的方式将这些设备配置为支持数据包标记。您不能假设将在 Internet 或其他网络上支持服务质量。即使在其他网络上支持服务质量，也不能保证以配置您的网络上的服务的相同方式来配置 QoS。



Microsoft Lync Server 2013 不需要服务质量；如果您目前未使用 QoS，则不需要在安装 Lync Server 2013 之前先安装该服务。如果在您的网络上发生大量的数据包丢失，建议用来缓解此问题的方法是添加额外的带宽。如果无法添加更多的带宽，您可能想要改为实施服务质量。

Lync Server 2013 提供对服务质量的完全支持：这意味着已使用 QoS 的组织可以轻松地将 Lync Server 集成到他们的现有网络基础结构中。为执行此操作，您必须执行以下任务：

  - [为不基于 Windows 的设备启用 QoS](lync-server-2013-enabling-qos-for-devices-that-are-not-based-on-windows.md)。默认情况下，会针对运行其他操作系统的计算机和其他设备（如 iPhone）禁用 QoS。虽然您可以使用 Lync Server 为设备启用和禁用服务质量，但通常无法使用该产品修改这些设备所使用的 DSCP 代码。

  - [配置会议、应用程序和中介服务器的端口范围](lync-server-2013-configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md)。您必须为不同的数据包类型（如音频和视频）保留一组唯一的端口。比方说，使用 Lync Server 2013，您不能通过将属性值设置为 True 或 False 来启用或禁用服务质量。而是可以通过配置端口范围，然后创建并应用组策略，来启用服务质量。如果您稍后决定不使用 QoS，则只需删除相应的组策略对象，即可“禁用”服务质量。

  - [配置边缘服务器的端口范围](lync-server-2013-configuring-port-ranges-for-your-edge-servers.md)。虽然不需要，但是可以将您的边缘服务器配置为与其他服务器使用相同的端口范围。

  - [配置 Microsoft Lync 客户端的端口范围](lync-server-2013-configuring-port-ranges-for-your-microsoft-lync-clients.md)。这些端口范围仅适用于客户端计算机，并且通常与在您的服务器上配置的端口范围有所不同。

  - [在 Lync Server 2013 中为您的会议、应用程序和中介服务器配置服务质量策略](lync-server-2013-configuring-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers.md)。这些策略可确定应用到不同数据包类型的 DSCP 代码。

  - [配置 A/V 边缘服务器的服务质量策略](lync-server-2013-configuring-a-quality-of-service-policy-for-your-a-v-edge-servers.md)。仅应对边缘服务器的内端执行此操作。原因是服务质量设计用于内部网络而不是 Internet 上。

  - [配置在 Windows 7 或 Windows 8 上运行的客户端的服务质量策略](lync-server-2013-configuring-quality-of-service-policies-for-clients-running-on-windows-7-or-windows-8.md)。请注意，Microsoft Lync Server 2013 不支持将 QoS 用于其他 Windows 操作系统，如 Windows Vista 或 Windows XP。

  - [在 Microsoft Lync Phone Edition 设备上配置服务质量](lync-server-2013-configuring-quality-of-service-on-microsoft-lync-phone-edition-devices.md)。默认情况下，会针对 Lync Phone Edition 设备启用 QoS。但是，您可能想要更改默认 DSCP 值，以确保您的组织中的所有音频数据包均使用相同的 DSCP 代码。

> [!NOTE]  
> 如果使用 Microsoft Windows Server 2012 或 Windows Server 2012 R2，您可能会对可用于在该平台上管理服务质量的新的一组 Windows PowerShell cmdlet 感兴趣。有关详细信息，请参阅“Windows PowerShell 中的网络服务质量 Cmdlet”，网址为 <a href="http://go.microsoft.com/fwlink/p/?linkid=285379">http://go.microsoft.com/fwlink/p/?LinkId=285379</a>。


