---
title: Microsoft Teams 中的 Walkie Talkie 应用
author: LanaChin
ms.author: v-lanachin
manager: samanro
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: 如何从 ITAdmin 的角度在 Microsoft Teams 中配置 Walkie Talkie 应用。
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365-frontline
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 815d3c6b1e97ea75eaa7ae4e35d3e41dd3c6e9e4
ms.sourcegitcommit: 46dbff43eec9631863b74b2b49c9a29c6497d8e8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2022
ms.locfileid: "67396443"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a>Microsoft Teams 中的 Walkie Talkie 应用

Teams 中的 Walkie Talkie 应用为团队提供即时推 (PTT) 通信，可在 Android 和 iOS 上使用。 Walkie Talkie 允许用户使用其成员所在的相同基础频道与其团队进行连接。 只有在频道中连接到 Walkie Talkie 的用户才会成为参与者，并且可以使用推转对话相互通信，一次一个。

使用 Teams 中的 Walkie Talkie，一线工作人员可以安全地与熟悉的 PTT 体验进行通信，而无需携带笨重的收音机，而 Walkie Talkie 可在任意位置使用 WiFi 或手机网络 Internet 连接。

> [!NOTE]
> Walkie Talkie 目前在中国不可用。

## <a name="deploying-walkie-talkie"></a>部署 Walkie Talkie

使用 Google Mobile Services (GMS) 和 iOS 设备的 Android 设备支持 Walkie Talkie。

### <a name="enable-or-disable-walkie-talkie-in-your-organization"></a>在组织中启用或禁用 Walkie Talkie

默认情况下，对组织中的所有 Teams 用户启用 Walkie Talkie。 你可以在 Microsoft Teams 管理中心的[管理应用](manage-apps.md)页面在组织级别关闭或打开此应用。

1. 在 Teams 管理中心的左侧导航中，转到“**Teams 应用**” > “**管理应用**”。
2. 在应用列表中，搜索 Walkie Talkie 应用，选择它，然后将 **“状态** ”切换为 **“已阻止** ”或 **“允许**”。

### <a name="enable-or-disable-walkie-talkie-for-specific-users-in-your-organization"></a>为组织中的特定用户启用或禁用 Walkie Talkie

若要允许或阻止组织中的特定用户使用 Walkie Talkie，请确保在 [“管理应用](manage-apps.md) ”页面上为组织启用 Walkie Talkie。 然后创建自定义应用权限策略并将其分配给这些用户。 要了解详细信息，请参阅[在 Teams 中管理应用权限策略](teams-app-permission-policies.md)。

### <a name="pin-walkie-talkie-to-teams"></a>将 Walkie Talkie 固定到 Teams

#### <a name="use-the-tailored-frontline-app-experience-to-pin-walkie-talkie-and-other-apps-to-teams"></a>使用定制的一线应用体验将 Walkie Talkie 和其他应用固定到 Teams

Teams 中定制的一线应用体验为拥有 [F 许可证](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt)的用户固定 Teams 中最相关的应用。 固定应用包括 Walkie Talkie、Shifts、Tasks 和 Approvals。 默认情况下，此功能处于启用状态，为一线员工提供根据其需求定制的现新体验。

应用固定到应用栏（Teams 桌面客户端侧面和 Teams 移动客户端底部的栏），用户可在其中快速轻松地访问应用栏。

若要了解详细信息，包括体验如何与你设置的应用策略配合使用，请参阅 [一线员工的 Tailor Teams 应用](/microsoft-365/frontline/pin-teams-apps-based-on-license?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json)。

#### <a name="use-an-app-setup-policy-to-pin-walkie-talkie-to-teams"></a>使用应用设置策略将 Walkie Talkie 固定到 Teams

通过应用设置策略，可以自定义 Teams 以固定用户中对用户最重要的应用。

若要为用户固定 Walkie Talkie 应用，可以编辑全局 (组织范围的默认) 策略或创建和分配自定义应用设置策略。 要了解详细信息，请参阅[在 Teams 中管理应用设置策略](teams-app-setup-policies.md)。

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="显示在“添加固定应用”窗格中将 Walkie Talkie 添加到固定应用列表的屏幕截图。" lightbox="media/deploy-walkie-talkie-2.png":::

## <a name="network-documentation"></a>网络文档

Teams 中的 Walkie Talkie 需要 Internet 连接。 为了获得最佳体验，需要满足以下网络条件。

