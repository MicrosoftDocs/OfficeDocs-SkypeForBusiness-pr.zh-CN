---
title: 检查 Internet 连接，查看Teams 电话系统
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: 检查 Internet 是否已准备好Teams 电话系统
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7b165f540fe3c6280f1c6a7c2b4dec716a1fa611
ms.sourcegitcommit: e86e3824c300c24e022d5cb1848338278a5a96a8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/03/2022
ms.locfileid: "63053091"
---
# <a name="check-your-internet-connection-for-teams-phone-system"></a>检查 Internet 连接，查看Teams 电话系统

Teams 电话系统是 Microsoft 在云中通过云Microsoft Teams手机Microsoft 365技术。 每个使用 Microsoft Teams 电话系统的设备都需要连接到 Internet。

若要获得最佳电话系统体验，您需要一个宽带 Internet 连接，该连接可以支持组织可能随时进行的最大电话呼叫数。 还需要确保网络上的计算机能够访问Microsoft 365服务。

## <a name="check-your-internet-connection-speed"></a>检查 Internet 连接速度

本文帮助确定 Internet 连接速度是否足够快，适合需要拨打电话的人。 您将提供有关您的组织的信息，并返回一份报告，其中显示您的用户和用户将使用多少 internet Teams电话系统。

### <a name="gather-information-about-your-internet-connection-and-users"></a>收集有关 Internet 连接和用户的信息

开始之前，你需要以下信息：

* Internet 连接的速度
* 多少人将主要电话系统办公室使用
* 多少人将主要电话系统远程位置（例如家庭办公室）使用

### <a name="enter-your-information-into-the-network-planner"></a>在网络规划器中输入你的信息

请按以下步骤操作：

1. 在浏览器中，转到 [https://admin.teams.microsoft.com](https://admin.teams.microsoft.com)。 使用具有全局管理员权限的帐户登录。 用于注册帐户的帐户Microsoft 365这些权限。
2. 打开“**计划**”，然后选择“**网络规划器**”。
3. 在“**网络计划**”下，选择“**添加**”。 输入计划的名称，然后选择“**应用**”。
4. 选择网络计划的名称。
5. 在下一页上，选择“**网络站点**”选项卡上的“**添加网络站点**”。
6. 填写"**网络站点名称、****网络用户** 和 **Internet 链接容量"字段**，然后选择"保存 **"**。 将此屏幕上的其他字段留空，不要选择“**ExpressRoute**”或“**已连接到 WAN**”选项。
7. 在“**报告**”选项卡上，选择“**启动报告**”。
8. 输入"报表 **名称**"和" (Office  远程) 的网络用户数，然后选择"生成报表"以创建显示 Teams 的带宽要求的报告。 我们将在下一部分告诉你如何阅读该报告。

### <a name="find-your-minimum-internet-connection-speed"></a>查找最低 Internet 连接速度

选择"生成 **报表"** Microsoft 365创建报表。

在 **"影响**"**列** Office 365行中，此数字显示 internet 连接Teams电话系统多少。 建议此数字不超过 Internet 连接总速度的 30%。 例如，如果 Internet 连接 *为 60 Mbps*，Teams和 电话系统不应超过 *18 Mbps*。

使用此公式确定最低 Internet 连接速度：<*影响> /0.3*。  

假设"影响"数字为 *4.6875 Mbps*。 查找最低 Internet 连接速度的计算公式为 *4.6875 / 0.3 = 15.6*。 在这种情况下，Internet 连接速度应至少为 *15.6 Mbps*。

如果Teams电话系统 Internet 连接速度的 30% 以上，则"影响"编号将显示为红色。 在这种情况下，可能需要升级 Internet 连接。

![连接速度警告。](../media/network-planner-report-speed-warning.png)

>[!NOTE]
> 网络规划器提供的带宽影响只是一个估计值。 建议使用呼叫质量[仪表板](../cqd-what-is-call-quality-dashboard.md)主动监视与组织内部用户进行音频和视频呼叫Microsoft Teams用户体验。

## <a name="make-sure-the-computers-and-devices-on-your-network-can-reach-microsoft-365"></a>确保网络上的计算机和设备可以访问 Microsoft 365

使用虚拟网络的计算机电话系统必须使用特定网络端口来与Microsoft 365通信。 这些端口实质上是设备通过网络或 Internet 相互通信的门。 你的防火墙需要允许网络上的设备通过下列 *出站* 网络端口访问 Microsoft 365：

* **TCP 端口** 80 和 443
* **UDP 端口** 3478、3479、3480 和 3481

检查防火墙是否允许在这些网络端口上通信的最简单方法是使用Microsoft 365[从](/microsoft-365/enterprise/office-365-network-mac-perf-onboarding-tool)要测试的办公地点使用 Microsoft 365 网络连接工具执行连接测试。 完成测试后，验证结果和建议。
