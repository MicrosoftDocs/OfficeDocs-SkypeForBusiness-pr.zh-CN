---
title: 为会议室和共享设备创建Teams帐户
ms.author: czawideh
author: cazawideh
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: 阅读本文，了解如何为会议室和共享设备（包括 Microsoft Teams 会议室、Teams 会议室 on Surface Hub 和 Teams 显示器上的热桌面）创建资源帐户。
ms.openlocfilehash: e7525a9e9ec6737bab18de4351675d567b61611b
ms.sourcegitcommit: dafe48cea1643e1bd79390482da9b002d7e9e0bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2022
ms.locfileid: "63514543"
---
# <a name="create-and-configure-resource-accounts-for-rooms-and-shared-teams-devices"></a>为会议室和共享设备创建和配置Teams帐户

本文提供为共享空间和设备创建资源帐户的步骤，包括为 Windows 上的 Microsoft Teams 会议室、Android 上的 Teams 会议室、Surface Hub 上的 Teams 会议室 和 Teams 显示器上的热桌面配置资源帐户的步骤.

Microsoft 365资源帐户是专用于Teams资源（如会议室或投影仪）的邮箱帐户和专用帐户。 这些资源帐户可以使用创建会议邀请时定义的规则自动响应会议邀请。 例如，如果您有一个公用资源（如会议室），您可以为该会议室设置一个资源帐户，该资源帐户将自动接受或拒绝会议邀请，具体取决于其日历可用性。

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

> [!NOTE]
> **Skype for Business** <br><br>
> 如果需要使资源帐户能够使用 Skype for Business，请参阅使用 Microsoft Teams 会议室 [部署Skype for Business Server](with-skype-for-business-server-2015.md)

## <a name="before-you-begin"></a>开始之前

### <a name="requirements"></a>要求

根据环境，需要一个或多个角色来创建资源帐户。

|**环境**|**所需角色**|
|-----|-----|
|Azure Active Directory  <br/> |全局管理员或用户管理员  <br/> |
|Active Directory  <br/> |Active Directory Enterprise管理员、域管理员或具有创建用户的委托权限。 Azure Active Directory 连接同步权限。  <br/> |
|Exchange Online  <br/> |全局管理员或Exchange管理员   <br/> |
|Exchange Server  <br/> |Exchange组织管理或收件人管理   <br/> |

如果要创建资源帐户Teams 会议室，UPN 必须与资源帐户的 SMTP 地址匹配。 在[Microsoft Teams 会议室之前](requirements.md)，请参阅Teams 会议室。

### <a name="what-license-do-you-need"></a>需要哪些许可证？

创建资源Microsoft 365之前，请检查它所需的许可证类型：

- **Teams** 会议 如果要将资源帐户与共享设备（如 Microsoft Teams 会议室或 Teams 显示器）关联到热桌面，并使用它加入 Teams 会议，以便与会者可以使用它来演示视频和音频，则需要 会议室 许可证。 有关会议室许可详细信息，请参阅Teams 会议室[许可](rooms-licensing.md)。

- **PSTN 呼叫** 如果希望资源拨打或接听外部电话号码（称为公用电话交换网 (PSTN 呼叫) ）的呼叫，则需要 Microsoft 365 电话系统 或 Microsoft 365 商务语音 许可证。 只需完成以下概述中的步骤 1。 然后，[Microsoft Teams附加许可证](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md)了解详细信息。

- &mdash;&mdash;如果您仅使用资源帐户预订资源，即邀请该资源加入您的会议，并自动接受或拒绝邀请，则无需向资源帐户分配许可证，并且只需完成以下概述中的步骤 1。  

## <a name="overview"></a>概述

