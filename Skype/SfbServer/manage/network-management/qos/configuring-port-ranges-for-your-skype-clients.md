---
title: 配置客户端的端口范围和的服务质量策略
ms.reviewer: ''
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48183694
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 本文介绍如何配置端口范围为您的客户端和 Skype 中的配置服务质量策略业务服务器上 Windows 10 运行的客户端。
ms.openlocfilehash: 2e5328406634302a1b076eec8466e7f7b9245150
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881519"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-clients-in-skype-for-business-server"></a>配置端口范围和客户端中的业务服务器 Skype 的服务质量策略

本文介绍如何配置端口范围为您的客户端和 Skype 中的配置服务质量策略业务服务器上 Windows 10 运行的客户端。

## <a name="configure-port-ranges"></a>配置端口范围

默认情况下 Skype 业务客户端应用程序可以使用之间的任何端口的端口 1024年和 65535 之间时涉及的通信会话;这是因为客户端未自动启用特定的端口范围。 若要使用的服务质量，但是，您需要将各种通信类型 （音频、 视频、 媒体、 应用程序共享和文件传输） 重新分配到一系列唯一的端口范围。 这可以通过使用 Set-csconferencingconfiguration cmdlet。

> [!NOTE]  
> 最终用户无法进行这些更改本身。 端口更改仅可通过使用 Set-csconferencingconfiguration cmdlet 的管理员。


您可以确定哪些端口范围当前正在使用的通信会话的业务 Server Management Shell 中运行以下命令从 Skype 中：

    Get-CsConferencingConfiguration

假定具有尚未对会议设置进行任何更改，因为业务服务器安装 Skype，应获得包括这些属性值的信息：

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

仔细查看上述输出中，如果您将看到以下两项的重要性。 首先，ClientMediaPortRangeEnabled 属性设置为 False:

    ClientMediaPortRangeEnabled : False

这是重要的因为当此属性设置为 False，Skype 业务客户端将使用之间的任何可用的端口的端口 1024年和 65535 之间时涉及的通信会话;这是无论任何其他端口设置 （例如，ClientMediaPort 或 ClientVideoPort），则返回 true。 如果您想要将使用率限制为一组指定的端口 （这是您想要执行操作，如果您计划实现服务质量），然后必须先启用客户端媒体端口范围。 可以完成的使用以下 Windows PowerShell 命令：

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

上述命令允许客户端的会议配置设置; 的全局集合的媒体端口范围但是，也可以将这些设置应用于站点作用域和/或服务范围 （对于仅会议服务器服务）。 若要启用客户端媒体端口范围为特定网站或服务器，指定该网站或服务器的标识，调用 Set-csconferencingconfiguration 时：

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

此外，您可以使用此命令同时为所有会议配置设置启用端口范围：

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

您将发现的另一个重要是重要性的，默认情况下的媒体端口范围为每种类型的网络流量，示例输出显示相同：

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

为了实现 QoS，每个这些端口范围需要是唯一的。 例如，您可能配置如下所示的端口范围：


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
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


在前面的表中，客户端端口范围代表的服务器配置的端口范围的子集。 例如，在服务器，应用程序共享已配置为使用端口 40803 到 49151;客户端计算机上应用程序共享被配置为使用通过 42019 42000 的端口。 过，这是主要是为了便于管理的 QoS： 客户端端口不必代表的服务器上使用的端口的子集。 （例如，客户端计算机上您无法配置应用程序共享才能使用，请说，端口通过 10019 10000。）但是，建议您使您的客户端端口范围，您服务器端口范围的子集。

此外，您可能已经注意到用于应用程序共享服务器、 留出设置 8348 端口，但仅 20 个端口已留在客户端上共享的应用程序。 太，这建议，但不严格的规则。 一般情况下，可以考虑每个可用的端口，以表示单个通信会话： 如果您有 100 端口的端口范围，这意味着无法参与问题的计算机中, 可用，最多，100 个通信会话在任何给定时间。 因为服务器很有可能会部件中与客户端的多个详细对话，所以应该打开许多比客户端上的服务器上的多个端口。 设置客户端上共享的应用程序的备用 20 个端口是指用户无法参与 20 应用程序共享会话，在指定的设备，以及所有同时。 应证明足以绝大多数您的用户。

