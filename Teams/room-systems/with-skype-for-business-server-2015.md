---
title: 部署业务服务器与 Skype 的 Microsoft 团队聊天室
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: 阅读此主题以如何部署业务服务器与 Skype 的 Microsoft 团队聊天室的信息。
ms.openlocfilehash: f047eceedba698d186490aa80646aa21b44c1e2d
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2019
ms.locfileid: "33362644"
---
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a><span data-ttu-id="a841a-103">部署业务服务器与 Skype 的 Microsoft 团队聊天室</span><span class="sxs-lookup"><span data-stu-id="a841a-103">Deploy Microsoft Teams Rooms with Skype for Business Server</span></span>
  
<span data-ttu-id="a841a-104">本主题介绍如何添加设备帐户的 Microsoft 团队聊天室后的单林在本地部署。</span><span class="sxs-lookup"><span data-stu-id="a841a-104">This topic explains how you add a device account for Microsoft Teams Rooms when you have a single-forest, on-premises deployment.</span></span>
  
<span data-ttu-id="a841a-105">如果您具有单林、 内部部署 Exchange 2013 sp1 或更高版本和 Skype 的业务服务器 2015年或更高版本，然后可以使用提供的 Windows PowerShell 脚本创建设备帐户。</span><span class="sxs-lookup"><span data-stu-id="a841a-105">If you have a single-forest, on-premises deployment with Exchange 2013 SP1 or later and Skype for Business Server 2015 or later, then you can use the provided Windows PowerShell scripts to create device accounts.</span></span> <span data-ttu-id="a841a-106">如果您正在使用的多林部署，您可以使用将产生相同的结果的等效 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a841a-106">If you're using a multi-forest deployment, you can use equivalent cmdlets that will produce the same results.</span></span> <span data-ttu-id="a841a-107">本节中对这些 cmdlet 进行了介绍。</span><span class="sxs-lookup"><span data-stu-id="a841a-107">Those cmdlets are described in this section.</span></span>

  
<span data-ttu-id="a841a-108">开始部署 Microsoft 团队聊天室之前，请确保您具有正确的权限运行相关联的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a841a-108">Before you begin to deploy Microsoft Teams Rooms, be sure you have the right permissions to run the associated cmdlets.</span></span>
  

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

   <span data-ttu-id="a841a-109">请注意，$strExchangeServer 是您的 Exchange 服务器的完全限定的域名 (FQDN) 和 $strLyncFQDN 是业务服务器部署您 Skype 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="a841a-109">Note that $strExchangeServer is the fully qualified domain name (FQDN) of your Exchange server, and $strLyncFQDN is the FQDN of your Skype for Business Server deployment.</span></span>

