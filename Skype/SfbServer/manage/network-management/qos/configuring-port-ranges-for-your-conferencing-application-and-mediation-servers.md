---
title: 为会议、应用程序和中介服务器配置端口范围和服务质量策略
ms.reviewer: ''
ms:assetid: 4d6eaa5d-0127-453f-be6a-e55384772d83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204872(v=OCS.15)
ms:contentKeyID: 48184074
mtps_version: v=OCS.15
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 本文介绍如何为会议、应用程序和中介服务器配置端口范围和服务质量策略。
ms.openlocfilehash: 6785756af5c79eb27d2b4e15b86155d1d58bbc88
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60760720"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-conferencing-application-and-mediation-servers"></a>为会议、应用程序和中介服务器配置端口范围和服务质量策略

本文介绍如何为会议、应用程序和中介服务器配置端口范围和服务质量策略。

## <a name="configure-port-ranges"></a>配置端口范围

若要实现服务质量，应为会议、应用程序和中介服务器上音频、视频和应用程序共享配置相同的端口范围;此外，这些端口范围不得以任何方式重叠。 为了使用简单示例，假定您在会议服务器上将端口 10000 至 10999 用于视频。 这意味着，您还必须在应用程序和中介服务器上为视频保留 10000 至 10999 这些端口。 如果不这样做，QoS 将不会按预期工作。

同样，假定您为视频保留了端口 10000 至 10999，但之后为音频保留了端口 10500 至 11999。 这会产生服务质量问题，因为端口范围重叠。 对于 QoS，每种形式必须具有一组唯一的端口：如果将端口 10000 至 10999 用于视频，则必须对音频) 使用不同的范围 (例如，11000 到 11999。

默认情况下，音频和视频端口范围不会在Skype for Business Server;但是，分配给应用程序共享的端口范围与音频和视频端口范围重叠。  (反过来，这意味着这些范围都不是唯一的。) 可以通过从 Skype for Business Server 命令行管理程序中运行以下三个命令来验证会议、应用程序和中介服务器的现有端口范围：

  Get-CsService -ConferencingServer |Select-Object Identity、AudioPortStart、AudioPortCount、VideoPortStart、VideoPortCount、AppSharingPortStart、AppSharingPortCount
    
  Get-CsService -ApplicationServer |Select-Object Identity、AudioPortStart、AudioPortCount
    
  Get-CsService -MediationServer |Select-Object Identity、AudioPortStart、AudioPortCount

> [!WARNING]  
> 正如您在上面的命令中看到的，每种端口类型（音频、视频和应用程序共享）将分配有两个不同的属性值：起始端口和端口计数。 起始端口指示用于相应形式的第一个端口；例如，如果音频起始端口等于 50000，则意味着用于音频通信的第一个端口为端口 50000。 如果音频端口计数为 2， (不是有效值，但在此处用于演示) ，这意味着仅为音频分配了两个端口。 如果第一个端口为端口 50000 并且总共有两个端口，则意味着第二个端口必须为端口 50001（端口范围必须是连续的）。 因此，音频的端口范围将为 50000 到 50001（包括 50000 和 50001）。<BR><br>注意，应用程序服务器和中介服务器仅支持音频的服务质量；您无需更改应用程序服务器或中介服务器中的视频或应用程序共享端口。

如果运行上述三个命令，将看到以下配置了Skype for Business Server端口值：

<table>
<colgroup>
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

如前所述，为 QoS Skype for Business Server端口时，应确保：1) 会议、应用程序和中介服务器中的音频端口设置相同;和 2) 端口范围不重叠。 如果您仔细查看上表，您将发现这三种服务器类型中的端口范围相同。 例如，起始音频端口在每个服务器类型上设置为端口 49152，并且每个服务器中为音频保留的总端口数也相同：8348。 但是，端口范围重叠：音频端口从端口 49152 开始，但为应用程序共享留出的端口也重叠。 为了充分利用服务质量，应重新配置应用程序共享以使用唯一的端口范围。 例如，可以将应用程序共享配置为从端口 40803 开始并使用 8348 端口。  (为什么使用 8348 端口？ 如果将这些值一起添加 -- 40803 + 8348 ， 这意味着应用程序共享将使用端口 40803 到端口 49150。 由于音频端口直到端口 49152 才会开始，因此您将不再具有任何重叠的端口范围。) 

选择应用程序共享的新端口范围后，可以使用 Set-CsConferencingServer cmdlet 进行更改。 此更改无需在应用程序服务器或中介服务器上进行，因为这些服务器不会处理应用程序共享流量。 如果您决定重新分配用于音频通信的端口，则只需更改这些服务器上的端口值。