要为您的会议配置设置的全局集合分配上述端口范围，可以使用以下 Skype 业务 Server 命令行管理程序命令：

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

或者，使用此命令分配这些相同的端口范围，您的所有会议配置设置：

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

单个用户必须从 for Business 的 Skype 注销，然后重新登录，才能实际使这些更改生效。

> [!NOTE]  
> 您可以还启用客户端媒体端口范围，并将这些端口范围，使用单个命令。 例如：<BR><CODE>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</CODE>

## <a name="configure-quality-of-service-policies-for-clients-running-on-windows-10"></a>在 Windows 10 上运行的客户端配置服务质量策略

除了指定供您 Skype 业务客户端使用的端口范围，您还必须创建单独的服务质量策略将应用于客户端计算机。 （创建会议、 应用程序和中介服务器的服务质量策略应该不应用到客户端计算机。）此信息仅适用于运行 Skype 业务客户端和 Windows 10 的计算机。

下面的示例使用此端口范围的设置创建音频策略和视频策略：


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
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

若要创建 Windows 10 计算机音频质量的服务策略，首次登录到计算机上已安装组策略管理。 打开组策略管理 （单击**开始**、**管理工具**，，然后单击**组策略管理**），然后完成以下过程：

1.  在组策略管理中，找到应在其中创建新策略的容器。 例如，如果您的所有客户端计算机位于名为客户端 OU，应客户端 OU 中创建新策略。

2.  右键单击相应的容器，然后单击**创建在这个域 GPO 并在此处链接**。

3.  **新建 GPO**对话框中，在**名称**框中，键入新的组策略对象的名称，然后单击**确定**。

4.  右键单击新创建的策略，然后单击**编辑**。

5.  在组策略管理编辑器中，展开**计算机配置**，展开**Windows 设置**、**基于策略的 QoS**，右键单击，然后单击**新建策略**。

6.  在**基于策略的 QoS**对话框中，在打开页上，键入**名称**框中的新策略的名称。 选择**指定 DSCP 值**并将值设置为**46**。 保留未选择，**指定出站调节率**，然后单击**下一步**。

7.  在下一页上，确保选中**所有应用程序**，，然后单击**下一步**。 此设置指示网络以查找所有包的特定应用程序创建的 46，而不仅仅是数据包的 DSCP 标记。

8.  在第三页上，确保同时**任何源 IP 地址**和**任何目标 IP 地址**选中，则，然后单击**下一步**。 这两个设置确保将管理数据包而不考虑哪台计算机 （IP 地址） 发送这些数据包和哪台计算机 （IP 地址） 将接收这些数据包。

9.  在第四页中，从**选择此 QoS 策略应用于的协议**下拉列表中选择**TCP 和 UDP** 。 TCP （传输控制协议） 和 UDP （用户数据报协议） 是最常使用的业务服务器和其客户端应用程序的 Skype 的两个网络协议。

10. 在标题下**指定源端口号**，**从此源端口或范围**中进行选择。 在相应的文本框中，键入供音频传输的端口范围。 例如，如果预留端口 50020 通过端口 50039 音频流量输入使用以下格式的端口范围： **50020:50039**。 单击“**完成**”。

创建音频 QoS 策略后您随后应创建视频的第二个策略。 若要创建视频的策略，请按照相同的基本过程您遵循创建音频策略时, 进行下列替换项操作：

  - 使用其他 （及唯一） 策略名称。

  - 设置为**34**而不是 46 的 DSCP 值。 （如前所述，您无需使用的 DSCP 值 34; 您只需必须分配比音频所使用的是不同的 DSCP 值。）

  - 使用视频流量的以前配置的端口范围。 例如，如果您保留了通过 58019 视频的端口 58000，设置为此的端口范围： **58000:58019**。

