---
title: 为客户端配置端口范围和服务质量策略
ms.reviewer: ''
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 本文介绍如何为在 Windows 10 上运行的客户端在 Skype for Business Server 中配置客户端的端口范围和配置服务质量策略。
ms.openlocfilehash: ce1690c295f1f5ed991780919370e5dbf5b5d6b1
ms.sourcegitcommit: f7ec026accb0bb91ce62a9d5f24ac4b70a514c4e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/25/2019
ms.locfileid: "35204012"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-clients-in-skype-for-business-server"></a>为 Skype for Business Server 中的客户端配置端口范围和服务质量策略

本文介绍如何为在 Windows 10 上运行的客户端在 Skype for Business Server 中配置客户端的端口范围和配置服务质量策略。

## <a name="configure-port-ranges"></a>配置端口范围

默认情况下, Skype for Business 客户端应用程序可以使用端口1024和65535之间的任何端口参与通信会话;这是因为不会为客户端自动启用特定端口范围。 但是, 为了使用服务质量, 你需要将各种流量类型 (音频、视频、媒体、应用程序共享和文件传输) 重新分配给一系列唯一的端口范围。 可通过使用 CsConferencingConfiguration cmdlet 完成此操作。

> [!NOTE]  
> 最终用户不能自行进行这些更改。 仅管理员可以使用 CsConferencingConfiguration cmdlet 进行端口更改。


通过从 Skype for Business 服务器管理外壳程序中运行以下命令, 可以确定当前用于通信会话的端口范围:

    Get-CsConferencingConfiguration

假设您在安装 Skype for Business 服务器后未对会议设置进行任何更改, 则应返回包含这些属性值的信息:

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

如果仔细查看前面的输出, 您将看到两个重要内容。 首先, ClientMediaPortRangeEnabled 属性设置为 False:

    ClientMediaPortRangeEnabled : False

这很重要, 因为当此属性设置为 False 时, Skype for Business 客户端将在通信会话中涉及到端口1024和65535之间的任何可用端口;无论任何其他端口设置 (例如, ClientMediaPort 或 ClientVideoPort), 都是如此。 如果你想要将使用率限制为指定的一组端口 (如果计划实现服务质量, 则需要执行此操作), 然后必须首先启用客户端媒体端口范围。 可以使用以下 Windows PowerShell 命令执行此操作:

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

前面的命令为会议配置设置的全局集合启用了客户端媒体端口范围;但是, 这些设置也可以应用于网站范围和/或服务范围 (仅适用于会议服务器服务)。 若要启用特定网站或服务器的客户端媒体端口范围, 请在调用 CsConferencingConfiguration 时指定该网站或服务器的标识:

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

或者, 你可以使用此命令同时为所有会议配置设置启用端口范围:

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

你将注意到的第二个重要事项是示例输出显示, 默认情况下, 为每种类型的网络流量设置的媒体端口范围是相同的:

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

为了实现 QoS, 这些端口范围中的每一个都必须是唯一的。 例如, 你可以配置如下所示的端口范围:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>客户端流量类型</th>
<th>端口启动</th>
<th>端口范围</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>音频</p></td>
<td><p>50020</p></td>
<td><p>名</p></td>
</tr>
<tr class="even">
<td><p>视频</p></td>
<td><p>58000</p></td>
<td><p>名</p></td>
</tr>
<tr class="odd">
<td><p>应用程序共享</p></td>
<td><p>42000</p></td>
<td><p>名</p></td>
</tr>
<tr class="even">
<td><p>文件传输</p></td>
<td><p>42020</p></td>
<td><p>名</p></td>
</tr>
</tbody>
</table>


在上表中, 客户端端口范围表示为服务器配置的端口范围的子集。 例如, 在服务器上, 应用程序共享配置为使用端口40803到 49151;在客户端计算机上, 将应用程序共享配置为使用端口42000到42019。 同样, 此操作主要用于简化 QoS 的管理: 客户端端口不必表示服务器上使用的端口子集。 (例如, 在客户端计算机上, 你可以配置要使用的应用程序共享, 例如端口10000到10019。)但是, 建议你将客户端端口范围设置为服务器端口范围的子集。

此外, 你可能已注意到已为服务器上的应用程序共享保留了8348端口, 但仅为客户端上的应用程序共享设置了20个端口。 我们也建议这样做, 但这并不是一种既难又快的规则。 通常, 你可以考虑每个可用的端口来表示单个通信会话: 如果端口范围内有100个端口, 则表示有问题的计算机可以参与, 在任何给定时间最多可参与100个通信会话。 由于服务器可能会涉及比客户端更多的对话, 因此打开服务器上的更多端口比在客户端上更有意义。 在客户端上为应用程序共享设置20个端口意味着, 用户可以同时在指定设备上参与20个应用程序共享会话。 这应该足以满足大多数用户的需要。

