---
title: Microsoft Teams中的 Walkie Talkie 应用
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
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
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3e311fb94996e1c51bb5f73190539cd0e1f9f127
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681893"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a>Microsoft Teams中的 Walkie Talkie 应用

Teams中的 Walkie Talkie 应用为团队提供即时推 (PTT) 通信，现已在Android & iOS上提供。 Walkie Talkie 允许用户使用其成员所在的相同基础频道与其团队进行连接。 只有在频道中连接到 Walkie Talkie 的用户才会成为参与者，并且可以使用推转对话相互通信，一次一个。

使用Teams中的 Walkie Talkie，一线工作人员现在可以安全地与熟悉的 PTT 体验进行通信，而无需携带大容量的收音机，而 Walkie Talkie 可与 WiFi 或手机网络 Internet 连接一起在任何地方工作。

> [!NOTE]
> Walkie Talkie 目前在中国不可用。

## <a name="getting-started"></a>入门

### <a name="deploying-walkie-talkie"></a>部署 Walkie Talkie

使用 Google 移动服务 (GMS) 和iOS设备的Android设备支持 Walkie Talkie。

### <a name="pin-walkie-talkie-to-teams"></a>将 Walkie Talkie 固定到Teams

#### <a name="use-the-tailored-frontline-app-experience-to-pin-walkie-talkie-and-other-apps-to-teams"></a>使用定制的一线应用体验固定 Walkie Talkie 和其他应用以Teams

Teams中定制的一线应用体验为拥有 [F 许可证](https://www.microsoft.com/microsoft-365/enterprise/frontline#office-SKUChooser-0dbn8nt)的用户固定Teams中最相关的应用。 固定应用包括 Walkie Talkie、Shifts、Tasks 和 审批。 默认情况下，此功能处于启用状态，为一线员工提供根据其需求定制的现新体验。

应用固定到应用栏（Teams桌面客户端侧面和Teams移动客户端底部的栏），用户可在其中快速轻松地访问它们。

若要了解详细信息，包括体验如何与你设置的应用策略配合使用，请参阅 [Tailor Teams一线员工的应用](pin-teams-apps-based-on-license.md)。

#### <a name="use-an-app-setup-policy-to-pin-walkie-talkie-to-teams"></a>使用应用设置策略将 Walkie Talkie 固定到Teams

通过应用设置策略，可以自定义Teams以固定用户中对用户最重要的应用。

若要为用户固定 Walkie Talkie 应用，可以编辑全局 (组织范围的默认) 策略或创建和分配自定义应用设置策略。 要了解详细信息，请参阅[在 Teams 中管理应用设置策略](teams-app-setup-policies.md)。

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="显示在“添加固定应用”窗格中将 Walkie Talkie 添加到固定应用列表的屏幕截图。" lightbox="media/deploy-walkie-talkie-2.png":::

### <a name="network-documentation"></a>网络文档

Teams中的 Walkie Talkie 需要 Internet 连接，并且需要低于网络条件才能获得最佳体验。

|指标 | 必需 |
|---|---|
|RTT)  (延迟 | < 300 毫秒 |
|抖动 |< 30 毫秒 |
|丢包 |< 1% |

如上所述，IP 网络上实时媒体的质量受到网络连接质量的极大影响，尤其是受到以下数量的影响：

- **延迟** - 这是从 A 点到网络上的 B 点获取 IP 数据包所需的时间。 此网络传播延迟基本上与两个点和光速之间的物理距离相关联，包括两者之间的各种路由器占用的更多开销。 延迟以往返时间 (RTT) 来度量。
- **到达间抖动** - 这是连续数据包之间的延迟平均变化。
- **数据包丢失** - 这通常定义为给定时间段内丢失的数据包的百分比。 数据包丢失直接影响音频质量-从小，个别丢失的数据包几乎没有影响，背靠背突发损失，导致完整的音频截断。

发送或接收音频时，Walkie Talkie 的预期数据使用量约为 20 Kb/s。 空闲时，Walkie Talkie 中的预期数据使用率可以忽略不计。

### <a name="walkie-talkie-devices"></a>Walkie Talkie 设备

一线工作人员经常需要说话和接听对讲机电话，即使他们的电话被锁定。 此体验可以通过具有专用 PTT 按钮的专用设备实现。

- **耳机**
  - 无线耳机 (iOS & Android) 
    - [BlueParrott](https://www.blueparrott.com/microsoft-teams-walkie-talkie)
  - 有线耳机仅 (Android) 
    - [克莱因电子](https://www.kleinelectronics.com/poc-accessories/mtwt/)
- **坚固的Android手机**
  - 三星[银河 XCover Pro](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/)， [银河 XCover 5](https://www.samsung.com/de/smartphones/others/galaxy-xcover-5-black-64gb-sm-g525fzkdeeb/buy)， [Galaxy Tab Active 3](https://www.samsung.com/us/business/tablets/galaxy-tab-active/buy/)
    - 手动设置 - 安装Teams后，导航到 XCover/Active 密钥>设置 >高级功能。 打开“使用应用控制 XCover 密钥”，然后选择“Teams”
    - [MDM 设置](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)
  - Zebra [TC5x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc52-tc57-series-touch-computer.html)、 [TC7x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc72-tc77-series-touch-computer.html)、 [TC2x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc21-tc26.html)、 [EC5x](https://www.zebra.com/us/en/products/mobile-computers/handheld/ec50-ec55.html)、 [EC30](https://www.zebra.com/us/en/products/mobile-computers/handheld/ec30.html)、 [MC3300](https://www.zebra.com/us/en/products/mobile-computers/handheld/mc3300.html)、 [MC9300](https://www.zebra.com/us/en/products/mobile-computers/handheld/mc9300.html) 
    - 手动设置 - 安装Teams后，默认情况下，专用 PTT 按钮 (LEFT_TRIGGER_2) 适用于 Walkie Talkie
    
> [!NOTE]
> 这些设备未Teams认证。 他们已被验证为使用Teams对讲机。

### <a name="license-requirements"></a>许可证要求

Walkie Talkie 应用包含在Office 365订阅中Teams的所有付费许可证[中](/office365/servicedescriptions/teams-service-description)。 有关获取Teams的详细信息，[请查看如何实现访问Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)？

## <a name="further-information"></a>详细信息

- IT 管理员可以通过应用策略来控制谁在使用 Walkie Talkie。
- 如果你的一线工作人员使用移动数据通过Teams进行通信，Walkie Talkie 将使用相同的方法。
- Walkie Talkie 应在低带宽的情况下或智能手机连接和工作的情况中正常工作。 当根本没有连接时，Walkie Talkie 将无法工作。

有关最终用户体验的进一步阅读，请参阅：

- [使用 Teams Walkie Talkie 开始](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [与你的团队与 Walkie Talkie 通信](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
