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
description: 本文介绍为 Microsoft Teams 认证的手机列表以及 Microsoft Teams 认证的手机中支持的功能。
ms.openlocfilehash: d62832c8feb69d3492eed7d2f1e2fc80b6e1e1ea
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269907"
---
# <a name="phones-for-microsoft-teams"></a>Microsoft Teams 的电话功能

Microsoft Teams 为需要传统手机体验的用户支持一系列桌面电话。 本文提供 Teams 手机的完整概述，并有助于规划、交付和管理 Microsoft Teams 手机，作为 Microsoft Phone 系统解决方案的一部分。 

为了在手机上提供高质量和可靠的 Microsoft Teams 体验，我们正在与 Yealink、Crestron、Lenovo、Polycom 和 Audiocodes 合作并积极合作，开发和认证各种桌面电话和会议室音频设备。 若要获取 Teams 设备上的最新和最新信息，请转到 [Teams 市场](https://office.com/teamsdevices)。

若要管理手机，需要全局管理员、Teams 服务管理员或 Teams 设备管理员。有关管理员角色的详细信息，请参阅 [使用 Microsoft Teams 管理员角色来管理 Teams](../using-admin-roles.md)。

## <a name="features-supported-by-teams-phones"></a>Teams 手机支持的功能

Teams 认证的手机具有多种功能，可帮助用户完成其工作，并帮助你管理其使用。 下面是 Teams 认证手机中提供的功能摘要：

- **认证** 手机使用新式身份验证来简化登录并提高安全性。 用户可以通过在手机上输入用户名和密码或从电脑/智能手机等其他设备登录来登录。
- **速度拨号和呼叫历史记录** 用户可以快速访问其联系人、呼叫历史记录和语音邮件。 他们可以轻松地直接从手机管理联系人和快速拨号条目。
- **会议和呼叫** 用户可以查看其日程安排，并使用 Teams 的一触式联接轻松加入会议。
- **呼叫组** 参与呼叫组的电话代理可以轻松管理其可用性，并接受或拒绝来自呼叫队列的传入呼叫。
- **用户委派** 执行助理和管理员可以管理其高管的电话 - 截获来电;代表执行人员进行呼叫;接听行政人员已搁置的呼叫：并监视主管是否在呼叫、被搁置等。
- **热桌面** 用户只需登录到手机即可获取联系人、会议和其他首选项。 完成后，他们可以注销并让手机为下一个用户做好准备。
- **视频** 通过视频支持电话，用户可以像在计算机上一样加入通话和视频会议。 用户可以在可用时使用手机的相机快门和麦克风静音开关来保持隐私。
- **在一起更好** 在连接到运行 64 位 Teams 桌面客户端的 Windows 电脑时，手机可以以集成方式锁定和解锁。
- **辅助功能** 手机具有多种辅助功能，如高对比度文本，使任何人都可以更轻松地使用它们。
- **动态和增强的 E911 支持** 拨打 911 的登录用户将看到他们在电话上的位置。 
    > [!IMPORTANT]
    > 如果手机未登录，或者没有 Internet 连接，则无法拨打 911 电话。 如果发生这种情况，则会在手机上显示通知。

除了上述功能，还可以根据分配给登录到手机的用户的许可证和电话策略类型来控制哪些功能可用。 例如，使用个人帐户登录到手机的用户可以访问各种功能 -呼叫、会议、语音邮件等。 但是，分配了一个登录到手机的通用区域电话许可证的帐户只能访问有限范围的功能;呼叫历史记录和会议计划可能不会保留，例如，以保护用户的隐私。

## <a name="required-licenses"></a>所需的许可证

Teams 许可证可以作为[其 Microsoft 365 和Office 365订阅的一](/office365/servicedescriptions/teams-service-description)部分购买。 若要详细了解在手机上使用 Teams 所需的许可证，请参阅可用 [的电话系统许可证](https://products.office.com/microsoft-teams/voice-calling)。

有关获取 Teams 的详细信息，请查看[如何实现访问 Microsoft Teams？](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)

## <a name="deploy-your-phones-using-intune"></a>使用Intune部署手机

若要了解有关如何使用Intune部署 Teams 显示器的详细信息，请参阅[部署 Teams 手机和 Teams 显示器](phones-displays-deploy.md)。

## <a name="manage-your-phones"></a>管理手机

使用 Microsoft Teams 管理中心管理和使 Teams 手机保持最新状态。 有关详细信息，请参阅 [在 Teams 中管理设备](device-management.md)。

## <a name="upgrade-your-phones-to-teams-displays"></a>将手机升级到 Teams 显示器

[Microsoft Teams 显示](teams-displays.md) 器是一类一体专用 Teams 设备，具有环境触摸屏和 Cortana 支持的免提体验。 使用 Teams 显示器，用户可以使用麦克风、相机和扬声器 (或蓝牙耳机) 实现可靠的通话和会议体验。 Teams 显示与用户的 Windows 电脑集成，以提供允许无缝跨设备交互的配套体验

可以将组织中的 Teams 手机升级到 Microsoft Teams 管理中心中的 Teams 显示。 此选项仅适用于支持升级到 Teams 显示器的手机。 若要了解详细信息，请参阅[“将 Teams 手机升级到 Teams”显示。](upgrade-phones-to-displays.md)

## <a name="see-also"></a>另请参阅

[Teams 市场](https://office.com/teamsdevices)

[Microsoft Teams 认证的 IP 电话](teams-ip-phones.md)