---
title: 在 Office 365 中设置 Skype 会议室系统帐户
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/6/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: 阅读本主题，了解如何在 Office 365 中设置 Skype 会议室系统帐户。
ms.openlocfilehash: be90831eba5f16f5a3b41f4c74c26333bf728926
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="provisioning-skype-room-system-accounts-in-office-365"></a><span data-ttu-id="e8de5-103">在 Office 365 中设置 Skype 会议室系统帐户</span><span class="sxs-lookup"><span data-stu-id="e8de5-103">Provisioning Skype Room System accounts in Office 365</span></span>
 
<span data-ttu-id="e8de5-104">阅读本主题，了解如何在 Office 365 中设置 Skype 会议室系统帐户。</span><span class="sxs-lookup"><span data-stu-id="e8de5-104">Read this topic to learn about provisioning Skype Room System accounts in Office 365.</span></span>
  
<span data-ttu-id="e8de5-105">以下各节介绍 Skype 的空间系统帐户配置 Office 365 租户。</span><span class="sxs-lookup"><span data-stu-id="e8de5-105">The following section covers Skype Room System account provisioning for an Office 365 tenant.</span></span>
  
## <a name="office-365-prerequisites"></a><span data-ttu-id="e8de5-106">Office 365 先决条件</span><span class="sxs-lookup"><span data-stu-id="e8de5-106">Office 365 prerequisites</span></span>

<span data-ttu-id="e8de5-107">你的联机租户必须满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="e8de5-107">Your online tenant must meet the following requirements:</span></span>
  
- <span data-ttu-id="e8de5-108">Office 365 计划必须包括 Skype 业务联机计划 2、 计划 3 或 Office 365 E1，E3 或 E5。</span><span class="sxs-lookup"><span data-stu-id="e8de5-108">The Office 365 plan must include Skype for Business Online Plan 2, Plan 3, or Office 365 E1, E3 or E5.</span></span>
    
- <span data-ttu-id="e8de5-109">您的组织必须启用业务的 Skype 的会议功能。</span><span class="sxs-lookup"><span data-stu-id="e8de5-109">Your tenant must have the conferencing capability of Skype for Business enabled.</span></span>
    
- <span data-ttu-id="e8de5-110">你的租户必须启用 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="e8de5-110">Your tenant must have Exchange Online enabled.</span></span> 
    
- <span data-ttu-id="e8de5-111">你的租户远程管理员必须具有以下 PowerShell 访问：</span><span class="sxs-lookup"><span data-stu-id="e8de5-111">Your tenant remote administrator must have the following PowerShell access:</span></span>
    
  - <span data-ttu-id="e8de5-112">Exchange 远程 PowerShell 访问</span><span class="sxs-lookup"><span data-stu-id="e8de5-112">Exchange Remote PowerShell access</span></span>
    
  - <span data-ttu-id="e8de5-113">Skype 业务在线远程 PowerShell 访问</span><span class="sxs-lookup"><span data-stu-id="e8de5-113">Skype for Business Online Remote PowerShell access</span></span>
    
  - <span data-ttu-id="e8de5-114">Windows Azure 活动目录模块用于 Windows PowerShell 访问 Office 365 提供目录访问</span><span class="sxs-lookup"><span data-stu-id="e8de5-114">Windows Azure Active Directory Module for Windows PowerShell to access Office 365 directory access</span></span>
    
<span data-ttu-id="e8de5-115">对于 Skype 会议室帐户，需要以下许可：</span><span class="sxs-lookup"><span data-stu-id="e8de5-115">For the Skype Room account, the following licensing is required:</span></span>
  
- <span data-ttu-id="e8de5-116">Skype 的商务在线计划 2 或 Office 365 E1 或 E3 许可证需要启用 Skype 会议。</span><span class="sxs-lookup"><span data-stu-id="e8de5-116">A Skype for Business Online Plan 2 or Office 365 E1 or E3 license is required to enable Skype Meetings.</span></span>
    
