---
title: 通过 Skype for Business 服务器部署 Microsoft 团队聊天室
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: ''
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: 阅读本主题，了解如何通过 Skype for Business 服务器部署 Microsoft 团队聊天室的相关信息。
ms.openlocfilehash: 8b1b3c96045d15740c6055449c91db2d9b127578
ms.sourcegitcommit: 9bead87a7f4c4e71f19f8980e9dce2b979735055
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2020
ms.locfileid: "41268811"
---
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a><span data-ttu-id="fc8c7-103">通过 Skype for Business 服务器部署 Microsoft 团队聊天室</span><span class="sxs-lookup"><span data-stu-id="fc8c7-103">Deploy Microsoft Teams Rooms with Skype for Business Server</span></span>
  
<span data-ttu-id="fc8c7-104">本主题介绍了如何在具有单个林内部部署的情况下为 Microsoft 团队聊天室添加设备帐户。</span><span class="sxs-lookup"><span data-stu-id="fc8c7-104">This topic explains how you add a device account for Microsoft Teams Rooms when you have a single-forest, on-premises deployment.</span></span>
  
<span data-ttu-id="fc8c7-105">如果你有一个具有 Exchange 2013 SP1 或更高版本以及 Skype for business Server 2015 或更高版本的单林、内部部署，则可以使用所提供的 Windows PowerShell 脚本创建设备帐户。</span><span class="sxs-lookup"><span data-stu-id="fc8c7-105">If you have a single-forest, on-premises deployment with Exchange 2013 SP1 or later and Skype for Business Server 2015 or later, then you can use the provided Windows PowerShell scripts to create device accounts.</span></span> <span data-ttu-id="fc8c7-106">如果你使用的是多目录林部署，则可以使用将产生相同结果的等效 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fc8c7-106">If you're using a multi-forest deployment, you can use equivalent cmdlets that will produce the same results.</span></span> <span data-ttu-id="fc8c7-107">本节中对这些 cmdlet 进行了介绍。</span><span class="sxs-lookup"><span data-stu-id="fc8c7-107">Those cmdlets are described in this section.</span></span>

  
<span data-ttu-id="fc8c7-108">开始部署 Microsoft 团队聊天室之前，请确保你拥有运行关联 cmdlet 的相应权限。</span><span class="sxs-lookup"><span data-stu-id="fc8c7-108">Before you begin to deploy Microsoft Teams Rooms, be sure you have the right permissions to run the associated cmdlets.</span></span>
  

   ``` Powershell
   Set-ExecutionPolicy Unrestricted
   $org='contoso.com'
   $cred=Get-Credential $admin@$org
   $sessExchange = New-PSSession -ConfigurationName microsoft.exchange -Credential $cred -AllowRedirection -Authentication Kerberos -ConnectionUri
   "http://$strExchangeServer/powershell" -WarningAction SilentlyContinue
   $sessLync = New-PSSession -Credential $cred -ConnectionURI "https://$strLyncFQDN/OcsPowershell" -AllowRedirection -WarningAction SilentlyContinue
   Import-PSSession $sessExchange
   Import-PSSession $sessLync
   ```

   <span data-ttu-id="fc8c7-109">请注意，$strExchangeServer 是 Exchange server 的完全限定的域名（FQDN），并且 $strLyncFQDN 是 Skype for Business Server 部署的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="fc8c7-109">Note that $strExchangeServer is the fully qualified domain name (FQDN) of your Exchange server, and $strLyncFQDN is the FQDN of your Skype for Business Server deployment.</span></span>

