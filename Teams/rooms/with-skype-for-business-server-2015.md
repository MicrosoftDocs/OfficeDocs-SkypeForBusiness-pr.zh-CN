---
title: 使用 Skype for Business Server 部署 Microsoft Teams 会议室
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: 阅读本主题，了解如何使用 Skype for Business Server 部署 Microsoft Teams 会议室。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9ee33ec1ded7e8461f629c4552236ee60828a168
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662257"
---
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a><span data-ttu-id="8f0aa-103">使用 Skype for Business Server 部署 Microsoft Teams 会议室</span><span class="sxs-lookup"><span data-stu-id="8f0aa-103">Deploy Microsoft Teams Rooms with Skype for Business Server</span></span>
  
<span data-ttu-id="8f0aa-104">本主题介绍在单林本地部署时如何为 Microsoft Teams 会议室添加设备帐户。</span><span class="sxs-lookup"><span data-stu-id="8f0aa-104">This topic explains how you add a device account for Microsoft Teams Rooms when you have a single-forest, on-premises deployment.</span></span>
  
<span data-ttu-id="8f0aa-105">如果你有使用 Exchange 2013 SP1 或更高版本以及 Skype for Business Server 2015 或更高版本的单林本地部署，可以使用提供的 Windows PowerShell 脚本创建设备帐户。</span><span class="sxs-lookup"><span data-stu-id="8f0aa-105">If you have a single-forest, on-premises deployment with Exchange 2013 SP1 or later and Skype for Business Server 2015 or later, then you can use the provided Windows PowerShell scripts to create device accounts.</span></span> <span data-ttu-id="8f0aa-106">如果使用多林部署，可以使用将生成相同结果的等效 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8f0aa-106">If you're using a multi-forest deployment, you can use equivalent cmdlets that will produce the same results.</span></span> <span data-ttu-id="8f0aa-107">本节中对这些 cmdlet 进行了介绍。</span><span class="sxs-lookup"><span data-stu-id="8f0aa-107">Those cmdlets are described in this section.</span></span>

  
<span data-ttu-id="8f0aa-108">在开始部署 Microsoft Teams 会议室之前，请确保拥有运行关联 cmdlet 所需的正确权限。</span><span class="sxs-lookup"><span data-stu-id="8f0aa-108">Before you begin to deploy Microsoft Teams Rooms, be sure you have the right permissions to run the associated cmdlets.</span></span>
  

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

   <span data-ttu-id="8f0aa-109">请注意$strExchangeServer是 Exchange 服务器的 FQDN (完全限定) ，$strLyncFQDN 是 Skype for Business Server 部署的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="8f0aa-109">Note that $strExchangeServer is the fully qualified domain name (FQDN) of your Exchange server, and $strLyncFQDN is the FQDN of your Skype for Business Server deployment.</span></span>