若要修改单个会议服务器上应用程序共享的端口值，请从命令行管理程序内运行类似Skype for Business Server命令：

  **Set-CsConferenceServer -Identity ConferencingServer：atl-cs-001.litwareinc.com -AppSharingPortStart 40803 -AppSharingPortCount 8348**

如果要在所有会议服务器上进行这些更改，可以改为运行此命令：

  **Get-CsService -ConferencingServer |ForEach-Object {Set-CsConferenceServer -Identity $_。Identity -AppSharingPortStart 40803 -AppSharingPortCount 8348}**

更改端口设置后，应停止并重新启动受更改影响的每项服务。

会议服务器、应用程序服务器和中介服务器不必共享完全相同的端口范围；您唯一必须做的是在所有服务器上留出唯一的端口范围。但是，如果您在所有服务器上使用相同的端口集，则管理一般会更加轻松。

## <a name="configure-a-quality-of-service-policy-in-skype-for-business-server-for-your-conferencing-application-and-mediation-servers"></a>在 Skype for Business Server 中为会议、应用程序和中介服务器配置服务质量策略

配置端口范围通过确保指定类型的所有流量（例如，所有音频流量）通过同一组端口进行传输来方便服务质量的使用。这使系统标识和标记给定数据包变得容易：如果端口 49152 是为音频通信保留的，则通过端口 49152 的所有数据包均可使用 DSCP 代码进行标记，以指示这是一个音频数据包。反过来，这使路由器能将此数据包标识为一个音频数据包，并为其提供比未标记数据包更高的优先级（如用于将文件从一台服务器复制到另一台服务器的数据包）。

但是，简单地将一组端口限制为特定类型的流量不会产生通过那些使用适当的 DSCP 代码标记的端口的数据包。 除了定义端口范围之外，还必须创建指定要与每个端口范围关联的 DSCP 代码的服务质量策略。 例如Skype for Business Server，这通常意味着创建两个策略：一个策略用于音频，另一个策略用于视频。

通过使用组策略，可轻松创建和管理服务质量策略。 （还可使用本地安全策略创建这些相同的策略。 但是，这要求您在每台计算机上重复相同的过程。) 初始 QoS 策略集 (一组用于音频，一组用于视频) 应仅应用于运行会议服务器、应用程序服务器和/或中介服务器服务的 Skype for Business Server 计算机。 如果所有这些计算机都位于同一个 Active Directory OU 中，则只需向该 OU 分配新的组策略 (GPO) 组策略对象。 或者，您也可以执行其他步骤将新策略定向到指定计算机；例如，您可将相应计算机放在某个安全组中，然后使用组策略安全筛选将 GPO 应用于该安全组。

若要创建用于管理音频的服务质量策略，请登录到安装了组策略管理的计算机。 打开组策略管理（单击“开始”，指向“管理工具”，然后单击“组策略管理”），然后完成下列过程：

1.  在组策略管理中，找到其中应创建新策略的容器。 例如，如果所有Skype for Business Server计算机都位于名为 Skype for Business Server 的 OU 中，则新策略应在 Skype for Business Server OU 中创建。

2.  右键单击相应的容器，然后单击"在此域中创建 **GPO"，并在此处链接** 它。

3.  在"**新建 GPO"** 对话框中，在"名称"框中键入新组策略对象的名称 (例如，Skype for Business Server **QoS**) ，然后单击"确定 **"。**

4.  右键单击新创建的策略，然后单击"编辑 **"。**

5.  在组策略管理编辑器中，依次展开“计算机配置”、“策略”和“Windows 设置”， 右键单击“基于策略的 QoS”，然后单击“创建新策略”。

6.  在"基于策略 **的 QoS"** 对话框的打开页上，键入新策略的名称 (例如，在"名称"框中键入 Skype for Business Server **QoS**) 。  选择“指定 DSCP 值”，并将该值设置为“46”。 将“指定出站调节率”保留为未选中状态，然后单击“下一步”。

7.  On the next page， make sure that **All applications** is selected， and then click **Next**. 这将确保所有应用程序与指定端口范围内带有指定 DSCP 代码的数据包匹配。

8.  第三页上，确保选中"任何 **源 IP** 地址"和"任何目标 IP 地址"，然后单击"下一步 **"。** 这两个设置确保将管理这些数据包，与哪台计算机（IP 地址）发送这些数据包及哪台计算机（IP 地址）将接收这些数据包无关。

9.  在第四页上，从“选择此 QoS 策略所适用的协议”下拉列表中选择“TCP 和 UDP”。 TCP (传输控制协议) 和 UDP (用户数据报协议) 是 Skype for Business Server 及其客户端应用程序最常使用的两种网络协议。