- <span data-ttu-id="e8de5-117">以允许具有企业语音功能的房间，使房间可以启用具有电话号码，为商务在线计划 2 与云 PBX 附加或 Office 365 E5 Skype 是必需的 (1)。</span><span class="sxs-lookup"><span data-stu-id="e8de5-117">To entitle the room with the Enterprise Voice capability so the room can be enabled with a phone number, a Skype for Business Online Plan 2 with the Cloud PBX Add-on or Office 365 E5 is required (1).</span></span>
    
- <span data-ttu-id="e8de5-118">给定会议中 PSTN 会议授权可用性由会议组织者的许可证决定。</span><span class="sxs-lookup"><span data-stu-id="e8de5-118">The availability of PSTN Conferencing entitlement within any given meeting is determined by the license of the meeting organizer.</span></span>
    
- <span data-ttu-id="e8de5-119">Skype 会议室帐户不需要 Exchange Online 许可证，因为应将该帐户配置为资源邮箱帐户。</span><span class="sxs-lookup"><span data-stu-id="e8de5-119">An Exchange Online license is not required for the Skype Room account because the account should be configured as a resource mailbox account.</span></span>
    
## <a name="provisioning-overview"></a><span data-ttu-id="e8de5-120">设置概述</span><span class="sxs-lookup"><span data-stu-id="e8de5-120">Provisioning overview</span></span>

<span data-ttu-id="e8de5-121">下图概述了 Skype 的空间系统帐户调配在 Office 365 中的流动。</span><span class="sxs-lookup"><span data-stu-id="e8de5-121">The following diagram provides an overview of the Skype Room System account provisioning flow in Office 365.</span></span>
  
