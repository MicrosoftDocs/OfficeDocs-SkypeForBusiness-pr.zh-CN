---
title: 为边缘服务器配置端口范围和服务质量
ms.reviewer: ''
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204996(v=OCS.15)
ms:contentKeyID: 48184469
mtps_version: v=OCS.15
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 本文介绍如何为边缘服务器配置端口范围以及如何为 A/V 边缘服务器配置服务质量策略。
ms.openlocfilehash: ae955eb8863f561cc1837b7f0319f7424f13e99c
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60829936"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-edge-servers-in-skype-for-business-server"></a>Configuring port ranges and a Quality of Service policy for your Edge Servers in Skype for Business Server

本文介绍如何为边缘服务器配置端口范围以及如何为 A/V 边缘服务器配置服务质量策略。

## <a name="configure-port-ranges"></a>配置端口范围

使用边缘服务器，不需要为音频、视频和应用程序共享配置单独的端口范围;同样，用于边缘服务器的端口范围也不需要与用于会议、应用程序和中介服务器的端口范围相匹配。 在继续我们的示例之前，必须强调一点，虽然此选项存在，但我们建议您不要更改端口范围，因为如果您从 50000 端口范围中移开，则可能会对一些方案产生不利影响。

例如，假定您已将会议、应用程序和中介服务器配置为使用这些端口范围：


<table>
<colgroup>
</colgroup>
<thead>
<tr class="header">
<th>数据包类型</th>
<th>起始端口</th>
<th>预留的端口数</th>
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
<td><p><strong>总计</strong></p></td>
<td><p>--</p></td>
<td><p>24730</p></td>
</tr>
</tbody>
</table>


可以看到，音频、视频和应用程序共享的端口范围从端口 40803 开始，包含共 24732 个端口。 如果愿意，可以通过从命令行管理程序内运行类似以下命令的命令，将给定边缘服务器配置为使用这些Skype for Business Server值：

  **Set-CsEdgeServer -Identity EdgeServer：atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730**

或者，可使用以下命令同时配置您组织中的所有边缘服务器：

  **Get-CsService -EdgeServer |ForEach-Object {Set-CsEdgeServer -Identity $_。Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}**

可以使用以下命令行管理程序命令验证边缘服务器的当前Skype for Business Server设置：

  **Get-CsService -EdgeServer |Select-Object Identity、MediaCommunicationPortStart、MediaCommunicationPortCount**

同样，虽然我们提供这些选项，但我们强烈建议您保留与端口配置一样的信息。

## <a name="configure-a-qos-policy-for-your-av-edge-servers"></a>为 A/V 边缘服务器配置 QoS 策略

除了为会议、应用程序和中介服务器创建 QoS 策略外，还必须为 A/V 边缘服务器的内部端创建音频和视频策略。 但是，边缘服务器中使用的策略与会议、应用程序和中介服务器中使用的策略不同。 对于会议、应用程序和中介服务器，您指定了源端口范围;使用边缘服务器时，需要指定目标端口范围。 因此，不能简单地将会议、应用程序和中介服务器 QoS 策略应用于边缘服务器：这些策略不起作用。 您必须创建新策略并将这些策略仅应用于边缘服务器。

以下过程介绍创建可用于在边缘服务器上管理服务质量的 Active Directory 组策略对象的过程。 当然，您的边缘服务器可能是没有 Active Directory 帐户的独立服务器。 如果是这样，可以使用本地组策略，而不使用 Active Directory 组策略：唯一的差别是必须使用本地组策略编辑器创建这些本地策略，并且必须在每台边缘服务器上分别创建同一组策略。 若要在边缘服务器上启动本地组策略编辑器，请执行下列操作：

1.  单击“开始”，然后单击“运行”。

2.  在" **运行"** 对话框中，键入 **gpedit.msc，** 然后按 Enter。

