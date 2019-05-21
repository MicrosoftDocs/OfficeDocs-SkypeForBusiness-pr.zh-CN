---
title: 为 Edge 服务器配置端口范围和服务质量
ms.reviewer: ''
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204996(v=OCS.15)
ms:contentKeyID: 48184469
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 本文介绍如何配置边缘服务器的端口范围以及如何为你的 A/V 边缘服务器配置服务质量策略。
ms.openlocfilehash: e918dfd371b007741b73312c20033ab911422529
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279459"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-edge-servers-in-skype-for-business-server"></a>为 Skype for Business Server 中的 Edge 服务器配置端口范围和服务质量策略

本文介绍如何配置边缘服务器的端口范围以及如何为你的 A/V 边缘服务器配置服务质量策略。

## <a name="configure-port-ranges"></a>配置端口范围

通过 Edge 服务器, 你无需为音频、视频和应用程序共享配置单独的端口范围;同样, 用于边缘服务器的端口范围不必与你的会议、应用程序和中介服务器使用的端口范围相匹配。 在继续本示例之前, 很重要的一点是, 虽然此选项存在, 但我们建议您不要更改端口范围, 因为如果移出50000端口范围, 这可能会对某些方案产生负面影响。

例如, 假设您已将您的会议、应用程序和中介服务器配置为使用这些端口范围:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>数据包类型</th>
<th>起始端口</th>
<th>保留的端口数</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>应用程序共享</p></td>
<td><p>40803</p></td>
<td><p>8348</p></td>
</tr>
<tr class="even">
<td><p>音频</p></td>
<td><p>49152</p></td>
<td><p>8348</p></td>
</tr>
<tr class="odd">
<td><p>视频</p></td>
<td><p>57500</p></td>
<td><p>8034</p></td>
</tr>
<tr class="even">
<td><p><strong>求和</strong></p></td>
<td><p>--</p></td>
<td><p>24730</p></td>
</tr>
</tbody>
</table>


正如你所看到的, 音频、视频和应用程序共享的端口范围从端口40803开始, 总共包括24732个端口。 如果你愿意, 可以将给定的边缘服务器配置为使用这些整体端口值, 方法是从 Skype for Business 服务器管理外壳程序中运行类似于此的命令:

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

或者, 使用以下命令同时配置组织中的所有边缘服务器:

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

你可以使用此 Skype for Business Server Management Shell 命令验证你的 Edge 服务器的当前端口设置:

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

同样, 虽然我们提供这些选项, 但我们强烈建议你将其保留为用于端口配置的操作。

## <a name="configure-a-qos-policy-for-your-av-edge-servers"></a>为您的 A/V 边缘服务器配置 QoS 策略

除了为你的会议、应用程序和中介服务器创建 QoS 策略之外, 还必须为你的 A/V 边缘服务器的内部端创建音频和视频策略。 但是, 你的 Edge 服务器上使用的策略与你的会议、应用程序和中介服务器上使用的策略不同。 对于会议、应用程序和中介服务器, 你指定了源端口范围;在 "边缘服务器" 中, 你需要指定目标端口范围。 因此, 你不能直接将会议、应用程序和中介服务器 QoS 策略应用到你的边缘服务器: 这些策略根本不起作用。 相反, 你必须创建新策略并将这些策略应用到 Edge 服务器。

以下过程介绍了创建可用于管理边缘服务器上的服务质量的 Active Directory 组策略对象的过程。 当然, 您的边缘服务器可能是没有 Active Directory 帐户的独立服务器。 如果是这种情况, 则可以使用本地组策略, 而不是 Active Directory 组策略: 唯一的区别在于必须使用本地组策略编辑器创建这些本地策略, 并且必须在每个边缘服务器上分别创建相同的策略集。 若要启动边缘服务器上的本地组策略编辑器, 请执行下列操作:

1.  单击 **“开始”**，然后单击 **“运行”**。

2.  在 "**运行**" 对话框中, 键入 " **gpedit.msc**", 然后按 ENTER。

如果你要创建基于 Active Directory 的策略, 则应登录到已安装组策略管理的计算机。 在这种情况下, 请打开组策略管理 (单击 "**开始**", 指向 "**管理工具**", 然后单击 "**组策略管理**"), 然后完成以下步骤:

1.  在 "组策略管理" 中, 找到应在其中创建新策略的容器。 例如, 如果所有 Skype for business 服务器计算机都位于名为 "Skype for business 服务器" 的 OU 中, 则应在 Skype for business Server OU 中创建新策略。

2.  右键单击相应的容器, 然后单击 "**在此域中创建 GPO", 然后在此处链接**。

3.  在 "**新建 GPO** " 对话框中, 在 "**名称**" 框中键入新组策略对象的名称 (例如, **Skype for business Server 音频**), 然后单击 **"确定"**。

4.  右键单击新创建的策略, 然后单击 "**编辑**"。

