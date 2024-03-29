---
title: Microsoft Teams 中的 Walkie Talkie 应用
author: LanaChin
ms.author: v-lanachin
manager: samanro
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: 如何从 IT 管理员的角度在 Microsoft Teams 中配置 Walkie Talkie 应用。
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365-frontline
- tier2
- highpri
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.date: 11/17/2022
ms.openlocfilehash: c4184e82e99fa4f3169fea14c62f3a892750bf8c
ms.sourcegitcommit: 776820a6c927fafabdfad9f50654fe7648d77bf3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/20/2023
ms.locfileid: "69845889"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a>Microsoft Teams 中的 Walkie Talkie 应用

Teams 中的 Walkie Talkie 应用为团队提供即时一键通 (PTT) 通信，可在 Android 和 iOS 上使用。 Walkie Talkie 允许用户使用他们所属的相同基础频道与其团队联系。

只有在频道中连接到 Walkie Talkie 的用户才能成为参与者，并且可以使用 PTT 相互通信。 用户将继续接收传输，直到他们点击  **“断开连接**”。

借助 Teams 中的 Walkie Talkie，用户可以安全地与熟悉的 PTT 体验进行通信，而无需携带笨重的无线电，并且 Walkie Talkie 可在任何位置使用 WiFi 或手机网络连接。

> [!NOTE]
> 沃基对讲机目前在中国不可用。

## <a name="license-requirements"></a>许可证要求

Walkie Talkie 包含在 [Microsoft 365 和 Office 365 订阅](/office365/servicedescriptions/teams-service-description)的所有 Teams 付费许可证中。 有关获取 Teams 的详细信息，请查看[如何实现获取 Microsoft Teams？](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)

## <a name="deploying-walkie-talkie"></a>部署 Walkie Talkie

使用 Google 移动服务 (GMS) 和 iOS 设备的 Android 设备支持 Walkie Talkie。

### <a name="step-1-make-sure-walkie-talkie-is-enabled-in-your-organization"></a>步骤 1：确保在你的组织中启用了 Walkie Talkie

默认情况下，将为你组织中的所有 Teams 用户启用 Walkie Talkie 应用。

可在 Microsoft Teams 管理中心的 [“管理应用](manage-apps.md) ”页上控制该应用是否在组织级别可用。 若要确认在组织中已启用该应用，请执行以下操作：

1. 在 Teams 管理中心的左侧导航中，转到“**Teams 应用**” > “**管理应用**”。
2. 在应用列表中，搜索“Walkie Talkie”应用，将其选中，并确保“ **状态** ”开关设置为 **“允许**”。

如果要允许或阻止组织中的特定用户使用 Walkie Talkie，请确保在 [“管理应用](manage-apps.md) ”页上为组织启用了 Walkie Talkie。 然后为应用权限创建自定义策略，并将其分配给这些用户。 要了解详细信息，请参阅[在 Teams 中管理应用权限策略](teams-app-permission-policies.md)。

### <a name="step-2-pin-walkie-talkie-to-teams"></a>步骤 2：将 Walkie Talkie 固定到 Teams

#### <a name="use-the-tailored-frontline-app-experience-to-pin-walkie-talkie-and-other-apps-to-teams"></a>使用定制的一线应用体验将 Walkie Talkie 和其他应用固定到 Teams

Teams 中定制的一线应用体验为拥有 [F 许可证](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt)的用户固定 Teams 中最相关的应用。 固定的应用包括 Walkie Talkie、排班、任务和审批。 默认情况下，此功能处于打开状态，为一线员工提供适合其需求的开箱即用体验。

应用被固定到 Teams 移动客户端底部的应用托盘，用户可在其中快速轻松地访问它们。

若要了解详细信息，包括体验如何与设置的应用策略配合使用，请参阅 [为一线员工定制 Teams 应用](/microsoft-365/frontline/pin-teams-apps-based-on-license?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json)。

#### <a name="use-an-app-setup-policy-to-pin-walkie-talkie-to-teams"></a>使用应用设置策略将 Walkie Talkie 固定到 Teams