![O365 的 Skype 会议室系统设置步骤](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a><span data-ttu-id="e8de5-123">识别新的会议室</span><span class="sxs-lookup"><span data-stu-id="e8de5-123">Identify a new conference room</span></span>

<span data-ttu-id="e8de5-124">您可能已经具有资源会议室邮箱在 Exchange 提供计划的功能，或者您可能会创建第一次以方便 Skype 的空间系统部署的资源邮箱。</span><span class="sxs-lookup"><span data-stu-id="e8de5-124">You may already have a resource room mailbox in Exchange that provides the scheduling feature, or you may be creating a resource mailbox for the first time to facilitate Skype Room System deployment.</span></span> <span data-ttu-id="e8de5-125">在任何情况下，你必须识别要在你的租户中使用的会议室帐户。</span><span class="sxs-lookup"><span data-stu-id="e8de5-125">In any case, you must identify a room account to be used in your tenant.</span></span> <span data-ttu-id="e8de5-126">Exchange 的联机资源调配和 Skype 业务规定部分提供这两种帐户的指南。</span><span class="sxs-lookup"><span data-stu-id="e8de5-126">The Exchange Online Provision and Skype for Business Provision sections provide guidance for both kinds of accounts.</span></span> <span data-ttu-id="e8de5-127">例如，假设您拥有下面的两个房间，和您想要为这两种部署 Skype 的空间系统：</span><span class="sxs-lookup"><span data-stu-id="e8de5-127">For example, let's say you have the following two rooms, and you would like to deploy Skype Room System for both of them:</span></span>
  
- <span data-ttu-id="e8de5-128">现有资源邮箱帐户：confrm1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="e8de5-128">Existing Resource Mailbox Account: confrm1@contoso.onmicrosoft.com</span></span>
    
- <span data-ttu-id="e8de5-129">新的资源邮箱帐户：confrm2@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="e8de5-129">New Resource Mailbox Account: confrm2@contoso.onmicrosoft.com</span></span>
    
## <a name="exchange-online-provisioning"></a><span data-ttu-id="e8de5-130">Exchange Online 设置</span><span class="sxs-lookup"><span data-stu-id="e8de5-130">Exchange Online provisioning</span></span>

<span data-ttu-id="e8de5-131">首先，连接到 Exchange 联机 PowerShell 通过[连接到 Exchange 联机 PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554)主题中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="e8de5-131">First, connect to Exchange Online PowerShell by following the instructions in the topic, [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
  
<span data-ttu-id="e8de5-132">要设置 Skype 的空间系统现有资源空间邮箱帐户，请在 Exchange 联机 PowerShell 运行下面的命令：</span><span class="sxs-lookup"><span data-stu-id="e8de5-132">To set an existing resource room mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="e8de5-133">要为 Skype 的空间系统创建一个新的 Exchange 资源邮箱帐户，请在 Exchange 联机 PowerShell 运行下面的命令：</span><span class="sxs-lookup"><span data-stu-id="e8de5-133">To create a new Exchange resource mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="e8de5-134">上述命令设置，或通过启用该帐户创建一个新的 Exchange 资源邮箱帐户的 Skype 的空间系统的使用情况。</span><span class="sxs-lookup"><span data-stu-id="e8de5-134">The previous commands set up or create a new Exchange resource mailbox account for Skype Room System usage by enabling the account.</span></span>
  
<span data-ttu-id="e8de5-135">在创建邮箱之后, 可用于 Exchange 联机继续设置 CalendarProcessing cmdlet 配置邮箱。</span><span class="sxs-lookup"><span data-stu-id="e8de5-135">After creating the mailbox, you can use the Set-CalendarProcessing cmdlet in Exchange Online PowerShell to configure the mailbox.</span></span> <span data-ttu-id="e8de5-136">有关更多详细信息，请参阅“单林本地部署”下的步骤 3 至 6。</span><span class="sxs-lookup"><span data-stu-id="e8de5-136">Refer to steps 3 through 6 under Single forest on-premises deployments for more details</span></span>
  
## <a name="skype-for-business-online-provisioning"></a><span data-ttu-id="e8de5-137">Skype for Business Online 设置</span><span class="sxs-lookup"><span data-stu-id="e8de5-137">Skype for Business Online provisioning</span></span>

<span data-ttu-id="e8de5-138">已创建并启用以前所示资源空间邮箱帐户后，帐户将同步从 Exchange Online 林到 Skype 对于在线业务的林使用 Windows Azure Active Directory 目录林。</span><span class="sxs-lookup"><span data-stu-id="e8de5-138">After a resource room mailbox account has been created and enabled as shown previously, the account will synchronize from the Exchange Online forest to Skype for Business Online forest by using the Windows Azure Active Directory forest.</span></span> <span data-ttu-id="e8de5-139">以下步骤需要调配业务在线池 Skype Skype 的空间系统帐户。</span><span class="sxs-lookup"><span data-stu-id="e8de5-139">The following steps are required to provision the Skype Room System account in the Skype for Business Online pool.</span></span> <span data-ttu-id="e8de5-140">这些步骤是相同的现有资源邮箱帐户或新创建的帐户 （confrm1 或 confrm2），因为一旦启用这些在 Exchange 联机，这些帐户的两个将同步到 Skype 的在线业务以相同的方式：</span><span class="sxs-lookup"><span data-stu-id="e8de5-140">These steps are the same for both an existing resource mailbox account or a newly created account (confrm1 or confrm2), because once they are enabled in Exchange Online, both of these accounts will be synchronized to Skype for Business Online in the same way:</span></span>
  
1. <span data-ttu-id="e8de5-141">创建远程 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="e8de5-141">Create a Remote PowerShell session.</span></span> <span data-ttu-id="e8de5-142">请注意，您将需要下载 Skype 业务联机接口模块和 Microsoft 联机服务登录的助手，并确保您的计算机配置。</span><span class="sxs-lookup"><span data-stu-id="e8de5-142">Note that you will need to download Skype for Business Online Connector Module and Microsoft Online Services Sign-In Assistant and make sure that your computer is configured.</span></span> <span data-ttu-id="e8de5-143">有关详细信息，请参阅[配置 Lync 在线管理您的计算机](http://technet.microsoft.com/library/bca143e2-659a-4161-9220-59ffd9fc2874.aspx)。</span><span class="sxs-lookup"><span data-stu-id="e8de5-143">For more information, see [Configuring Your Computer for Lync Online Management](http://technet.microsoft.com/library/bca143e2-659a-4161-9220-59ffd9fc2874.aspx).</span></span>
    
   ```
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="e8de5-144">若要启用业务的 Skype 的 Skype 的空间系统帐户，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="e8de5-144">To enable an Skype Room System account for Skype for Business, run the following command:</span></span>
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    <span data-ttu-id="e8de5-145">此属性可获取的地址通过使用以下命令切换到从一个现有客户托管您的业务用户的 Skype 在其中返回 RegistrarPool:</span><span class="sxs-lookup"><span data-stu-id="e8de5-145">You can obtain the RegistrarPool address where your Skype for Business users are homed from one of your existing accounts by using the following command to returns this property:</span></span>
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

## <a name="assigning-a-skype-for-business-online-license"></a><span data-ttu-id="e8de5-146">分配 Skype for Business Online 许可证</span><span class="sxs-lookup"><span data-stu-id="e8de5-146">Assigning a Skype for Business Online license</span></span>

<span data-ttu-id="e8de5-147">启用业务的 Skype 的 Skype 的空间系统帐户后，您可以为业务联机 (计划 2) 分配 Skype 或 Skype 为[中所述使用 Office 365 管理门户的在线业务 (计划 3) 许可证分配或删除 office 的许可证为企业 365](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US)或[Skype 业务加载项授权](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)。</span><span class="sxs-lookup"><span data-stu-id="e8de5-147">After you enable a Skype Room System account in Skype for Business, you can assign a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license by using the Office 365 administrative portal as described in [Assign or remove licenses for Office 365 for business](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) or in [Skype for Business add-on licensing](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7).</span></span> 
  
<span data-ttu-id="e8de5-148">指定为 Skype 在线业务许可证后，您将能够登录和验证该帐户是活动的业务客户端使用任何 Skype。</span><span class="sxs-lookup"><span data-stu-id="e8de5-148">After you assign a license for Skype for Business Online, you will be able to log in and validate that the account is active using any Skype for Business client.</span></span>
  
## <a name="password-expiration"></a><span data-ttu-id="e8de5-149">密码过期</span><span class="sxs-lookup"><span data-stu-id="e8de5-149">Password expiration</span></span>

<span data-ttu-id="e8de5-150">在 Office 365 中，所有用户帐户的默认密码过期策略是 90 天，除非你配置不同的密码过期策略。</span><span class="sxs-lookup"><span data-stu-id="e8de5-150">In Office 365, the default password expiration policy for all of your user accounts is 90 days unless you configure a different password expiration policy.</span></span> <span data-ttu-id="e8de5-151">Skype 的空间系统帐户时，您可以选择密码永不过期设置与以下步骤。</span><span class="sxs-lookup"><span data-stu-id="e8de5-151">For Skype Room System accounts, you can select the Password never expires setting with the following steps.</span></span>
  
1. <span data-ttu-id="e8de5-152">使用你的租户全局管理员凭据创建 Windows Azure Active Directory 会话。</span><span class="sxs-lookup"><span data-stu-id="e8de5-152">Create a Windows Azure Active Directory session by using your tenant global administrator credentials.</span></span>
    
    ```
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. <span data-ttu-id="e8de5-153">设置密码永不过期以前通过使用下面的命令创建的 Skype 的空间系统空间帐户设置：</span><span class="sxs-lookup"><span data-stu-id="e8de5-153">Set the Password never expires setting for the Skype Room System room account created previously by using the following command:</span></span>
    
   ```
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

<span data-ttu-id="e8de5-154">有关详细信息，请参阅[管理 Lync Online 对使用 Windows PowerShell](http://technet.microsoft.com/library/9ef2d853-10fb-4e02-a552-dcf6818d7153.aspx)。</span><span class="sxs-lookup"><span data-stu-id="e8de5-154">For more information, see [Using Windows PowerShell to Manage Lync Online](http://technet.microsoft.com/library/9ef2d853-10fb-4e02-a552-dcf6818d7153.aspx).</span></span>
  

