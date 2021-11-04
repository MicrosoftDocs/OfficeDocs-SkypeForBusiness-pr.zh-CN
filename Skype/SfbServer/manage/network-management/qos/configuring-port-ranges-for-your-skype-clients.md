---
title: 为客户端配置端口范围和服务质量策略
ms.reviewer: ''
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
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
description: 本文介绍如何为客户端配置端口范围，以及如何在 Skype for Business Server 中为在 Windows 10 上运行的客户端配置服务质量策略。
ms.openlocfilehash: b2382a5060d0723f76312a089ab50b0b41314c8e
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60742108"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-clients-in-skype-for-business-server"></a>在客户端中配置端口范围和服务质量Skype for Business Server

本文介绍如何为客户端配置端口范围，以及如何在 Skype for Business Server 中为在 Windows 10 上运行的客户端配置服务质量策略。

## <a name="configure-port-ranges"></a>配置端口范围

默认情况下，Skype for Business客户端应用程序可以在涉及通信会话时使用端口 1024 和 65535 之间的任何端口;这是因为不会为客户端自动启用特定端口范围。 但是，若要使用服务质量，您将需要为一系列特定端口范围重新分配各种通信类型（音频、视频、媒体、应用程序共享和文件传输）。 可使用 Set-CsConferencingConfiguration cmdlet 完成此操作。

> [!NOTE]  
> 最终用户无法自行进行这些更改。 端口更改只能由管理员使用 Set-CsConferencingConfiguration cmdlet 进行。


通过从命令行管理程序内运行以下命令，可以确定当前用于通信会话Skype for Business Server范围：

**Get-CsConferencingConfiguration**

假定自安装会议后未对会议设置Skype for Business Server，应返回包含以下属性值的信息：

ClientMediaPortRangeEnabled ： False<br/>
ClientAudioPort ： 5350<br/>
ClientAudioPortRange ： 40<br/>
ClientVideoPort ： 5350<br/>
ClientVideoPortRange ：40<br/>
ClientAppSharingPort ：5350<br/>
ClientAppSharingPortRange ：40<br/>
ClientFileTransferPort ： 5350<br/>
ClientTransferPortRange ：40<br/>

如果您仔细查看上面的输出，您会发现两点很重要。首先，ClientMediaPortRangeEnabled 属性设置为 False：

**ClientMediaPortRangeEnabled ： False**

这一点很重要，因为当此属性设置为 False 时，Skype for Business客户端将在涉及通信会话时使用端口 1024 和 65535 之间的任何可用端口;无论使用何种其他端口设置， (，例如 ClientMediaPort 或 ClientVideoPort) 。 如果要将用法限制为一组指定的端口 (并且如果计划实施服务质量) ，则希望这样做，则必须先启用客户端媒体端口范围。 可以使用以下命令完成Windows PowerShell操作：

**Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True**

上述命令为会议配置设置的全局集合启用客户端媒体端口范围；但是，这些设置也可应用于站点范围和/或服务范围（仅限会议服务器服务）。若要为特定站点或服务器启用客户端媒体端口范围，请在调用 Set-CsConferencingConfiguration 时指定该站点或服务器的标识：

**Set-CsConferencingConfiguration -Identity "site：Redmond" -ClientMediaPortRangeEnabled $True**

或者，也可以使用此命令同时为您的所有会议配置设置启用端口范围：

**Get-CsConferencingConfiguration |Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True**

您将发现的另一个重要事项是，示例输出显示默认情况下为每种类型的网络通信设置的媒体端口范围是相同的：

ClientAudioPort ： 5350<br/>
ClientVideoPort ： 5350<br/>
ClientAppSharingPort ：5350<br/>
ClientFileTransferPort ： 5350<br/>

若要实施 QoS，其中每个端口范围都需要是唯一的。例如，您可以按如下所示配置端口范围：


<table>
<colgroup>
</colgroup>
<thead>
<tr class="header">
<th>客户端通信类型</th>
<th>起始端口</th>
<th>端口范围</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>音频</p></td>
<td><p>50020</p></td>
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>视频</p></td>
<td><p>58000</p></td>
<td><p>20</p></td>
</tr>
<tr class="odd">
<td><p>应用程序共享</p></td>
<td><p>42000</p></td>
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>文件传输</p></td>
<td><p>42020</p></td>
<td><p>20</p></td>
</tr>
</tbody>
</table>


在上表中，客户端端口范围表示为您的服务器配置的端口范围的一部分。 例如，在服务器上，应用程序共享已配置为使用 40803 和 49151 之间的端口；在客户端计算机上，应用程序共享配置为使用 42000 和 42019 之间的端口。 这样做主要用于简化 QoS 管理：客户端端口不需要表示服务器上使用的端口的子集。  (例如，在客户端计算机上，可以将应用程序共享配置为使用端口 10000 到 10019。) 但是，建议您将客户端端口范围作为服务器端口范围的子集。

