---
title: 在 Microsoft 365 和 Office 365 中预配 Skype 会议室系统帐户
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: 阅读本主题，了解如何在 Microsoft 365 或 Office 365 中设置 Skype 会议室系统帐户。
ms.openlocfilehash: e2796d9a81f918c0503382e23aad5ead711240e7
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779708"
---
# <a name="provisioning-skype-room-system-accounts-in-microsoft-365-and-office-365"></a><span data-ttu-id="859d3-103">在 Microsoft 365 和 Office 365 中预配 Skype 会议室系统帐户</span><span class="sxs-lookup"><span data-stu-id="859d3-103">Provisioning Skype Room System accounts in Microsoft 365 and Office 365</span></span>
 
<span data-ttu-id="859d3-104">阅读本主题，了解如何在 Office 365 中设置 Skype 会议室系统帐户。</span><span class="sxs-lookup"><span data-stu-id="859d3-104">Read this topic to learn about provisioning Skype Room System accounts in Office 365.</span></span>
  
<span data-ttu-id="859d3-105">以下部分介绍了 Office 365 组织的 Skype 会议室系统帐户设置。</span><span class="sxs-lookup"><span data-stu-id="859d3-105">The following section covers Skype Room System account provisioning for an Office 365 organization.</span></span>
  
## <a name="microsoft-365-and-office-365-prerequisites"></a><span data-ttu-id="859d3-106">Microsoft 365 和 Office 365 先决条件</span><span class="sxs-lookup"><span data-stu-id="859d3-106">Microsoft 365 and Office 365 prerequisites</span></span>

<span data-ttu-id="859d3-107">您的联机租户必须满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="859d3-107">Your online tenant must meet the following requirements:</span></span>
  