2. <span data-ttu-id="8f0aa-110">建立会话后，您将创建新邮箱并启用为 RoomMailboxAccount，或更改现有会议室邮箱的设置。</span><span class="sxs-lookup"><span data-stu-id="8f0aa-110">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="8f0aa-111">这将允许帐户向 Microsoft Teams 会议室进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="8f0aa-111">This will allow the account to authenticate to Microsoft Teams Rooms.</span></span>

    <span data-ttu-id="8f0aa-112">如果要更改现有的资源邮箱：</span><span class="sxs-lookup"><span data-stu-id="8f0aa-112">If you're changing an existing resource mailbox:</span></span>

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   <span data-ttu-id="8f0aa-113">如果要创建新的资源邮箱：</span><span class="sxs-lookup"><span data-stu-id="8f0aa-113">If you're creating a new resource mailbox:</span></span>

   ``` Powershell
   New-Mailbox -UserPrincipalName PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="8f0aa-114">您可以在设备帐户上设置各种 Exchange 属性，以改进人员的会议体验。</span><span class="sxs-lookup"><span data-stu-id="8f0aa-114">You can set various Exchange properties on the device account to improve the meeting experience for people.</span></span> <span data-ttu-id="8f0aa-115">你可以看到需要在 Exchange 属性部分设置的属性。</span><span class="sxs-lookup"><span data-stu-id="8f0aa-115">You can see which properties need to be set in the Exchange properties section.</span></span>

   ``` Powershell
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. <span data-ttu-id="8f0aa-116">如果决定让密码永不过期，也可使用 Windows PowerShell cmdlet 进行设置。</span><span class="sxs-lookup"><span data-stu-id="8f0aa-116">If you decide to have the password not expire, you can set that with Windows PowerShell cmdlets too.</span></span> <span data-ttu-id="8f0aa-117">有关详细信息，请参阅“密码管理”。</span><span class="sxs-lookup"><span data-stu-id="8f0aa-117">See Password management for more information.</span></span>

   ``` Powershell
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. <span data-ttu-id="8f0aa-118">在 Active Directory 中启用帐户，以便向 Microsoft Teams 会议室进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="8f0aa-118">Enable the account in Active Directory so it will authenticate to Microsoft Teams Rooms.</span></span>

   ``` Powershell
   Set-AdUser $acctUpn -Enabled $true
   ```

6. <span data-ttu-id="8f0aa-119">通过启用 Skype for Business Server 池上的 Microsoft Teams 会议室 Active Directory 帐户，为 Skype for Business Server 启用设备帐户：</span><span class="sxs-lookup"><span data-stu-id="8f0aa-119">Enable the device account with Skype for Business Server by enabling your Microsoft Teams Rooms Active Directory account on a Skype for Business Server pool:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    <span data-ttu-id="8f0aa-120">该项目需要使用会话初始协议 (SIP) 地址和域控制器。</span><span class="sxs-lookup"><span data-stu-id="8f0aa-120">You'll need to use the Session Initiation Protocol (SIP) address and domain controller for the Project</span></span>

7. <span data-ttu-id="8f0aa-121">**可选。**</span><span class="sxs-lookup"><span data-stu-id="8f0aa-121">**Optional.**</span></span> <span data-ttu-id="8f0aa-122">您还可以允许 Microsoft Teams 会议室通过为您的帐户启用 (，在 PSTN) 拨打和接收企业语音电话交换网。</span><span class="sxs-lookup"><span data-stu-id="8f0aa-122">You can also allow Microsoft Teams Rooms to make and receive public switched telephone network (PSTN) phone calls by enabling Enterprise Voice for your account.</span></span> <span data-ttu-id="8f0aa-123">企业语音不是 Microsoft Teams 会议室的一项要求，但如果你需要 Microsoft Teams 会议室客户端的 PSTN 拨号功能，下面将了解如何启用此功能：</span><span class="sxs-lookup"><span data-stu-id="8f0aa-123">Enterprise Voice isn't a requirement for Microsoft Teams Rooms, but if you want PSTN dialing functionality for the Microsoft Teams Rooms client, here's how to enable it:</span></span>

   ``` Powershell
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01
   ```

   <span data-ttu-id="8f0aa-p106">同样，需要用你自己的信息替换所提供的域控制器和电话号码示例。参数值 $true 保持不变。</span><span class="sxs-lookup"><span data-stu-id="8f0aa-p106">Again, you'll need to replace the provided domain controller and phone number examples with your own information. The parameter value $true stays the same.</span></span>

## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a><span data-ttu-id="8f0aa-126">示例：Exchange 和本地 Skype for Business Server 中的会议室帐户设置</span><span class="sxs-lookup"><span data-stu-id="8f0aa-126">Sample: room account setup in Exchange and Skype for Business Server on premises</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="8f0aa-127">相关主题</span><span class="sxs-lookup"><span data-stu-id="8f0aa-127">Related topics</span></span>

[<span data-ttu-id="8f0aa-128">为 Microsoft Teams 会议室配置帐户</span><span class="sxs-lookup"><span data-stu-id="8f0aa-128">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="8f0aa-129">Microsoft Teams 会议室规划</span><span class="sxs-lookup"><span data-stu-id="8f0aa-129">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="8f0aa-130">部署 Microsoft Teams 会议室</span><span class="sxs-lookup"><span data-stu-id="8f0aa-130">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="8f0aa-131">配置 Microsoft Teams 会议室控制台</span><span class="sxs-lookup"><span data-stu-id="8f0aa-131">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="8f0aa-132">管理 Microsoft Teams 会议室</span><span class="sxs-lookup"><span data-stu-id="8f0aa-132">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)