2. <span data-ttu-id="fc8c7-110">建立会话后，你将创建一个新邮箱并将其作为 RoomMailboxAccount 启用，或更改现有会议室邮箱的设置。</span><span class="sxs-lookup"><span data-stu-id="fc8c7-110">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="fc8c7-111">这将允许帐户对 Microsoft 团队聊天室进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="fc8c7-111">This will allow the account to authenticate to Microsoft Teams Rooms.</span></span>

    <span data-ttu-id="fc8c7-112">如果要更改现有的资源邮箱：</span><span class="sxs-lookup"><span data-stu-id="fc8c7-112">If you're changing an existing resource mailbox:</span></span>

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   <span data-ttu-id="fc8c7-113">如果要创建新的资源邮箱，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="fc8c7-113">If you're creating a new resource mailbox:</span></span>

   ``` Powershell
   New-Mailbox -UserPrincipalName PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="fc8c7-114">你可以在设备帐户上设置各种 Exchange 属性来改善人员的会议体验。</span><span class="sxs-lookup"><span data-stu-id="fc8c7-114">You can set various Exchange properties on the device account to improve the meeting experience for people.</span></span> <span data-ttu-id="fc8c7-115">你可以看到需要在 Exchange 属性部分设置的属性。</span><span class="sxs-lookup"><span data-stu-id="fc8c7-115">You can see which properties need to be set in the Exchange properties section.</span></span>

   ``` Powershell
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. <span data-ttu-id="fc8c7-116">如果您决定让密码永不过期，则可以使用 Windows PowerShell cmdlet 设置该密码。</span><span class="sxs-lookup"><span data-stu-id="fc8c7-116">If you decide to have the password not expire, you can set that with Windows PowerShell cmdlets too.</span></span> <span data-ttu-id="fc8c7-117">有关详细信息，请参阅“密码管理”。</span><span class="sxs-lookup"><span data-stu-id="fc8c7-117">See Password management for more information.</span></span>

   ``` Powershell
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. <span data-ttu-id="fc8c7-118">在 Active Directory 中启用帐户，以便它将对 Microsoft 团队聊天室进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="fc8c7-118">Enable the account in Active Directory so it will authenticate to Microsoft Teams Rooms.</span></span>

   ``` Powershell
   Set-AdUser $acctUpn -Enabled $true
   ```

6. <span data-ttu-id="fc8c7-119">通过在 Skype for business 服务器池上启用 Microsoft 团队聊天室 Active Directory 帐户，通过 Skype for business 服务器启用设备帐户：</span><span class="sxs-lookup"><span data-stu-id="fc8c7-119">Enable the device account with Skype for Business Server by enabling your Microsoft Teams Rooms Active Directory account on a Skype for Business Server pool:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    <span data-ttu-id="fc8c7-120">该项目需要使用会话初始协议 (SIP) 地址和域控制器。</span><span class="sxs-lookup"><span data-stu-id="fc8c7-120">You'll need to use the Session Initiation Protocol (SIP) address and domain controller for the Project</span></span>

7. <span data-ttu-id="fc8c7-121">**可选。**</span><span class="sxs-lookup"><span data-stu-id="fc8c7-121">**Optional.**</span></span> <span data-ttu-id="fc8c7-122">你还可以允许 Microsoft 团队聊天室通过为你的帐户启用企业语音来拨打和接收公共交换电话网络（PSTN）电话呼叫。</span><span class="sxs-lookup"><span data-stu-id="fc8c7-122">You can also allow Microsoft Teams Rooms to make and receive public switched telephone network (PSTN) phone calls by enabling Enterprise Voice for your account.</span></span> <span data-ttu-id="fc8c7-123">企业语音不是 Microsoft 团队聊天室的必要条件，但如果你希望 Microsoft 团队聊天室客户端的 PSTN 拨号功能，请按以下方法启用它：</span><span class="sxs-lookup"><span data-stu-id="fc8c7-123">Enterprise Voice isn't a requirement for Microsoft Teams Rooms, but if you want PSTN dialing functionality for the Microsoft Teams Rooms client, here's how to enable it:</span></span>

   ``` Powershell
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01
   ```

   <span data-ttu-id="fc8c7-p106">同样，需要用你自己的信息替换所提供的域控制器和电话号码示例。参数值 $true 保持不变。</span><span class="sxs-lookup"><span data-stu-id="fc8c7-p106">Again, you'll need to replace the provided domain controller and phone number examples with your own information. The parameter value $true stays the same.</span></span>

## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a><span data-ttu-id="fc8c7-126">示例： Exchange 和 Skype for business Server 内部部署中的房间帐户设置</span><span class="sxs-lookup"><span data-stu-id="fc8c7-126">Sample: room account setup in Exchange and Skype for Business Server on premises</span></span>

``` Powershell
New-Mailbox -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String "" -AsPlainText -Force)
-UserPrincipalName rigel1@contoso.com

Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false
-RemovePrivateProperty $false
Set-CalendarProcessing -Identity rigel1 -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"

Enable-CsMeetingRoom -Identity rigel1@contoso.com -RegistrarPool cs3.contoso.com -SipAddressType EmailAddress
Set-CsMeetingRoom -Identity rigel1 -EnterpriseVoiceEnabled $true -LineURI tel:+155555555555
Grant-CsVoicePolicy -PolicyName dk -Identity rigel1
Grant-CsDialPlan -PolicyName e15dp2.contoso.com -Identity rigel1
```

## <a name="see-also"></a><span data-ttu-id="fc8c7-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fc8c7-127">See also</span></span>

[<span data-ttu-id="fc8c7-128">为 Microsoft 团队聊天室配置帐户</span><span class="sxs-lookup"><span data-stu-id="fc8c7-128">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="fc8c7-129">规划 Microsoft 团队聊天室</span><span class="sxs-lookup"><span data-stu-id="fc8c7-129">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="fc8c7-130">部署 Microsoft 团队聊天室</span><span class="sxs-lookup"><span data-stu-id="fc8c7-130">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="fc8c7-131">配置 Microsoft 团队聊天室控制台</span><span class="sxs-lookup"><span data-stu-id="fc8c7-131">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="fc8c7-132">管理 Microsoft Teams 会议室</span><span class="sxs-lookup"><span data-stu-id="fc8c7-132">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)