- <span data-ttu-id="859d3-108">Microsoft 365 或 Office 365 计划必须包括 Skype for Business Online 计划2或 Office 365 E1、E3 或 E5。</span><span class="sxs-lookup"><span data-stu-id="859d3-108">The Microsoft 365 or Office 365 plan must include Skype for Business Online Plan 2, or Office 365 E1, E3 or E5.</span></span> <br/><span data-ttu-id="859d3-109">有关 Skype for business Online 计划的详细信息，请参阅[skype For Business Online 服务说明](https://technet.microsoft.com/library/jj822172.aspx)。</span><span class="sxs-lookup"><span data-stu-id="859d3-109">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>
    
- <span data-ttu-id="859d3-110">你的租户必须启用 Skype for Business 的会议功能。</span><span class="sxs-lookup"><span data-stu-id="859d3-110">Your tenant must have the conferencing capability of Skype for Business enabled.</span></span>
    
- <span data-ttu-id="859d3-111">你的租户必须启用了 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="859d3-111">Your tenant must have Exchange Online enabled.</span></span> 
    
- <span data-ttu-id="859d3-112">您的租户远程管理员必须具有以下 PowerShell 访问权限：</span><span class="sxs-lookup"><span data-stu-id="859d3-112">Your tenant remote administrator must have the following PowerShell access:</span></span>
    
  - <span data-ttu-id="859d3-113">Exchange 远程 PowerShell 访问</span><span class="sxs-lookup"><span data-stu-id="859d3-113">Exchange Remote PowerShell access</span></span>
    
  - <span data-ttu-id="859d3-114">Skype for Business Online 远程 PowerShell 访问</span><span class="sxs-lookup"><span data-stu-id="859d3-114">Skype for Business Online Remote PowerShell access</span></span>
    
  - <span data-ttu-id="859d3-115">用于 Windows PowerShell 的 windows Azure Active Directory 模块以访问 Office 365 目录访问</span><span class="sxs-lookup"><span data-stu-id="859d3-115">Windows Azure Active Directory Module for Windows PowerShell to access Office 365 directory access</span></span>
    
<span data-ttu-id="859d3-116">对于 Skype 会议室帐户，需要以下许可：</span><span class="sxs-lookup"><span data-stu-id="859d3-116">For the Skype Room account, the following licensing is required:</span></span>
  
- <span data-ttu-id="859d3-117">启用 Skype 会议需要 Skype for Business Online 计划2或 Office 365 E1 或 E3 许可证。</span><span class="sxs-lookup"><span data-stu-id="859d3-117">A Skype for Business Online Plan 2 or Office 365 E1 or E3 license is required to enable Skype Meetings.</span></span>
    
- <span data-ttu-id="859d3-118">若要使用企业语音功能为会议室 entitle，以便可以使用电话号码启用会议室，则需要具有电话系统许可证或 Office 365 E5 的 Skype for Business Online 计划2（1）。</span><span class="sxs-lookup"><span data-stu-id="859d3-118">To entitle the room with the Enterprise Voice capability so the room can be enabled with a phone number, a Skype for Business Online Plan 2 with the Phone System license or Office 365 E5 is required (1).</span></span>
    
- <span data-ttu-id="859d3-119">如果需要来自会议的电话拨入功能，则需要音频会议和电话系统许可证。</span><span class="sxs-lookup"><span data-stu-id="859d3-119">If you need dial-in capabilities from a meeting, you will need an audio conferencing and Phone System license.</span></span>  <span data-ttu-id="859d3-120">如果需要来自会议的拨出功能，则需要国内或国内和国际通话套餐。</span><span class="sxs-lookup"><span data-stu-id="859d3-120">If you need dial-out capabilities from a meeting, you will need a domestic or domestic and international Calling Plan.</span></span> 
    
- <span data-ttu-id="859d3-121">Skype 会议室帐户不需要 Exchange Online 许可证，因为应将该帐户配置为资源邮箱帐户。</span><span class="sxs-lookup"><span data-stu-id="859d3-121">An Exchange Online license is not required for the Skype Room account because the account should be configured as a resource mailbox account.</span></span>
    
## <a name="provisioning-overview"></a><span data-ttu-id="859d3-122">预配概述</span><span class="sxs-lookup"><span data-stu-id="859d3-122">Provisioning overview</span></span>

<span data-ttu-id="859d3-123">下图概述了 Office 365 中的 Skype 会议室系统帐户预配流。</span><span class="sxs-lookup"><span data-stu-id="859d3-123">The following diagram provides an overview of the Skype Room System account provisioning flow in Office 365.</span></span>
  
![O365 的 Skype 会议室系统预配步骤](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a><span data-ttu-id="859d3-125">标识新的会议室</span><span class="sxs-lookup"><span data-stu-id="859d3-125">Identify a new conference room</span></span>

<span data-ttu-id="859d3-126">您可能已经在 Exchange 中有一个资源室邮箱提供了计划功能，或者您可能第一次创建了资源邮箱以促进 Skype 会议室系统部署。</span><span class="sxs-lookup"><span data-stu-id="859d3-126">You may already have a resource room mailbox in Exchange that provides the scheduling feature, or you may be creating a resource mailbox for the first time to facilitate Skype Room System deployment.</span></span> <span data-ttu-id="859d3-127">在任何情况下，都必须标识要在租户中使用的会议室帐户。</span><span class="sxs-lookup"><span data-stu-id="859d3-127">In any case, you must identify a room account to be used in your tenant.</span></span> <span data-ttu-id="859d3-128">Exchange Online 设置和 Skype for Business 设置部分提供了这两种帐户的指南。</span><span class="sxs-lookup"><span data-stu-id="859d3-128">The Exchange Online Provision and Skype for Business Provision sections provide guidance for both kinds of accounts.</span></span> <span data-ttu-id="859d3-129">例如，假设你有以下两个聊天室，并且想要为这两个聊天室部署 Skype 会议室系统：</span><span class="sxs-lookup"><span data-stu-id="859d3-129">For example, let's say you have the following two rooms, and you would like to deploy Skype Room System for both of them:</span></span>
  
- <span data-ttu-id="859d3-130">现有资源邮箱帐户： confrm1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="859d3-130">Existing Resource Mailbox Account: confrm1@contoso.onmicrosoft.com</span></span>
    
- <span data-ttu-id="859d3-131">新资源邮箱帐户： confrm2@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="859d3-131">New Resource Mailbox Account: confrm2@contoso.onmicrosoft.com</span></span>
    
## <a name="exchange-online-provisioning"></a><span data-ttu-id="859d3-132">Exchange Online 设置</span><span class="sxs-lookup"><span data-stu-id="859d3-132">Exchange Online provisioning</span></span>

<span data-ttu-id="859d3-133">首先，按照主题 "[连接到 Exchange Online powershell](https://go.microsoft.com/fwlink/p/?LinkId=396554)" 中的说明操作，连接到 Exchange online powershell。</span><span class="sxs-lookup"><span data-stu-id="859d3-133">First, connect to Exchange Online PowerShell by following the instructions in the topic, [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
  
<span data-ttu-id="859d3-134">若要为 Skype 会议室系统设置现有的资源室邮箱帐户，请在 Exchange Online PowerShell 中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="859d3-134">To set an existing resource room mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```powershell
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="859d3-135">若要为 Skype 会议室系统创建新的 Exchange 资源邮箱帐户，请在 Exchange Online PowerShell 中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="859d3-135">To create a new Exchange resource mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```powershell
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="859d3-136">通过启用此帐户，以前的命令为 Skype 会议室系统的使用设置或创建新的 Exchange 资源邮箱帐户。</span><span class="sxs-lookup"><span data-stu-id="859d3-136">The previous commands set up or create a new Exchange resource mailbox account for Skype Room System usage by enabling the account.</span></span>
  
<span data-ttu-id="859d3-137">创建邮箱后，您可以使用 Exchange Online PowerShell 中的 Set-calendarprocessing cmdlet 来配置邮箱。</span><span class="sxs-lookup"><span data-stu-id="859d3-137">After creating the mailbox, you can use the Set-CalendarProcessing cmdlet in Exchange Online PowerShell to configure the mailbox.</span></span> <span data-ttu-id="859d3-138">有关更多详细信息，请参阅单林本地部署下的步骤3至6</span><span class="sxs-lookup"><span data-stu-id="859d3-138">Refer to steps 3 through 6 under Single forest on-premises deployments for more details</span></span>

## <a name="assigning-a-skype-for-business-online-license"></a><span data-ttu-id="859d3-139">分配 Skype for Business Online 许可证</span><span class="sxs-lookup"><span data-stu-id="859d3-139">Assigning a Skype for Business Online license</span></span>

<span data-ttu-id="859d3-140">现在，您可以使用 Office 365 管理门户（如在 Office 365 for business 或[Skype For business 附加许可](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)中[分配或删除许可证](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US)中所述），分配 skype For business online （计划2）或 skype For business online （计划3）许可证。</span><span class="sxs-lookup"><span data-stu-id="859d3-140">Now you can assign a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license by using the Office 365 administrative portal as described in [Assign or remove licenses for Office 365 for business](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) or in [Skype for Business add-on licensing](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7).</span></span> 
  
<span data-ttu-id="859d3-141">为 Skype for business Online 分配许可证后，你将能够使用任何 Skype for business 客户端登录并验证帐户是否处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="859d3-141">After you assign a license for Skype for Business Online, you will be able to log in and validate that the account is active using any Skype for Business client.</span></span>
  
## <a name="skype-for-business-online-provisioning"></a><span data-ttu-id="859d3-142">Skype for Business Online 设置</span><span class="sxs-lookup"><span data-stu-id="859d3-142">Skype for Business Online provisioning</span></span>

<span data-ttu-id="859d3-143">在创建并按之前显示的那样启用了 resource 会议室邮箱帐户之后，并且已为 Skype For business Online 授权帐户，该帐户将使用 Windows Azure Active Directory 林从 Exchange Online 林同步到 Skype for business Online 林。</span><span class="sxs-lookup"><span data-stu-id="859d3-143">After a resource room mailbox account has been created and enabled as shown previously, and you have licensed the account for Skype For Business Online the account will synchronize from the Exchange Online forest to Skype for Business Online forest by using the Windows Azure Active Directory forest.</span></span> <span data-ttu-id="859d3-144">若要在 Skype for business Online 池中预配 Skype 会议室系统帐户，需要执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="859d3-144">The following steps are required to provision the Skype Room System account in the Skype for Business Online pool.</span></span> <span data-ttu-id="859d3-145">对于现有资源邮箱帐户或新创建的帐户（confrm1 或 confrm2），这些步骤都相同，因为它们在 Exchange Online 中启用后，这两个帐户将以相同的方式同步到 Skype for business Online：</span><span class="sxs-lookup"><span data-stu-id="859d3-145">These steps are the same for both an existing resource mailbox account or a newly created account (confrm1 or confrm2), because once they are enabled in Exchange Online, both of these accounts will be synchronized to Skype for Business Online in the same way:</span></span>
  
1. <span data-ttu-id="859d3-146">创建远程 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="859d3-146">Create a Remote PowerShell session.</span></span> <span data-ttu-id="859d3-147">请注意，你将需要下载 Skype for Business Online 连接器模块和 Microsoft Online Services 登录助手，并确保已配置你的计算机。</span><span class="sxs-lookup"><span data-stu-id="859d3-147">Note that you will need to download Skype for Business Online Connector Module and Microsoft Online Services Sign-In Assistant and make sure that your computer is configured.</span></span> <span data-ttu-id="859d3-148">有关详细信息，请参阅[设置适用于 Windows PowerShell 的计算机](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="859d3-148">For more information, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
    
   ```powershell
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="859d3-149">若要为 Skype for business 启用 Skype 会议室系统帐户，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="859d3-149">To enable an Skype Room System account for Skype for Business, run the following command:</span></span>
    
   ```powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    <span data-ttu-id="859d3-150">您可以通过使用以下命令返回此属性，获取您的 Skype for business 用户驻留在现有帐户之一中的 RegistrarPool 地址：</span><span class="sxs-lookup"><span data-stu-id="859d3-150">You can obtain the RegistrarPool address where your Skype for Business users are homed from one of your existing accounts by using the following command to returns this property:</span></span>
    
   ```powershell
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

>[!NOTE] 
><span data-ttu-id="859d3-151">Skype 会议室系统帐户不支持多重身份验证（MFA）。</span><span class="sxs-lookup"><span data-stu-id="859d3-151">Multi-Factor Authentication (MFA) isn't supported for Skype Room System accounts.</span></span> 

## <a name="password-expiration"></a><span data-ttu-id="859d3-152">密码有效期</span><span class="sxs-lookup"><span data-stu-id="859d3-152">Password expiration</span></span>

<span data-ttu-id="859d3-153">在 Office 365 中，除非您配置不同的密码过期策略，否则所有用户帐户的默认密码过期策略都是90天。</span><span class="sxs-lookup"><span data-stu-id="859d3-153">In Office 365, the default password expiration policy for all of your user accounts is 90 days unless you configure a different password expiration policy.</span></span> <span data-ttu-id="859d3-154">对于 Skype 会议室系统帐户，你可以使用以下步骤选择 "密码永不过期" 设置。</span><span class="sxs-lookup"><span data-stu-id="859d3-154">For Skype Room System accounts, you can select the Password never expires setting with the following steps.</span></span>
  
1. <span data-ttu-id="859d3-155">使用租户全局管理员凭据创建 Windows Azure Active Directory 会话。</span><span class="sxs-lookup"><span data-stu-id="859d3-155">Create a Windows Azure Active Directory session by using your tenant global administrator credentials.</span></span>
    
    ```powershell
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. <span data-ttu-id="859d3-156">为先前使用以下命令创建的 Skype 会议室系统室帐户设置 "密码永不过期" 设置：</span><span class="sxs-lookup"><span data-stu-id="859d3-156">Set the Password never expires setting for the Skype Room System room account created previously by using the following command:</span></span>
    
   ```powershell
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

<span data-ttu-id="859d3-157">有关详细信息，请参阅[设置适用于 Windows PowerShell 的计算机](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="859d3-157">For more information, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  
## <a name="validate"></a><span data-ttu-id="859d3-158">验证</span><span class="sxs-lookup"><span data-stu-id="859d3-158">Validate</span></span>

<span data-ttu-id="859d3-159">若要进行验证，你应该能够使用任何 Skype for Business 客户端登录到你创建的帐户。</span><span class="sxs-lookup"><span data-stu-id="859d3-159">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

