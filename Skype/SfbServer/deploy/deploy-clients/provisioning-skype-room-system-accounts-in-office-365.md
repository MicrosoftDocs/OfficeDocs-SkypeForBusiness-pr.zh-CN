---
title: 在 Microsoft 365 和 Office 365 中预配 Skype 会议室系统帐户
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: 阅读本主题，了解如何在 Microsoft 365 或 Office 365 中预配 Skype 会议室系统帐户。
ms.openlocfilehash: 8e44e648e12ec4db1e8acf9617c02937f9418c41
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569374"
---
# <a name="provisioning-skype-room-system-accounts-in-microsoft-365-and-office-365"></a><span data-ttu-id="b62e4-103">在 Microsoft 365 和 Office 365 中预配 Skype 会议室系统帐户</span><span class="sxs-lookup"><span data-stu-id="b62e4-103">Provisioning Skype Room System accounts in Microsoft 365 and Office 365</span></span>
 
<span data-ttu-id="b62e4-104">阅读本主题，了解如何在 Microsoft 365 或 Office 365 中预配 Skype 会议室系统帐户。</span><span class="sxs-lookup"><span data-stu-id="b62e4-104">Read this topic to learn about provisioning Skype Room System accounts in Microsoft 365 or Office 365.</span></span>
  
<span data-ttu-id="b62e4-105">以下部分介绍了 Skype 会议室系统帐户设置。</span><span class="sxs-lookup"><span data-stu-id="b62e4-105">The following section covers Skype Room System account provisioning.</span></span>
  
## <a name="microsoft-365-and-office-365-prerequisites"></a><span data-ttu-id="b62e4-106">Microsoft 365 和 Office 365 必备组件</span><span class="sxs-lookup"><span data-stu-id="b62e4-106">Microsoft 365 and Office 365 prerequisites</span></span>

<span data-ttu-id="b62e4-107">联机租户必须满足以下要求：</span><span class="sxs-lookup"><span data-stu-id="b62e4-107">Your online tenant must meet the following requirements:</span></span>
  