**步骤 1 -** [创建新的资源帐户](#create-a-resource-account)。 或者，如果会议室邮箱已存在，并且您想要将其转换为资源帐户，您可以修改现有Exchange[邮箱](?tabs=existing-account#create-a-resource-account)。

**步骤 2 -** 然后，[为会议配置](#configure-mailbox-properties)Teams帐户。

**步骤 3 -** 如果资源帐户将关联到共享设备（例如，Teams桌面显示）时，[请关闭密码过期](#turn-off-password-expiration)。

**步骤 4 -** 最后，[分配会议室许可证](#assign-a-meeting-room-license)，以便帐户可以访问Microsoft Teams。

创建和配置资源帐户后，请参阅查看其他[](#next-steps)设置任务（包括通讯组、网络功能以及呼叫）的"下一步"步骤。

## <a name="create-a-resource-account"></a>创建资源帐户

> [!TIP]
> 命名资源帐户时，建议使用电子邮件地址开头的标准命名约定。 这有助于创建动态组，以简化管理Azure Active Directory。 例如，可以针对将与该资源关联的所有资源帐户使用"Microsoft Teams 会议室"。

> [!TIP]
> 我们建议使用 Exchange Online 和 Azure Active Directory 创建所有资源帐户。

从以下选项卡之一使用 方法创建资源帐户：

#### <a name="in-microsoft-365-admin-center"></a>[**在 Microsoft 365 管理中心**](#tab/m365-admin-center)

1. 登录到 Microsoft 365 管理中心。

2. 为租户提供管理员Microsoft 365凭据。

3. 转到左侧 **面板** 中的"资源"，然后选择"会议室& **设备"**。 如果这些选项在左侧面板中不可用，可能需要先选择" **全部显示** "。

4. 选择 **"添加资源邮箱** "以创建新的聊天室帐户。 输入帐户显示名称电子邮件地址，选择"添加 **"**，然后选择"关闭 **"**。

5. 默认情况下，资源帐户配置如下设置：

    - 允许重复会议
    - 自动拒绝超出以下限制的会议
      - 预订时段 (天) ：180
      - 最长持续时间 (小时) ：24
    - 自动接受会议请求

    如果要更改它们，请在选择"关闭 **"之前选择** "设置计划 **选项"**。 如果以后想要更改它们，请转到 **ResourcesRooms** >  **&设备，** 选择资源帐户。 然后在" **预订选项"下**，选择" **编辑"**。

6. 转到" **用户** > **""活动** 用户"，然后选择创建的聊天室以打开属性面板。

7. 接下来，为资源帐户分配密码。 在面板中，选择" **重置密码"**。
 
8. 要求用户在共享设备上更改密码将导致登录问题。 取消 **选中"要求此用户在首次登录时更改其密码"，** 然后选择"重置 **"**。

9. 在" **许可证和应用"** 部分中 **，将"** 选择位置"设置为要安装设备的国家/地区。 然后选择要分配的许可证（例如"会议室"，然后选择"保存 **更改"**。 许可证可能因组织而异。

若要更改资源邮箱的设置，请参阅[配置邮箱属性](#configure-mailbox-properties)或使用 Exchange管理中心。

可能还需要将带宽策略或会议策略应用到此帐户。 有关详细信息 [，](#next-steps) 请参阅"下一步"。

#### <a name="with-exchange-online"></a>[**使用 Exchange Online**](#tab/exchange-online)

1. 连接 [PowerShell Exchange Online。](/powershell/exchange/connect-to-exchange-online-powershell)

    ``` PowerShell
    Connect-ExchangeOnline
    ```

2. 默认情况下，会议室邮箱没有关联的帐户。 创建会议室邮箱时添加帐户，以便它可以向Microsoft Teams。

    如果要创建新的资源邮箱：
    
    ``` PowerShell
    New-Mailbox -MicrosoftOnlineServicesID <Office365 ID> -Name <String> -Alias <string> -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
    ```
    
    此示例使用以下设置创建新的会议室邮箱：

        - Account: ConferenceRoom01@contoso.com
          
        - Name: ConferenceRoom01
        
        - Alias: ConferenceRoom01
        
        - Account password: P@$$W0rd5959

    ``` PowerShell
    New-Mailbox -MicrosoftOnlineServicesID ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
    ```

如果不使用混合Exchange，可以继续执行下一步配置[邮箱属性](#configure-mailbox-properties)。

如果使用混合Exchange，则需要为本地域帐户添加电子邮件地址。 有关详细信息[，请参阅同步Office 365用户帐户](https://support.microsoft.com/topic/how-to-use-smtp-matching-to-match-on-premises-user-accounts-to-office-365-user-accounts-for-directory-synchronization-75673b94-e1b8-8a9e-c413-ee5a2a1a6a78)目录。

#### <a name="with-exchange-server"></a>[**使用 Exchange Server**](#tab/exchange-server)

  1. 连接 Exchange命令行管理程序。 [打开 Exchange 命令行管理程序](/powershell/exchange/exchange-server/open-the-exchange-management-shell)，或者使用[远程 PowerShell Exchange服务器](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)。

   2. 创建新的会议室邮箱：

      ``` PowerShell
      New-Mailbox -UserPrincipalName <UPN> -Name <String> -Alias <String> -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
      ```
     
   此示例使用以下设置创建新的会议室邮箱：

   - 帐户：ConferenceRoom01@contoso.com
  
   - 名称：ConferenceRoom01

   - 别名：ConferenceRoom01

   - 帐户密码：P@$$W 0rd5959

   ``` PowerShell
   New-Mailbox -UserPrincipalName ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
   ```

#### <a name="modify-an-existing-exchange-room-mailbox"></a>[**修改现有Exchange邮箱**](#tab/existing-account)

若要修改现有会议室邮箱以成为资源帐户，请使用以下语法：

``` PowerShell
Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
```

此示例为别名为 ConferenceRoom02 的现有会议室邮箱启用帐户，将密码9898P@$$W 0rd。

``` PowerShell
Set-Mailbox -Identity ConferenceRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
```

如果使用混合Exchange，则还需要为本地域帐户添加电子邮件地址。 有关详细信息[，请参阅同步Office 365用户帐户](https://support.microsoft.com/topic/how-to-use-smtp-matching-to-match-on-premises-user-accounts-to-office-365-user-accounts-for-directory-synchronization-75673b94-e1b8-8a9e-c413-ee5a2a1a6a78)目录。

有关详细的语法和参数信息，请参阅 [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) 和 [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox)。

> [!NOTE]
> 如果要为 Teams Room 创建此Surface Hub，则还应在此帐户上启用 ActiveSync。 这允许您直接从应用程序发送电子邮件，Surface Hub Whiteboard 等功能。 有关详细信息[，请参阅将 ActiveSync 策略 (Surface Hub) ](/surface-hub/apply-activesync-policies-for-surface-hub-device-accounts)设备帐户。

---

> [!IMPORTANT]
> 如果仅使用此资源帐户预订空间并自动接受或拒绝邀请，则已完成设置。 如果你使用此资源帐户进行 PSTN 呼叫，请参阅Microsoft Teams[附加](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md)许可证以确定它所需的许可证。
>
> 仅在资源帐户用于 Teams 会议室 on Windows、Teams 会议室 on Android、Teams 会议室 on Surface Hub 或 Teams 显示器时，才继续下一部分。

## <a name="configure-mailbox-properties"></a>配置邮箱属性

在 Exchange PowerShell（联机或本地）中，在会议室邮箱上配置以下设置以改进会议体验：

- **AutomateProcessing： `AutoAccept`** 会议组织者直接收到会议室预订决策，无需人工干预。

- **AddOrganizerToSubject： `$false`** 会议组织者不会添加到会议请求的主题。

- **DeleteComments： `$false`** 在传入会议请求的邮件正文中保留任何文本。 这是处理外部会议Teams第三方会议以提供 One Touch Join 体验所必需。

- **DeleteSubject： `$false`** 保留传入会议请求的主题。

- **ProcessExternalMeetingMessages： `$true`** 指定是否处理源自组织外部Exchange请求。 对于外部Teams和第三[方会议是必需的](/microsoftteams/rooms/third-party-join)。

- **RemovePrivateProperty： `$false`** 确保会议组织者在原始会议请求中发送的专用标志保持不变。

- **AddAdditionalResponse： `$true`** AdditionalResponse 参数指定的文本将添加到会议请求。

- **AdditionalResponse："这是Microsoft Teams会议室！"** 要添加到会议接受响应的其他文本。

此示例在名为 ConferenceRoom01 的会议室邮箱上配置这些设置：

``` PowerShell
Set-CalendarProcessing -Identity "ConferenceRoom01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -ProcessExternalMeetingMessages $true -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
```

有关详细的语法和参数信息，请参阅 [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing)。

## <a name="turn-off-password-expiration"></a>关闭密码过期

如果资源帐户密码过期，设备在到期日期后不会登录。 然后，需要更改资源帐户的密码，然后在每个设备上更新密码。 若要避免这种情况，可以关闭密码过期。
  
> [!NOTE]
> 设置 **密码永不过期** 是共享设备Microsoft Teams要求。 如果域规则禁止密码过期，则需要为每个设备资源帐户创建Teams例外。

请按照以下选项卡之一中的步骤关闭密码过期：

#### <a name="azure-active-directory-20"></a>[**Azure Active Directory 2.0**](#tab/azure-active-directory2-password/)

首先，连接 Active Directory PowerShell：

```PowerShell
   Connect-AzureAD
```

然后， [请参阅将密码设置为永不过期](/microsoft-365/admin/add-users/set-password-to-never-expire?view=o365-worldwide#set-a-password-to-never-expire)。

此示例将帐户的密码 ConferenceRoom01@contoso.com 永不过期。

```PowerShell
Set-AzureADUser -ObjectID ConferenceRoom01@contoso.com -PasswordPolicies DisablePasswordExpiration
```

#### <a name="azure-active-directory-10"></a>[**Azure Active Directory 1.0**](#tab/azure-active-directory1-password/)

 1. 连接 MSOnline PowerShell：

       ```PowerShell
       Connect-MsolService
       ```

       有关 Active Directory 的详细信息，请参阅 Azure Active Directory ([MSOnline) ](/powershell/azure/active-directory/overview?view=azureadps-1.0)。

2. 使用以下语法将密码设置为永不过期：

    ```PowerShell
    Set-MsolUser -Identity <samAccountName> -PasswordNeverExpires $true
    ```

    此示例将帐户的密码 ConferenceRoom01@contoso.com 永不过期。

    ```PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -PasswordNeverExpires $true
    ```

#### <a name="active-directory-on-premises"></a>[**Active Directory (本地)**](#tab/active-directory1-password/)

1. 连接 Active Directory PowerShell：

    ```PowerShell
       Import-Module ActiveDirectory
    ```
    
    有关 Active Directory PowerShell 的详细信息，请参阅 [ActiveDirectory](/powershell/module/activedirectory/?view=windowsserver2022-ps)。

2. 使用以下语法将密码设置为永不过期：

    ```PowerShell
    Set-ADUser -Identity <samAccountName> -PasswordNeverExpires $true
    ```

    此示例将帐户的密码 ConferenceRoom01@contoso.com 永不过期。

    ```PowerShell
    Set-ADUser -Identity ConferenceRoom01@contoso.com -PasswordNeverExpires $true
    ```

---

## <a name="assign-a-meeting-room-license"></a>分配会议室许可证

资源帐户需要Microsoft 365或Office 365许可证才能登录Microsoft Teams。

> [!NOTE]
> Microsoft Teams 会议室标准版Microsoft Teams 会议室高级版共享会议室设备的两个可用 SKUS，包括Teams 会议室。 使用热桌面Teams需要会议室许可证。 有关详细信息，请参阅Teams[许可](rooms-licensing.md)。

若要使用许可证分配Microsoft 365 管理中心，请参阅[向用户分配许可证](/microsoft-365/admin/manage/assign-licenses-to-users)。 若要使用 Azure AD分配许可证，请参阅以下选项卡之一：

#### <a name="active-directory-20"></a>[**Active Directory 2.0**](#tab/active-directory2-license/)


1. 连接 Azure AD
  
    ```PowerShell
    Connect-AzureAD
    ```

     有关 Active Directory 的详细信息，请参阅 [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/overview?view=azureadps-2.0)。
    
2. 使用 cmdlet 将使用位置分配给 `Set-AzureADUser` 资源帐户。 这会确定可用的许可证 SKUS。

    此示例中，用户位于美国 (美国) ：

    ```PowerShell
    Set-AzureADUser -ObjectID ConferenceRoom01@contoso.com -UsageLocation 'US'
    ```

3. 然后，使用 `Get-AzureADSubscribedSku` 检索组织或组织的可用 S MICROSOFT 365 Office 365列表。

    ```PowerShell
    Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
    ```

4. 若要分配许可证，请使用 `Set-AzureADUser` cmdlet，并将许可证 SKU ID (步骤 2) 转换为 PowerShell 许可证类型对象。 然后，将该对象分配给资源帐户。 在下面的示例中，许可证 SKU ID 为 6070a4c8-34c6-4937-8dfb-39bbc6397a60，并分配给帐户 conferenceroom01@contoso.com：

    ```PowerShell
    #Create an object for a single license type
    $License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense 
    $License.SkuId = "6070a4c8-34c6-4937-8dfb-39bbc6397a60" 
       
    #Create an object for a multiple license type
    $Licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses 
       
    #Add the single license object to the multiple license object
    $Licenses.AddLicenses = $License 
       
    #Assign the license to the resource account
    Set-AzureADUserLicense -ObjectId ConferenceRoom01@contoso.com -AssignedLicenses $Licenses
    ```

#### <a name="active-directory-10"></a>[**Active Directory 1.0**](#tab/active-directory1-license/)

1. 连接 MSOnline PowerShell。

   ```PowerShell
   Connect-MsolService
   ```

    有关 Active Directory 的详细信息，请参阅 Azure Active Directory ([MSOnline) 。](/powershell/azure/active-directory/overview?view=azureadps-1.0)

2.  使用 cmdlet 将使用位置分配给 `Set-MsolUser` 资源帐户。 这会确定可用的许可证 SKUS。

    此示例中，用户位于美国 (美国) 。
    
    ```PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -UsageLocation 'US'
    ```
    
    然后，可以使用 `Get-MsolAccountSku` 检索组织或组织Microsoft 365可用的 S OFFICE 365列表。

4. 若要分配许可证，请使用 `Set-MsolUser` cmdlet。 本示例将"contoso：MEETING_ROOM"许可证分配给帐户 conferenceroom01@contoso.com：

    ```PowerShell
    Set-MsolUserLicense -UserPrincipalName 'ConferenceRoom01@contoso.com' -AddLicenses 'contoso:MEETING_ROOM'
    ```

---

若要验证帐户创建和许可证分配，请Teams创建的帐户登录到任何客户端。

## <a name="next-steps"></a>后续步骤

### <a name="network-and-bandwidth"></a>网络和带宽

您可能需要对此帐户应用自定义网络、带宽或会议策略。 有关网络和带宽策略详细信息，请参阅 [音频和视频的会议&设置](/microsoftteams/meeting-policies-audio-and-video)。 对于Teams 会议室，建议将会议策略带宽设置为 10 Mbps。

出于协作目的，请PowerPoint实时笔记、白板和共享笔记。 您可能需要创建会议策略来调整参与者和来宾设置，Teams 会议室。 例如，查看大厅设置，例如要自动允许的与会者。 有关会议策略Teams，请参阅[管理会议Microsoft Teams](/microsoftteams/meeting-policies-overview)。

### <a name="calling"></a>通话

使用资源帐户启用调用没有独特的要求。 启用资源帐户以与启用常规用户相同的方式进行调用。

> [!NOTE]
> 建议通过向设备资源帐户分配呼叫策略来关闭共享设备的语音邮件。 有关详细信息[，请参阅](../teams-calling-policy.md)Teams呼叫和呼叫转发。

### <a name="configure-distribution-groups"></a>配置通讯组

若要组织会议室位置，可以将设备资源帐户添加到Exchange组。 例如，如果在三个不同的地理位置设有办公室，可以创建三个通讯组，并为每个位置添加相应的资源帐户。 有关详细信息，请参阅 [创建聊天室列表](/exchange/recipients/room-mailboxes?view=exchserver-2019#create-a-room-list)。

## <a name="related-articles"></a>相关文章

[为帐户配置Microsoft Teams 会议室](rooms-configure-accounts.md)

[Microsoft Teams 会议室规划](rooms-plan.md)

[部署 Microsoft Teams 会议室](rooms-deploy.md)

[管理 Microsoft Teams 会议室](rooms-manage.md)

[Microsoft Teams 会议室许可](rooms-licensing.md)
