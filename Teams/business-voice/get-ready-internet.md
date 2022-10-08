---
title: 检查 Teams 电话系统的 Internet 连接
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: 检查你的 Internet 是否已准备好使用 Teams 电话系统
appliesto:
- Microsoft Teams
ms.collection:
- M365-voice
ms.openlocfilehash: 7cef6f8b9a3bfa6aa99fe342f8d1abf66f7c6594
ms.sourcegitcommit: fc87f4300f53abf7a049936944abb21d0cade0d9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2022
ms.locfileid: "68480932"
---
# <a name="check-your-internet-connection-for-teams-phone-system"></a>检查 Teams 电话系统的 Internet 连接

Teams 电话系统是 Microsoft 在 Microsoft Teams 中使用 Microsoft 365 云启用手机功能的技术。 每个使用 Microsoft Teams 和电话系统的设备都需要连接到 Internet。

若要获得最佳电话系统体验，需要使用宽带 Internet 连接来支持组织随时可能拨打的最大电话数。 还需要确保网络上的计算机可以访问 Microsoft 365 服务。

## <a name="check-your-internet-connection-speed"></a>检查 Internet 连接速度

本文有助于确定 Internet 连接是否足够快，以容纳需要拨打电话的人数。 你将提供有关组织的信息，并返回一个报表，其中显示 Teams 和电话系统将使用多少 Internet 连接。

### <a name="gather-information-about-your-internet-connection-and-users"></a>收集有关 Internet 连接和用户的信息

开始之前，你需要以下信息：

* Internet 连接的速度
* 有多少人将主要从您的办公室使用电话系统
* 有多少人将主要从远程位置（例如家庭办公室）使用电话系统

### <a name="enter-your-information-into-the-network-planner"></a>在网络规划器中输入你的信息

请按以下步骤操作：

1. 在浏览器中，转到 [https://admin.teams.microsoft.com](https://admin.teams.microsoft.com)。 使用具有全局管理员权限的帐户登录。 用于注册 Microsoft 365 的帐户具有这些权限。
2. 打开“**计划**”，然后选择“**网络规划器**”。
3. 在“**网络计划**”下，选择“**添加**”。 输入计划的名称，然后选择“**应用**”。
4. 选择网络计划的名称。
5. 在下一页上，选择“**网络站点**”选项卡上的“**添加网络站点**”。
6. 填写 **“网络站点名称**”、“ **网络用户**”和 **“Internet 链接容量** ”字段，然后选择 **“保存**”。 将此屏幕上的其他字段留空，不要选择“**ExpressRoute**”或“**已连接到 WAN**”选项。
7. 在“**报告**”选项卡上，选择“**启动报告**”。
8. 输入 **报表名称** 和 Office 和 **远程**)  (**网络用户** 数，然后选择 **“生成报** 表”以创建显示 Teams 带宽要求的报表。 我们将在下一部分中告知如何阅读报表。

### <a name="find-your-minimum-internet-connection-speed"></a>查找最低 Internet 连接速度

选择 **“生成报表**”时，Microsoft 365 将创建一个报表。

在 **“影响**”列下和 **Office 365** 行中，此数字显示 Teams 和电话系统将使用多少 Internet 连接。 建议此数字不超过 Internet 连接总速度的 30%。 例如，如果 Internet 连接为 *60 Mbps*，则 Teams 和电话系统应使用不超过 *18 Mbps*。

使用此公式确定最低 Internet 连接速度：<*影响数>/0.3*。  

假设影响号为 *4.6875 Mbps*。 查找最低 Internet 连接速度的计算为 *4.6875 / 0.3 = 15.6*。 在这种情况下，Internet 连接速度应至少为 *15.6 Mbps*。

如果 Teams 和电话系统将使用 Internet 总连接速度的 30% 以上， **则影响** 号码将显示为红色。 在这种情况下，可能需要升级 Internet 连接。

![连接速度警告。](../media/network-planner-report-speed-warning.png)

>[!NOTE]
> 网络规划器提供的带宽影响仅是估计值。 建议使用 [通话质量仪表板](../cqd-what-is-call-quality-dashboard.md) ，通过组织内的 Microsoft Teams 主动监视用户的音频和视频通话体验。

## <a name="make-sure-the-computers-and-devices-on-your-network-can-reach-microsoft-365"></a>确保网络上的计算机和设备可以访问 Microsoft 365

使用电话系统的计算机和设备必须使用特定的网络端口与 Microsoft 365 服务通信。 这些端口本质上是设备通过网络或 Internet 相互通信的门。 你的防火墙需要允许网络上的设备通过下列 *出站* 网络端口访问 Microsoft 365：

* **TCP 端口** 80 和 443
* **UDP 端口** 3478、3479、3480 和 3481

检查防火墙是否允许在这些网络端口上通信的最简单方法是使用要测试的办公位置中的 [Microsoft 365 网络连接工具](/microsoft-365/enterprise/office-365-network-mac-perf-onboarding-tool) 执行连接测试。 完成测试后，请验证结果和建议。
