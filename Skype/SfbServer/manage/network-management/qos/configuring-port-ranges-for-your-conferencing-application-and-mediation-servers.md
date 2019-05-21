---
title: 为你的会议、应用程序和中介服务器配置端口范围和服务质量策略
ms.reviewer: ''
ms:assetid: 4d6eaa5d-0127-453f-be6a-e55384772d83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204872(v=OCS.15)
ms:contentKeyID: 48184074
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 本文介绍如何为你的会议、应用程序和中介服务器配置端口范围和服务质量策略。
ms.openlocfilehash: e0bd6092792a9ed813aadecc004f58830bc5b133
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279458"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers"></a>为你的会议、应用程序和中介服务器配置端口范围和服务质量策略

本文介绍如何为你的会议、应用程序和中介服务器配置端口范围和服务质量策略。

## <a name="configure-port-ranges"></a>配置端口范围

若要实现服务质量, 你应该在你的会议、应用程序和中介服务器上配置与音频、视频和应用程序共享相同的端口范围;此外, 这些端口范围不得以任何方式重叠。 若要使用一个简单的示例, 请假设你在你的会议服务器上使用端口10000到10999获取视频。 这意味着你还必须为应用程序和中介服务器上的视频保留端口10000到10999。 如果不这样做, QoS 将不会按预期工作。

同样, 假设您为视频保留了端口10000到 10999, 但随后为音频保留了端口10500至11999。 这可能会导致服务质量出现问题, 因为端口范围重叠。 使用 QoS, 每个模态必须具有一组独特的端口: 如果将端口10000到10999用于视频, 则必须使用不同的范围 (例如, 11000 到 11999, 适用于音频)。

默认情况下, 在 Skype for Business 服务器中, 音频和视频端口范围不重叠;但是, 分配给应用程序共享的端口范围与音频和视频端口范围重叠。 (反过来, 这意味着这些范围都不是唯一的。)你可以通过在 Skype for Business Server Management Shell 中运行以下三个命令来验证你的会议、应用程序和中介服务器的现有端口范围:

    Get-CsService -ConferencingServer | Select-Object Identity, AudioPortStart, AudioPortCount, VideoPortStart, VideoPortCount, AppSharingPortStart, AppSharingPortCount
    
    Get-CsService -ApplicationServer | Select-Object Identity, AudioPortStart, AudioPortCount
    
    Get-CsService -MediationServer | Select-Object Identity, AudioPortStart, AudioPortCount

> [!WARNING]  
> 正如您在前面的命令中所看到的, 每个端口类型 (音频、视频和应用程序共享) 都分配有两个单独的属性值: 端口开始和端口计数。 端口启动指示用于该模态的第一个端口;例如, 如果音频端口开始等于 50000, 则表示音频流量使用的第一个端口是端口50000。 如果音频端口计数为 2 (这是一个无效的值, 但在此处用于说明用途), 则意味着只有两个端口分配给音频。 如果第一个端口是端口 50000, 并且总共有两个端口, 则意味着第二个端口必须是端口 50001 (端口范围必须保持连续)。 因此, 音频的端口范围将是端口50000到 50001 (包括端口到)。<BR><br>请注意, 应用服务器和中介服务器仅支持音频的 QoS;无需在应用程序服务器或中介服务器中更改视频或应用程序共享端口。

如果你运行上述三个命令, 你将看到 "Skype for Business" 服务器的默认端口值配置如下:

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>属性</th>
<th>会议服务器</th>
<th>应用程序服务器</th>
<th>中介服务器</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AudioPortStart</p></td>
<td><p>49152</p></td>
<td><p>49152</p></td>
<td><p>49152</p></td>
</tr>
<tr class="even">
<td><p>AudioPortCount</p></td>
<td><p>8348</p></td>
<td><p>8348</p></td>
<td><p>8348</p></td>
</tr>
<tr class="odd">
<td><p>VideoPortStart</p></td>
<td><p>57501</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p>VideoPortCount</p></td>
<td><p>8034</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="odd">
<td><p>ApplicationSharingPortStart</p></td>
<td><p>49152</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
<tr class="even">
<td><p>ApplicationSharingPortCount</p></td>
<td><p>16383</p></td>
<td><p>--</p></td>
<td><p>--</p></td>
</tr>
</tbody>
</table>

如前所述, 在配置用于 QoS 的 Skype for Business 服务器端口时, 你应该确保: 1) 音频端口设置在你的所有会议、应用程序和中介服务器上完全相同;和 2) 端口范围不重叠。 如果仔细查看上表, 您将看到端口范围在三种服务器类型中相同。 例如, 每个服务器类型上的起始音频端口设置为端口 49152, 并且每台服务器中为音频保留的端口总数也相同: 8348。 但是, 端口范围重叠: 音频端口从端口49152开始, 但将为应用程序共享预留端口。 为了获得最佳使用服务质量, 应将应用程序共享重新配置为使用唯一的端口范围。 例如, 你可以将应用程序共享配置为从端口40803开始, 并使用8348端口。 (为什么是8348端口？ 如果将这些值一起添加-40803 + 8348-这意味着应用程序共享将通过端口49150使用端口40803。 由于音频端口不会在端口49152开始, 因此你将不再有任何重叠的端口范围。)