另外，您可能已注意到，为服务器上的应用程序共享留出了 8348 个端口，但为客户端上的应用程序共享只留出了 20 个端口。 这也是推荐方法，但不是一种硬性规定。 通常，你可以考虑每个可用的端口来表示单个通信会话：如果端口范围内有 100 个可用端口，这意味着该计算机在任何给定时间最多可以参与 100 个通信会话。 因为服务器参与的会话数可能多于客户端，所以在服务器上打开的端口数应多于在客户端上打开的端口数。 为客户端上的应用程序共享留出 20 个端口意味着用户可以参与指定设备上的 20 个应用程序共享会话，并且所有会话是同时进行的。 对于您的大多数用户来说，这样做应该足够了。

若要将上述端口范围分配给会议配置设置的全局集合，可以使用以下命令行Skype for Business Server命令行管理程序命令：

**Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20**

或者，使用此命令为您的所有会议配置设置分配这些相同的端口范围：

**Get-CsConferencingConfiguration |Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20**

各个用户必须注销Skype for Business然后重新登录，这些更改才能实际生效。

> [!NOTE]  
> 您还可以启用客户端媒体端口范围，然后使用单个命令分配这些端口范围。例如：<BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>

## <a name="configure-quality-of-service-policies-for-clients-running-on-windows-10"></a>为在客户端上运行的客户端配置服务质量Windows 10

除了指定供客户端使用的端口范围Skype for Business，还必须创建将应用于客户端计算机的单独的服务质量策略。  (为会议、应用程序和中介服务器创建的服务质量策略不应应用于客户端计算机。) 此信息仅适用于运行 Skype for Business 客户端和 Windows 10 的计算机。

以下示例使用此端口范围的设置创建音频策略和视频策略：


<table>
<colgroup>
</colgroup>
<thead>
<tr class="header">
<th>客户端通信类型</th>
<th>起始端口</th>
<th>端口范围</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>音频</p></td>
<td><p>50020</p></td>
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>视频</p></td>
<td><p>58000</p></td>
<td><p>20</p></td>
</tr>
<tr class="odd">
<td><p>应用程序共享</p></td>
<td><p>42000</p></td>
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>文件传输</p></td>
<td><p>42020</p></td>
<td><p>20</p></td>
</tr>
</tbody>
</table>

若要为计算机创建服务质量音频Windows 10，请首先登录到安装了组策略管理的计算机。 打开"组策略 (，单击"开始"，指向"管理工具"，然后单击"组策略) ，然后完成以下过程： 

1.  在组策略管理中，找到其中应创建新策略的容器。 例如，如果所有客户端计算机都位于名为"客户端"的 OU 中，应在客户端 OU 中新建策略。

2.  右键单击相应的容器，然后单击"在此域中创建 **GPO"，并在此处链接** 它。

3.  在"**新建 GPO"** 对话框中的"名称"框中，键入新组策略对象的名称，然后单击"确定 **"。**

4.  右键单击新创建的策略，然后单击"编辑 **"。**

5.  在组策略管理编辑器中，展开"计算机配置"，展开 **Windows 设置"，** 右键单击"基于策略的 **QoS"，** 然后单击"**创建新策略"。**

6.  在" **基于策略的 QoS"** 对话框的打开页上，在"名称"框中键入新 **策略** 的名称。 选择“指定 DSCP 值”，并将该值设置为“46”。 将“指定出站调节率”保留为未选中状态，然后单击“下一步”。

7.  On the next page， select **Only applications with this executable name，** enter **Lync.exe** as the name， and then click **Next**. 此设置指示策略仅对来自客户端的匹配Skype for Business优先级。

8.  第三页上，确保选中"任何 **源 IP** 地址"和"任何目标 **IP** 地址"，然后单击"下一步 **"。** 这两个设置确保将管理这些数据包，与哪台计算机（IP 地址）发送这些数据包及哪台计算机（IP 地址）将接收这些数据包无关。

9.  在第四页上，从“选择此 QoS 策略所适用的协议”下拉列表中选择“TCP 和 UDP”。 TCP (传输控制协议) 和 UDP (用户数据报协议) 是 Skype for Business Server 及其客户端应用程序最常使用的两种网络协议。

10. 在标题“指定源端口号”下，选择“从此源端口或范围”。在附带的文本框中，键入为音频传输保留的端口范围。例如，如果您为音频流量保留端口 50020 到端口 50039，则使用以下格式输入端口范围：“50020:50039”。单击“完成”。

