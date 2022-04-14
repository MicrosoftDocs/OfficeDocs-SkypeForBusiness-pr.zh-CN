---
title: Microsoft Teams中的 Walkie Talkie 应用程序
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
ms.openlocfilehash: c19894106dfd06c13ec9936657837aa42fcdade0
ms.sourcegitcommit: 480046a53dfb6e6cf867e1920f8fb43dda9d3774
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2022
ms.locfileid: "62015012"
---
# <a name="walkie-talkie-app-in-microsoft-teams"></a>Microsoft Teams中的 Walkie Talkie 应用

Teams中的 Walkie Talkie 应用为团队提供即时推 (PTT) 通信，现在可在 Android & iOS 上使用。 Walkie Talkie 允许用户使用其成员所在的相同基础频道与其团队进行连接。 只有在频道中连接到 Walkie Talkie 的用户才会成为参与者，并且可以使用推转对话相互通信，一次一个。

使用Teams中的 Walkie Talkie，一线工作人员现在可以安全地与熟悉的 PTT 体验进行通信，而无需携带大容量的收音机，而 Walkie Talkie 可与 WiFi 或手机网络 Internet 连接一起在任何地方工作。

## <a name="getting-started"></a>入门

### <a name="deploying-walkie-talkie"></a>部署 Walkie Talkie

使用 Google 移动服务 (GMS) 和 iOS 设备的 Android 设备支持 Walkie Talkie。 

目前，Walkie Talkie 尚未预安装。 若要为组织中的用户启用此功能，需要将 Walkie Talkie 添加到从 [Teams 管理中心](https://admin.teams.microsoft.com/)分配给用户的 [App 安装策略](teams-app-setup-policies.md) 。 启用后，Walkie Talkie 将在 48 小时内在应用上推出。

### <a name="adding-walkie-talkie-to-your-app-list"></a>将 Walkie Talkie 添加到应用列表

在Microsoft Teams管理中心，**在 Teams** **appSetup** >  策略下，应将 **“允许用户固定**”设置为 **“打开**”。 然后，在“固定应用”部分下，单击 **“+添加应用**”。

:::image type="content" source="media/deploy-walkie-talkie-1.png" alt-text="显示要选择的“固定应用”部分和“添加应用”按钮。":::

在右侧显示的 **“添加固定应用** ”面板上，使用 **“搜索** ”文本框查找 Walkie Talkie。 将它作为搜索结果时，选择名称右侧的 **“添加** ”按钮以将其添加到列表中。

:::image type="content" source="media/deploy-walkie-talkie-2.png" alt-text="显示“添加固定应用”边栏，其中在搜索窗格中输入了 Walkie，搜索结果中显示 Walkie Talkie 应用，旁边有“添加”按钮。":::

Walkie Talkie 应用现在应显示在固定应用列表中，单击“ **保存** ”按钮后可供使用。

:::image type="content" source="media/deploy-walkie-talkie-3.png" alt-text="显示已固定应用列表，其中添加了 Walkie Talkie 应用，并在列表下方显示“保存”按钮。":::

### <a name="network-documentation"></a>网络文档

Teams中的 Walkie Talkie 需要 Internet 连接，并且需要低于网络条件才能获得最佳体验。

|指标 | 必需 |
|---|---|
|RTT)  (延迟 | < 300ms |
|抖动 |< 30ms |
|丢包 |< 1% |

如上所述，IP 网络上实时媒体的质量受到网络连接质量的极大影响，尤其是受到以下数量的影响：

- **延迟** - 这是从 A 点到网络上的 B 点获取 IP 数据包所需的时间。 此网络传播延迟基本上与两个点和光速之间的物理距离相关联，包括两者之间的各种路由器占用的更多开销。 延迟以往返时间 (RTT) 来度量。
- **到达间抖动** - 这是连续数据包之间的延迟平均变化。
- **数据包丢失** - 这通常定义为给定时间段内丢失的数据包的百分比。 数据包丢失直接影响音频质量-从小，个别丢失的数据包几乎没有影响，背靠背突发损失，导致完整的音频截断。

发送或接收音频时，Walkie Talkie 的预期数据使用量约为 20 Kb/s。 空闲时，Walkie Talkie 中的预期数据使用率可以忽略不计。

### <a name="walkie-talkie-devices"></a>Walkie Talkie 设备

一线工作人员经常需要说话和接听对讲机电话，即使他们的电话被锁定。 此体验可以通过具有专用 PTT 按钮的专用设备实现。

- **耳机**
  - Android & iOS (无线耳机) 
    - [BlueParrott](https://www.blueparrott.com/microsoft-teams-walkie-talkie)
  - Android (有线耳机仅) 
    - [克莱因电子](https://www.kleinelectronics.com/poc-accessories/mtwt/)
- **坚固的 Android 手机**
  - 三星[银河 XCover Pro](https://www.samsung.com/us/business/products/mobile/phones/galaxy-xcover-pro/)， [银河 XCover 5](https://www.samsung.com/de/smartphones/others/galaxy-xcover-5-black-64gb-sm-g525fzkdeeb/buy)， [Galaxy Tab Active 3](https://www.samsung.com/us/business/tablets/galaxy-tab-active/buy/)
    - 手动设置 - 安装Teams后，导航到 XCover/Active 密钥>设置 >高级功能。 打开“使用应用控制 XCover 密钥”，然后选择“Teams”
    - [MDM 设置](https://docs.samsungknox.com/admin/knox-service-plugin/intune-teams.htm)
  - Zebra [TC5x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc52-tc57-series-touch-computer.html)、 [TC7x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc72-tc77-series-touch-computer.html)、 [TC2x](https://www.zebra.com/us/en/products/mobile-computers/handheld/tc21-tc26.html)、 [EC5x](https://www.zebra.com/us/en/products/mobile-computers/handheld/ec50-ec55.html)、 [EC30](https://www.zebra.com/us/en/products/mobile-computers/handheld/ec30.html)、 [MC3300](https://www.zebra.com/us/en/products/mobile-computers/handheld/mc3300.html)、 [MC9300](https://www.zebra.com/us/en/products/mobile-computers/handheld/mc9300.html) 
    - 手动设置 - 安装Teams后，默认情况下，专用 PTT 按钮 (LEFT_TRIGGER_2) 适用于 Walkie Talkie
    
> [!NOTE]
> 这些设备未Teams认证。 他们已被验证为使用Teams对讲机。

### <a name="license-requirements"></a>许可证要求

Walkie Talkie 应用包含在Office 365订阅中Teams的所有付费许可证[中](/office365/servicedescriptions/teams-service-description)。 有关获取Teams的详细信息，请查看 [如何实现获取Microsoft Teams的访问权限](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)？

## <a name="further-information"></a>详细信息

- ITAdmins 可以通过应用策略保持对使用 Walkie Talkie 的人员的控制。
- 如果你的一线工作人员使用移动数据通过Teams进行通信，Walkie Talkie 将使用相同的方法。
- Walkie Talkie 应在低带宽的情况下或智能手机连接和工作的情况中正常工作。 如果根本没有连接，Walkie Talkie 将无法工作。

有关最终用户体验的进一步阅读，请参阅：

- [使用 Teams Walkie Talkie 开始](https://support.microsoft.com/office/get-started-with-teams-walkie-talkie-25bdc3d5-bbb2-41b7-89bf-650fae0c8e0c)
- [与你的团队与 Walkie Talkie 通信](https://support.microsoft.com/office/communicate-with-your-team-in-walkie-talkie-e4342550-5516-4451-b9ec-93166b60f8a4)
