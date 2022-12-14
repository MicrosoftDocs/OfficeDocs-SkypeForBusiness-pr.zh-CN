---
title: Microsoft Teams 的电话功能
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: kponnus
ms.topic: reference
ms.service: msteams
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
- Teams_ITAdmin_Devices
search.appverid: MET150
ms.localizationpriority: medium
description: 本文介绍已获得 Microsoft Teams 认证的电话列表，以及经 Microsoft Teams 认证的手机中支持的功能。
ms.openlocfilehash: 05283550190b1ed2498993ff80712b4894038f31
ms.sourcegitcommit: 0d97dc6616b3d633564409e39c08311af1522705
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/14/2022
ms.locfileid: "69392402"
---
# <a name="phones-for-microsoft-teams"></a>Microsoft Teams 的电话功能

Microsoft Teams 为需要传统手机体验的用户支持一系列桌面电话。 本文提供了 Teams 电话的完整概述，可帮助规划、交付和管理Microsoft Teams 电话，作为Microsoft电话系统解决方案的一部分。 

为了在手机上提供高质量且可靠的Microsoft Teams 体验，我们正在与 Yealink、Crestron、Lenovo、Polycom 和 Audiocodes 合作开发并认证各种桌面电话和会议室音频设备。 若要获取 Teams 设备上的最新信息，请转到 [Teams 市场](https://office.com/teamsdevices)。

若要管理电话，你需要是全局管理员、Teams 服务管理员或 Teams 设备管理员。有关管理员角色的详细信息，请参阅[使用 Microsoft Teams 管理员角色来管理 Teams](../using-admin-roles.md)。

## <a name="features-supported-by-teams-phones"></a>Teams 手机支持的功能

Teams 认证的手机具有广泛的功能，可帮助用户完成工作，并帮助你管理其使用。 下面是 Teams 认证手机中可用功能的摘要：

- **认证** 手机使用新式身份验证来简化登录并提高安全性。 用户可通过在手机上输入用户名和密码或从电脑/智能手机等其他设备登录来登录。
- **快速拨号和呼叫历史记录** 用户可以快速访问其联系人、呼叫历史记录和语音邮件。 他们可以直接通过手机轻松管理联系人和快速拨号条目。
- **会议和通话** 用户可以使用 Teams 的一键式加入查看其日程安排并轻松加入会议。
- **呼叫组** 参与呼叫组的电话代理可以轻松管理其可用性，并接受或拒绝来自呼叫队列的来电。
- **用户委派** 行政助理和管理员可以管理其高管的电话 - 拦截来电;代表执行人员拨打电话;接管高管搁置的电话;并监视执行人员是否正在通话、暂停等。
- **办公桌** 用户只需登录到电话即可获取其联系人、会议和其他首选项。 完成后，他们可以注销并让手机准备好供下一个用户使用。
- **视频** 支持视频的电话允许用户像在计算机一样加入通话和视频会议。 用户可以通过使用手机的相机快门和麦克风静音开关（如果可用）来保持隐私。
- **在一起更好** 连接到运行 64 位 Teams 桌面客户端的 Windows 电脑时，手机可以集成方式锁定和解锁。
- **辅助功能** 手机具有多种辅助功能，例如高对比度文本，使任何人都可以更轻松地使用它们。
- **动态和增强的 E911 支持** 呼叫 911 的已登录用户将在手机上看到其位置。 
    > [!IMPORTANT]
    > 如果手机未登录，或者没有 Internet 连接，则无法拨打 911 呼叫。 如果发生这种情况，则会在手机上显示通知。

除了上述功能，还可以根据分配给登录手机的用户的许可证类型和电话策略来控制哪些功能可用。 例如，使用个人帐户登录手机的用户可以访问各种功能-通话、会议、语音邮件等。 但是，分配有 **Microsoft Teams 共享设备** 许可证的帐户只能访问有限的功能范围;例如，为了保护用户的隐私，可能无法保留通话历史记录和会议计划。

## <a name="required-licenses"></a>所需许可证

Teams 许可证可以作为其 [Microsoft 365 和 Office 365 订阅](/office365/servicedescriptions/teams-service-description)的一部分购买。 若要详细了解在手机上使用 Teams 所需的许可证，请参阅可用的 [电话系统许可证](https://products.office.com/microsoft-teams/voice-calling)。

有关获取 Teams 的详细信息，请查看[如何实现获取Microsoft Teams 的访问权限？](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)

## <a name="deploy-your-phones-using-intune"></a>使用 Intune 部署手机

若要详细了解如何使用Intune部署 Teams 显示器，请参阅[部署 Teams 电话和 Teams 显示器](phones-displays-deploy.md)。

## <a name="manage-your-phones"></a>管理你的手机

使用 Microsoft Teams 管理中心管理 Teams 电话并使其保持最新状态。 有关详细信息，请参阅 [在 Teams 中管理设备](device-management.md)。

## <a name="upgrade-your-phones-to-teams-displays"></a>将手机升级到 Teams 显示器

[Microsoft Teams 显示器](teams-displays.md)是一种一体式专用 Teams 设备，它们具有环境触摸屏和由 Cortana 提供支持的免手动体验。 借助 Teams 显示器，用户可以使用麦克风、相机和扬声器 (或蓝牙头戴显示设备) 来获得可靠的通话和会议体验。 Teams 显示器与用户的 Windows 电脑集成，带来允许无缝跨设备交互的配套体验

可以将组织中的 Teams 电话升级到 Teams Microsoft 管理中心中的 Teams 显示。 此选项仅适用于支持升级到 Teams 显示器的手机。 若要了解详细信息，请参阅 [将 Teams 电话升级到 Teams 显示器](upgrade-phones-to-displays.md)。

## <a name="see-also"></a>另请参阅

[Teams 市场](https://office.com/teamsdevices)

[Microsoft Teams 认证的 IP 电话](teams-ip-phones.md)