应用设置策略允许自定义 Teams，以固定用户中最重要的应用。

若要为用户固定 Walkie Talkie 应用，可以编辑全局 (组织范围的默认) 策略，或在应用设置策略中创建并分配自定义策略。 要了解详细信息，请参阅[在 Teams 中管理应用设置策略](teams-app-setup-policies.md)。

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="显示将 Walkie Talkie 添加到“添加固定应用”窗格中的固定应用列表的屏幕截图。" lightbox="media/deploy-walkie-talkie-2.png":::

## <a name="network-documentation"></a>网络文档

Teams 中的 Walkie Talkie 需要 Internet 连接。 要获得最佳体验，需要满足以下网络条件。

|指标 | 必需 |
|---|---|
|RTT) 延迟 ( | < 300 毫秒 |
|抖动 |< 30 毫秒 |
|丢包 |< 1% |

如上所述，IP 网络上的实时媒体质量受到网络连接质量的极大影响，尤其是受以下数量的影响：

- **延迟** - 从网络上的点 A 获取 IP 数据包到点 B 所需的时间。 这种网络传播延迟实质上与两点之间的物理距离和光速有关，包括介于两者之间的各种路由器占用的更多开销。 延迟度量为往返时间 (RTT) 。
- **到达间抖动** - 连续数据包之间的平均延迟变化。
- **数据包丢失** - 数据包丢失通常定义为在给定时间范围内丢失的数据包的百分比。 数据包丢失直接影响音频质量-从几乎没有影响的小型单个丢失数据包，到导致完全音频切断的背靠背突发丢失。

发送或接收音频时，对讲机的预期数据使用量约为 20 Kb/秒。 空闲时，对讲机的预期数据使用量可以忽略不计。

## <a name="walkie-talkie-devices"></a>对讲机设备

一线员工通常需要说话和接听对讲机电话，即使他们的电话被锁定。 这种体验可以通过具有专用 PTT 按钮的专用设备实现。

#### <a name="headsets"></a>耳机

-  (iOS 和 Android) 的无线头戴显示设备
  - [BlueParrott](https://www.blueparrott.com/microsoft-teams-walkie-talkie)
- 仅) android (有线头戴显示设备
  - [克莱因电子](https://www.kleinelectronics.com/poc-accessories/mtwt/)

#### <a name="rugged-android-phones"></a>加固型 Android 手机

- Crosscall [Core-X4](https://www.crosscall.com/en_FR/core-x4-1001010801327.html)、 [Core-M5](https://www.crosscall.com/en_FR/core-m5-1001011101114.html)、 [Action-X5](https://www.crosscall.com/en_FR/action-x5-1001020701220.html)、 [Core-X5](https://www.crosscall.com/en_FR/core-x5-1001010701695.html) 和 [Core-T5](https://www.crosscall.com/en_FR/core-t5-1003011401749.html)
  - 手动设置：安装 Teams 后，转到 **“设置** > **”按钮**。 在“专用”按钮 (1 或 2) 上，选择“ **长按**”，然后选择“ **PTT 应用**”。 选择 **“自定义**”旁边的蓝色滚轮，然后选择“ **Teams**”。
- Kyocera [DuraForce Ultra 5G](https://kyoceramobile.com/duraforce-ultra-5g/) 和 [DuraSport 5G](https://kyoceramobile.com/durasport-5g/)
  - 手动设置：安装 Teams 后，转到 **“设置** > **可编程密钥**”。 选择 **PTT 键** 或 **长按** (，具体取决于设备) ，然后选择 **Teams**。
- Honeywell [CT30 XP](https://sps.honeywell.com/us/en/products/productivity/mobile-computers/handheld-computers/ct30-xp-handheld-computer)、 [CT30 XP HC](https://sps.honeywell.com/us/en/products/productivity/mobile-computers/handheld-computers/ct30-xp-hc-mobile-computer)、 [CT45 XP](https://sps.honeywell.com/us/en/products/productivity/mobile-computers/handheld-computers/ct45-ct45-xp)、 [EDA51](https://sps.honeywell.com/us/en/products/productivity/mobile-computers/handheld-computers/scanpal-eda51-handheld-computer)、 [EDA52](https://sps.honeywell.com/us/en/products/productivity/mobile-computers/handheld-computers/eda52-handheld-computer)、 [EDA52 HC](https://sps.honeywell.com/gb/en/products/productivity/mobile-computers/healthcare-computers/scanpal-eda52-healthcare-mobile-computer)、 
  - 手动设置：安装 Teams 后，专用 PTT 按钮默认适用于 Walkie Talkie。
- Samsung [Galaxy XCover Pro](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/)， [Galaxy XCover 5](https://www.samsung.com/de/smartphones/others/galaxy-xcover-5-black-64gb-sm-g525fzkdeeb/buy)， [Galaxy Tab Active 3](https://www.samsung.com/us/business/tablets/galaxy-tab-active/buy/)
  - 手动设置：安装 Teams 后，转到 **“设置** > **高级功能** > **XCover/Active 密钥**”。 **使用应用打开 Control XCover 密钥**，然后选择 **“Teams**”。
  - [MDM 设置](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)
- Sonim [XP8](https://www.sonimtech.com/products/devices/xp8/)
  - 手动设置：安装 Teams 后，转到 **“设置** > **可编程密钥**”。 选择 **“选择 PTT 密钥应用**”，然后选择“ **Teams**”。
- Zebra [TC5x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc52-tc57-series-touch-computer.html)、 [TC7x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc72-tc77-series-touch-computer.html)、 [TC2x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc21-tc26.html)、 [EC5x](https://www.zebra.com/us/en/products/mobile-computers/handheld/ec50-ec55.html)、 [EC30](https://www.zebra.com/us/en/products/mobile-computers/handheld/ec30.html)、 [MC3300](https://www.zebra.com/us/en/products/mobile-computers/handheld/mc3300.html)、 [MC9300](https://www.zebra.com/us/en/products/mobile-computers/handheld/mc9300.html) 
  - 手动设置：安装 Teams 后，专用 PTT 按钮 (LEFT_TRIGGER_2) 默认适用于 Walkie Talkie。

> [!NOTE]
> 这些设备未经过 Teams 认证。 它们已经过验证，可与 Teams Walkie Talkie 配合使用。

## <a name="bluetooth-devices"></a>蓝牙设备

> [!NOTE]
> 如果用户使用的是蓝牙配件，请确保移动设备管理 (MDM) 解决方案不会阻止蓝牙设备。

在运行 Android OS 版本 12 或更高版本的设备上，需要蓝牙权限，并且不再需要使用 BLE 堆栈进行连接的位置权限。 如果未在 Teams 级别授予“就近权限”，用户将收到蓝牙权限提示。 无论蓝牙配件（如头戴显示设备）是否已连接到其设备，都将显示此提示。 如果蓝牙配件已连接，则点击“ **允许”** 将 Walkie 对讲机连接到蓝牙配件。

## <a name="get-insight-into-walkie-talkie-usage-and-performance"></a>深入了解 Walkie Talkie 使用情况和性能

Teams 管理中心中的 [Walkie Talkie 使用情况和性能报告](teams-analytics-and-reports/walkie-talkie-usage-report.md) 提供了你组织中的 Walkie Talkie 活动和性能概述。 该报表提供诸如进行和接收的 PTT 传输数、通道活动、传输持续时间以及设备和参与者详细信息等信息。

## <a name="more-information"></a>更多信息

- 如果用户使用移动数据通过 Teams 进行通信，则 Walkie Talkie 将使用相同的方法。
- 对讲机在低带宽情况下或智能手机已连接并正常工作的情况下应能正常工作。 在没有连接的情况下，对讲机将不起作用。

若要详细了解最终用户体验，请参阅：

- [Teams Walkie Talkie 入门](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [使用 Walkie Talkie 与团队沟通](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
