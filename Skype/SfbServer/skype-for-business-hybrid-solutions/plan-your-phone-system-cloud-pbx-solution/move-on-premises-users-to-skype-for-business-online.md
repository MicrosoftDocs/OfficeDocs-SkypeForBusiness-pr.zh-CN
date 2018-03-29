---
title: 移动内部用户 Skype 的在线业务
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/27/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
ms.custom: Strat_SB_Hybrid
ms.assetid: 2475674a-f592-4fa8-ae99-f71cbea54dc0
description: 摘要： 有关移动信息内部用户 Skype 的在线业务。
ms.openlocfilehash: 9aa4c87d713af437f1fbb81cd23e354792559aa8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="move-on-premises-users-to-skype-for-business-online"></a><span data-ttu-id="eba1b-103">移动内部用户 Skype 的在线业务</span><span class="sxs-lookup"><span data-stu-id="eba1b-103">Move on-premises users to Skype for Business Online</span></span>
 
<span data-ttu-id="eba1b-104">**摘要：**有关移动信息内部用户 Skype 的在线业务。</span><span class="sxs-lookup"><span data-stu-id="eba1b-104">**Summary:** Information about moving on-premises users to Skype for Business Online.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="eba1b-105">在迁移到 Skype for Business Online 之前，必须更新 Lync Phone Edition 设备以符合最低的必要固件要求。</span><span class="sxs-lookup"><span data-stu-id="eba1b-105">Lync Phone Edition devices MUST be updated to minimum required firmware in your on premises environment PRIOR to moving to Skype for Business Online.</span></span> <span data-ttu-id="eba1b-106">如果在更新固件之前将用户从本地环境迁移到联机环境，用户将无法使用其电话进行连接。</span><span class="sxs-lookup"><span data-stu-id="eba1b-106">If you move your users from on-premises to online prior to updating the firmware, users will be unable to connect using their phones.</span></span> <span data-ttu-id="eba1b-107">要更正此问题，必须将用户移回到本地环境以将其电话固件更新为最低要求的固件。</span><span class="sxs-lookup"><span data-stu-id="eba1b-107">To correct this problem, users must be moved back to the on premises environment to have their phones updated to the minimum firmware.</span></span> <span data-ttu-id="eba1b-108">请勿在将用户移回到本地环境之前尝试更新到最低要求的固件或对电话执行硬重置。</span><span class="sxs-lookup"><span data-stu-id="eba1b-108">DO NOT ATTEMPT TO UPDATE TO MINIMUM FIRMWARE OR HARD RESET THE PHONE PRIOR TO MOVING THE USER BACK TO YOUR ON PREMISES ENVIRONMENT.</span></span>
<span data-ttu-id="eba1b-109">如果在设备未安装最低要求的固件时执行了硬重置，设备将默认为使用 PIN 身份验证，而 Skype for Business Online 不支持这种验证方式。</span><span class="sxs-lookup"><span data-stu-id="eba1b-109">If a hard reset is performed while the device is not at minimum firmware it will default to using PIN Authentication, which is not supported in Skype for Business Online.</span></span> <span data-ttu-id="eba1b-110">有关详细信息，请参阅[获取电话 Skype 的在线业务](https://support.office.com/en-us/article/Getting-phones-for-Skype-for-Business-Online-91f2d947-45fc-4fab-bd8b-2e313531c477?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="eba1b-110">For more information, please refer to [Getting Phones for Skype for Business Online](https://support.office.com/en-us/article/Getting-phones-for-Skype-for-Business-Online-91f2d947-45fc-4fab-bd8b-2e313531c477?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
<span data-ttu-id="eba1b-111">这是一个可选步骤，是必需的只有当您转向内部用户 Skype 的在线业务。</span><span class="sxs-lookup"><span data-stu-id="eba1b-111">This is an optional step that is required only if you are moving on-premises users to Skype for Business Online.</span></span> <span data-ttu-id="eba1b-112">在开始转向用户 Skype 的在线业务之前，检查，Skype 业务在线连接器 （Windows PowerShell 模块） 在您前端服务器上部署。</span><span class="sxs-lookup"><span data-stu-id="eba1b-112">Before you begin to move users to Skype for Business Online, check that the Skype for Business Online Connector (Windows PowerShell module) is deployed on your Front End Servers.</span></span> <span data-ttu-id="eba1b-113">如果不是这样，则可以从[下载中心](https://www.microsoft.com/en-us/download/details.aspx?id=39366)下载。</span><span class="sxs-lookup"><span data-stu-id="eba1b-113">If it isn't, you can download it from [the download center](https://www.microsoft.com/en-us/download/details.aspx?id=39366).</span></span> <span data-ttu-id="eba1b-114">此外，要准备 AD，您需要配置 Azure AD Connect。</span><span class="sxs-lookup"><span data-stu-id="eba1b-114">Also, to prepare your AD, you'll need to configure Azure AD Connect.</span></span> <span data-ttu-id="eba1b-115">所使用的 AAD Connect 版本必须是版本 1.0.9125.0 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="eba1b-115">The version of AAD Connect you use must be version 1.0.9125.0 or later.</span></span> <span data-ttu-id="eba1b-116">如果您使用较早版本的 AAD Connect 工具或 DirSync，请升级到支持的版本。</span><span class="sxs-lookup"><span data-stu-id="eba1b-116">If you are using an earlier version of AAD Connect tools or DirSync, please upgrade to the supported version.</span></span> <span data-ttu-id="eba1b-117">您可以升级您的当前安装并维护您在环境中定义的任何自定义规则。</span><span class="sxs-lookup"><span data-stu-id="eba1b-117">You can upgrade your current installation and maintain any custom rules you have defined in your environment.</span></span>
  
<span data-ttu-id="eba1b-118">移动用户使用任一 Skype 业务服务器的控制面板或 Skype 业务服务器管理外壳程序在内部部署中，但您必须为您的 Office 365 部署具有管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="eba1b-118">You move users using either Skype for Business Server Control Panel or Skype for Business Server Management Shell in your on-premises deployment, but you must have administrator credentials for your Office 365 deployment.</span></span>
  
## <a name="moving-users-by-using-skype-for-business-control-panel"></a><span data-ttu-id="eba1b-119">移动用户通过 Skype 业务控制面板</span><span class="sxs-lookup"><span data-stu-id="eba1b-119">Moving users by using Skype for Business Control Panel</span></span>

### <a name="to-move-a-user-to-skype-for-business-online"></a><span data-ttu-id="eba1b-120">若要将用户移动到 Skype，进行在线业务</span><span class="sxs-lookup"><span data-stu-id="eba1b-120">To move a user to Skype for Business Online</span></span>

1. <span data-ttu-id="eba1b-121">从分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户，登录到您有 Skype 业务服务器，或在的内部部署中的任何计算机至少 Skype 业务服务器管理工具安装。</span><span class="sxs-lookup"><span data-stu-id="eba1b-121">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment that has Skype for Business Server, or at least Skype for Business Server Admin tools installed.</span></span>
    
2. <span data-ttu-id="eba1b-122">从 「 开始 」 菜单或桌面快捷方式，打开 Skype 业务服务器的控制面板。</span><span class="sxs-lookup"><span data-stu-id="eba1b-122">From the Start menu or desktop shortcut, open the Skype for Business Server Control Panel.</span></span>
    
    <span data-ttu-id="eba1b-123">如果您配置了一个使用管理的 URL，还可以访问 Skype 业务服务器的控制面板。</span><span class="sxs-lookup"><span data-stu-id="eba1b-123">You can also access the Skype for Business Server Control Panel by using the Admin URL if you have configured one.</span></span>
    
3. <span data-ttu-id="eba1b-124">在左导航栏中，单击“**用户**”。</span><span class="sxs-lookup"><span data-stu-id="eba1b-124">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="eba1b-125">在“搜索用户”****框中，键入要启用的用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”****。</span><span class="sxs-lookup"><span data-stu-id="eba1b-125">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>
    
5. <span data-ttu-id="eba1b-126">单击用户，然后在“**操作**”菜单中单击“**将所选用户移动到 Skype for Business Online**”。</span><span class="sxs-lookup"><span data-stu-id="eba1b-126">Click the user, then in the **Action** menu, click **Move selected users to Skype for Business Online**.</span></span>
    
6. <span data-ttu-id="eba1b-127">在“**将用户移动到 Skype For Business Online**”页面上，阅读信息，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="eba1b-127">On the **Move users to Skype For Business Online** page, read the information and then click **Next**.</span></span>
    
7. <span data-ttu-id="eba1b-128">在下一页上，如果您不尚未登录到 Office 365，单击**登录到 Office 365**，提供您的凭据，并单击**确定**和**下一步**。</span><span class="sxs-lookup"><span data-stu-id="eba1b-128">On the next page, if you are not yet signed in to Office 365, click **Sign in to Office 365**, provide your credentials, and click **OK** and **Next**.</span></span>
    
8. <span data-ttu-id="eba1b-129">确认要移动的用户数是否正确，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="eba1b-129">Confirm that the number of users to be moved is correct, and click **Next**.</span></span>
    
9. <span data-ttu-id="eba1b-130">在下一页上，查看结果，然后单击“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="eba1b-130">On the next page, review the results and click **Close**.</span></span>
    
## <a name="moving-users-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="eba1b-131">移动用户通过 Skype 业务服务器管理外壳程序</span><span class="sxs-lookup"><span data-stu-id="eba1b-131">Moving users by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="eba1b-132">要移动到您的在线业务的租户的 Skype 的内部用户，运行以下 cmdlet 在 Skype 业务管理程序，对 Microsoft Office 365 租户使用管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="eba1b-132">To move an on-premises user to your Skype for Business Online tenant, run the following cmdlets in the Skype for Business Server Management Shell, using the administrator credentials for your Microsoft Office 365 tenant.</span></span> <span data-ttu-id="eba1b-133">使用要移动的用户的信息替换“username@contoso.com”。</span><span class="sxs-lookup"><span data-stu-id="eba1b-133">Replace "username@contoso.com" with the information for the user that you want to move.</span></span>
  
```
$creds=Get-Credential
```

```
Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>
```

<span data-ttu-id="eba1b-134">指定**HostedMigrationOverrideUrl**参数必须到池承载迁移服务正在运行，按以下格式的 URL 的 URL 的格式： _Https://\<池的 FQDN\>/HostedMigration/hostedmigrationService.svc_。</span><span class="sxs-lookup"><span data-stu-id="eba1b-134">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format: _Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc_.</span></span>
  
<span data-ttu-id="eba1b-135">您可以通过查看 Office 365 租户帐户业务在线管理中心 Skype URL 确定承载迁移服务的 URL。</span><span class="sxs-lookup"><span data-stu-id="eba1b-135">You can determine the URL to the Hosted Migration Service by viewing the URL for the Skype for Business Online Admin center for your Office 365 tenant account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="eba1b-136">URL 区分大小写。</span><span class="sxs-lookup"><span data-stu-id="eba1b-136">The URL is case sensitive.</span></span> 
  
### <a name="to-determine-the-hosted-migration-service-url-for-your-office-365-tenant"></a><span data-ttu-id="eba1b-137">确定 Office 365 租户的托管迁移服务 URL</span><span class="sxs-lookup"><span data-stu-id="eba1b-137">To determine the Hosted Migration Service URL for your Office 365 tenant</span></span>

1. <span data-ttu-id="eba1b-138">以管理员身份登录到 Office 365 租户。</span><span class="sxs-lookup"><span data-stu-id="eba1b-138">Login to your Office 365 tenant as an administrator.</span></span>
    
2. <span data-ttu-id="eba1b-139">打开“Skype for Business 管理中心”****。</span><span class="sxs-lookup"><span data-stu-id="eba1b-139">Open the **Skype for Business admin center**.</span></span>
    
3. <span data-ttu-id="eba1b-140">显示“Skype for Business 管理中心”****后，选中并复制地址栏中一直到 **lync.com** 的 URL。示例 URL 如下所示：</span><span class="sxs-lookup"><span data-stu-id="eba1b-140">With the **Skype for Business admin center** displayed, select and copy the URL in the address bar up to **lync.com**. An example URL looks similar to the following:</span></span>
    
     `https://webdir0a.online.lync.com/lscp/?language=en-US&amp;tenantID=`
    
4. <span data-ttu-id="eba1b-141">将 URL 中的 **webdir** 替换为 **admin**，得到以下 URL：</span><span class="sxs-lookup"><span data-stu-id="eba1b-141">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span> 
    
     `https://admin0a.online.lync.com`
    
5. <span data-ttu-id="eba1b-142">向 URL 附加以下字符串：**/HostedMigration/hostedmigrationService.svc**。</span><span class="sxs-lookup"><span data-stu-id="eba1b-142">Append the following string to the URL: **/HostedMigration/hostedmigrationService.svc**.</span></span>
    
    <span data-ttu-id="eba1b-143">所生成的 URL，这是**HostedMigrationOverrideUrl**的值，应如下所示：</span><span class="sxs-lookup"><span data-stu-id="eba1b-143">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
    
     `https://admin0a.online.lync.com/HostedMigration/hostedmigrationService.svc`
    

