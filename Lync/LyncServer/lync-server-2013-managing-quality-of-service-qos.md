---
title: Lync Server 2013：管理服务质量（QoS）
ms.reviewer: ''
f1.keywords:
- NOCSH
TOCTitle: Managing Quality of Service (QoS)
author: lanachin
ms.author: v-lanac
ms.manager: serdars
ms:assetid: ab1051c3-8380-4d72-86df-37a61b1e4a41
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg405409(v=OCS.15)
ms:contentKeyID: 48185049
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce88471361c63fde3ebf8a3ea716a140567e722e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725582"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-quality-of-service-qos-in-lync-server-2013"></a>在 Lync Server 2013 中管理服务质量（QoS）

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-11-07_

服务质量（QoS）是在某些组织中使用的网络技术，可帮助为音频和视频通信提供最佳的最终用户体验。 QoS 最常用于带宽受限的网络：有大量的网络数据包（这些数据包的可用带宽相对较少），服务质量为管理员提供了一种为数据包分配更高优先级的方式。携带音频或视频数据。 通过为这些数据包提供更高优先级，音频和视频通信可能会更快、更少中断，而不是涉及文件传输、web 浏览或数据库备份等内容的网络会话。 这是因为用于文件传输或数据库备份的网络数据包被分配了 "最大努力" 优先级。

<div>


> [!NOTE]  
> 作为一般规则，服务质量仅适用于内部网络上的通信会话。 实现 QoS 时，配置服务器和路由器以支持数据包标记;但是，你可以配置这些设备以支持以特定方式标记数据包。 您无法假定在 Internet 或其他网络上不支持该服务质量。 即使在其他网络上支持优质 if 服务，也不能保证 QoS 的配置方式与您在网络上配置该服务的方式相同。



</div>

Microsoft Lync Server 2013 不需要服务质量;如果当前未使用 QoS，则不需要在安装 Lync Server 2013 之前安装该服务。 如果你在网络上遇到大量数据包丢失，建议的缓解此问题的方法是增加额外带宽。 如果无法增加更多的带宽，则你可能希望改为实现服务质量。

Lync Server 2013 提供全面的服务质量支持：这意味着已使用 QoS 的组织可以轻松地将 Lync Server 集成到其现有网络基础结构中。 若要执行此操作，必须执行以下任务：

  - [在 Lync Server 2013 中为不基于 Windows 的设备启用 QoS](lync-server-2013-enabling-qos-for-devices-that-are-not-based-on-windows.md)。 默认情况下，会针对运行其他操作系统的计算机和其他设备（如 iPhone）禁用 QoS。 尽管可以使用 Lync Server 启用和禁用设备的服务质量，但通常无法使用该产品修改这些设备使用的 DSCP 代码。

  - [在 Lync Server 2013 中为您的会议、应用程序和中介服务器配置端口范围](lync-server-2013-configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md)。 您必须为不同的数据包类型（如音频和视频）保留一组唯一的端口。 使用 Lync Server 2013，您不能通过将属性值设置为 True 或 False 来启用或禁用服务质量。 而是通过配置端口范围，然后创建和应用组策略来启用服务质量。 如果稍后决定不使用 QoS，您只需通过删除相应的组策略对象即可 "禁用" 服务质量。

  - [在 Lync Server 2013 中为 Edge 服务器配置端口范围](lync-server-2013-configuring-port-ranges-for-your-edge-servers.md)。 虽然不需要，但是可以将您的边缘服务器配置为与其他服务器使用相同的端口范围。

  - [在 Lync Server 2013 中为您的 Microsoft Lync 客户端配置端口范围](lync-server-2013-configuring-port-ranges-for-your-microsoft-lync-clients.md)。 这些端口范围仅适用于客户端计算机，并且通常与服务器上配置的端口范围不同。

  - [为你的会议、应用程序和中介服务器在 Lync Server 2013 中配置服务质量策略](lync-server-2013-configuring-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers.md)。 这些策略确定了应用于不同数据包类型的 DSCP 代码。

  - [在 Lync Server 2013 中为您的 a/V 边缘服务器配置服务质量策略](lync-server-2013-configuring-a-quality-of-service-policy-for-your-a-v-edge-servers.md)。 仅应对边缘服务器的内端执行此操作。 这是因为 "服务质量" 专用于在内部网络上使用，而不是在 Internet 上使用。

  - [在 Lync Server 2013 中为运行在 Windows 7 或 windows 8 上的客户端配置服务质量策略](lync-server-2013-configuring-quality-of-service-policies-for-clients-running-on-windows-7-or-windows-8.md)。 请注意，Microsoft Lync Server 2013 不支持其他 Windows 操作系统（如 Windows Vista 或 Windows XP）的 QoS。

  - [在 Lync Server 2013 中配置 Microsoft Lync Phone Edition 设备上的服务质量](lync-server-2013-configuring-quality-of-service-on-microsoft-lync-phone-edition-devices.md)。 默认情况下，将为 Lync Phone Edition 设备启用 QoS。 但是，你可能需要更改默认 DSCP 值，以确保你的组织中的所有音频数据包都使用相同的 DSCP 代码。

<div>


> [!NOTE]  
> 如果你使用的是 Microsoft Windows Server 2012 或 Windows Server 2012 R2，你可能会对可用于管理该平台上的服务质量的新的一组 Windows PowerShell cmdlet 感兴趣。 有关详细信息，请参阅 Windows PowerShell 中的网络服务 Cmdlet 的[https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps](https://docs.microsoft.com/powershell/module/netqos/?view=winserver2012-ps)网络质量。



</div>

</div>

<span> </span>

</div>

</div>

</div>

