---
title: 启用Teams 会议室设备加入第三方会议
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
ms.localizationpriority: medium
description: 本文讨论如何配置组织和Teams 会议室设备以支持加入 Cisco Webex 和 Zoom 的第三方会议。
ms.openlocfilehash: 23eefeb564e3333b1bc2105a1fc4d57a0ff41bbe
ms.sourcegitcommit: bdb919a6f53556f76dd4a71759412023e6e18fbb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2022
ms.locfileid: "66529674"
---
# <a name="enable-teams-rooms-devices-to-join-third-party-meetings"></a>启用Teams 会议室设备加入第三方会议

Microsoft Teams 会议室设备支持加入第三方联机会议（也称为直接来宾加入）的一次性体验。 启用后，可以使用Teams 会议室加入在 Cisco Webex 和 Zoom 上托管的会议，就像可以加入 Microsoft Teams 中托管的会议一样容易。

支持的设备和服务：

- Windows 上的 MTR，所有认证模型 - Zoom、Cisco Webex

- Android、Poly、Yealink 和 Logitech 认证模型上的 MTR - 缩放

> [!NOTE]
> 若要从Teams 会议室设备加入 Cisco Webex 会议，需要使用 Cisco Webex Web 应用程序版本 WBS 40.7 或更高版本在 Webex Meetings Pro 中托管 Cisco 会议。 

若要从Teams 会议室加入第三方会议，需要执行以下操作：

1. 将Teams 会议室Exchange Online会议室邮箱配置为处理第三方会议的邀请。
2. 确保组织没有任何策略会阻止你连接到第三方会议服务。
3. 配置Teams 会议室以允许第三方会议。

以下部分介绍如何完成其中的每一个步骤。

## <a name="step-1-allow-calendar-invite-processing-for-third-party-meetings"></a>步骤 1：允许处理第三方会议的日历邀请

若要从团队会议室启用一触式联接体验，首先需要为设备的Exchange Online会议室邮箱设置日历处理规则。 会议室邮箱需要允许外部会议并保留邮件正文和主题，以便查看加入第三方会议所需的 URL。 若要使用 [Set-CalendarProcessing](/powershell/module/exchange/set-calendarprocessing.) cmdlet 设置这些会议室邮箱选项，请执行以下操作：

1. 连接到 Exchange Online PowerShell。 有关详细信息，请参阅[使用基本身份验证连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) 或[使用多重身份验证连接到 Exchange Online PowerShell](/powershell/exchange/mfa-connect-to-exchange-online-powershell)，具体取决于身份验证方法。

2. 如果运行以下命令不知道，请获取会议室邮箱的用户主体名称 (UPN) ：

    ```powershell
    Get-Mailbox | Where {$_.RoomMailboxAccountEnabled -eq $True} | Format-Table Name, UserPrincipalName
    ```
    
3. 查找与Teams 会议室设备关联的会议室邮箱的名称，并记下其 UPN。

4. 找到会议室邮箱的 UPN 后，请运行以下命令。 替换 `<UserPrincipalName>` 为会议室邮箱的 UPN：

    ```powershell
    Set-CalendarProcessing <UserPrincipalName> -ProcessExternalMeetingMessages $True -DeleteComments $False -DeleteSubject $False
    ```

详细了解 [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)。

## <a name="step-2-configure-office-365-threat-protection-and-link-rewrite"></a>步骤 2：配置Office 365威胁防护和链接重写

若要启用一触式联接体验，需要在会议邀请中提供第三方会议的会议加入链接信息并可读。 如果组织使用[Microsoft Defender for Office 365](/microsoft-365/security/office-365-security/safe-links)安全链接功能，或者使用第三方解决方案扫描所有传入和传出 URL 以获取威胁，则可能会更改会议加入 URL，并使会议无法被Teams 会议室设备识别。 若要确保不会发生这种情况，需要将第三方会议服务的 URL 添加到 Defender for [Office 365 安全链接 **不重写** 列表](/microsoft-365/security/office-365-security/safe-links)或第三方 URL 重写异常列表。

 如果使用第三方解决方案，请参阅该解决方案的说明，将 URL 添加到其 URL 重写异常列表。

下面是可能需要添加到Defender for Office 365安全链接 *不重写* 列表或第三方 URL 重写异常列表的一些示例条目：

- **Cisco Webex** `*.webex.com/*`
- **缩放**`*.zoom.us/*`， `*.zoom.com/*``*.zoomgov.com/*`

