---
title: 为会议室和共享Teams设备创建资源帐户
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
description: 请阅读本文，了解如何为会议室和共享设备创建资源帐户，包括Microsoft Teams 会议室、Surface Hub上的Teams 会议室以及Teams显示器上的热桌面。
ms.openlocfilehash: e788ca2086faf86f602ef0938d520ea03dce4ef4
ms.sourcegitcommit: 5bfd2e210617e4388241500eeda7b50d5f2a0ba3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2022
ms.locfileid: "64885020"
---
# <a name="create-and-configure-resource-accounts-for-rooms-and-shared-teams-devices"></a>为会议室和共享Teams设备创建和配置资源帐户

本文提供了为共享空间和设备创建资源帐户的步骤，其中包括为Windows、Android 上的 Microsoft Teams 会议室Teams 会议室、Surface Hub上的Teams 会议室和Teams显示器上的热桌面配置资源帐户的步骤.

Microsoft 365资源帐户是专用于特定资源（如会议室或投影机）的邮箱和Teams帐户。 这些资源帐户可以使用创建时定义的规则自动响应会议邀请。 例如，如果你有一个常见的资源（例如会议室），则可以为该会议室设置一个资源帐户，该帐户将根据会议室的日历可用性自动接受或拒绝会议邀请。 

每个资源帐户对于单个Microsoft Teams 会议室安装或Teams显示热桌面实现都是独一无二的。

> [!NOTE]
> 如果使用Microsoft Teams面板，则Teams 会议室资源帐户将登录到Teams 会议室和关联的Teams面板。

[!INCLUDE [m365-teams-resource-account-difference](../includes/m365-teams-resource-account-difference.md)]

> [!NOTE]
> **Skype for Business** <br><br>
> 如果需要使资源帐户能够使用Skype for Business，请参阅[使用Skype for Business Server部署Microsoft Teams 会议室](with-skype-for-business-server-2015.md)

## <a name="before-you-begin"></a>开始之前

### <a name="requirements"></a>要求

根据你的环境，你需要一个或多个角色来创建资源帐户。

|**环境**|**必需角色**|
|-----|-----|
|Azure Active Directory  <br/> |全局管理员或用户管理员  <br/> |
|Active Directory  <br/> |Active Directory Enterprise管理员、域管理员或具有创建用户的委派权限。 Azure Active Directory 连接同步权限。  <br/> |
|Exchange Online  <br/> |全局管理员或Exchange管理员   <br/> |
|Exchange Server  <br/> |Exchange组织管理或收件人管理   <br/> |

如果要为Teams 会议室创建资源帐户，UPN 必须与资源帐户的 SMTP 地址匹配。 在部署Teams 会议室之前，请参阅Microsoft Teams 会议室[要求](requirements.md)。

### <a name="what-license-do-you-need"></a>需要什么许可证？

创建Microsoft 365资源帐户之前，请检查它需要哪种类型的许可证：

- **Teams会议** 如果要将资源帐户与共享设备（例如Microsoft Teams会议室或Teams显示器）关联到热桌面，并使用它加入Teams会议，以便与会者可以使用它通过它呈现视频和音频，则需要会议室许可证。 有关会议室许可的详细信息，请[参阅Teams 会议室许可](rooms-licensing.md)。

- **PSTN 调用** 如果希望资源拨打或接听外部电话号码（ (称为公共交换电话网络或 PSTN 呼叫) ）的呼叫，则需要Microsoft 365 电话系统或Microsoft 365 商务语音许可证。 只需在以下概述中完成步骤 1。 然后，有关详细信息，请参阅[Microsoft Teams加载项许可证](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md)。

- 如果仅使用资源帐户来预订资源&mdash;，请邀请资源加入会议，并让其自动接受或拒绝邀请&mdash;，无需向资源帐户分配许可证，只需在以下概述中完成步骤 1。  

## <a name="overview"></a>概述

