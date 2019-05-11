---
title: 配置边缘服务器的端口范围和服务质量
ms.reviewer: ''
ms:assetid: 6f0ae442-6624-4e3f-849a-5b9e387fb8cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204996(v=OCS.15)
ms:contentKeyID: 48184469
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 本文介绍如何配置边缘服务器的端口范围以及如何配置服务质量策略 a / V 边缘服务器。
ms.openlocfilehash: 38fb71f995b1e4569b1bae11cc809ff0c5b358cc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33913074"
---
# <a name="configuring-port-ranges-and-a-quality-of-service-policy-for-your-edge-servers-in-skype-for-business-server"></a>配置端口范围和 Skype 业务服务器在边缘服务器的服务质量策略

本文介绍如何配置边缘服务器的端口范围以及如何配置服务质量策略 a / V 边缘服务器。

## <a name="configure-port-ranges"></a>配置端口范围

与边缘服务器，您不必配置单独的端口范围的音频、 视频和应用程序共享;同样，用于边缘服务器的端口范围没有匹配用于您的会议、 应用程序和中介服务器的端口范围。 我们继续进行我们的示例之前，请务必压力时存在此选项，建议您更改端口范围，如这可能会影响某些情况下，如果移动超出 50000 端口范围。

例如，假设您已配置的会议、 应用程序和中介服务器要使用这些端口范围：


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
<td><p><strong>汇总</strong></p></td>
<td><p>--</p></td>
<td><p>24730</p></td>
</tr>
</tbody>
</table>


您可以看到，您的端口范围的音频、 视频和应用程序共享端口 40803 处开始，并包含总共 24732 端口。 如果您愿意，您可以配置给定的边缘服务器，使用这些总体来运行 Business Server 命令行管理程序命令与此类似从中 Skype 端口值：

    Set-CsEdgeServer -Identity EdgeServer:atl-edge-001.litwareinc.com -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730

或者，使用以下命令同时配置您的组织中的所有边缘服务器：

    Get-CsService -EdgeServer | ForEach-Object {Set-CsEdgeServer -Identity $_.Identity -MediaCommunicationPortStart 40803 -MediaCommunicationPortCount 24730}

您可以使用此 Skype 业务 Server 命令行管理程序命令验证边缘服务器的当前端口设置：

    Get-CsService -EdgeServer | Select-Object Identity, MediaCommunicationPortStart, MediaCommunicationPortCount

同样，虽然我们执行提供这些选项，我们强烈建议您保持不变的端口配置操作。

## <a name="configure-a-qos-policy-for-your-av-edge-servers"></a>QoS 策略配置 a / V 边缘服务器

除了创建 QoS 策略会议、 应用程序和中介服务器，还必须创建音频和视频策略的内部端 A / V 边缘服务器。 但是，边缘服务器上使用的策略与具有不同会议、 应用程序和中介服务器上使用的策略。 会议、 应用程序和中介服务器，您指定的源端口范围;与边缘服务器，您需要指定的目标端口范围。 因此，不能只需将会议、 应用程序和中介服务器 QoS 策略应用到边缘服务器： 这些策略只需将不起作用。 相反，您必须创建新策略，并将这些策略应用于边缘服务器仅。

以下过程介绍创建用于管理边缘服务器上的服务质量的 Active Directory 组策略对象的过程。 当然，则可能边缘服务器是独立服务器不具有 Active Directory 帐户。 如果是这样，您可以使用本地组策略，而不是 Active Directory 组策略： 唯一的区别是，您必须创建使用本地组策略编辑器中，这些本地策略，并分别必须在每台边缘服务器上创建一组相同的策略。 要开始在边缘服务器上的本地组策略编辑器，请执行以下操作：

1.  单击 **“开始”**，然后单击 **“运行”**。

2.  在**运行**对话框中，键入**gpedit.msc**，，然后按 ENTER。

如果您正在创建基于 Active Directory 的策略，然后您应登录到计算机上已安装组策略管理。 在这种情况下，打开组策略管理 （单击**开始**、**管理工具**，，然后单击**组策略管理**），然后完成以下步骤：

1.  在组策略管理中，找到应在其中创建新策略的容器。 例如，如果您的业务服务器计算机的所有 Skype 都位于业务服务器命名 Skype OU 中，新策略应创建在 Skype 对于业务服务器 OU。

2.  右键单击相应的容器，然后单击**创建在这个域 GPO 并在此处链接**。

3.  **新建 GPO**对话框中，在 (例如，**对于业务服务器音频的 Skype**)，**名称**框中键入新的组策略对象的名称，然后单击**确定**。