选择了应用程序共享的新端口范围后, 您可以使用 CsConferencingServer cmdlet 进行更改。 无需在应用程序服务器或中介服务器上进行此更改, 因为这些服务器不处理应用程序共享流量。 如果你决定重新分配用于音频流量的端口, 则只需在这些服务器上更改端口值。

若要修改单个会议服务器上的应用程序共享的端口值, 请在 Skype for Business Server Management Shell 中运行与此类似的命令:

    Set-CsConferenceServer -Identity ConferencingServer:atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348

如果要在所有的会议服务器上进行这些更改, 可以改为运行以下命令:

    Get-CsService -ConferencingServer | ForEach-Object {Set-CsConferenceServer -Identity $_.Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}

更改端口设置后, 你应该停止并重新启动受更改影响的每个服务。

不强制您的会议服务器、应用程序服务器和中介服务器共享完全相同的端口范围;唯一的真正要求是, 您可以在所有服务器上留出唯一的端口范围。 但是, 如果你在所有服务器上使用相同的端口集, 管理通常会更容易。

## <a name="configure-a-quality-of-service-policy-in-skype-for-business-server-for-your-conferencing-application-and-mediation-servers"></a>在 Skype for Business Server for 你的会议、应用程序和中介服务器中配置服务质量策略

通过配置端口范围, 可确保指定类型的所有流量 (例如, 所有音频流量) 通过同一组端口传播, 从而促进服务质量的使用。 这使系统可以轻松识别和标记给定数据包: 如果端口49152是为音频流量保留的, 则通过端口49152传送的任何数据包都可以使用 DSCP 代码进行标记, 以指示这是音频数据包。 这使路由器能够将数据包识别为音频数据包, 并为其提供比未标记数据包更高的优先级 (如用于将文件从一台服务器复制到另一台服务器的数据包)。

但是, 仅将一组端口限制为特定类型的流量不会导致数据包传播到使用相应 DSCP 代码标记的这些端口。 除了定义端口范围之外, 还必须创建服务策略的质量策略, 以指定与每个端口范围关联的 DSCP 代码。 对于 Skype for business 服务器, 这通常意味着创建两个策略: 一个用于音频, 另一个用于视频。

通过使用组策略, 最轻松地创建和管理服务质量策略。 (也可以使用本地安全策略创建这些相同的策略。 但是, 这要求你在每台计算机上重复相同的过程。)QoS 策略的初始集 (一个用于音频, 另一个用于视频) 应仅应用于运行会议服务器、应用服务器和/或中介服务器服务的 Skype for business 服务器计算机。 如果所有这些计算机都位于同一个 Active Directory OU 中, 则只需将新的组策略对象 (GPO) 分配给该 OU 即可。 或者, 你可以执行其他步骤将新策略定向到指定的计算机;例如, 你可以将相应的计算机放置在安全组中, 然后使用组策略安全筛选功能将 GPO 仅应用于该安全组。

若要创建用于管理音频的服务质量策略, 请登录到已安装组策略管理的计算机。 打开组策略管理 (单击 "**开始**", 指向 "**管理工具**", 然后单击 "**组策略管理**"), 然后完成以下过程:

1.  在 "组策略管理" 中, 找到应在其中创建新策略的容器。 例如, 如果所有 Skype for Business 服务器计算机都位于名为 "Skype for business 服务器" 的 OU 中, 则应在 Skype for Business Server OU 中创建新策略。

2.  右键单击相应的容器, 然后单击 "**在此域中创建 GPO", 然后在此处链接**。

3.  在 "**新建 GPO** " 对话框中, 在 "**名称**" 框中键入新组策略对象的名称 (例如, **Skype for business 服务器 QoS**), 然后单击 **"确定"**。

4.  右键单击新创建的策略, 然后单击 "**编辑**"。

5.  在组策略管理编辑器中, 展开 "**计算机配置**", 展开 "**策略**", 展开 " **Windows 设置**", 右键单击 "**基于策略的 QoS**", 然后单击 "**创建新策略**"。

6.  在 "**基于策略的 QoS** " 对话框中的 "开始" 页面上, 在 "**名称**" 框中键入新策略的名称 (例如, **Skype for business Server QoS**)。 选择 "**指定 DSCP 值**" 并将值设置为**46**。 "退出"**指定出站阻止率**未选中, 然后单击 "**下一步**"。

7.  在下一页上, 确保已选中 "**所有应用程序**", 然后单击 "**下一步**"。 这只是确保所有应用程序都将指定端口范围中的数据包与指定的 DSCP 代码相匹配。

8.  在第三页上, 确保选中了 "**任何来源 ip 地址" 和 "任何目标 ip 地址**", 然后单击 "**下一步**"。 这两个设置确保数据包将被管理, 无论哪台计算机 (IP 地址) 发送这些数据包以及哪台计算机 (IP 地址) 将接收这些数据包。

