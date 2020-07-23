---
title: 允许团队聊天室设备加入第三方会议
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: 本文介绍如何配置组织和团队室设备以支持加入 Cisco WebEx 和缩放的第三方会议。
ms.openlocfilehash: 708fb7f9d243559a571b2b9016fab1e38aa63114
ms.sourcegitcommit: 3e5cac88911611c94c0330bf50af9c34db308cdf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/22/2020
ms.locfileid: "45372211"
---
# <a name="enable-teams-room-devices-to-join-third-party-meetings"></a>允许团队会议室设备加入第三方会议

Microsoft 团队会议室设备支持连接第三方在线会议的一种触摸体验。 启用后，你可以使用团队聊天室设备加入在 Cisco WebEx 和缩放<sup>1</sup>上托管的会议，就像可以加入 Microsoft 团队中托管的会议一样轻松。

在你可以从团队聊天室设备加入第三方会议之前，你需要执行以下操作：

1. 配置团队聊天室设备的 Exchange Online 聊天室邮箱以处理第三方会议的邀请
2. 请确保你的组织没有任何策略，这些策略将阻止你连接到第三方会议服务
3. 将团队聊天室设备配置为允许第三方会议

以下部分介绍了如何执行每个步骤。

## <a name="step-1-allow-calendar-invite-processing-for-third-party-meetings"></a>步骤1：允许第三方会议的日历邀请处理

若要从团队聊天室设备启用一条触摸式加入体验，首先需要为设备的 Exchange Online 会议室邮箱设置日历处理规则。 会议室邮箱需要允许外部会议并保留邮件正文和主题，以便它可以看到加入第三方会议所需的 URL。 若要使用[CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) cmdlet 设置这些聊天室邮箱选项，请执行以下操作：

1. 连接到 Exchange Online PowerShell。 有关详细信息，请参阅使用[基本身份验证连接到 Exchange Online powershell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps)或[使用多重身份验证连接到 exchange online powershell](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps)，具体取决于你的身份验证方法。

2. 通过运行以下命令来获取聊天室邮箱的用户主体名称（UPN）：

    ```powershell
    Get-Mailbox | Where {$_.RoomMailboxAccountEnabled -eq $True} | Format-Table Name, UserPrincipalName
    ```
3. 查找与团队聊天室设备关联的聊天室邮箱的名称，并记下其 UPN

4. 找到聊天室邮箱的 UPN 后，运行以下命令。 替换 `<UserPrincipalName>` 为聊天室邮箱的 UPN：

    ```powershell
    Set-CalendarProcessing <UserPrincipalName> -ProcessExternalMeetingMessages $True -DeleteComments $False -DeleteSubject $False
    ```

了解有关[Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell?view=exchange-ps)的详细信息。

## <a name="step-2-configure-office-365-threat-protection-and-link-rewrite"></a>步骤2：配置 Office 365 威胁防护和链接重写

若要启用单一触控的连接体验，需要在会议邀请中演示和阅读会议邀请中的会议加入链接信息。 如果你的组织使用[Office 365 高级威胁防护安全链接](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links)   功能，或者你使用第三方解决方案来扫描所有传入和传出的威胁，则可能会更改会议加入 Url 并使团队聊天室设备无法识别会议。 若要确保不会发生这种情况，你需要将第三方会议服务的 Url 添加到 ATP 安全链接 "不重写" 列表或第三方 URL 重写例外列表。

若要将第三方会议服务 Url 添加到 ATP 安全链接 "不重写" 列表，请按照[使用 ATP 安全链接设置自定义的 "不重写 url" 列表](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide)中的步骤进行操作。 如果你使用第三方解决方案，请参阅该解决方案的说明，将 Url 添加到其 URL 重写例外列表。

下面是一些可能需要添加到 ATP 安全链接 "不重写" 列表或第三方 URL 重写例外列表的示例条目：

- **Cisco WebEx**`*.webex.com*`
- **缩放** `*zoom.us*` 、 `*zoom.com*``*zoomgov.com*`

若要将 Url 的完整列表添加到你的 ATP 安全链接 "请勿重写" 列表或第三方 URL 重写例外列表，请联系你想要接受会议邀请的第三方会议服务提供商。 

> [!CAUTION]
> 仅将你信任的 Url 添加到你的 ATP 安全链接 "请勿重写" 列表或第三方 URL 重写例外列表。

## <a name="step-3-enable-third-party-meetings-on-device"></a>步骤3：在设备上启用第三方会议

您需要执行的最后一步是允许每个团队房间设备加入第三方会议。 第三方会议需要用户名和电子邮件地址才能加入。 如果需要使用的用户名和电子邮件地址与设备的会议室邮箱不同，则需要将其添加到你的设备。 你可以在设备设置或 XML 配置文件中执行此操作。

### <a name="use-device-settings"></a>使用设备设置

若要使用其触摸屏配置团队聊天室设备，请执行下列操作：

1. 在 Microsoft 团队聊天室设备上，选择 " **更多 ...** "
2. 选择 " **设置**"，然后输入设备管理员的用户名和密码
3. 转到 " **会议"**   选项卡，选择 " **Cisco WebEx**"、"**缩放**<sup>1</sup>" 或两者
4. 如果要加入与会议室邮箱关联的用户名和电子邮件地址的会议，请选择 "**加入会议室信息**"
5. 如果想要使用备用用户名和电子邮件地址加入会议，请选择 "**使用自定义信息加入**"，然后输入要使用的用户名和电子邮件地址
6. 选择 " **保存并退出**"。 您的设备将重新启动。

### <a name="use-the-skypesettingsxml-configuration-file"></a>使用 SkypeSettings.xml 配置文件

可将以下设置添加到 `SkypeSettings.xml` 位于中的文件 `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState` 。 有关文件的详细信息 `SkypeSettings.xml` ，请参阅[使用 XML 配置文件远程管理 Microsoft 团队聊天室控制台设置](xml-config-file.md)。

若要启用 Cisco WebEx 会议，请将 `WebExMeetingsEnabled` XML 元素设置为 **True**，如下所示。

```xml
<WebExMeetingsEnabled>True</WebExMeetingsEnabled>
```

若要启用 "缩放<sup>1</sup>会议"，请将 `ZoomMeetingsEnabled` XML 元素设置为 **True**，如下所示。

```xml
<ZoomMeetingsEnabled>True</ZoomMeetingsEnabled>
```

你可以选择指定自定义用户名和电子邮件地址，以便使用以下 XML 元素加入第三方会议。 如果你提供的值无效，团队聊天室设备将默认为使用会议室邮箱用户名和电子邮件地址。

```xml
<UseCustomInfoForThirdPartyMeetings>true</UseCustomInfoForThirdPartyMeetings>

<CustomDisplayNameForThirdPartyMeetings>guestname</CustomDisplayNameForThirdPartyMeetings>

<CustomDisplayEmailForThirdPartyMeetings>guest@contoso.com</CustomDisplayEmailForThirdPartyMeetings>
```

> [!NOTE]
> 要从团队房间设备加入 Cisco WebEx 会议，需要使用 Cisco WebEx web 应用程序版本 WBS 40.7 或更高版本托管 Cisco 会议。

<sup>1</sup>缩放会议目前仅可通过技术访问计划选择 Microsoft 团队聊天室客户（点击）。
