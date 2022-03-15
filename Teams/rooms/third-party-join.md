---
title: 启用Teams 会议室设备加入第三方会议
ms.author: czawideh
author: cazawideh
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 本文讨论如何配置组织和Teams 会议室设备，以支持第三方会议加入 Cisco WebEx 和 Zoom。
ms.openlocfilehash: a4ae34593570d4b81eb381eb0fe68f1dea26d578
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503899"
---
# <a name="enable-teams-room-devices-to-join-third-party-meetings"></a>启用Teams会议室设备加入第三方会议

Microsoft Teams 会议室设备支持一键式体验来加入第三方联机会议，也称为直接来宾加入。 启用后，可以使用Teams 会议室加入 Cisco WebEx 和 Zoom 上托管的会议，就像加入在 Microsoft Teams 中托管的会议一样。

需要执行以下操作，然后才能Teams 会议室第三方会议：

1. 将Teams 会议室的Exchange Online邮箱配置为处理第三方会议的邀请。
2. 确保您的组织没有任何阻止您连接到第三方会议服务的策略。
3. 配置Teams 会议室以允许第三方会议。

以下部分将展示如何执行上述每个步骤。

## <a name="step-1-allow-calendar-invite-processing-for-third-party-meetings"></a>步骤 1：允许处理第三方会议的日历邀请

若要从团队聊天室启用一键式加入体验，首先需要为设备的会议室邮箱设置Exchange Online规则。 会议室邮箱需要允许外部会议并保留邮件正文和主题，以便它可以看到加入第三方会议所需的 URL。 若要使用 [Set-CalendarProcessing](/powershell/module/exchange/set-calendarprocessing?view=exchange-ps.) cmdlet 设置这些会议室邮箱选项，请执行下列操作：

1. 连接 PowerShell Exchange Online。 有关详细信息，请参阅连接Exchange Online身份验证的 [PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps) 连接，Exchange Online多重身份验证使用 [PowerShell](/powershell/exchange/mfa-connect-to-exchange-online-powershell?view=exchange-ps)，具体取决于身份验证方法。

2. 运行以下 (，) 获取会议室邮箱的 UPN 用户主体名称：

    ```powershell
    Get-Mailbox | Where {$_.RoomMailboxAccountEnabled -eq $True} | Format-Table Name, UserPrincipalName
    ```
    
3. 查找与设备关联的会议室邮箱Teams 会议室并记下其 UPN。

4. 找到会议室邮箱的 UPN 后，运行以下命令。 将 `<UserPrincipalName>` 替换为会议室邮箱的 UPN：

    ```powershell
    Set-CalendarProcessing <UserPrincipalName> -ProcessExternalMeetingMessages $True -DeleteComments $False -DeleteSubject $False
    ```

详细了解 [PowerShell Exchange Online。](/powershell/exchange/exchange-online-powershell?view=exchange-ps)

## <a name="step-2-configure-office-365-threat-protection-and-link-rewrite"></a>步骤 2：配置Office 365威胁防护和链接重写

若要启用一键式加入体验，会议邀请中需要显示并阅读来自第三方会议的会议加入链接信息。 如果你的组织使用 [Office 365 高级威胁防护 保险箱 链接](/microsoft-365/security/office-365-security/atp-safe-links)功能，或者如果你使用扫描所有传入和传出 URL 以识别威胁的第三方解决方案，则可能会更改会议加入 URL，使 Teams 会议室 设备无法识别会议。 若要确保不会发生此情况，需要将第三方会议服务的 URL 添加到 ATP 保险箱 链接"不重写"列表或第三方 URL 重写异常列表。

若要将第三方会议服务 URL 添加到 ATP 保险箱 链接"不重写"列表，请按照使用 [ATP](/microsoft-365/security/office-365-security/set-up-a-custom-do-not-rewrite-urls-list-with-atp?view=o365-worldwide) 链接设置自定义不重写 URL 列表中的步骤保险箱链接。 如果使用第三方解决方案，请参阅该解决方案的说明，将 URL 添加到其 URL 重写异常列表。

下面是可能需要添加到 AT 保险箱P 链接链接"不重写"列表或第三方 URL 重写异常列表的一些示例条目：

- **Cisco WebEx** `*.webex.com*`
- **缩放** `*.zoom.us*`、 `*.zoom.com*`、 `*.zoomgov.com*`

有关要添加到 ATP 保险箱 链接"不重写"列表或第三方 URL 重写异常列表的完整 URL 列表，请联系要接受其会议邀请的第三方会议服务提供商。 

> [!CAUTION]
> 仅将信任的 URL 添加到 ATP 保险箱链接"不重写"列表或第三方 URL 重写异常列表。

## <a name="step-3-enable-third-party-meetings-on-teams-rooms"></a>步骤 3：启用第三方会议Teams 会议室

需要执行的最后一个步骤是允许Teams 会议室第三方会议。 第三方会议需要用户名和密码来加入。 如果需要使用的用户名和电子邮件地址不同于设备的会议室邮箱，则需要将其添加到设备。 可以在设置或 XML Teams 会议室中执行此操作配置文件。

### <a name="use-device-settings"></a>使用设备设置

若要Teams 会议室触摸屏控制台配置屏幕，请执行下列操作：

1. 在控制台Microsoft Teams 会议室，选择"更多 **..."**。
2. 选择 **设置**"，然后输入设备管理员用户名和密码。
3. 转到"会议 **"选项卡** ，选择 **"Cisco WebEx**"和/ **或"缩放**"。
4. 如果要使用与会议室邮箱关联的用户名和电子邮件地址加入会议，请选择"使用会议室信息 **加入"**。
5. 如果要使用备用用户名和电子邮件地址加入会议，请选择"使用自定义信息加入"，并输入想要使用的用户名和电子邮件地址。
6. 选择 **"保存并退出"**。 设备将重启。

### <a name="use-the-skypesettingsxml-configuration-file"></a>使用 SkypeSettings.xml 配置文件

可以将以下设置添加到 `SkypeSettings.xml` 位于 中的 文件 `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState`。 有关该文件详细信息，`SkypeSettings.xml`请参阅[使用 XML 配置文件Microsoft Teams 会议室远程管理主机设置](xml-config-file.md)。

若要启用 Cisco WebEx 会议，将 `WebExMeetingsEnabled` XML 元素设置为 **True**，如下所示。

```xml
<WebExMeetingsEnabled>True</WebExMeetingsEnabled>
```

若要启用 Zoom 会议，请将 `ZoomMeetingsEnabled` XML 元素设置为 **True**，如下所示。

```xml
<ZoomMeetingsEnabled>True</ZoomMeetingsEnabled>
```

可以选择性地指定自定义用户名和电子邮件地址，以使用以下 XML 元素加入第三方会议。 如果提供的值无效，则Teams 会议室默认使用会议室邮箱用户名和电子邮件地址。

```xml
<UseCustomInfoForThirdPartyMeetings>true</UseCustomInfoForThirdPartyMeetings>

<CustomDisplayNameForThirdPartyMeetings>guestname</CustomDisplayNameForThirdPartyMeetings>

<CustomDisplayEmailForThirdPartyMeetings>guest@contoso.com</CustomDisplayEmailForThirdPartyMeetings>
```

> [!NOTE]
> 若要从 Teams 会议室 设备加入 Cisco WebEx 会议，需使用 Cisco WebEx Web 应用程序版本 WBS 40.7 或更高版本在 WebEx Meetings Pro 中托管 Cisco 会议。 
