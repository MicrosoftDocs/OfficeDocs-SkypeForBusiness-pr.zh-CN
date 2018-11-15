---
title: 在 Office 365 中设置 Skype 会议室系统帐户
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: 阅读本主题，了解如何在 Office 365 中设置 Skype 会议室系统帐户。
ms.openlocfilehash: a1b24e25236f221d280631efd83c0e83b7ae44f2
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2018
ms.locfileid: "26532761"
---
# <a name="provisioning-skype-room-system-accounts-in-office-365"></a><span data-ttu-id="e2ba3-103">在 Office 365 中设置 Skype 会议室系统帐户</span><span class="sxs-lookup"><span data-stu-id="e2ba3-103">Provisioning Skype Room System accounts in Office 365</span></span>
 
<span data-ttu-id="e2ba3-104">阅读本主题，了解如何在 Office 365 中设置 Skype 会议室系统帐户。</span><span class="sxs-lookup"><span data-stu-id="e2ba3-104">Read this topic to learn about provisioning Skype Room System accounts in Office 365.</span></span>
  
<span data-ttu-id="e2ba3-105">以下各节介绍设置 Office 365 租户的 Skype 会议室系统帐户。</span><span class="sxs-lookup"><span data-stu-id="e2ba3-105">The following section covers Skype Room System account provisioning for an Office 365 tenant.</span></span>
  
## <a name="office-365-prerequisites"></a><span data-ttu-id="e2ba3-106">Office 365 先决条件</span><span class="sxs-lookup"><span data-stu-id="e2ba3-106">Office 365 prerequisites</span></span>

<span data-ttu-id="e2ba3-107">你的联机租户必须满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="e2ba3-107">Your online tenant must meet the following requirements:</span></span>
  