10. 在标题“指定源端口号”下，选择“从此源端口或范围”。 在附带的文本框中，键入为音频传输保留的端口范围。 例如，如果为音频流量保留端口 49152 到端口 57500，则使用此格式输入端口范围 **：49152：57500。** 单击“完成”。

> [!NOTE]  
> DSCP 值“46”有一定程度任意性：虽然 DSCP 46 通常用于标记音频数据包，但您不一定要使用 DSCP 46 进行音频通信。 如果已实施 QoS，并且对音频 (（例如 DSCP 40) ）使用不同的 DSCP 代码，则应该将服务质量策略配置为使用相同的代码 (即 40 用于音频) 。 如果正在实现服务质量，则建议对音频使用 DSCP 46，这只是因为此值常用于标记音频数据包。

为音频流量创建 QoS 策略后，应为视频流量创建第二个策略 (（可选）第三个策略来管理应用程序共享流量) 。 要为视频创建策略，请按照您创建音频策略时遵循的相同基本过程，进行下列替换项：

  - 使用不同的策略 (和) 策略 (，例如Skype for Business Server **视频**) 。

  - 将 DSCP 值设置为“34”而不是 46。（注意，不一定要使用 DSCP 值 34。唯一的要求是对视频使用与用于音频的 DSCP 值不同的 DSCP 值。）

  - 对视频流量使用以前配置的端口范围。 例如，如果为视频保留端口 57501 到 65535，请设置端口范围 **：57501：65535。**

如果决定创建用于管理应用程序共享通信的策略，则必须创建第三个策略，进行以下替换：

  - 使用不同的策略 (和唯) 策略 (例如，Skype for Business Server **应用程序共享**) 。

  - 将 DSCP 值设置为“24”而不是 46。（同样，不一定要使用 DSCP 值 24。唯一的要求是对应用程序共享使用与用于音频或视频的 DSCP 值不同的 DSCP 值。）

  - 对视频流量使用以前配置的端口范围。 例如，如果为应用程序共享保留了端口 40803 到 49151，则端口范围设置为 **：40803：49151**。

在计算机中刷新组策略之前，已创建的新策略Skype for Business Server生效。 尽管组策略会定期自行刷新，但是您可以通过在需要刷新的组策略所在的每台计算机上运行下列命令来强制立即刷新：

  **Gpupdate.exe /force**

此命令可以从命令行管理程序Skype for Business Server运行，也可以从在管理员凭据下运行的任何命令窗口中运行。 若要在管理员凭据下运行命令窗口，请单击“开始”，右键单击“命令提示符”，然后单击“以管理员身份运行”。

若要验证是否已应用新的 QoS 策略，请执行下列操作：

1.  在Skype for Business Server计算机上，单击"**开始"，** 然后单击"运行 **"。**

2.  在" **运行** "对话框中，键入 **regedit**，然后按 Enter。

3.  在注册表编辑器中 **，展开计算机**，展开 **HKEY LOCAL \_ \_ MACHINE，** 展开 **SOFTWARE，** 展开 **策略**，**展开 Microsoft，** 展开 **Windows**，然后单击 **QoS**。 在“QoS”下，您应看到刚刚创建的每个 QoS 策略对应的注册表项。 例如，如果您创建了两个新策略 (一个名为 Skype for Business Server Audio QoS，另一个名为 Skype for Business Server Video QoS) ，您应看到 Skype for Business Server Audio QoS 和 Skype for Business Server Video QoS 的注册表项。

要确保将网络数据包标记为相应的 DSCP 值，还应该通过完成以下过程在每台计算机上创建新的注册表项：

1.  单击“开始”，然后单击“运行”。

2.  在" **运行** "对话框中，键入 **regedit**，然后按 Enter。

3.  在注册表编辑器中，展开 **"HKEY \_ LOCAL \_ MACHINE"，** 展开 **"系统**"，展开 **"CurrentControlSet"，** 展开 **"服务**"，然后展开 **"Tcpip"。**

4.  右键单击“Tcpip”，指向“新建”，然后单击“项”。 在新建注册表项后，键入 **QoS，** 然后按 Enter 重命名该注册表项。

5.  右键单击“QoS”，指向“新建”，然后单击“字符串值”。 创建新的注册表值后，键入 **"不使用 NLA"，** 然后按 Enter 重命名该值。

6.  双击“不使用 NLA”。 在"**编辑字符串**"对话框中，在"值数据"框中键入 **1，** 然后单击"确定 **"。**

7.  关闭注册表编辑器并重新启动计算机。
