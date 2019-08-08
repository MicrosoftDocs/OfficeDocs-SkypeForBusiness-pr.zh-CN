---
title: Skype 会议室系统会议室设置脚本
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a66067d2-22b0-48f1-a5d0-e0cd0ece2e5a
description: 阅读本主题，了解如何查找用于设置 Skype 会议室系统帐户的示例脚本。
ms.openlocfilehash: 7c462dea9f1a885fbf8a4fb4f6aeee4ca4f8c3d3
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235021"
---
# <a name="skype-room-system-room-setup-scripts"></a><span data-ttu-id="a0c5d-103">Skype 会议室系统会议室设置脚本</span><span class="sxs-lookup"><span data-stu-id="a0c5d-103">Skype Room System room setup scripts</span></span>
 
<span data-ttu-id="a0c5d-104">阅读本主题，了解如何查找用于设置 Skype 会议室系统帐户的示例脚本。</span><span class="sxs-lookup"><span data-stu-id="a0c5d-104">Read this topic to find sample scripts for provisioning Skype Room System accounts.</span></span>
  
<span data-ttu-id="a0c5d-105">本部分介绍了可用于设置 Skype 会议室系统帐户的示例脚本。</span><span class="sxs-lookup"><span data-stu-id="a0c5d-105">This section illustrates sample scripts that can be used to provision Skype Room System accounts.</span></span> <span data-ttu-id="a0c5d-106">这些脚本仅用于说明目的，并且只应在咨询你的 IT 专家或域管理员之后使用。</span><span class="sxs-lookup"><span data-stu-id="a0c5d-106">These scripts are for illustrative purposes only and should be used only after consulting with your IT expert or domain administrator.</span></span>
  
## <a name="example-setup-script-skype-for-business-and-exchange-server-on-premises"></a><span data-ttu-id="a0c5d-107">示例安装脚本: Skype for business 和 Exchange Server (内部部署)</span><span class="sxs-lookup"><span data-stu-id="a0c5d-107">Example Setup Script: Skype for Business and Exchange Server (On Premises)</span></span>

```
# On Exchange 
Set-Mailbox -Identity confroom@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a 
Lync Meeting to take advantage of enhanced meeting experience from LRS"

Set-CalendarProcessing -id confroom@contoso.com -RemovePrivateProperty $false -AddOrganizerToSubject $false -AddAdditionalResponse 
$true -AdditionalResponse "This is an LRS room!" -DeleteSubject $false -AutomateProcessing AutoAccept 
# The following is used to preserve the Lync Meeting invitations - so create these based on your Lync Federated partners# Per Lync Federated Partner as a Recommended Practice to ensure Meetings show in Lync with Join#New-RemoteDomain -DomainName Microsoft.com -Name Microsoft$true#Set-RemoteDomain -Identity Microsoft -TNEFEnabled $true
Set-ADAccountPassword -Identity "conference room"# Paste the next command on its own. Enter a blank password first, then enter the new password "password" twiceEnable-ADAccount -Identity "confroom"# On LyncEnable-CsMeetingRoom -SipAddress "sip:confroom@contoso.com" -RegistrarPool cie-srv-02.contoso.com -Identity 'conference room' 
Set-CsMeetingRoom -Identity "conference room" -LineURI "tel:+14255551669;ext=1669" -EnterpriseVoiceEnabled $true
```

## <a name="example-setup-script-skype-for-business-and-exchange-server-online"></a><span data-ttu-id="a0c5d-108">示例安装脚本: Skype for business 和 Exchange Server Online</span><span class="sxs-lookup"><span data-stu-id="a0c5d-108">Example Setup Script: Skype for Business and Exchange Server Online</span></span>

<span data-ttu-id="a0c5d-109">在运行脚本之前，请务必查看以下先决条件：</span><span class="sxs-lookup"><span data-stu-id="a0c5d-109">Make sure you've reviewed the following prerequisites before running the script:</span></span>
  
- <span data-ttu-id="a0c5d-110">适用于 IT 专业人员 BETA 的 Microsoft Online Services 登录助手</span><span class="sxs-lookup"><span data-stu-id="a0c5d-110">Microsoft Online Services Sign-In Assistant for IT Professionals BETA</span></span>
    
- <span data-ttu-id="a0c5d-111">用于 Windows PowerShell 的 Windows Azure Active Directory 模块（64 位版本）或（32 位版本）</span><span class="sxs-lookup"><span data-stu-id="a0c5d-111">Windows Azure Active Directory Module for Windows PowerShell (64-bit version) or (32-bit version)</span></span>
    
- <span data-ttu-id="a0c5d-112">用于 Lync Online 的 Windows PowerShell 模块</span><span class="sxs-lookup"><span data-stu-id="a0c5d-112">Windows PowerShell Module for Lync Online</span></span>
    
- <span data-ttu-id="a0c5d-113">根据需要重启</span><span class="sxs-lookup"><span data-stu-id="a0c5d-113">Reboot if needed</span></span>
    
```
# Note you have to enter each command one at a time and update any bold fields for your environment
$rm="LyncRoom"
$org='YourTenantName.onmicrosoft.com'
$rmURI="$rm@$org"$newpass='MyPass@word1'# This Section Signs into Remote PowerShell
$cred=Get-Credential admin@$org
$sess=New-PSSession -ConfigurationName microsoft.exchange -Credential $cred -AllowRedirection -Authentication basic -ConnectionUri https://ps.outlook.com/powershell
Import-PSSession $sess
Import-Module LyncOnlineConnector
$cssess=New-CsOnlineSession -Credential $cred
Import-PSSession $cssess -AllowClobber
Connect-MsolService -Credential $cred# This Section Create the Calendar Mailbox and Enables it for Lync
New-Mailbox -MicrosoftOnlineServicesID $rmURI -room -Name $rm -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
 -EnableRoomMailboxAccount $true

Set-CalendarProcessing -Identity $rmURI -DeleteSubject $false -AutomateProcessing AutoAccept 
Set-CalendarProcessing -Identity $rmURI -RemovePrivateProperty $false -AddOrganizerToSubject $false -AddAdditionalResponse $true -AdditionalResponse
 "This is an LRS room!"# Configure the Account to Not Expire
Set-MsolUser -UserPrincipalName $rm -PasswordNeverExpires $true# You need to detect your Lync Pool Registrar name. Using a normal Offic365/LyncOnline user account from your tenant, run the next command and update the RegistrarPool value for the second command coming up
Get-CsOnlineUser -Identity 'admin@YourTenantName.onmicrosoft.com' | fl *registrar*# Update with above result
Enable-CsMeetingRoom -Identity $rmURI -RegistrarPool "sippoolsn20a07.infra.lync.com" -SipAddressType EmailAddress
# If the previous command fails with an error regarding the account name not being found you might need to wait and try again in a few minutes. If you wait too long, you'll need to sign in again to remote PowerShell as detailed above.
```