- <span data-ttu-id="b62e4-108">Microsoft 365 或 Office 365 计划必须包括 Skype for Business Online 计划 2 或 Office 365 E1、E3 或 E5。</span><span class="sxs-lookup"><span data-stu-id="b62e4-108">The Microsoft 365 or Office 365 plan must include Skype for Business Online Plan 2, or Office 365 E1, E3 or E5.</span></span> <br/><span data-ttu-id="b62e4-109">有关 Skype for Business Online 计划的详细信息，请参阅 [Skype for Business Online 服务说明](https://technet.microsoft.com/library/jj822172.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b62e4-109">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>
    
- <span data-ttu-id="b62e4-110">你的租户必须启用 Skype for Business 的会议功能。</span><span class="sxs-lookup"><span data-stu-id="b62e4-110">Your tenant must have the conferencing capability of Skype for Business enabled.</span></span>
    
- <span data-ttu-id="b62e4-111">租户必须启用 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="b62e4-111">Your tenant must have Exchange Online enabled.</span></span> 
    
- <span data-ttu-id="b62e4-112">租户远程管理员必须具有以下 PowerShell 访问权限：</span><span class="sxs-lookup"><span data-stu-id="b62e4-112">Your tenant remote administrator must have the following PowerShell access:</span></span>
    
  - <span data-ttu-id="b62e4-113">Exchange 远程 PowerShell 访问</span><span class="sxs-lookup"><span data-stu-id="b62e4-113">Exchange Remote PowerShell access</span></span>
    
  - <span data-ttu-id="b62e4-114">Skype for Business Online 远程 PowerShell 访问</span><span class="sxs-lookup"><span data-stu-id="b62e4-114">Skype for Business Online Remote PowerShell access</span></span>
    
  - <span data-ttu-id="b62e4-115">Windows Azure Active Directory 模块Windows PowerShell访问 Microsoft 365 或 Office 365 目录访问权限</span><span class="sxs-lookup"><span data-stu-id="b62e4-115">Windows Azure Active Directory Module for Windows PowerShell to access Microsoft 365 or Office 365 directory access</span></span>
    
<span data-ttu-id="b62e4-116">对于 Skype 会议室帐户，需要以下许可：</span><span class="sxs-lookup"><span data-stu-id="b62e4-116">For the Skype Room account, the following licensing is required:</span></span>
  
- <span data-ttu-id="b62e4-117">需要 Skype for Business Online 计划 2 或 Office 365 E1 或 E3 许可证才能启用 Skype 会议。</span><span class="sxs-lookup"><span data-stu-id="b62e4-117">A Skype for Business Online Plan 2 or Office 365 E1 or E3 license is required to enable Skype Meetings.</span></span>
    
- <span data-ttu-id="b62e4-118">若要使会议室具有 企业语音 功能，以便可以使用电话号码启用会议室，需要具有电话系统许可证或 Office 365 E5 的 Skype for Business Online 计划 2 (1) 。</span><span class="sxs-lookup"><span data-stu-id="b62e4-118">To entitle the room with the Enterprise Voice capability so the room can be enabled with a phone number, a Skype for Business Online Plan 2 with the Phone System license or Office 365 E5 is required (1).</span></span>
    
- <span data-ttu-id="b62e4-119">如果需要来自会议的电话拨入功能，则需要音频会议和电话系统许可证。</span><span class="sxs-lookup"><span data-stu-id="b62e4-119">If you need dial-in capabilities from a meeting, you will need an audio conferencing and Phone System license.</span></span>  <span data-ttu-id="b62e4-120">如果需要会议拨出功能，则需要国内或国内和国际通话套餐。</span><span class="sxs-lookup"><span data-stu-id="b62e4-120">If you need dial-out capabilities from a meeting, you will need a domestic or domestic and international Calling Plan.</span></span> 
    
- <span data-ttu-id="b62e4-121">Skype 会议室帐户不需要 Exchange Online 许可证，因为该帐户应配置为资源邮箱帐户。</span><span class="sxs-lookup"><span data-stu-id="b62e4-121">An Exchange Online license is not required for the Skype Room account because the account should be configured as a resource mailbox account.</span></span>
    
## <a name="provisioning-overview"></a><span data-ttu-id="b62e4-122">预配概述</span><span class="sxs-lookup"><span data-stu-id="b62e4-122">Provisioning overview</span></span>

<span data-ttu-id="b62e4-123">下图概述了 Skype 会议室系统帐户设置流。</span><span class="sxs-lookup"><span data-stu-id="b62e4-123">The following diagram provides an overview of the Skype Room System account provisioning flow.</span></span>
  
![Skype 会议室系统预配步骤](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a><span data-ttu-id="b62e4-125">确定新的会议室</span><span class="sxs-lookup"><span data-stu-id="b62e4-125">Identify a new conference room</span></span>

<span data-ttu-id="b62e4-126">你可能已经在 Exchange 中拥有提供计划功能的资源会议室邮箱，或者你可能第一次创建资源邮箱来推动 Skype 会议室系统部署。</span><span class="sxs-lookup"><span data-stu-id="b62e4-126">You may already have a resource room mailbox in Exchange that provides the scheduling feature, or you may be creating a resource mailbox for the first time to facilitate Skype Room System deployment.</span></span> <span data-ttu-id="b62e4-127">在任何情况下，都必须标识要用于租户的会议室帐户。</span><span class="sxs-lookup"><span data-stu-id="b62e4-127">In any case, you must identify a room account to be used in your tenant.</span></span> <span data-ttu-id="b62e4-128">Exchange Online 预配和 Skype for Business 预配部分为这两种类型的帐户提供指导。</span><span class="sxs-lookup"><span data-stu-id="b62e4-128">The Exchange Online Provision and Skype for Business Provision sections provide guidance for both kinds of accounts.</span></span> <span data-ttu-id="b62e4-129">例如，假设你有以下两个会议室，并且你要为这两个会议室部署 Skype 会议室系统：</span><span class="sxs-lookup"><span data-stu-id="b62e4-129">For example, let's say you have the following two rooms, and you would like to deploy Skype Room System for both of them:</span></span>
  
- <span data-ttu-id="b62e4-130">现有资源邮箱帐户：confrm1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="b62e4-130">Existing Resource Mailbox Account: confrm1@contoso.onmicrosoft.com</span></span>
    
- <span data-ttu-id="b62e4-131">新建资源邮箱帐户：confrm2@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="b62e4-131">New Resource Mailbox Account: confrm2@contoso.onmicrosoft.com</span></span>
    
## <a name="exchange-online-provisioning"></a><span data-ttu-id="b62e4-132">Exchange Online 预配</span><span class="sxs-lookup"><span data-stu-id="b62e4-132">Exchange Online provisioning</span></span>

<span data-ttu-id="b62e4-133">首先，按照主题"连接到 Exchange Online PowerShell"中的说明连接到[Exchange Online PowerShell。](https://go.microsoft.com/fwlink/p/?LinkId=396554)</span><span class="sxs-lookup"><span data-stu-id="b62e4-133">First, connect to Exchange Online PowerShell by following the instructions in the topic, [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
  
<span data-ttu-id="b62e4-134">若要为 Skype 会议室系统设置现有资源会议室邮箱帐户，请运行 Exchange Online PowerShell 中的以下命令：</span><span class="sxs-lookup"><span data-stu-id="b62e4-134">To set an existing resource room mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```powershell
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="b62e4-135">若要为 Skype 会议室系统创建新的 Exchange 资源邮箱帐户，请运行 Exchange Online PowerShell 中的以下命令：</span><span class="sxs-lookup"><span data-stu-id="b62e4-135">To create a new Exchange resource mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```powershell
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="b62e4-136">前面的命令通过启用该帐户来设置或创建新的 Exchange 资源邮箱帐户以使用 Skype 会议室系统。</span><span class="sxs-lookup"><span data-stu-id="b62e4-136">The previous commands set up or create a new Exchange resource mailbox account for Skype Room System usage by enabling the account.</span></span>
  
<span data-ttu-id="b62e4-137">创建邮箱后，可以在 Exchange Online PowerShell Set-CalendarProcessing cmdlet 配置邮箱。</span><span class="sxs-lookup"><span data-stu-id="b62e4-137">After creating the mailbox, you can use the Set-CalendarProcessing cmdlet in Exchange Online PowerShell to configure the mailbox.</span></span> <span data-ttu-id="b62e4-138">有关更多详细信息，请参阅单林本地部署下的步骤 3 到步骤 6</span><span class="sxs-lookup"><span data-stu-id="b62e4-138">Refer to steps 3 through 6 under Single forest on-premises deployments for more details</span></span>

## <a name="assigning-a-skype-for-business-online-license"></a><span data-ttu-id="b62e4-139">分配 Skype for Business Online 许可证</span><span class="sxs-lookup"><span data-stu-id="b62e4-139">Assigning a Skype for Business Online license</span></span>

<span data-ttu-id="b62e4-140">现在，可以使用 Microsoft 365 管理门户分配 Skype for Business Online (计划 2) 或 Skype for Business Online (计划 3) 许可证，如分配或删除 [Microsoft 365](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) 商业版许可证或 [Skype for Business](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)附加许可中所述。</span><span class="sxs-lookup"><span data-stu-id="b62e4-140">Now you can assign a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license by using the Microsoft 365 administrative portal as described in [Assign or remove licenses for Microsoft 365 for business](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) or in [Skype for Business add-on licensing](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7).</span></span> 
  
<span data-ttu-id="b62e4-141">为 Skype for Business Online 分配许可证后，你将能够登录并验证该帐户是否在任何 Skype for Business 客户端上处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="b62e4-141">After you assign a license for Skype for Business Online, you will be able to log in and validate that the account is active using any Skype for Business client.</span></span>
  
## <a name="skype-for-business-online-provisioning"></a><span data-ttu-id="b62e4-142">Skype for Business Online 预配</span><span class="sxs-lookup"><span data-stu-id="b62e4-142">Skype for Business Online provisioning</span></span>

<span data-ttu-id="b62e4-143">按照前面所示创建和启用资源会议室邮箱帐户，并且你已许可 Skype For Business Online 帐户后，该帐户将通过使用 Windows Azure Active Directory 林从 Exchange Online 林同步到 Skype for Business Online 林。</span><span class="sxs-lookup"><span data-stu-id="b62e4-143">After a resource room mailbox account has been created and enabled as shown previously, and you have licensed the account for Skype For Business Online the account will synchronize from the Exchange Online forest to Skype for Business Online forest by using the Windows Azure Active Directory forest.</span></span> <span data-ttu-id="b62e4-144">若要在 Skype for Business Online 池中设置 Skype 会议室系统帐户，需要执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="b62e4-144">The following steps are required to provision the Skype Room System account in the Skype for Business Online pool.</span></span> <span data-ttu-id="b62e4-145">对于现有资源邮箱帐户或新创建的帐户 (confrm1 或 confrm2) ，这些步骤是相同的，因为在 Exchange Online 中启用这些步骤后，这两个帐户都将以相同方式同步到 Skype for Business Online：</span><span class="sxs-lookup"><span data-stu-id="b62e4-145">These steps are the same for both an existing resource mailbox account or a newly created account (confrm1 or confrm2), because once they are enabled in Exchange Online, both of these accounts will be synchronized to Skype for Business Online in the same way:</span></span>
  
1. <span data-ttu-id="b62e4-146">创建远程 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="b62e4-146">Create a Remote PowerShell session.</span></span> <span data-ttu-id="b62e4-147">请注意，你将需要下载 [Teams PowerShell 模块](https://docs.microsoft.com/microsoftteams/teams-powershell-install)。</span><span class="sxs-lookup"><span data-stu-id="b62e4-147">Note that you will need to download [Teams PowerShell module](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>
    
  ```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
  ```

2. <span data-ttu-id="b62e4-148">若要为 Skype for Business 启用 Skype 会议室系统帐户，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="b62e4-148">To enable an Skype Room System account for Skype for Business, run the following command:</span></span>
    
   ```powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    <span data-ttu-id="b62e4-149">可以通过以下命令返回此属性，从你的现有帐户之一获取你的 Skype for Business 用户所拥有注册器池地址：</span><span class="sxs-lookup"><span data-stu-id="b62e4-149">You can obtain the RegistrarPool address where your Skype for Business users are homed from one of your existing accounts by using the following command to returns this property:</span></span>
    
   ```powershell
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

>[!NOTE] 
><span data-ttu-id="b62e4-150">Skype 会议室系统 (MFA) 不支持多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="b62e4-150">Multi-Factor Authentication (MFA) isn't supported for Skype Room System accounts.</span></span> 

## <a name="password-expiration"></a><span data-ttu-id="b62e4-151">密码有效期</span><span class="sxs-lookup"><span data-stu-id="b62e4-151">Password expiration</span></span>

<span data-ttu-id="b62e4-152">在 Microsoft 365 或 Office 365 中，除非配置不同的密码过期策略，否则所有用户帐户的默认密码过期策略为 90 天。</span><span class="sxs-lookup"><span data-stu-id="b62e4-152">In Microsoft 365 or Office 365, the default password expiration policy for all of your user accounts is 90 days unless you configure a different password expiration policy.</span></span> <span data-ttu-id="b62e4-153">对于 Skype 会议室系统帐户，可以通过以下步骤选择"密码永不过期"设置。</span><span class="sxs-lookup"><span data-stu-id="b62e4-153">For Skype Room System accounts, you can select the Password never expires setting with the following steps.</span></span>
  
1. <span data-ttu-id="b62e4-154">使用Windows Azure全局管理员凭据创建 Active Directory 会话。</span><span class="sxs-lookup"><span data-stu-id="b62e4-154">Create a Windows Azure Active Directory session by using your tenant global administrator credentials.</span></span>
    
    ```powershell
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. <span data-ttu-id="b62e4-155">使用以下命令为以前创建的 Skype 会议室系统会议室帐户设置"密码永不过期"设置：</span><span class="sxs-lookup"><span data-stu-id="b62e4-155">Set the Password never expires setting for the Skype Room System room account created previously by using the following command:</span></span>
    
   ```powershell
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

<span data-ttu-id="b62e4-156">有关详细信息，请参阅为[计算机设置Windows PowerShell。](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="b62e4-156">For more information, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  
## <a name="validate"></a><span data-ttu-id="b62e4-157">验证</span><span class="sxs-lookup"><span data-stu-id="b62e4-157">Validate</span></span>

<span data-ttu-id="b62e4-158">为了进行验证，你应该能够使用任意 Skype for Business 客户端登录到你创建的帐户。</span><span class="sxs-lookup"><span data-stu-id="b62e4-158">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