无论您是在创建 Active Directory 策略还是本地策略, 该过程都是相同的:

1.  在组策略管理编辑器或本地组策略编辑器中, 展开 "**计算机配置**", 展开 "**策略**", 展开 " **Windows 设置**", 右键单击 "**基于策略的 QoS**", 然后单击 "**创建新策略**"。

2.  在 "**基于策略的 QoS** " 对话框中的 "开始" 页面上, 在 "**名称**" 框中键入新策略的名称 (例如, **Skype for business Server 音频**)。 选择 "**指定 DSCP 值**" 并将值设置为**46**。 "退出"**指定出站阻止率**未选中, 然后单击 "**下一步**"。

3.  在下一页上, 确保已选中 "**所有应用程序**", 然后单击 "**下一步**"。 此设置指示网络查找 DSCP 标记为46的所有数据包, 而不仅仅是由特定应用程序创建的数据包。

4.  在第三页上, 确保选中了 "**任何来源 ip 地址**" 和 "**任何目标 ip 地址**", 然后单击 "**下一步**"。 这两个设置确保数据包将被管理, 无论哪台计算机 (IP 地址) 发送这些数据包以及哪台计算机 (IP 地址) 将接收这些数据包。

5.  在第4页上, 从 "**选择协议此 QoS 策略应用**于" 下拉列表中选择 " **TCP 和 UDP** "。 TCP (传输控制协议) 和 UDP (用户数据报协议) 是 Skype for Business 服务器及其客户端应用程序最常使用的两种网络协议。

6.  在 "标题" 下,**指定目标端口号**, 选择 "**从此目标端口或范围**"。 在 "随附文本" 框中, 键入为音频传输保留的端口范围。 例如, 如果您通过端口57500为音频流量保留了端口 49152, 请使用以下格式输入端口范围: **49152:57500**。 单击“**完成**”。

为音频流量创建 QoS 策略后, 应为视频流量创建第二个策略。 若要创建视频的策略, 请按照创建音频策略时所遵循的基本过程进行操作, 进行以下替换:

  - 使用不同 (且唯一) 的策略名称 (例如, **Skype For Business 服务器视频**)。

  - 将 DSCP 值设置为**34**而不是46。 (请注意, 您不必使用34的 DSCP 值。 唯一的要求是对视频使用的 DSCP 值与用于音频的值不同。)

  - 对视频流量使用以前配置的端口范围。 例如, 如果您已为视频保留端口57501到 65535, 请将端口范围设置为: **57501:65535**。 同样, 应将此配置为目标端口范围。

如果你决定创建用于管理应用程序共享流量的策略, 则必须创建第三个策略, 从而进行以下替换:

  - 使用不同 (且唯一) 的策略名称 (例如, **Skype For Business 服务器应用程序共享**)。

  - 将 DSCP 值设置为**24** , 而不是46。 (同样, 您无需使用 DSCP 值24。 唯一的要求是对应用程序共享使用的 DSCP 值与音频或视频使用的 DSCP 值不同。)

  - 对视频流量使用以前配置的端口范围。 例如, 如果你已为应用程序共享保留了端口40803到 49151, 请将端口范围设置为: **40803:49151**。

在边缘服务器上刷新组策略之前, 你创建的新策略将不会生效。 尽管组策略会自己定期刷新，但你可以在需要刷新组策略的每台计算机上运行以下命令，强制立即刷新：

    Gpudate.exe /force

此命令可以从 Skype for Business 服务器内运行, 也可以从任何运行在 "管理员凭据" 下的命令窗口运行。 若要在管理员凭据下运行命令窗口，请单击“**开始**”，右键单击“**命令提示符**”，然后单击“**以管理员身份运行**”。 请注意, 即使在运行 Gpudate 后, 你也可能需要重启 Edge 服务器。

为了帮助确保网络数据包使用适当的 DSCP 值进行标记, 还应通过完成以下过程在每台计算机上创建一个新的注册表项:

1.  单击 **“开始”**，然后单击 **“运行”**。

2.  在 "**运行**" 对话框中, 键入**regedit**, 然后按 ENTER。

3.  在注册表编辑器中, 展开 **"\_HKEY\_本地计算机**", 依次展开 "**系统**"、" **CurrentControlSet**"、"**服务**", 然后展开 " **Tcpip**"。

4.  右键单击 " **Tcpip**", 指向 "**新建**", 然后单击 "**项**"。 创建新的注册表项后, 键入**QoS**, 然后按 enter 重命名该项。

5.  右键单击 " **QoS**", 指向 "**新建**", 然后单击 "**字符串值**"。 创建新的注册表值后, 键入 "不**使用 NLA**", 然后按 enter 重命名该值。

6.  双击 "**不使用 NLA**"。 在 "**编辑字符串**" 对话框中, 在 "**值数据**" 框中键入**1** , 然后单击 **"确定"**。

7.  关闭注册表编辑器, 然后重新启动计算机。