**步骤 1 -** [创建新的资源帐户](#create-a-resource-account)。 或者，如果会议室邮箱已存在，并且要将其转换为资源帐户，则可以[修改现有的Exchange会议室邮箱](?tabs=existing-account#create-a-resource-account)。

**步骤 2 -** 然后，为Teams会议 [配置帐户](#configure-mailbox-properties)。

**步骤 3 -** 如果资源帐户要与共享设备关联，例如Teams使用热桌面显示，[请关闭密码过期](#turn-off-password-expiration)。

**步骤 4 -** 最后，[分配会议室许可证](#assign-a-meeting-room-license)，以便帐户可以访问Microsoft Teams。

创建和配置资源帐户后，请参阅 [后续步骤](#next-steps) ，查看其他设置任务，包括分发组、网络功能和调用。

## <a name="create-a-resource-account"></a>创建资源帐户

> [!TIP]
> 命名资源帐户时，建议使用电子邮件地址开头的标准命名约定。 这将有助于创建动态组，以简化Azure Active Directory中的管理。 例如，可以对与Microsoft Teams 会议室关联的所有资源帐户使用“mtr-”。

> [!TIP]
> 建议使用Exchange Online和Azure Active Directory创建所有资源帐户。

使用以下选项卡之一的方法创建资源帐户：

#### <a name="in-microsoft-365-admin-center"></a>[**在Microsoft 365 管理中心**](#tab/m365-admin-center)

1. 登录到 Microsoft 365 管理中心。

2. 为Microsoft 365租户提供管理员凭据。

3. 转到左侧面板中的 **“资源** ”，然后选择 **“会议室”&设备**。 如果这些选项在左侧面板中不可用，则可能需要先选择 **“全部显示** ”。

4. 选择 **“添加资源”邮箱** 以创建新的会议室帐户。 输入帐户的显示名称和电子邮件地址，选择 **“添加**”，然后选择 **“关闭**”。

5. 默认情况下，资源帐户配置有以下设置：

    - 允许重复会议
    - 自动拒绝超出以下限制的会议
      - 预订窗口 (天) ：180
      - 最长持续时间 (小时) ：24
    - 自动接受会议请求

    如果要更改它们，请在选择 **“关闭**”之前选择 **“设置计划选项**”。 如果以后要更改它们，请转到 **ResourceRooms** >  **&设备**，选择资源帐户。 然后在 **“预订”选项** 下，选择 **“编辑**”。

6. 转到 **UsersActive** >  用户，然后选择创建的房间以打开属性面板。

7. 接下来，将密码分配给资源帐户。 在面板中，选择 **“重置密码**”。
 
8. 要求用户更改共享设备上的密码会导致登录问题。 取消选中 **要求此用户在首次登录时更改其密码**，然后选择 **“重置**”。

9. 在 **“许可证和应用** ”部分中，将 **“选择”位置** 设置为将安装设备的国家或地区。 然后选择要分配的许可证，例如会议室，然后选择 **“保存更改**”。 许可证可能因组织而异。

若要更改资源邮箱的设置，请参阅[配置邮箱属性](#configure-mailbox-properties)或使用Exchange管理中心。

你可能需要将带宽策略或会议策略应用到此帐户。 有关详细信息，请参阅 [后续步骤](#next-steps) 。

#### <a name="with-exchange-online"></a>[**使用Exchange Online**](#tab/exchange-online)

1. 连接到 [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

    ``` PowerShell
    Connect-ExchangeOnline
    ```

2. 默认情况下，会议室邮箱没有关联的帐户。 创建会议室邮箱时添加帐户，以便它可以使用Microsoft Teams进行身份验证。

    如果要创建新的资源邮箱：
    
    ``` PowerShell
    New-Mailbox -MicrosoftOnlineServicesID <Office365 ID> -Name <String> -Alias <string> -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
    ```
    
    此示例使用以下设置创建新会议室邮箱：

    - 帐户：ConferenceRoom01@contoso.com
          
    - 名称：ConferenceRoom01
        
     - 别名：ConferenceRoom01
        
     - 帐户密码：P@$$W 0rd5959

    ``` PowerShell
    New-Mailbox -MicrosoftOnlineServicesID ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
    ```

如果你不在Exchange混合配置中，则可以继续执行下一步，[配置邮箱属性](#configure-mailbox-properties)。

如果使用的是Exchange混合配置，则需要为本地域帐户添加电子邮件地址。 有关详细信息，请参阅[本地同步和Office 365用户帐户目录](https://support.microsoft.com/topic/how-to-use-smtp-matching-to-match-on-premises-user-accounts-to-office-365-user-accounts-for-directory-synchronization-75673b94-e1b8-8a9e-c413-ee5a2a1a6a78)。

#### <a name="with-exchange-server"></a>[**使用Exchange Server**](#tab/exchange-server)

  1. 连接Exchange Management Shell。 [打开 Exchange Management Shell](/powershell/exchange/exchange-server/open-the-exchange-management-shell) 或[使用远程 PowerShell 连接到Exchange服务器](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)。

   2. 若要创建新会议室邮箱，请执行以下操作：

      ``` PowerShell
      New-Mailbox -UserPrincipalName <UPN> -Name <String> -Alias <String> -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
      ```
     
   此示例使用以下设置创建新会议室邮箱：

   - 帐户：ConferenceRoom01@contoso.com
  
   - 名称：ConferenceRoom01

   - 别名：ConferenceRoom01

   - 帐户密码：P@$$W 0rd5959

   ``` PowerShell
   New-Mailbox -UserPrincipalName ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
   ```

#### <a name="modify-an-existing-exchange-room-mailbox"></a>[**修改现有Exchange会议室邮箱**](#tab/existing-account)

若要修改现有会议室邮箱以成为资源帐户，请使用以下语法：

``` PowerShell
Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
```

本示例为具有别名值 ConferenceRoom02 的现有会议室邮箱启用帐户，并将密码设置为 9898P@$$W 0rd。

``` PowerShell
Set-Mailbox -Identity ConferenceRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
```

如果使用的是Exchange混合配置，则还需要为本地域帐户添加电子邮件地址。 有关详细信息，请参阅[本地同步和Office 365用户帐户目录](https://support.microsoft.com/topic/how-to-use-smtp-matching-to-match-on-premises-user-accounts-to-office-365-user-accounts-for-directory-synchronization-75673b94-e1b8-8a9e-c413-ee5a2a1a6a78)。

有关详细的语法和参数信息，请参阅 [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) 和 [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox)。

> [!NOTE]
> 如果要为Surface Hub上的Teams会议室创建此帐户，还应在此帐户上启用 ActiveSync。 这将允许你直接从Surface Hub发送电子邮件，可用于 Whiteboard 等功能。 有关详细信息，请参阅[将 ActiveSync 策略应用到设备帐户 (Surface Hub) ](/surface-hub/apply-activesync-policies-for-surface-hub-device-accounts)。

---

> [!IMPORTANT]
> 如果仅使用此资源帐户来预订空间并自动接受或拒绝邀请，则已完成设置。 如果使用此资源帐户进行 PSTN 调用，请参阅[Microsoft Teams加载项许可证](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md)以确定它需要什么许可证。
>
> 仅当资源帐户用于Windows上的Teams 会议室、Android 上的Teams 会议室、Surface Hub上的Teams 会议室或热桌面的Teams显示时，才继续下一部分。

## <a name="configure-mailbox-properties"></a>配置邮箱属性

在 Exchange PowerShell（联机或本地）中，在会议室邮箱中配置以下设置以改善会议体验：

- **AutomateProcessing： `AutoAccept`** 会议组织者在没有人工干预的情况下直接收到会议室预留决定。

- **AddOrganizerToSubject： `$false`** 会议组织者不会添加到会议请求的主题中。

- **DeleteComments： `$false`** 将任何文本保留在传入会议请求的消息正文中。 这是处理外部Teams和第三方会议以提供 One Touch Join 体验所必需的。

- **DeleteSubject： `$false`** 保留传入会议请求的主题。

- **ProcessExternalMeetingMessages： `$true`** 指定是否处理源自Exchange组织外部的会议请求。 外部Teams会议和第[三方会议](/microsoftteams/rooms/third-party-join)是必需的。

- **RemovePrivateProperty： `$false`** 确保会议组织者在原始会议请求中发送的私有标志保持指定状态。

- **AddAdditionalResponse： `$true`** AdditionalResponse 参数指定的文本将添加到会议请求中。

- **AdditionalResponse：“这是一个Microsoft Teams会议室！** 要添加到会议接受响应的其他文本。

本示例在名为 ConferenceRoom01 的会议室邮箱上配置以下设置：

``` PowerShell
Set-CalendarProcessing -Identity "ConferenceRoom01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -ProcessExternalMeetingMessages $true -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
```

有关详细的语法和参数信息，请参阅 [Set-CalendarProcessing](/powershell/module/exchange/mailboxes/set-calendarprocessing)。

## <a name="turn-off-password-expiration"></a>关闭密码过期

如果资源帐户密码过期，设备不会在到期日期后登录。 然后，需要更改资源帐户的密码，然后在每个设备上更新密码。 为了避免这种情况，可以关闭密码过期。
  
> [!NOTE]
> 对于共享Microsoft Teams设备，设置 **密码永远不会过期**。 如果域规则禁止密码过期，则需要为每个Teams设备资源帐户创建异常。

按照以下选项卡之一中的步骤关闭密码过期：

#### <a name="azure-active-directory-20"></a>[**Azure Active Directory 2.0**](#tab/azure-active-directory2-password/)

首先，连接到 Active Directory PowerShell：

```PowerShell
   Connect-AzureAD
```

然后，请参阅 [“将密码设置为永不过期](/microsoft-365/admin/add-users/set-password-to-never-expire?view=o365-worldwide#set-a-password-to-never-expire)”。

本示例将帐户 ConferenceRoom01@contoso.com 的密码设置为永不过期。

```PowerShell
Set-AzureADUser -ObjectID ConferenceRoom01@contoso.com -PasswordPolicies DisablePasswordExpiration
```

#### <a name="azure-active-directory-10"></a>[**Azure Active Directory 1.0**](#tab/azure-active-directory1-password/)

 1. 连接到 MSOnline PowerShell：

       ```PowerShell
       Connect-MsolService
       ```

       有关 Active Directory 的详细信息，请[参阅 Azure Active Directory (MSOnline) ](/powershell/azure/active-directory/overview?view=azureadps-1.0)。

2. 使用以下语法将密码设置为永不过期：

    ```PowerShell
    Set-MsolUser -Identity <samAccountName> -PasswordNeverExpires $true
    ```

    本示例将帐户 ConferenceRoom01@contoso.com 的密码设置为永不过期。

    ```PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -PasswordNeverExpires $true
    ```

#### <a name="active-directory-on-premises"></a>[**Active Directory (本地)**](#tab/active-directory1-password/)

1. 连接到 Active Directory PowerShell：

    ```PowerShell
       Import-Module ActiveDirectory
    ```
    
    有关 Active Directory PowerShell 的详细信息，请参阅 [ActiveDirectory](/powershell/module/activedirectory/?view=windowsserver2022-ps)。

2. 使用以下语法将密码设置为永不过期：

    ```PowerShell
    Set-ADUser -Identity <samAccountName> -PasswordNeverExpires $true
    ```

    本示例将帐户 ConferenceRoom01@contoso.com 的密码设置为永不过期。

    ```PowerShell
    Set-ADUser -Identity ConferenceRoom01@contoso.com -PasswordNeverExpires $true
    ```

---

## <a name="assign-a-meeting-room-license"></a>分配会议室许可证

资源帐户需要Microsoft 365或Office 365许可证才能登录到Microsoft Teams。

> [!NOTE]
> Microsoft Teams 会议室标准版和Microsoft Teams 会议室高级版是共享会议室设备（包括Teams 会议室）的两个可用 SKU。 使用热桌面Teams显示器需要会议室许可证。 有关详细信息，请参阅[Teams会议室许可](rooms-licensing.md)。

若要使用Microsoft 365 管理中心分配许可证，请参阅[向用户分配许可证](/microsoft-365/admin/manage/assign-licenses-to-users)。 若要使用Azure AD分配许可证，请参阅以下选项卡之一：

#### <a name="active-directory-20"></a>[**Active Directory 2.0**](#tab/active-directory2-license/)


1. 连接Azure AD
  
    ```PowerShell
    Connect-AzureAD
    ```

     有关 Active Directory 的详细信息，请[参阅 Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/overview?view=azureadps-2.0)。
    
2. 使用 `Set-AzureADUser` cmdlet 将使用位置分配给资源帐户。 这决定了哪些许可证 SKU 可用。

    在此示例中，用户位于美国 (美国) ：

    ```PowerShell
    Set-AzureADUser -ObjectID ConferenceRoom01@contoso.com -UsageLocation 'US'
    ```

3. 然后，用于`Get-AzureADSubscribedSku`检索Microsoft 365或Office 365组织的可用 SKU 列表。

    ```PowerShell
    Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
    ```

4. 若要分配许可证，请使用 `Set-AzureADUser` cmdlet 并将许可证 SKU ID 转换 (请参阅步骤 2) 为 PowerShell 许可证类型对象。 然后，将该对象分配给资源帐户。 在以下示例中，许可证 SKU ID 为 6070a4c8-34c6-4937-8dfb-39bbc6397a60，并将其分配给帐户 conferenceroom01@contoso.com：

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

1. 连接到 MSOnline PowerShell。

   ```PowerShell
   Connect-MsolService
   ```

    有关 Active Directory 的详细信息，请[参阅 Azure Active Directory (MSOnline) 。](/powershell/azure/active-directory/overview?view=azureadps-1.0)

2.  使用 `Set-MsolUser` cmdlet 将使用位置分配给资源帐户。 这决定了哪些许可证 SKU 可用。

    在此示例中，用户位于美国 (美国) 中。
    
    ```PowerShell
    Set-MsolUser -UserPrincipalName 'ConferenceRoom01@contoso.com' -UsageLocation 'US'
    ```
    
    然后，可以使用`Get-MsolAccountSku`它来检索Microsoft 365或Office 365组织的可用 SKU 列表。

4. 若要分配许可证，请使用 `Set-MsolUser` cmdlet。 在此示例中，“contoso：MEETING_ROOM”许可证分配给帐户 conferenceroom01@contoso.com：

    ```PowerShell
    Set-MsolUserLicense -UserPrincipalName 'ConferenceRoom01@contoso.com' -AddLicenses 'contoso:MEETING_ROOM'
    ```

---

若要验证帐户创建和许可证分配，请使用创建的帐户登录到任何Teams客户端。

## <a name="next-steps"></a>后续步骤

### <a name="meeting-policies"></a>会议策略

可能需要将自定义网络、带宽或会议策略应用到此帐户。 有关网络和带宽策略的详细信息，请参阅 [音频&视频的会议策略设置](/microsoftteams/meeting-policies-audio-and-video)。 对于Teams 会议室，建议将会议策略带宽设置为 10 Mbps。

出于协作目的，请打开PowerPoint Live、白板和共享笔记。 建议启用会议策略设置“立即在私人会议中开会”。 你可能想要创建会议策略来调整参与者和来宾设置以Teams 会议室。 例如，查看大厅设置，例如，哪些与会者自动允许参加会议。 有关Teams会议策略的详细信息，请参阅[Microsoft Teams中的管理会议策略](/microsoftteams/meeting-policies-overview)。

### <a name="calling"></a>通话

没有使用资源帐户启用调用的唯一要求。 启用资源帐户以与启用常规用户相同的方式进行调用。

> [!NOTE]
> 建议通过向设备资源帐户分配呼叫策略来关闭共享设备的语音邮件。 有关详细信息，请参阅[Teams中的呼叫和呼叫转发](../teams-calling-policy.md)。

### <a name="configure-distribution-groups-for-teams-calendar"></a>为Teams日历配置通讯组

若要组织会议室位置，可以将设备资源帐户添加到Exchange通讯组。 例如，如果在三个不同的地理位置设有办公室，则可以创建三个分发组并将相应的资源帐户添加到每个位置。 有关详细信息，请参阅 [“创建会议室”列表](/exchange/recipients/room-mailboxes?view=exchserver-2019#create-a-room-list)。

### <a name="configure-places-for-outlook-calendar"></a>为Outlook 日历配置位置
若要在会议室查找器Outlook中显示会议室位置，需要使用 Set-Place Exchange PowerShell cmdlet。 不仅Set-Place在Outlook中填充会议室查找器，还允许添加其他元数据，例如房间容量或会议室所在的楼层。 有关详细信息，请参阅 [Set-Place](/powershell/module/exchange/set-place)。

## <a name="related-articles"></a>相关文章

[为Microsoft Teams 会议室配置帐户](rooms-configure-accounts.md)

[Microsoft Teams 会议室规划](rooms-plan.md)

[部署 Microsoft Teams 会议室](rooms-deploy.md)

[管理 Microsoft Teams 会议室](rooms-manage.md)

[Microsoft Teams 会议室许可](rooms-licensing.md)