|指标 | 必需 |
|---|---|
|RTT)  (延迟 | < 300 毫秒 |
|抖动 |< 30 毫秒 |
|丢包 |< 1% |

如上所述，IP 网络上实时媒体的质量受到网络连接质量的极大影响，尤其是受到以下数量的影响：

- **延迟** - 从 A 点到网络上的 B 点获取 IP 数据包所需的时间。 此网络传播延迟基本上与两个点和光速之间的物理距离相关联，包括两者之间的各种路由器占用的更多开销。 延迟以往返时间 (RTT) 来度量。
- **到达间抖动** - 连续数据包之间的延迟平均变化。
- **数据包丢失** - 数据包丢失通常定义为给定时间段内丢失的数据包的百分比。 数据包丢失直接影响音频质量，从几乎没有影响的小而单个丢失的数据包，到导致完全音频截断的背靠背突发丢失。

发送或接收音频时，Walkie Talkie 的预期数据使用量约为 20 Kb/s。 空闲时，Walkie Talkie 中的预期数据使用率可以忽略不计。

## <a name="walkie-talkie-devices"></a>Walkie Talkie 设备

一线工作人员经常需要说话和接听对讲机电话，即使他们的电话被锁定。 此体验可以通过具有专用 PTT 按钮的专用设备实现。

#### <a name="headsets"></a>耳机

- iOS 和 Android)  (无线耳机
  - [BlueParrott](https://www.blueparrott.com/microsoft-teams-walkie-talkie)
- Android (有线耳机仅) 
  - [克莱因电子](https://www.kleinelectronics.com/poc-accessories/mtwt/)

#### <a name="rugged-android-phones"></a>坚固的 Android 手机

- Crosscall [Core-X4](https://www.crosscall.com/en_FR/core-s4-1004010501053.html)、 [Core-M5](https://www.crosscall.com/en_FR/core-m5-1001011101114.html)、 [Action-X5](https://www.crosscall.com/en_FR/action-x5-1001020701220.html)、 [Core-X5](https://www.crosscall.com/en_FR/core-x5-1001010701695.html) 和 [Core-T5](https://www.crosscall.com/en_FR/core-t5-1003011401749.html)
  - 手动设置：安装 Teams 后，转到 **“设置** > **”按钮**。 在“专用”按钮 (1 或 2) ，选择 **“长按”**，然后选择 **PTT 应用**。 选择“ **自定义**”旁边的蓝色方向盘，然后选择 **Teams**。
- Kyocera [DuraForce 超级 5G](https://kyoceramobile.com/duraforce-ultra-5g/) 和 [DuraSport 5G](https://kyoceramobile.com/durasport-5g/)
  - 手动设置：安装 Teams 后，转到 **“设置** > **可编程密钥**”。 根据设备) 选择 **PTT 密钥** 或 **按住** (，然后选择 **Teams**。
- Samsung [Galaxy XCover Pro](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/)， [Galaxy XCover 5](https://www.samsung.com/de/smartphones/others/galaxy-xcover-5-black-64gb-sm-g525fzkdeeb/buy)， [Galaxy Tab Active 3](https://www.samsung.com/us/business/tablets/galaxy-tab-active/buy/)
  - 手动设置：安装 Teams 后，转到 **“设置** > **高级功能** > **”XCover/Active 密钥**。 使用 **应用打开控制 XCover 密钥** 并选择 **Teams**。
  - [MDM 设置](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)
- Sonim [XP8](https://www.sonimtech.com/products/devices/xp8/)
  - 手动设置：安装 Teams 后，转到 **“设置** > **可编程密钥**”。 选择 **“选择 PTT 密钥”应用**，然后选择 **Teams**。
- Zebra [TC5x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc52-tc57-series-touch-computer.html)、 [TC7x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc72-tc77-series-touch-computer.html)、 [TC2x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc21-tc26.html)、 [EC5x](https://www.zebra.com/us/en/products/mobile-computers/handheld/ec50-ec55.html)、 [EC30](https://www.zebra.com/us/en/products/mobile-computers/handheld/ec30.html)、 [MC3300](https://www.zebra.com/us/en/products/mobile-computers/handheld/mc3300.html)、 [MC9300](https://www.zebra.com/us/en/products/mobile-computers/handheld/mc9300.html) 
  - 手动设置：安装 Teams 后，默认情况下，专用 PTT 按钮 (LEFT_TRIGGER_2) 适用于 Walkie Talkie。

> [!NOTE]
> 这些设备未通过 Teams 认证。 他们已被验证为使用 Teams Walkie Talkie。

## <a name="license-requirements"></a>许可证要求

Walkie Talkie 应用包含在 Office 365 订阅中 Teams 的所有付费许可证[中](/office365/servicedescriptions/teams-service-description)。 有关获取 Teams 的详细信息，请查看[如何实现访问 Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)？

## <a name="more-information"></a>更多信息

- 如果你的一线工作人员使用移动数据通过 Teams 进行通信，Walkie Talkie 将使用相同的方法。
- Walkie Talkie 应在低带宽的情况下或智能手机连接和工作的情况中正常工作。 当根本没有连接时，Walkie Talkie 将无法工作。

若要详细了解最终用户体验，请参阅：

- [Teams Walkie Talkie 入门](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [与你的团队与 Walkie Talkie 通信](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
