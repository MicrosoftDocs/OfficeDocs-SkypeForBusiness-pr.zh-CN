---
title: 'Lync Server 2013: 将用户移动到 Lync Online'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Move users to Lync Online
ms:assetid: 6a523c86-2eac-4fa4-973a-4406872c9a7d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204969(v=OCS.15)
ms:contentKeyID: 48184392
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 410fd1fe521bd8d4750b290a54db26adb630a8be
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826659"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-users-to-lync-online-in-lync-server-2013"></a><span data-ttu-id="fda0b-102">在 Lync Server 2013 中将用户移动到 Lync Online</span><span class="sxs-lookup"><span data-stu-id="fda0b-102">Move users to Lync Online in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fda0b-103">_**主题上次修改时间:** 2014-05-29_</span><span class="sxs-lookup"><span data-stu-id="fda0b-103">_**Topic Last Modified:** 2014-05-29_</span></span>

<span data-ttu-id="fda0b-104">开始将用户迁移到 Lync Online 之前, 应备份与要移动的帐户相关联的用户数据。</span><span class="sxs-lookup"><span data-stu-id="fda0b-104">Before you start migrating users to Lync Online, you should backup the user data associated with the accounts to be moved.</span></span> <span data-ttu-id="fda0b-105">并非所有用户数据都会与用户帐户一并移动。</span><span class="sxs-lookup"><span data-stu-id="fda0b-105">Not all user data is moved with the user account.</span></span> <span data-ttu-id="fda0b-106">有关信息, 请参阅[Lync Server 2013: data 中的备份和还原要求](lync-server-2013-backup-and-restoration-requirements-data.md)。</span><span class="sxs-lookup"><span data-stu-id="fda0b-106">For information, see [Backup and restoration requirements in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md).</span></span>

<div>

## <a name="migrate-user-settings-to-lync-online"></a><span data-ttu-id="fda0b-107">将用户设置迁移到 Lync Online</span><span class="sxs-lookup"><span data-stu-id="fda0b-107">Migrate User Settings to Lync Online</span></span>

<span data-ttu-id="fda0b-108">用户设置随用户帐户一起移动。</span><span class="sxs-lookup"><span data-stu-id="fda0b-108">User settings are moved with the user account.</span></span> <span data-ttu-id="fda0b-109">一些本地设置不随用户帐户一起移动。</span><span class="sxs-lookup"><span data-stu-id="fda0b-109">Some on-premises settings are not moved with the user account.</span></span>

</div>

<div>

## <a name="moving-pilot-users-to-lync-online"></a><span data-ttu-id="fda0b-110">将试验用户移至 Lync Online</span><span class="sxs-lookup"><span data-stu-id="fda0b-110">Moving Pilot Users to Lync Online</span></span>

<span data-ttu-id="fda0b-111">在开始将用户移动到 Lync Online 之前, 你可能希望移动几个试验用户, 以确认你的环境是否已正确配置。</span><span class="sxs-lookup"><span data-stu-id="fda0b-111">Before you begin to move users to Lync Online, you may want to move a few pilot users to confirm that your environment is correctly configured.</span></span> <span data-ttu-id="fda0b-112">然后, 你可以在尝试移动其他用户之前验证 Lync 功能和服务是否按预期方式工作。</span><span class="sxs-lookup"><span data-stu-id="fda0b-112">You can then verify that Lync features and services function as expected before attempting to move additional users.</span></span>

<span data-ttu-id="fda0b-113">若要将本地用户移动到 Lync Online 租户, 请使用 Microsoft Office 365 租户的管理员凭据在 Lync Server Management Shell 中运行以下 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fda0b-113">To move an on-premises user to your Lync Online tenant, run the following cmdlets in the Lync Server Management Shell, using the administrator credentials for your Microsoft Office 365 tenant.</span></span> <span data-ttu-id="fda0b-114">使用要移动的用户的信息替换“username@contoso.com”。</span><span class="sxs-lookup"><span data-stu-id="fda0b-114">Replace "username@contoso.com" with the information for the user that you want to move.</span></span>

   ```
    $creds=Get-Credential
   ```

   ```
    Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>
   ```

<span data-ttu-id="fda0b-115">为**HostedMigrationOverrideUrl**参数指定的 url 的格式必须是运行托管迁移服务的池的 url, 格式如下: HTTPS://\<池 FQDN/HostedMigration/\>hostedmigrationService。</span><span class="sxs-lookup"><span data-stu-id="fda0b-115">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format: Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc.</span></span>

<span data-ttu-id="fda0b-116">您可以通过查看 Office 365 租户帐户的 Lync Online 控制面板的 URL 来确定托管迁移服务的 URL。</span><span class="sxs-lookup"><span data-stu-id="fda0b-116">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Office 365 tenant account.</span></span>

