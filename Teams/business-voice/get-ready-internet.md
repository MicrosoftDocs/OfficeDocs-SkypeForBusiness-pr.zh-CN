---
title: 检查用于企业语音的 Internet 连接
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: 473c053036b766ef475c3aed5f0bba2d24dd9e6c
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824880"
---
# <a name="check-your-internet-connection-for-business-voice"></a>检查用于企业语音的 Internet 连接

企业语音随 Microsoft 365 一起位于云中。 使用 Microsoft Teams 和企业语音的每台设备都需要连接到 Internet。

若要获得最佳的企业语音体验，你需要足够快的宽带 Internet 连接，确保能够支持你的组织可能同时拨打的最多电话数量。 此外，还需确保网络上的计算机可以访问 Microsoft 365 服务器。

若要执行下面的步骤，必须有一个租户包含以下订阅之一：

* Office 365 商业协作版
* Office 365 商业高级版
* Office 365 E1
* Office 365 E3
* Office 365 F1
* Microsoft 365 A1
* Microsoft 365 A3
* Microsoft 365 E3
* Microsoft 365 商业版

无需企业语音许可证即可执行这些步骤。

## <a name="check-your-internet-connection-speed"></a>检查 Internet 连接速度

本文将帮助你确定自己的 Internet 连接速度是否能满足大量人员拨打电话以及主持视频会议的需求。 通过提供有关你的组织的信息，你便会获得返回的报告，其中显示 Teams 和企业语音将使用的 Internet 连接带宽。

### <a name="gather-information-about-your-internet-connection-and-users"></a>收集有关 Internet 连接和用户的信息

开始之前，你需要以下信息：

* Internet 连接速度
* 有多少人主要在办公室使用企业语音
* 有多少人主要从远程位置（例如家庭办公室）使用企业语音

### <a name="enter-your-information-into-the-network-planner"></a>在网络规划器中输入你的信息

请按以下步骤操作：

1. 在浏览器中，转到 https://admin.teams.microsoft.com。 使用具有全局管理员权限的帐户登录。 用于注册 Office 365 的帐户便拥有这些权限。
2. 打开“**计划**”，然后选择“**网络规划器**”。
3. 在“**网络计划**”下，选择“**添加**”。 输入计划的名称，然后选择“**应用**”。 网络计划应如下所示：

    ![网络规划器主屏幕](../media/network-planner-main.png)
1. 选择网络计划的名称。 （即上图中的**主要办公室**。）
2. 在下一页上，选择“**网络站点**”选项卡上的“**添加网络站点**”。
3. 仅填写以下屏幕截图中所示的字段，然后选择“**保存**”。 将此屏幕上的其他字段留空，不要选择“**ExpressRoute**”或“**已连接到 WAN**”选项。

    ![网络规划器站点信息](../media/network-planner-site-info.png)
1. 在“**报告**”选项卡上，选择“**启动报告**”。
1. 输入以下信息，然后选择“**生成报告**”，从而创建一份显示 Teams 带宽要求的报告。 我们将在下一节中介绍如何阅读该报告。

    ![网络规划器报告信息](../media/network-planner-report-info.png)

### <a name="find-your-minimum-internet-connection-speed"></a>查找最低的 Internet 连接速度

选择“**生成报告**”时，Office 365 将创建如下所示的报告：

![网络规划器报告详细信息](../media/network-planner-report.png)

突出显示的数字显示了 Teams 和企业语音将使用的 Internet 连接带宽。 建议该数字不超过 Internet 总连接速度的 30%。 例如，如果 Internet 连接速度是 60 Mbps，则 Teams 和企业语音的使用量不应超过 18 Mbps。

使用以下公式可以确定最低的 Internet 连接速度：*\<突出显示的数字> / 0.3*。 根据上图中突出显示的数字，计算结果为 *4.6875 / 0.3 = 15.6*。 在这种情况下，Internet 连接速度应至少为 15.6 Mbps。

如果 Teams 和企业语音的使用量将超过 Internet 总连接速度的 30%，则突出显示的数字将显示为红色。 在这种情况下，可能需要升级 Internet 连接。

![连接速度警告](../media/network-planner-report-speed-warning.png)

## <a name="make-sure-the-computers-and-devices-on-your-network-can-reach-microsoft-365"></a>确保网络上的计算机和设备可以访问 Microsoft 365

使用企业语音的计算机和设备必须使用特定的网络端口与 Microsoft 365 服务器进行通信。 这些端口本质上是一种“门”；设备通过这个门在网络或 Internet 上互相通信。 你的防火墙需要允许网络上的设备通过下列*出站*网络端口访问 Microsoft 365：

* **TCP 端口** 80 和 443
* **UDP 端口** 3478、3479、3480 和 3481

检查防火墙是否允许在这些网络端口上进行通信的最简单方法是在 Teams 中进行测试呼叫：

1. 在网络上的计算机上转到 https://aka.ms/getteams 并安装 Teams。 请确保计算机有扬声器和麦克风。
2. 打开 Teams 并使用 Microsoft 365 帐户登录。
3. 在 Teams 中，选择你的个人资料图片，然后转到“**设置**” > “**设备**”。
4. 在“**音频设备**”下，选择“**进行测试呼叫**”。
5. 按照相关步骤留言，然后回放给你自己听。

   * 如果呼叫已接通，并且可以听到自己的留言，则表示你的防火墙已正确设置。
   * 如果呼叫已接通，但无法听到语音指示或留言，请确保已正确设置扬声器和麦克风，然后重试。
   * 如果呼叫未接通，或已经接通但无法听到留言，则可能需要更新防火墙，以便允许访问所需的网络端口。 请查看防火墙的文档，或联系 IT 专家获取帮助。

 如果你是 IT 专业人员，想要详细了解如何准备大型或更复杂的网络来支持企业语音，请查看[评估环境](../3-envision-evaluate-my-environment.md)。 这篇文章提供了有关带宽、代理和防火墙要求的信息，还介绍了如何使用[网络评估工具](../3-envision-evaluate-my-environment.md#test-the-network)来测试网络。