如果您决定创建用于管理应用程序共享流量的策略，请进行下列替换项：

  - 使用其他 （及唯一） 策略名称 (例如，**业务服务器应用程序共享的 Skype**)。

  - 设置为**24**而不是 46 的 DSCP 值。 （同样，此值没有为 24; 它只是必须使用音频和视频的 DSCP 值以外的其他。）

  - 使用视频流量的以前配置的端口范围。 例如，如果您保留了通过应用程序共享 42019 端口 42000，设置为此的端口范围： **42000:42019**。

文件传输策略：

  - 使用其他 （及唯一） 策略名称 (例如，**业务 Server 文件传输的 Skype**)。

  - DSCP 值设置为**14**。 （同样，此值没有为 14; 它只是必须是唯一的 DSCP 代码。）

  - 对应用程序中使用以前配置的端口范围。 例如，如果您保留了通过应用程序共享 42039 端口 42020，设置为此的端口范围： **42020:42039**。

组策略已在客户端计算机上刷新，已创建的新策略才会生效。 尽管组策略会自己定期刷新，但你可以在需要刷新组策略的每台计算机上运行以下命令，强制立即刷新：

    Gpudate.exe /force

此命令可以从在管理员凭据下运行的任何命令窗口运行。 若要在管理员凭据下运行命令窗口，请单击“**开始**”，右键单击“**命令提示符**”，然后单击“**以管理员身份运行**”。

请记住这些策略应面向客户端计算机。 它们应不会应用到业务服务器运行 Skype 的服务器。

为了帮助确保使用适当的 DSCP 值标记网络数据包，，还应通过完成以下过程在每台计算机上创建新的注册表项：

1.  单击 **“开始”**，然后单击 **“运行”**。

2.  在**运行**对话框中，键入**regedit**，，然后按 ENTER。

3.  在注册表编辑器中，展开**HKEY\_本地\_计算机**，展开**系统**，展开**CurrentControlSet**，展开**服务**，然后展开**Tcpip**。

4.  右键单击**Tcpip**，指向**新建**，，然后单击**项**。 创建新的注册表项后，键入**QoS**，，，然后按 ENTER 以重命名该项。

5.  右键单击**QoS**，指向**新建**，，然后单击**字符串值**。 创建新的注册表值后，键入**不使用 NLA**，，，然后按 ENTER 以重命名该值。

6.  双击**不使用 NLA**。 **编辑字符串**对话框中，在**值数据**框中，键入**1** ，然后单击**确定**。

7.  关闭注册表编辑器和 eboot 您的计算机。

### <a name="configure-quality-of-service-on-computers-with-multiple-network-adapters"></a>在具有多个网络适配器的计算机上配置服务质量

如果您有多个网络适配器的计算机，您可能会偶尔中运行 DSCP 值所示 0x00 的问题，而不是所配置的值。 这通常会不能够访问您的 Active Directory 域 （例如，如果这些适配器均被使用专用网络） 一个或多个网络适配器的计算机上。 在这样的情况下，DSCP 值标记的适配器的可以访问域，但不是将无法访问域的适配器将标记。

如果您想要包括到您的域，无权访问的适配器的计算机中的所有网络适配器的标记 DSCP 值您需要添加并配置对注册表值。 可通过完成以下过程：

1.  单击 **“开始”**，然后单击 **“运行”**。

2.  在**运行**对话框中，键入**regedit**，，然后按 ENTER。

3.  在注册表编辑器中，展开**HKEY\_本地\_计算机**，展开**系统**，展开**CurrentControlSet**，展开**服务**，然后展开**Tcpip**。

4.  如果看不到标记**QoS** ，然后右键单击**Tcpip**注册表项，指向**新建**，，然后单击**项**。 创建新密钥后，键入**QoS**，，，然后按 ENTER 以重命名该项。

5.  右键单击**QoS**，指向**新建**，，然后单击**字符串值**。 创建新的注册表值后，键入**不使用 NLA**，，，然后按 ENTER 以重命名该值。

6.  双击**不使用 NLA**。 **编辑字符串**对话框中，在**值数据**框中，键入**1** ，然后单击**确定**。

创建并配置新的注册表值之后, 将需要重新启动计算机以使更改生效。

## <a name="see-also"></a>另请参阅

[在 Windows 10 中创建组策略对象](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)