- <span data-ttu-id="e2ba3-108">Office 365 计划必须包括 Skype 业务 Online 计划 2，或 Office 365 E1、 E3 或 E5。</span><span class="sxs-lookup"><span data-stu-id="e2ba3-108">The Office 365 plan must include Skype for Business Online Plan 2, or Office 365 E1, E3 or E5.</span></span> <br/><span data-ttu-id="e2ba3-109">Skype 的业务 Online 计划的详细信息，请参阅[Skype for Business Online 服务说明](https://technet.microsoft.com/library/jj822172.aspx)。</span><span class="sxs-lookup"><span data-stu-id="e2ba3-109">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>
    
- <span data-ttu-id="e2ba3-110">Skype for Business 启用会议功能，必须拥有您的租户。</span><span class="sxs-lookup"><span data-stu-id="e2ba3-110">Your tenant must have the conferencing capability of Skype for Business enabled.</span></span>
    
- <span data-ttu-id="e2ba3-111">你的租户必须启用 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="e2ba3-111">Your tenant must have Exchange Online enabled.</span></span> 
    
- <span data-ttu-id="e2ba3-112">你的租户远程管理员必须具有以下 PowerShell 访问：</span><span class="sxs-lookup"><span data-stu-id="e2ba3-112">Your tenant remote administrator must have the following PowerShell access:</span></span>
    
  - <span data-ttu-id="e2ba3-113">Exchange 远程 PowerShell 访问</span><span class="sxs-lookup"><span data-stu-id="e2ba3-113">Exchange Remote PowerShell access</span></span>
    
  - <span data-ttu-id="e2ba3-114">Skype 业务 Online Remote PowerShell 访问</span><span class="sxs-lookup"><span data-stu-id="e2ba3-114">Skype for Business Online Remote PowerShell access</span></span>
    
  - <span data-ttu-id="e2ba3-115">Windows Azure Active Directory 模块用于 Windows PowerShell 访问 Office 365 目录访问</span><span class="sxs-lookup"><span data-stu-id="e2ba3-115">Windows Azure Active Directory Module for Windows PowerShell to access Office 365 directory access</span></span>
    
<span data-ttu-id="e2ba3-116">对于 Skype 会议室帐户，需要以下许可：</span><span class="sxs-lookup"><span data-stu-id="e2ba3-116">For the Skype Room account, the following licensing is required:</span></span>
  
- <span data-ttu-id="e2ba3-117">启用 Skype 会议需要 Skype 业务 Online 计划 2 或 Office 365 E1 或 E3 许可证。</span><span class="sxs-lookup"><span data-stu-id="e2ba3-117">A Skype for Business Online Plan 2 or Office 365 E1 or E3 license is required to enable Skype Meetings.</span></span>
    
- <span data-ttu-id="e2ba3-118">以允许与企业语音功能的聊天室，以便可以与一个电话号码启用会议室，业务 Online 计划 2 的电话系统许可证或 Office 365 E5 Skype 是需要 (1)。</span><span class="sxs-lookup"><span data-stu-id="e2ba3-118">To entitle the room with the Enterprise Voice capability so the room can be enabled with a phone number, a Skype for Business Online Plan 2 with the Phone System license or Office 365 E5 is required (1).</span></span>
    
- <span data-ttu-id="e2ba3-119">如果您需要电话拨入式会议的功能，您将需要的音频会议和电话系统许可证。</span><span class="sxs-lookup"><span data-stu-id="e2ba3-119">If you need dial-in capabilities from a meeting, you will need an audio conferencing and Phone System license.</span></span>  <span data-ttu-id="e2ba3-120">如果您需要从会议拨出功能，您将需要国内或国内和国际呼叫规划。</span><span class="sxs-lookup"><span data-stu-id="e2ba3-120">If you need dial-out capabilities from a meeting, you will need a domestic or domestic and international Calling Plan.</span></span> 
    
- <span data-ttu-id="e2ba3-121">Skype 会议室帐户不需要 Exchange Online 许可证，因为应将该帐户配置为资源邮箱帐户。</span><span class="sxs-lookup"><span data-stu-id="e2ba3-121">An Exchange Online license is not required for the Skype Room account because the account should be configured as a resource mailbox account.</span></span>
    
## <a name="provisioning-overview"></a><span data-ttu-id="e2ba3-122">设置概述</span><span class="sxs-lookup"><span data-stu-id="e2ba3-122">Provisioning overview</span></span>

<span data-ttu-id="e2ba3-123">下图概述了设置 Office 365 中的流的 Skype 会议室系统帐户。</span><span class="sxs-lookup"><span data-stu-id="e2ba3-123">The following diagram provides an overview of the Skype Room System account provisioning flow in Office 365.</span></span>
  
![O365 的 Skype 会议室系统设置步骤](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a><span data-ttu-id="e2ba3-125">识别新的会议室</span><span class="sxs-lookup"><span data-stu-id="e2ba3-125">Identify a new conference room</span></span>

<span data-ttu-id="e2ba3-126">您可能已经资源会议室邮箱在 Exchange 提供计划功能，或您可能会创建第一次为了方便 Skype 会议室系统部署的资源邮箱。</span><span class="sxs-lookup"><span data-stu-id="e2ba3-126">You may already have a resource room mailbox in Exchange that provides the scheduling feature, or you may be creating a resource mailbox for the first time to facilitate Skype Room System deployment.</span></span> <span data-ttu-id="e2ba3-127">在任何情况下，你必须识别要在你的租户中使用的会议室帐户。</span><span class="sxs-lookup"><span data-stu-id="e2ba3-127">In any case, you must identify a room account to be used in your tenant.</span></span> <span data-ttu-id="e2ba3-128">Exchange Online 设置和 Skype 业务设置部分提供的这两种帐户的指导。</span><span class="sxs-lookup"><span data-stu-id="e2ba3-128">The Exchange Online Provision and Skype for Business Provision sections provide guidance for both kinds of accounts.</span></span> <span data-ttu-id="e2ba3-129">例如，假设您具有以下两个聊天室，并且您希望为这两个部署 Skype 会议室系统：</span><span class="sxs-lookup"><span data-stu-id="e2ba3-129">For example, let's say you have the following two rooms, and you would like to deploy Skype Room System for both of them:</span></span>
  
- <span data-ttu-id="e2ba3-130">现有资源邮箱帐户：confrm1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="e2ba3-130">Existing Resource Mailbox Account: confrm1@contoso.onmicrosoft.com</span></span>
    
- <span data-ttu-id="e2ba3-131">新的资源邮箱帐户：confrm2@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="e2ba3-131">New Resource Mailbox Account: confrm2@contoso.onmicrosoft.com</span></span>
    
## <a name="exchange-online-provisioning"></a><span data-ttu-id="e2ba3-132">Exchange Online 设置</span><span class="sxs-lookup"><span data-stu-id="e2ba3-132">Exchange Online provisioning</span></span>

<span data-ttu-id="e2ba3-133">首先，连接到 Exchange Online PowerShell 中的主题，[连接到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554)中的说明。</span><span class="sxs-lookup"><span data-stu-id="e2ba3-133">First, connect to Exchange Online PowerShell by following the instructions in the topic, [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
  
<span data-ttu-id="e2ba3-134">若要设置 Skype 会议室系统现有资源会议室邮箱帐户，请在 Exchange Online PowerShell 中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="e2ba3-134">To set an existing resource room mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="e2ba3-135">要为 Skype 会议室系统中创建新的 Exchange 资源邮箱帐户，请在 Exchange Online PowerShell 中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="e2ba3-135">To create a new Exchange resource mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="e2ba3-136">上面的命令设置，或通过启用的帐户创建新 Exchange 资源邮箱帐户 Skype 会议室系统使用情况。</span><span class="sxs-lookup"><span data-stu-id="e2ba3-136">The previous commands set up or create a new Exchange resource mailbox account for Skype Room System usage by enabling the account.</span></span>
  
<span data-ttu-id="e2ba3-137">创建邮箱之后, 可用于 Exchange Online PowerShell 中的 Set-calendarprocessing cmdlet 配置邮箱。</span><span class="sxs-lookup"><span data-stu-id="e2ba3-137">After creating the mailbox, you can use the Set-CalendarProcessing cmdlet in Exchange Online PowerShell to configure the mailbox.</span></span> <span data-ttu-id="e2ba3-138">有关更多详细信息，请参阅“单林本地部署”下的步骤 3 至 6。</span><span class="sxs-lookup"><span data-stu-id="e2ba3-138">Refer to steps 3 through 6 under Single forest on-premises deployments for more details</span></span>

## <a name="assigning-a-skype-for-business-online-license"></a><span data-ttu-id="e2ba3-139">分配 Skype for Business Online 许可证</span><span class="sxs-lookup"><span data-stu-id="e2ba3-139">Assigning a Skype for Business Online license</span></span>

<span data-ttu-id="e2ba3-140">现在您可以分配 Skype 业务 Online (计划 2) 或 Skype 业务 Online (计划 3) 许可证[分配](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US)或删除业务的 Office 365 的许可证或[Skype 对业务的加载项中所述使用 Office 365 管理门户许可](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)。</span><span class="sxs-lookup"><span data-stu-id="e2ba3-140">Now you can assign a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license by using the Office 365 administrative portal as described in [Assign or remove licenses for Office 365 for business](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) or in [Skype for Business add-on licensing](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7).</span></span> 
  
<span data-ttu-id="e2ba3-141">分配许可证的 Skype 业务 online 后，您将能够登录并验证该帐户是活动的业务客户端使用任何 Skype。</span><span class="sxs-lookup"><span data-stu-id="e2ba3-141">After you assign a license for Skype for Business Online, you will be able to log in and validate that the account is active using any Skype for Business client.</span></span>
  
## <a name="skype-for-business-online-provisioning"></a><span data-ttu-id="e2ba3-142">Skype for Business Online 设置</span><span class="sxs-lookup"><span data-stu-id="e2ba3-142">Skype for Business Online provisioning</span></span>

<span data-ttu-id="e2ba3-143">和之后资源会议室邮箱帐户已创建并启用前面所示的 Skype 的业务 Online 帐户将同步从 Exchange Online 林中到 Skype 的业务联机林使用，您具有许可帐户Windows Azure Active Directory 林。</span><span class="sxs-lookup"><span data-stu-id="e2ba3-143">After a resource room mailbox account has been created and enabled as shown previously, and you have licensed the account for Skype For Business Online the account will synchronize from the Exchange Online forest to Skype for Business Online forest by using the Windows Azure Active Directory forest.</span></span> <span data-ttu-id="e2ba3-144">以下步骤所需设置中为业务联机池 Skype 的 Skype 会议室系统帐户。</span><span class="sxs-lookup"><span data-stu-id="e2ba3-144">The following steps are required to provision the Skype Room System account in the Skype for Business Online pool.</span></span> <span data-ttu-id="e2ba3-145">这些步骤是相同的现有资源邮箱帐户或新创建的帐户 （confrm1 或 confrm2），因为后启用它们在 Exchange Online，这两个这些帐户将同步到 Skype 业务 online 相同的方式：</span><span class="sxs-lookup"><span data-stu-id="e2ba3-145">These steps are the same for both an existing resource mailbox account or a newly created account (confrm1 or confrm2), because once they are enabled in Exchange Online, both of these accounts will be synchronized to Skype for Business Online in the same way:</span></span>
  
1. <span data-ttu-id="e2ba3-146">创建远程 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="e2ba3-146">Create a Remote PowerShell session.</span></span> <span data-ttu-id="e2ba3-147">请注意，您将需要下载 Skype 业务 Online 连接器模块和 Microsoft Online Services 登录助手，并确保您的计算机配置。</span><span class="sxs-lookup"><span data-stu-id="e2ba3-147">Note that you will need to download Skype for Business Online Connector Module and Microsoft Online Services Sign-In Assistant and make sure that your computer is configured.</span></span> <span data-ttu-id="e2ba3-148">有关详细信息，请参阅[Windows PowerShell 将计算机设置](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="e2ba3-148">For more information, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
    
   ```
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="e2ba3-149">若要启用 for Business 的 Skype Skype 会议室系统帐户，运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="e2ba3-149">To enable an Skype Room System account for Skype for Business, run the following command:</span></span>
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    <span data-ttu-id="e2ba3-150">您可以获取的 RegistrarPool 地址其中业务用户您 Skype 位于从您的现有帐户之一使用以下命令以返回该属性：</span><span class="sxs-lookup"><span data-stu-id="e2ba3-150">You can obtain the RegistrarPool address where your Skype for Business users are homed from one of your existing accounts by using the following command to returns this property:</span></span>
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

  
## <a name="password-expiration"></a><span data-ttu-id="e2ba3-151">密码过期</span><span class="sxs-lookup"><span data-stu-id="e2ba3-151">Password expiration</span></span>

<span data-ttu-id="e2ba3-152">在 Office 365 中，所有用户帐户的默认密码过期策略是 90 天，除非你配置不同的密码过期策略。</span><span class="sxs-lookup"><span data-stu-id="e2ba3-152">In Office 365, the default password expiration policy for all of your user accounts is 90 days unless you configure a different password expiration policy.</span></span> <span data-ttu-id="e2ba3-153">对于 Skype 会议室系统帐户时，您可以选择密码永不过期设置以下步骤。</span><span class="sxs-lookup"><span data-stu-id="e2ba3-153">For Skype Room System accounts, you can select the Password never expires setting with the following steps.</span></span>
  
1. <span data-ttu-id="e2ba3-154">使用你的租户全局管理员凭据创建 Windows Azure Active Directory 会话。</span><span class="sxs-lookup"><span data-stu-id="e2ba3-154">Create a Windows Azure Active Directory session by using your tenant global administrator credentials.</span></span>
    
    ```
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. <span data-ttu-id="e2ba3-155">设置密码永不过期之前使用以下命令创建的 Skype 会议室系统会议室帐户的设置：</span><span class="sxs-lookup"><span data-stu-id="e2ba3-155">Set the Password never expires setting for the Skype Room System room account created previously by using the following command:</span></span>
    
   ```
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

<span data-ttu-id="e2ba3-156">有关详细信息，请参阅[Windows PowerShell 将计算机设置](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="e2ba3-156">For more information, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  
## <a name="validate"></a><span data-ttu-id="e2ba3-157">验证</span><span class="sxs-lookup"><span data-stu-id="e2ba3-157">Validate</span></span>

<span data-ttu-id="e2ba3-158">进行验证，您应该能够使用任何 Skype 业务客户端登录到您创建的帐户。</span><span class="sxs-lookup"><span data-stu-id="e2ba3-158">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