若要将 URL 的完整列表添加到Defender for Office 365安全链接 *不重写* 列表或第三方 URL 重写异常列表，请联系要接受会议邀请的第三方会议服务提供商。

> [!CAUTION]
> 仅将信任的 URL 添加到Microsoft Defender for Office 365安全链接 *不重写* 列表或第三方 URL 重写异常列表。

## <a name="step-3a-enable-third-party-meetings-on-teams-rooms-on-windows"></a>步骤 3a：在 Windows 上的Teams 会议室上启用第三方会议

需要执行的最后一步是允许Teams 会议室加入第三方会议。 第三方会议需要用户名和电子邮件地址才能加入。 如果需要使用的用户名和电子邮件地址不同于设备的会议室邮箱，则需要将它们添加到设备。 可以在Teams 会议室设置或 XML 配置文件中执行此操作。 可以在任何支持Teams 会议室或 Windows 上Teams 会议室的 XML 配置文件的Teams 会议室设置中执行此操作。

### <a name="use-device-settings"></a>使用设备设置

若要使用触摸屏控制台在 Windows 上配置Teams 会议室，请执行以下操作：

1. 在Microsoft Teams 会议室控制台上，选择 **“更多**”。
2. 选择 **“设置”**，然后输入设备管理员用户名和密码。
3. 转到 **“会议”** 选项卡，选择要启用 (的第三方会议提供程序，例如， **Webex**、 **Zoom** 等) 。
4. 如果要使用与会议室邮箱关联的用户名和电子邮件地址加入会议，请选择 **“加入会议室信息**”。
5. 如果要使用备用用户名和电子邮件地址加入会议，请选择 **“使用自定义信息加入** ”，然后输入要使用的用户名和电子邮件地址。
6. 选择 **“保存”并退出**。 设备将重启。

### <a name="use-the-skypesettingsxml-configuration-file"></a>使用SkypeSettings.xml配置文件

可将以下设置添加到位于其中 `SkypeSettings.xml` 的文件中 `C:\Users\Skype\AppData\Local\Packages\Microsoft.SkypeRoomSystem_8wekyb3d8bbwe\LocalState`。 有关该文件的`SkypeSettings.xml`详细信息，请参阅[使用 XML 配置文件远程管理Microsoft Teams 会议室控制台设置](xml-config-file.md)。

若要启用 Cisco Webex 会议，请将 XML 元素设置 `WebexMeetingsEnabled` 为 **True**，如下所示。

```xml
<WebexMeetingsEnabled>True</WebexMeetingsEnabled>
```

若要启用 Zoom 会议，请将 XML 元素设置 `ZoomMeetingsEnabled` 为 **True**，如下所示。

```xml
<ZoomMeetingsEnabled>True</ZoomMeetingsEnabled>
```

可以选择使用以下 XML 元素指定用于加入第三方会议的自定义用户名和电子邮件地址。 如果提供的值无效，则Teams 会议室设备将默认使用会议室邮箱用户名和电子邮件地址。

```xml
<UseCustomInfoForThirdPartyMeetings>true</UseCustomInfoForThirdPartyMeetings>

<CustomDisplayNameForThirdPartyMeetings>guestname</CustomDisplayNameForThirdPartyMeetings>

<CustomDisplayEmailForThirdPartyMeetings>guest@contoso.com</CustomDisplayEmailForThirdPartyMeetings>
```
## <a name="step-3b-enable-third-party-meetings-on-teams-rooms-on-android"></a>步骤 3b：在 Android 上的Teams 会议室上启用第三方会议

若要使用触摸屏控制台或会议室前显示器在 Android 上配置Teams 会议室，请执行以下操作：

1.  在Microsoft Teams 会议室控制台或会议室前显示屏上，选择 **“更多**”。
2.  选择 **“设置”**，然后：
    -   例如，如果使用个人帐户 (具有 E5 许可证的帐户) ，请选择 **“会议”** 选项。
    -   例如，如果使用共享帐户 (具有Teams 会议室许可证的资源帐户) ，请选择 **“设备设置**”，**找到 Teams 管理员 设置**，输入管理员密码，然后选择 **“会议**”选项。
      > [!NOTE]
      > 某些设备制造商需要管理员密码才能访问 **设备设置** 。

    ![Android 上 MTR 的会议设置](..\media\mtrandroid.png)

3.  选择要启用的第三方会议提供程序。
4.  如果要使用自定义用户名和电子邮件地址加入会议，请选择 **“使用自定义名称和电子邮件加入**”。 若要更新自定义个人信息，请按 **“编辑自定义信息”** 并输入首选名称和电子邮件地址。