在您为音频创建了 QoS 策略后，然后应该为视频创建第二个策略。要为视频创建策略，请按照您创建音频策略时遵循的相同基本过程，进行下列替换项：

  - 使用不同的策略 (和唯) 名称。

  - 将 DSCP 值设置为“34”代替 46。（如先前所述，您不必使用为 34 的 DSCP 值；只是必须分配一个与用于音频不同的 DSCP 值。）

  - 对视频流量使用以前配置的端口范围。 例如，如果为视频保留端口 58000 至 58019，则端口范围设置为 **：58000：58019。**

如果您决定创建用于管理应用程序共享流量的策略，请进行以下替换：

  - 使用不同的策略 (和唯) 策略 (例如，Skype for Business Server **应用程序共享**) 。

  - 将 DSCP 设置为“24”代替 46。（另外，此值不必为 24；只是必须用于不同于音频和视频的 DSCP 值。）

  - 对视频流量使用以前配置的端口范围。 例如，如果为应用程序共享保留了端口 42000 到 42019，则端口范围设置为 **：42000：42019。**

对于文件传输策略：

  - 使用不同的 (和唯) 策略 (例如，Skype for Business Server **文件** 传输) 。

  - 将 DSCP 值设置为“14”。（另外，此值不必为 14；只是它必须为唯一 DSCP 代码。）

  - 使用以前为应用程序配置的端口范围。 例如，如果为应用程序共享保留端口 42020 到 42039，则端口范围设置为 **：42020：42039。**

在客户端计算机上刷新组策略之前，已创建的新策略不会生效。尽管组策略会定期自行刷新，但是您可以通过在需要刷新的组策略所在的每台计算机上运行下列命令来强制立即刷新：

**Gpupdate.exe /force**

可从在管理员凭据下运行的任何命令窗口运行此命令。要在管理员凭据下运行命令窗口，请单击“开始”，右键单击“命令提示符”，然后单击“以管理员身份运行”。

请记住，应该将这些策略指向客户端计算机目标。 它们不应应用于运行 Skype for Business Server。

要确保将网络数据包标记为相应的 DSCP 值，还应该通过完成以下过程在每台计算机上创建新的注册表项：

1.  单击“开始”，然后单击“运行”。

2.  在" **运行** "对话框中，键入 **regedit**，然后按 Enter。

3.  在注册表编辑器中，展开 **"HKEY \_ LOCAL \_ MACHINE"，** 展开 **"系统**"，展开 **"CurrentControlSet"，** 展开 **"服务**"，然后展开 **"Tcpip"。**

4.  右键单击“Tcpip”，指向“新建”，然后单击“项”。 在新建注册表项后，键入 **QoS，** 然后按 Enter 重命名该注册表项。

5.  右键单击“QoS”，指向“新建”，然后单击“字符串值”。 创建新的注册表值后，键入 **"不使用 NLA"，** 然后按 Enter 重命名该值。

6.  双击“不使用 NLA”。 在"**编辑字符串**"对话框中，在"值数据"框中键入 **1，** 然后单击"确定 **"。**

7.  关闭注册表编辑器并引导你的计算机。

### <a name="configure-quality-of-service-on-computers-with-multiple-network-adapters"></a>在具有多个网络适配器的计算机上配置服务质量

如果您的计算机具有多个网络适配器，则有时可能会遇到 DSCP 值显示为 0x00而不是配置的值的问题。 此错误通常会发生在一个或多个网络适配器无法访问 Active Directory 域的计算机上（例如，如果这些适配器用于专用网络）。 如果出现这种情况，则将 DSCP 值标记为使这些适配器可以访问该域，但不会标记为使这些适配器无法访问该域。

如果要标记计算机中所有网络适配器（包括无法访问域的适配器）的 DSCP 值，则需要在注册表中添加和配置值。 这可通过执行下列过程来完成：

1.  单击“开始”，然后单击“运行”。

2.  在" **运行** "对话框中，键入 **regedit**，然后按 Enter。

3.  在注册表编辑器中，展开 **"HKEY \_ LOCAL \_ MACHINE"，** 展开 **"系统**"，展开 **"CurrentControlSet"，** 展开 **"服务**"，然后展开 **"Tcpip"。**

4.  如果没有看到标记为“QoS”的注册表项，则右键单击“Tcpip”，指向“新建”，然后单击“项”。 创建新密钥后，键入 **QoS，** 然后按 Enter 重命名该密钥。

5.  右键单击“QoS”，指向“新建”，然后单击“字符串值”。 创建新的注册表值后，键入 **"不使用 NLA"，** 然后按 Enter 重命名该值。

6.  双击“不使用 NLA”。 在"**编辑字符串**"对话框中，在"值数据"框中键入 **1，** 然后单击"确定 **"。**

创建并配置新注册表值后，需要重新启动计算机，更改才能生效。

## <a name="see-also"></a>另请参阅

[在"策略"中创建组策略Windows 10](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)
