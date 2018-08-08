---
title: 部署 Skype 会议室与 Skype 的业务服务器的系统 v2
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: 阅读此主题以如何部署业务服务器与 Skype 的 Skype 会议室系统 v2 的信息。
ms.openlocfilehash: a1d46012979cd908a00113c4573133da63e844ba
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20976826"
---
# <a name="deploy-skype-room-systems-v2-with-skype-for-business-server"></a><span data-ttu-id="f833c-103">部署 Skype 会议室与 Skype 的业务服务器的系统 v2</span><span class="sxs-lookup"><span data-stu-id="f833c-103">Deploy Skype Room Systems v2 with Skype for Business Server</span></span>
  
<span data-ttu-id="f833c-104">本主题介绍如何为单林在本地部署后添加 Skype 会议室系统 v2 的设备帐户。</span><span class="sxs-lookup"><span data-stu-id="f833c-104">This topic explains how you add a device account for Skype Room Systems v2 when you have a single-forest, on-premises deployment.</span></span>
  
<span data-ttu-id="f833c-105">如果您具有单林、 内部部署 Exchange 2013 sp1 或更高版本和 Skype 的业务服务器 2015年或更高版本，然后可以使用提供的 Windows PowerShell 脚本创建设备帐户。</span><span class="sxs-lookup"><span data-stu-id="f833c-105">If you have a single-forest, on-premises deployment with Exchange 2013 SP1 or later and Skype for Business Server 2015 or later, then you can use the provided Windows PowerShell scripts to create device accounts.</span></span> <span data-ttu-id="f833c-106">如果您正在使用的多林部署，您可以使用将产生相同的结果的等效 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f833c-106">If you're using a multi-forest deployment, you can use equivalent cmdlets that will produce the same results.</span></span> <span data-ttu-id="f833c-107">本节中对这些 cmdlet 进行了介绍。</span><span class="sxs-lookup"><span data-stu-id="f833c-107">Those cmdlets are described in this section.</span></span>

<span data-ttu-id="f833c-108">设置用户帐户的最简单方式是它们使用远程 Windows PowerShell 进行配置。</span><span class="sxs-lookup"><span data-stu-id="f833c-108">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="f833c-109">Microsoft 提供的[SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105)，脚本将帮助创建新的用户帐户，或验证必须以帮助您将它们转换为兼容的 Skype 会议室系统 v2 用户帐户的现有资源帐户。</span><span class="sxs-lookup"><span data-stu-id="f833c-109">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Skype Room Systems v2 user accounts.</span></span> <span data-ttu-id="f833c-110">如果您愿意，您可以按照以下步骤来配置您的 Skype 会议室系统 v2 设备将使用的帐户。</span><span class="sxs-lookup"><span data-stu-id="f833c-110">If you prefer, you can follow the steps below to configure accounts your Skype Room Systems v2 device will use.</span></span>
  
## <a name="deploy-skype-room-systems-v2-with-skype-for-business-server"></a><span data-ttu-id="f833c-111">部署 Skype 会议室与 Skype 的业务服务器的系统 v2</span><span class="sxs-lookup"><span data-stu-id="f833c-111">Deploy Skype Room Systems v2 with Skype for Business Server</span></span>