若要将之前的端口范围分配给你的会议配置设置的全局集合, 你可以使用以下 Skype for Business Server Management Shell 命令:

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

或者, 使用此命令为所有会议配置设置分配这些相同的端口范围:

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

单个用户必须从 Skype for Business 注销, 然后重新登录才能使这些更改实际生效。

> [!NOTE]  
> 您还可以启用客户端媒体端口范围, 然后使用一个命令分配这些端口范围。 例如：<BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>

## <a name="configure-quality-of-service-policies-for-clients-running-on-windows-10"></a>为在 Windows 10 上运行的客户端配置服务质量策略

除了指定用于 Skype for Business 客户端的端口范围之外, 还必须创建将应用于客户端计算机的单独的服务质量策略。 (为会议、应用程序和中介服务器创建的服务质量策略不应应用于客户端计算机。)此信息仅适用于运行 Skype for Business 客户端和 Windows 10 的计算机。

以下示例使用这组端口范围创建音频策略和视频策略:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>客户端流量类型</th>
<th>端口启动</th>
<th>端口范围</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>音频</p></td>
<td><p>50020</p></td>
<td><p>名</p></td>
</tr>
<tr class="even">
<td><p>视频</p></td>
<td><p>58000</p></td>
<td><p>名</p></td>
</tr>
<tr class="odd">
<td><p>应用程序共享</p></td>
<td><p>42000</p></td>
<td><p>名</p></td>
</tr>
<tr class="even">
<td><p>文件传输</p></td>
<td><p>42020</p></td>
<td><p>名</p></td>
</tr>
</tbody>
</table>

若要创建适用于 Windows 10 计算机的服务质量音频策略, 请首先登录到已安装组策略管理的计算机。 打开组策略管理 (单击 "**开始**", 指向 "**管理工具**", 然后单击 "**组策略管理**"), 然后完成以下过程:

1.  在 "组策略管理" 中, 找到应在其中创建新策略的容器。 例如, 如果所有客户端计算机都位于一个名为 "客户端" 的 OU 中, 则应在客户端 OU 中创建新策略。

2.  右键单击相应的容器, 然后单击 "**在此域中创建 GPO", 然后在此处链接**。

3.  在 "**新建 GPO** " 对话框中, 在 "**名称**" 框中键入新组策略对象的名称, 然后单击 **"确定"**。

4.  右键单击新创建的策略, 然后单击 "**编辑**"。

5.  在组策略管理编辑器中, 展开 "**计算机配置**", 展开 " **Windows 设置**", 右键单击 "**基于策略的 QoS**", 然后单击 "**创建新策略**"。

6.  在 "**基于策略的 QoS** " 对话框中的 "开始" 页面上, 在 "**名称**" 框中键入新策略的名称。 选择 "**指定 DSCP 值**" 并将值设置为**46**。 "退出"**指定出站阻止率**未选中, 然后单击 "**下一步**"。

7.  在下一页上, 选择 "**仅限具有此可执行名称的应用程序**", 输入**Lync**作为名称, 然后单击 "**下一步**"。 此设置指示策略仅优先考虑 Skype for Business 客户端中匹配的流量。

8.  在第三页上, 确保选中了 "**任何来源 ip 地址**" 和 "**任何目标 ip 地址**", 然后单击 "**下一步**"。 这两个设置确保数据包将被管理, 无论哪台计算机 (IP 地址) 发送这些数据包以及哪台计算机 (IP 地址) 将接收这些数据包。

9.  在第4页上, 从 "**选择协议此 QoS 策略应用**于" 下拉列表中选择 " **TCP 和 UDP** "。 TCP (传输控制协议) 和 UDP (用户数据报协议) 是 Skype for Business 服务器及其客户端应用程序最常使用的两种网络协议。

10. 在 "标题" 下,**指定源端口号**, 选择 "**从此源端口或范围**"。 在 "随附文本" 框中, 键入为音频传输保留的端口范围。 例如, 如果您通过端口50039为音频流量保留了端口 50020, 请输入使用以下格式的端口范围: **50020:50039**。 单击“**完成**”。

为音频创建 QoS 策略后, 您应该为视频创建第二个策略。 若要创建视频的策略, 请按照创建音频策略时所遵循的基本过程进行操作, 进行以下替换:

  - 使用不同的 (且唯一的) 策略名称。

  - 将 DSCP 值设置为**34**而不是46。 (如前面所述, 您不必使用 DSCP 值 34; 您只需为用于音频的值分配一个不同的 DSCP 值。)

  - 对视频流量使用以前配置的端口范围。 例如, 如果您已为视频保留端口58000到 58019, 请将端口范围设置为: **58000:58019**。