如果要创建基于 Active Directory 的策略，应登录已安装“组策略管理”的计算机。 在这种情况下，打开组策略管理 (**单击"开始**"，指向"管理工具"，然后单击"组策略管理) "，然后完成以下步骤： 

1.  在组策略管理中，找到其中应创建新策略的容器。 例如，如果所有Skype for Business Server计算机都位于名为 Skype for Business Server 的 OU 中，应在该 OU 中创建Skype for Business Server策略。

2.  右键单击相应的容器，然后单击"在此域中创建 **GPO"，并在此处链接** 它。

3.  在"**新建 GPO"** 对话框中，在"名称"框中键入新组策略对象的名称 (例如，Skype for Business Server **音频) ，** 然后单击"确定 **"。**

4.  右键单击新创建的策略，然后单击"编辑 **"。**

无论您要创建 Active Directory 策略还是本地策略，此处的过程都相同：

1.  在组策略管理编辑器或本地组策略编辑器中，依次展开“计算机配置”、“策略”和“Windows 设置”，右键单击“基于策略的 QoS”，然后单击“新建策略”。

2.  在"基于策略 **的 QoS"** 对话框的打开页上，键入新策略的名称 (例如，在"名称"框中Skype for Business Server"音频 **) "。** 选择“指定 DSCP 值”，并将该值设置为“46”。 将“指定出站调节率”保留为未选中状态，然后单击“下一步”。

3.  On the next page， make sure that **All applications** is selected， and then click **Next**. 此设置指示该网络查看 DSCP 标记为 46 的所有数据包，不只是由特定应用程序创建的数据包。

4.  第三页上，确保选中"任何 **源 IP** 地址"和"任何目标 **IP** 地址"，然后单击"下一步 **"。** 这两个设置确保将管理这些数据包，与哪台计算机（IP 地址）发送这些数据包及哪台计算机（IP 地址）将接收这些数据包无关。

5.  在第四页上，从“选择此 QoS 策略所适用的协议”下拉列表中选择“TCP 和 UDP”。 TCP (传输控制协议) 和 UDP (用户数据报协议) 是 Skype for Business Server 及其客户端应用程序最常使用的两种网络协议。

6.  在标题“指定目标端口号”下，选择“从此目标端口或范围”。 在对应的文本框中，键入为音频传输保留的端口范围。 例如，如果为音频流量保留端口 49152 到端口 57500，则使用此格式输入端口范围 **：49152：57500。** 单击“完成”。

为音频流量创建 QoS 策略后，应为视频流量创建第二个策略。 要为视频创建策略，请按照您创建音频策略时遵循的相同基本过程，进行下列替换项：

  - 使用不同的 (和唯) 策略 (例如，Skype for Business Server **视频**) 。

  - 将 DSCP 值设置为“34”而不是 46。（注意，不一定要使用 DSCP 值 34。唯一的要求是对视频使用与用于音频的 DSCP 值不同的 DSCP 值。）

  - 对视频流量使用以前配置的端口范围。 例如，如果为视频保留端口 57501 到 65535，请设置端口范围 **：57501：65535。** 同样，应将其配置为目标端口范围。

如果决定创建用于管理应用程序共享通信的策略，则必须创建第三个策略，进行以下替换：

  - 使用不同的策略 (和唯) 策略 (例如，Skype for Business Server **应用程序共享**) 。

  - 将 DSCP 值设置为“24”而不是 46。（同样，不一定要使用 DSCP 值 24。唯一的要求是对应用程序共享使用与用于音频或视频的 DSCP 值不同的 DSCP 值。）

  - 对视频流量使用以前配置的端口范围。 例如，如果为应用程序共享保留了端口 40803 到 49151，则端口范围设置为 **：40803：49151**。

在边缘服务器中刷新组策略之前，您已创建的新策略将不会生效。尽管组策略会定期地自行刷新，但可通过在需要刷新组策略的每台计算机上运行以下命令来强制立即刷新：

 **Gpudate.exe /force**

此命令可以从命令行管理Skype for Business Server运行，也可以从在管理员凭据下运行的任何命令窗口运行。 若要在管理员凭据下运行命令窗口，请单击“开始”，右键单击“命令提示符”，然后单击“以管理员身份运行”。 请注意，即使在运行 Gpudate.exe 之后，您仍然可能需要重新启动边缘服务器。

为了帮助确保用适当的 DSCP 值标记网络数据包，还应通过完成以下过程在每台计算机上创建一个新的注册表项：

1.  单击“开始”，然后单击“运行”。

2.  在" **运行** "对话框中，键入 **regedit**，然后按 Enter。

3.  在注册表编辑器中，展开 **"HKEY \_ LOCAL \_ MACHINE"，** 展开 **"系统**"，展开 **"CurrentControlSet"，** 展开 **"服务**"，然后展开 **"Tcpip"。**

4.  右键单击“Tcpip”，指向“新建”，然后单击“项”。 在新建注册表项后，键入 **QoS，** 然后按 Enter 重命名该注册表项。

5.  右键单击“QoS”，指向“新建”，然后单击“字符串值”。 创建新的注册表值后，键入 **"不使用 NLA"，** 然后按 Enter 重命名该值。

6.  双击“不使用 NLA”。 在"**编辑字符串**"对话框中，在"值数据"框中键入 **1，** 然后单击"确定 **"。**

7.  关闭注册表编辑器并重新启动计算机。