<span data-ttu-id="f833c-112">您部署与 Skype 的 Skype 会议室系统 v2 业务服务器之前，请确保已满足的要求。</span><span class="sxs-lookup"><span data-stu-id="f833c-112">Before you deploy Skype Room Systems v2 with Skype for Business Server, be sure you have met the requirements.</span></span> <span data-ttu-id="f833c-113">有关详细信息，请参阅[Skype 会议室系统 v2 要求](../../plan-your-deployment/clients-and-devices/requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f833c-113">For more information, see [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md).</span></span>
  
<span data-ttu-id="f833c-114">开始部署 Skype 会议室系统 v2 之前，请确保您具有正确的权限运行相关联的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="f833c-114">Before you begin to deploy Skype Room Systems v2, be sure you have the right permissions to run the associated cmdlets.</span></span>
  
1. <span data-ttu-id="f833c-115">从 PC 启动远程 Windows PowerShell 会话并连接到 Exchange。</span><span class="sxs-lookup"><span data-stu-id="f833c-115">Start a remote Windows PowerShell session from a PC and connect to Exchange.</span></span> 
    
   ```
   Set-ExecutionPolicy Unrestricted
   $org='contoso.com'
   $cred=Get-Credential $admin@$org
   $sessExchange = New-PSSession -ConfigurationName microsoft.exchange -Credential $cred -AllowRedirection -Authentication Kerberos -ConnectionUri
   "http://$strExchangeServer/powershell" -WarningAction SilentlyContinue
   $sessLync = New-PSSession -Credential $cred -ConnectionURI "https://$strLyncFQDN/OcsPowershell" -AllowRedirection -WarningAction SilentlyContinue
   Import-PSSession $sessExchange
   Import-PSSession $sessLync
 
   ```

   <span data-ttu-id="f833c-116">请注意，$strExchangeServer 是您的 Exchange 服务器的完全限定的域名 (FQDN) 和 $strLyncFQDN 是业务服务器部署您 Skype 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="f833c-116">Note that $strExchangeServer is the fully qualified domain name (FQDN) of your Exchange server, and $strLyncFQDN is the FQDN of your Skype for Business Server deployment.</span></span>
    
2. <span data-ttu-id="f833c-117">后建立会话，您将创建新邮箱并启用作为 RoomMailboxAccount 或更改现有的会议室邮箱的设置。</span><span class="sxs-lookup"><span data-stu-id="f833c-117">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="f833c-118">这将允许对 Skype 会议室系统 v2 进行身份验证的帐户。</span><span class="sxs-lookup"><span data-stu-id="f833c-118">This will allow the account to authenticate to Skype Room Systems v2.</span></span>
    
    <span data-ttu-id="f833c-119">如果要更改现有的资源邮箱：</span><span class="sxs-lookup"><span data-stu-id="f833c-119">If you're changing an existing resource mailbox:</span></span>
    
   ```
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   <span data-ttu-id="f833c-120">如果您正在创建新的资源邮箱：</span><span class="sxs-lookup"><span data-stu-id="f833c-120">If you're creating a new resource mailbox:</span></span>
    
   ```
   New-Mailbox -UserPrincipalName PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room 
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="f833c-121">设备帐户以改善会议体验的人员，您可以设置各种 Exchange 属性。</span><span class="sxs-lookup"><span data-stu-id="f833c-121">You can set various Exchange properties on the device account to improve the meeting experience for people.</span></span> <span data-ttu-id="f833c-122">你可以看到需要在 Exchange 属性部分设置的属性。</span><span class="sxs-lookup"><span data-stu-id="f833c-122">You can see which properties need to be set in the Exchange properties section.</span></span>
    
   ```
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments 
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. <span data-ttu-id="f833c-123">如果您决定具有不过期的密码，您可以设置的使用 Windows PowerShell cmdlet 太。</span><span class="sxs-lookup"><span data-stu-id="f833c-123">If you decide to have the password not expire, you can set that with Windows PowerShell cmdlets too.</span></span> <span data-ttu-id="f833c-124">有关详细信息，请参阅“密码管理”。</span><span class="sxs-lookup"><span data-stu-id="f833c-124">See Password management for more information.</span></span>
    
   ```
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. <span data-ttu-id="f833c-125">启用 Active Directory 中的帐户，因此它将向 Skype 会议室系统 v2 中进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="f833c-125">Enable the account in Active Directory so it will authenticate to Skype Room Systems v2.</span></span>
    
   ```
   Set-AdUser $acctUpn -Enabled $true
   ```

6. <span data-ttu-id="f833c-126">使您在 Skype 业务服务器池上的 Skype 会议室系统 v2 Active Directory 帐户，从而启用业务 Server Skype 的设备帐户：</span><span class="sxs-lookup"><span data-stu-id="f833c-126">Enable the device account with Skype for Business Server by enabling your Skype Room Systems v2 Active Directory account on a Skype for Business Server pool:</span></span>
    
   ```
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com 
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    <span data-ttu-id="f833c-127">该项目需要使用会话初始协议 (SIP) 地址和域控制器。</span><span class="sxs-lookup"><span data-stu-id="f833c-127">You'll need to use the Session Initiation Protocol (SIP) address and domain controller for the Project</span></span> 
    
7. <span data-ttu-id="f833c-128">**可选。**</span><span class="sxs-lookup"><span data-stu-id="f833c-128">**Optional.**</span></span> <span data-ttu-id="f833c-129">您还可以允许 Skype 会议室系统 v2 发起和接收通过您的帐户为启用企业语音的公用电话交换网 (pstn) 电话呼叫。</span><span class="sxs-lookup"><span data-stu-id="f833c-129">You can also allow Skype Room Systems v2 to make and receive public switched telephone network (PSTN) phone calls by enabling Enterprise Voice for your account.</span></span> <span data-ttu-id="f833c-130">企业语音不需要 Skype 会议室系统 v2，但如果您希望 PSTN 拨号功能 Skype 会议室系统 v2 客户端，下面是如何启用它：</span><span class="sxs-lookup"><span data-stu-id="f833c-130">Enterprise Voice isn't a requirement for Skype Room Systems v2, but if you want PSTN dialing functionality for the Skype Room Systems v2 client, here's how to enable it:</span></span>
    
   ```
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01
   ```

   <span data-ttu-id="f833c-p108">同样，需要用你自己的信息替换所提供的域控制器和电话号码示例。参数值 $true 保持不变。</span><span class="sxs-lookup"><span data-stu-id="f833c-p108">Again, you'll need to replace the provided domain controller and phone number examples with your own information. The parameter value $true stays the same.</span></span>
    
## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a><span data-ttu-id="f833c-133">Exchange 和 Skype 的本地业务服务器中的示例： 会议室帐户设置</span><span class="sxs-lookup"><span data-stu-id="f833c-133">Sample: room account setup in Exchange and Skype for Business Server on premises</span></span>

```
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

## <a name="see-also"></a><span data-ttu-id="f833c-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f833c-134">See also</span></span>

[<span data-ttu-id="f833c-135">配置帐户 Skype 会议室系统 v2</span><span class="sxs-lookup"><span data-stu-id="f833c-135">Configure accounts for Skype Room Systems v2</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="f833c-136">规划 Skype 会议室系统 v2</span><span class="sxs-lookup"><span data-stu-id="f833c-136">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[<span data-ttu-id="f833c-137">部署 Skype 会议室系统 v2</span><span class="sxs-lookup"><span data-stu-id="f833c-137">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="f833c-138">配置 Skype 会议室系统 v2 控制台</span><span class="sxs-lookup"><span data-stu-id="f833c-138">Configure a Skype Room Systems v2 console</span></span>](console.md)
  
[<span data-ttu-id="f833c-139">管理 Skype 会议室系统 v2</span><span class="sxs-lookup"><span data-stu-id="f833c-139">Manage Skype Room Systems v2</span></span>](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)