<span data-ttu-id="fda0b-117">**确定 Office 365 租户的托管迁移服务 URL**</span><span class="sxs-lookup"><span data-stu-id="fda0b-117">**To determine the Hosted Migration Service URL for your Office 365 tenant**</span></span>

1.  <span data-ttu-id="fda0b-118">以管理员身份登录到 Office 365 租户。</span><span class="sxs-lookup"><span data-stu-id="fda0b-118">Login to your Office 365 tenant as an administrator.</span></span>

2.  <span data-ttu-id="fda0b-119">打开**Lync 管理中心**。</span><span class="sxs-lookup"><span data-stu-id="fda0b-119">Open the **Lync admin center**.</span></span>

3.  <span data-ttu-id="fda0b-120">在显示**Lync 管理中心**的情况下, 在地址栏中选择并将 URL 复制到**lync.com**。</span><span class="sxs-lookup"><span data-stu-id="fda0b-120">With the **Lync admin center** displayed, select and copy the URL in the address bar up to **lync.com**.</span></span> <span data-ttu-id="fda0b-121">示例 URL 如下所示：</span><span class="sxs-lookup"><span data-stu-id="fda0b-121">An example URL looks similar to the following:</span></span>
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  <span data-ttu-id="fda0b-122">将 URL 中的 **webdir** 替换为 **admin**，得到以下 URL：</span><span class="sxs-lookup"><span data-stu-id="fda0b-122">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>
    
    `https://admin0a.online.lync.com`

5.  <span data-ttu-id="fda0b-123">向 URL 附加以下字符串：**/HostedMigration/hostedmigrationservice.svc**。</span><span class="sxs-lookup"><span data-stu-id="fda0b-123">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
    
    <span data-ttu-id="fda0b-124">得到的 URL 是 **HostedMigrationOverrideUrl** 的值，应类似于以下形式：</span><span class="sxs-lookup"><span data-stu-id="fda0b-124">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

<div>

## <a name="moving-users-to-lync-online"></a><span data-ttu-id="fda0b-125">将用户移动到 Lync Online</span><span class="sxs-lookup"><span data-stu-id="fda0b-125">Moving Users to Lync Online</span></span>

<span data-ttu-id="fda0b-126">你可以通过使用[move-csuser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet 和– Filter 参数来移动多个用户, 以选择具有分配给用户帐户的特定属性的用户, 如 RegistrarPool。</span><span class="sxs-lookup"><span data-stu-id="fda0b-126">You can move multiple users by using the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet with the –Filter parameter to select the users with a specific property assigned to the user accounts, such as RegistrarPool.</span></span> <span data-ttu-id="fda0b-127">然后, 你可以将返回的用户管道[转到 move-csuser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) cmdlet, 如下例所示。</span><span class="sxs-lookup"><span data-stu-id="fda0b-127">You can then pipe the returned users to the [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) cmdlet, as shown in the following example.</span></span>

    Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>

<span data-ttu-id="fda0b-128">您还可以使用 –OU 参数检索指定 OU 中的所有用户，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="fda0b-128">You can also use the –OU parameter to retrieve all users in the specified OU, as shown in the following example.</span></span>

    Get-CsUser -OU "cn=hybridusers,cn=contoso.." | Move-CsUser -Target sipfed.online.lync.com -Credentials $creds -HostedMigrationOverrideUrl <URL>

</div>

<div>

## <a name="verify-lync-online-user-settings-and-features"></a><span data-ttu-id="fda0b-129">验证 Lync Online 用户设置和功能</span><span class="sxs-lookup"><span data-stu-id="fda0b-129">Verify Lync Online User Settings and Features</span></span>

<span data-ttu-id="fda0b-130">可通过以下方式验证用户是否已成功移动：</span><span class="sxs-lookup"><span data-stu-id="fda0b-130">You can verify that the user was moved successfully in the following ways:</span></span>

  - <span data-ttu-id="fda0b-131">在 Lync Online "控制面板" 中查看用户的状态。</span><span class="sxs-lookup"><span data-stu-id="fda0b-131">View the status of the user in the Lync Online Control Panel.</span></span> <span data-ttu-id="fda0b-132">用于本地用户和联机用户的可视指示器不同。</span><span class="sxs-lookup"><span data-stu-id="fda0b-132">The visual indicator for on-premises users and online users is different.</span></span>

  - <span data-ttu-id="fda0b-133">运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="fda0b-133">Run the following cmdlet:</span></span>
    
        Get-CsUser -Identity

</div>

</div>

<span> </span>

</div>

</div>

</div>