4.  右键单击新创建的策略，然后单击**编辑**。

从此处的过程是相同无论您创建的 Active Directory 策略还是本地策略：

1.  在组策略管理编辑器或本地组策略编辑器中，表中，展开**计算机配置**、 展开**策略**、 **Windows 设置**数据，右键单击**基于策略的 QoS**，，然后单击**创建新策略**。

2.  在**基于策略的 QoS**对话框中，在打开页上，键入**名称**框中的新策略 (例如，**对于业务服务器音频的 Skype**) 的名称。 选择**指定 DSCP 值**并将值设置为**46**。 保留未选择，**指定出站调节率**，然后单击**下一步**。

3.  在下一页上，确保选中**所有应用程序**，，然后单击**下一步**。 此设置指示网络以查找所有包的特定应用程序创建的 46，而不仅仅是数据包的 DSCP 标记。

4.  在第三页上，确保同时**任何源 IP 地址**和**任何目标 IP 地址**选中，则，然后单击**下一步**。 这两个设置确保将管理数据包而不考虑哪台计算机 （IP 地址） 发送这些数据包和哪台计算机 （IP 地址） 将接收这些数据包。

5.  在第四页中，从**选择此 QoS 策略应用于的协议**下拉列表中选择**TCP 和 UDP** 。 TCP （传输控制协议） 和 UDP （用户数据报协议） 是最常使用的业务服务器和其客户端应用程序的 Skype 的两个网络协议。

6.  在标题下**指定目标端口号**，**从此目标端口或范围**中进行选择。 在相应的文本框中，键入供音频传输的端口范围。 例如，如果预留端口 49152 到音频流量的端口 57500，输入使用以下格式的端口范围： **49152:57500**。 单击“**完成**”。

在创建音频流量的 QoS 策略后，您应创建视频流量的第二个策略。 若要创建视频的策略，请按照相同的基本过程您遵循创建音频策略时, 进行下列替换项操作：

  - 使用其他 （及唯一） 策略名称 (例如， **Skype 业务 Server 视频**)。

  - 设置为**34**而不是 46 的 DSCP 值。 （请注意，不需要使用 34 DSCP 值。 唯一的要求是不是用于音频，视频使用不同的 DSCP 值。）

  - 使用视频流量的以前配置的端口范围。 例如，如果您保留了端口 57501 到 65535 视频，设置为此的端口范围： **57501:65535**。 同样，这应配置为目标端口范围。

如果您决定创建用于管理应用程序共享流量的策略，则必须创建第三方策略，进行以下替代：

  - 使用其他 （及唯一） 策略名称 (例如，**业务服务器应用程序共享的 Skype**)。

  - 设置为**24**而不是 46 的 DSCP 值。 （同样，您不需要使用 DSCP 值，共 24 部分。 唯一的要求。 您可用于不同的 DSCP 值应用程序共享比使用音频或视频）

  - 使用视频流量的以前配置的端口范围。 例如，如果您保留了端口 40803 到 49151 应用程序共享，设置为此的端口范围： **40803:49151**。

组策略已在边缘服务器上刷新，已创建的新策略才会生效。 尽管组策略会自己定期刷新，但你可以在需要刷新组策略的每台计算机上运行以下命令，强制立即刷新：

    Gpudate.exe /force

此命令可以从运行内 Skype 业务服务器或从管理员凭据运行任何命令窗口。 若要在管理员凭据下运行命令窗口，请单击“**开始**”，右键单击“**命令提示符**”，然后单击“**以管理员身份运行**”。 请注意，您可能需要在运行 Gpudate.exe 后重新启动边缘服务器。

为了帮助确保使用适当的 DSCP 值标记网络数据包，，还应通过完成以下过程在每台计算机上创建新的注册表项：

1.  单击 **“开始”**，然后单击 **“运行”**。

2.  在**运行**对话框中，键入**regedit**，，然后按 ENTER。

3.  在注册表编辑器中，展开**HKEY\_本地\_计算机**，展开**系统**，展开**CurrentControlSet**，展开**服务**，然后展开**Tcpip**。

4.  右键单击**Tcpip**，指向**新建**，，然后单击**项**。 创建新的注册表项后，键入**QoS**，，，然后按 ENTER 以重命名该项。

5.  右键单击**QoS**，指向**新建**，，然后单击**字符串值**。 创建新的注册表值后，键入**不使用 NLA**，，，然后按 ENTER 以重命名该值。

6.  双击**请勿使用 NLA**。 **编辑字符串**对话框中，在**值数据**框中，键入**1** ，然后单击**确定**。

7.  关闭注册表编辑器，然后重新启动计算机。