2. <span data-ttu-id="a841a-110">后建立会话，您将创建新邮箱并启用作为 RoomMailboxAccount 或更改现有的会议室邮箱的设置。</span><span class="sxs-lookup"><span data-stu-id="a841a-110">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="a841a-111">这将允许对 Microsoft 团队聊天室进行身份验证的帐户。</span><span class="sxs-lookup"><span data-stu-id="a841a-111">This will allow the account to authenticate to Microsoft Teams Rooms.</span></span>

    <span data-ttu-id="a841a-112">如果要更改现有的资源邮箱：</span><span class="sxs-lookup"><span data-stu-id="a841a-112">If you're changing an existing resource mailbox:</span></span>

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   <span data-ttu-id="a841a-113">如果您正在创建新的资源邮箱：</span><span class="sxs-lookup"><span data-stu-id="a841a-113">If you're creating a new resource mailbox:</span></span>

   ``` Powershell
   New-Mailbox -UserPrincipalName PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="a841a-114">设备帐户以改善会议体验的人员，您可以设置各种 Exchange 属性。</span><span class="sxs-lookup"><span data-stu-id="a841a-114">You can set various Exchange properties on the device account to improve the meeting experience for people.</span></span> <span data-ttu-id="a841a-115">你可以看到需要在 Exchange 属性部分设置的属性。</span><span class="sxs-lookup"><span data-stu-id="a841a-115">You can see which properties need to be set in the Exchange properties section.</span></span>

   ``` Powershell
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. <span data-ttu-id="a841a-116">如果您决定具有不过期的密码，您可以设置的使用 Windows PowerShell cmdlet 太。</span><span class="sxs-lookup"><span data-stu-id="a841a-116">If you decide to have the password not expire, you can set that with Windows PowerShell cmdlets too.</span></span> <span data-ttu-id="a841a-117">有关详细信息，请参阅“密码管理”。</span><span class="sxs-lookup"><span data-stu-id="a841a-117">See Password management for more information.</span></span>

   ``` Powershell
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. <span data-ttu-id="a841a-118">启用 Active Directory 中的帐户，因此它将对 Microsoft 团队聊天室进行验证。</span><span class="sxs-lookup"><span data-stu-id="a841a-118">Enable the account in Active Directory so it will authenticate to Microsoft Teams Rooms.</span></span>

   ``` Powershell
   Set-AdUser $acctUpn -Enabled $true
   ```

6. <span data-ttu-id="a841a-119">使业务服务器池 Skype 上的 Microsoft 团队聊天室 Active Directory 帐户，从而启用业务 Server Skype 的设备帐户：</span><span class="sxs-lookup"><span data-stu-id="a841a-119">Enable the device account with Skype for Business Server by enabling your Microsoft Teams Rooms Active Directory account on a Skype for Business Server pool:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    <span data-ttu-id="a841a-120">该项目需要使用会话初始协议 (SIP) 地址和域控制器。</span><span class="sxs-lookup"><span data-stu-id="a841a-120">You'll need to use the Session Initiation Protocol (SIP) address and domain controller for the Project</span></span>

7. <span data-ttu-id="a841a-121">**可选。**</span><span class="sxs-lookup"><span data-stu-id="a841a-121">**Optional.**</span></span> <span data-ttu-id="a841a-122">您还可以允许 Microsoft 团队聊天室发起和接收通过您的帐户为启用企业语音的公用电话交换网 (pstn) 电话呼叫。</span><span class="sxs-lookup"><span data-stu-id="a841a-122">You can also allow Microsoft Teams Rooms to make and receive public switched telephone network (PSTN) phone calls by enabling Enterprise Voice for your account.</span></span> <span data-ttu-id="a841a-123">企业语音不需要 Microsoft 团队聊天室，但如果您希望 Microsoft 团队聊天室客户端的 PSTN 拨号功能，下面是如何启用它：</span><span class="sxs-lookup"><span data-stu-id="a841a-123">Enterprise Voice isn't a requirement for Microsoft Teams Rooms, but if you want PSTN dialing functionality for the Microsoft Teams Rooms client, here's how to enable it:</span></span>

   ``` Powershell
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01
   ```

   <span data-ttu-id="a841a-p106">同样，需要用你自己的信息替换所提供的域控制器和电话号码示例。参数值 $true 保持不变。</span><span class="sxs-lookup"><span data-stu-id="a841a-p106">Again, you'll need to replace the provided domain controller and phone number examples with your own information. The parameter value $true stays the same.</span></span>

## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a><span data-ttu-id="a841a-126">Exchange 和 Skype 的本地业务服务器中的示例： 会议室帐户设置</span><span class="sxs-lookup"><span data-stu-id="a841a-126">Sample: room account setup in Exchange and Skype for Business Server on premises</span></span>

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

## <a name="see-also"></a><span data-ttu-id="a841a-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a841a-127">See also</span></span>

[<span data-ttu-id="a841a-128">为 Microsoft 团队房间配置帐户</span><span class="sxs-lookup"><span data-stu-id="a841a-128">Configure accounts for Microsoft Teams Rooms</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="a841a-129">规划 Microsoft 团队聊天室</span><span class="sxs-lookup"><span data-stu-id="a841a-129">Plan for Microsoft Teams Rooms</span></span>](skype-room-systems-v2-0.md)
  
[<span data-ttu-id="a841a-130">部署 Microsoft 团队聊天室</span><span class="sxs-lookup"><span data-stu-id="a841a-130">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="a841a-131">配置 Microsoft 团队聊天室控制台</span><span class="sxs-lookup"><span data-stu-id="a841a-131">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="a841a-132">管理 Microsoft Teams 会议室</span><span class="sxs-lookup"><span data-stu-id="a841a-132">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)