9.  在第4页上, 从 "**选择协议此 QoS 策略应用**于" 下拉列表中选择 " **TCP 和 UDP** "。 TCP (传输控制协议) 和 UDP (用户数据报协议) 是 Skype for Business 服务器及其客户端应用程序最常使用的两种网络协议。

10. 在 "标题" 下,**指定源端口号**, 选择 "**从此源端口或范围**"。 在 "随附文本" 框中, 键入为音频传输保留的端口范围。 例如, 如果您通过端口57500为音频流量保留了端口 49152, 请使用以下格式输入端口范围: **49152:57500**。 单击“**完成**”。

> [!NOTE]  
> 46的 DSCP 值有一定的作用: 尽管 DSCP 46 通常用于标记音频数据包, 但您不必使用 DSCP 46 进行音频通信。 如果你已实现 QoS, 并且使用的是不同的音频 DSCP 代码 (例如, DSCP 40), 则应将你的服务质量策略配置为使用相同的代码 (例如, 40 表示音频)。 如果您刚刚实现服务质量, 建议您对音频使用 DSCP 46, 只是因为该值通常用于标记音频数据包。

为音频流量创建 QoS 策略后, 您应该为视频通信创建第二个策略 (也可以是用于管理应用程序共享流量的第三个策略)。 若要创建视频的策略, 请按照创建音频策略时所遵循的基本过程进行操作, 进行以下替换:

  - 使用不同 (且唯一) 的策略名称 (例如, **Skype For Business 服务器视频**)。

  - 将 DSCP 值设置为**34**而不是46。 (请注意, 您不必使用34的 DSCP 值。 唯一的要求是对视频使用的 DSCP 值与用于音频的值不同。)

  - 对视频流量使用以前配置的端口范围。 例如, 如果您已为视频保留端口57501到 65535, 请将端口范围设置为: **57501:65535**。

如果你决定创建用于管理应用程序共享流量的策略, 则必须创建第三个策略, 从而进行以下替换:

  - 使用不同 (且唯一) 的策略名称 (例如, **Skype For Business 服务器应用程序共享**)。

  - 将 DSCP 值设置为**24** , 而不是46。 (同样, 您无需使用 DSCP 值24。 唯一的要求是对应用程序共享使用的 DSCP 值与音频或视频使用的 DSCP 值不同。)

  - 对视频流量使用以前配置的端口范围。 例如, 如果你已为应用程序共享保留了端口40803到 49151, 请将端口范围设置为: **40803:49151**。

在 Skype for business 服务器计算机上刷新组策略之前, 你创建的新策略将不会生效。 尽管组策略会自己定期刷新，但你可以在需要刷新组策略的每台计算机上运行以下命令，强制立即刷新：

    Gpupdate.exe /force

此命令可通过 Skype for Business 服务器命令行管理程序或在 "管理员凭据" 下运行的任何命令窗口中运行。 若要在管理员凭据下运行命令窗口，请单击“**开始**”，右键单击“**命令提示符**”，然后单击“**以管理员身份运行**”。

若要验证是否已应用新的 QoS 策略, 请执行下列操作:

1.  在 Skype for business 服务器计算机上, 单击 "**开始**", 然后单击 "**运行**"。

2.  在 "**运行**" 对话框中, 键入**regedit**, 然后按 ENTER。

3.  在注册表编辑器中, 展开 "**计算机**", 依次展开 " **\_HKEY 本地\_计算机**"、"**软件**"、"**策略**"、" **Microsoft**"、" **Windows**", 然后单击 " **QoS**"。 在 " **QoS** " 下, 你应该看到刚才创建的每个 QoS 策略的注册表项。 例如, 如果你创建了两个新策略 (一个名为 Skype for business 服务器音频 QoS 和另一个命名的 Skype for business 服务器视频 QoS), 则应查看 Skype for business Server 音频 QoS 和 Skype for business server 视频 qos 的注册表项。

为了帮助确保网络数据包使用适当的 DSCP 值进行标记, 还应通过完成以下过程在每台计算机上创建一个新的注册表项:

1.  单击 **“开始”**，然后单击 **“运行”**。

2.  在 "**运行**" 对话框中, 键入**regedit**, 然后按 ENTER。

3.  在注册表编辑器中, 展开 **"\_HKEY\_本地计算机**", 依次展开 "**系统**"、" **CurrentControlSet**"、"**服务**", 然后展开 " **Tcpip**"。

4.  右键单击 " **Tcpip**", 指向 "**新建**", 然后单击 "**项**"。 创建新的注册表项后, 键入**QoS**, 然后按 enter 重命名该项。

5.  右键单击 " **QoS**", 指向 "**新建**", 然后单击 "**字符串值**"。 创建新的注册表值后, 键入 "不**使用 NLA**", 然后按 enter 重命名该值。

6.  双击 "不**使用 NLA**"。 在 "**编辑字符串**" 对话框中, 在 "**值数据**" 框中键入**1** , 然后单击 **"确定"**。

7.  关闭注册表编辑器, 然后重新启动计算机。