如果你决定创建用于管理应用程序共享流量的策略, 请执行以下替换:

  - 使用不同 (且唯一) 的策略名称 (例如, **Skype For Business 服务器应用程序共享**)。

  - 将 DSCP 值设置为**24** , 而不是46。 (同样, 此值无需为 24; 它必须与用于音频和视频的 DSCP 值不同。)

  - 对视频流量使用以前配置的端口范围。 例如, 如果你已为应用程序共享保留了端口42000到 42019, 请将端口范围设置为: **42000:42019**。

对于文件传输策略:

  - 使用不同的 (且唯一的) 策略名称 (例如, **Skype For Business 服务器文件传输**)。

  - 将 DSCP 值设置为**14**。 (同样, 此值不必是 14; 它必须是唯一的 DSCP 代码。)

  - 使用以前配置的应用程序端口范围。 例如, 如果你已为应用程序共享保留了端口42020到 42039, 请将端口范围设置为: **42020:42039**。

在客户端计算机上刷新组策略之前, 你创建的新策略将不会生效。 尽管组策略会自己定期刷新，但你可以在需要刷新组策略的每台计算机上运行以下命令，强制立即刷新：

    Gpudate.exe /force

此命令可以从在管理员凭据下运行的任何命令窗口运行。 若要在管理员凭据下运行命令窗口，请单击“**开始**”，右键单击“**命令提示符**”，然后单击“**以管理员身份运行**”。

请记住, 这些策略应面向客户端计算机。 不应将它们应用于运行 Skype for Business Server 的服务器。

为了帮助确保网络数据包使用适当的 DSCP 值进行标记, 还应通过完成以下过程在每台计算机上创建一个新的注册表项:

1.  单击 **“开始”**，然后单击 **“运行”**。

2.  在 "**运行**" 对话框中, 键入**regedit**, 然后按 ENTER。

3.  在注册表编辑器中, 展开 **"\_HKEY\_本地计算机**", 依次展开 "**系统**"、" **CurrentControlSet**"、"**服务**", 然后展开 " **Tcpip**"。

4.  右键单击 " **Tcpip**", 指向 "**新建**", 然后单击 "**项**"。 创建新的注册表项后, 键入**QoS**, 然后按 enter 重命名该项。

5.  右键单击 " **QoS**", 指向 "**新建**", 然后单击 "**字符串值**"。 创建新的注册表值后, 键入 "不**使用 NLA**", 然后按 enter 重命名该值。

6.  双击 "不**使用 NLA**"。 在 "**编辑字符串**" 对话框中, 在 "**值数据**" 框中键入**1** , 然后单击 **"确定"**。

7.  关闭注册表编辑器并 eboot 您的计算机。

### <a name="configure-quality-of-service-on-computers-with-multiple-network-adapters"></a>在具有多个网络适配器的计算机上配置服务质量

如果您有具有多个网络适配器的计算机, 有时可能会遇到问题, 其中 DSCP 值显示为0x00 而不是配置值。 这通常出现在有一个或多个网络适配器无法访问你的 Active Directory 域的计算机上 (例如, 如果这些适配器用于专用网络)。 在此类情况下, 将为可以访问域的适配器标记 DSCP 值, 但不会为无法访问域的适配器标记 DSCP 值。

如果你想要为计算机中的所有网络适配器标记 DSCP 值 (包括对你的域没有访问权限的适配器), 你将需要向注册表添加和配置值。 可通过完成以下过程来执行此操作:

1.  单击 **“开始”**，然后单击 **“运行”**。

2.  在 "**运行**" 对话框中, 键入**regedit**, 然后按 ENTER。

3.  在注册表编辑器中, 展开 **"\_HKEY\_本地计算机**", 依次展开 "**系统**"、" **CurrentControlSet**"、"**服务**", 然后展开 " **Tcpip**"。

4.  如果看不到标记为 " **QoS** " 的注册表项, 请右键单击 " **Tcpip**", 指向 "**新建**", 然后单击 "**项**"。 创建新密钥后, 键入**QoS**, 然后按 enter 重命名该键。

5.  右键单击 " **QoS**", 指向 "**新建**", 然后单击 "**字符串值**"。 创建新的注册表值后, 键入 "不**使用 NLA**", 然后按 enter 重命名该值。

6.  双击 "不**使用 NLA**"。 在 "**编辑字符串**" 对话框中, 在 "**值数据**" 框中键入**1** , 然后单击 **"确定"**。

创建并配置新的注册表值后, 您需要重新启动计算机才能使更改生效。

## <a name="see-also"></a>另请参阅

[在 Windows 10 中创建组策略对象](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)
