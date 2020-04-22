---
title: Lync Server 2013：将用户移动到 Lync Online
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move users to Lync Online
ms:assetid: 6a523c86-2eac-4fa4-973a-4406872c9a7d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204969(v=OCS.15)
ms:contentKeyID: 48184392
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5106d4e27921d9407b2663410cc0872892479ebb
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779849"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-users-to-lync-online-in-lync-server-2013"></a><span data-ttu-id="54926-102">在 Lync Server 2013 中将用户移动到 Lync Online</span><span class="sxs-lookup"><span data-stu-id="54926-102">Move users to Lync Online in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54926-103">_**上次修改的主题：** 2014-05-29_</span><span class="sxs-lookup"><span data-stu-id="54926-103">_**Topic Last Modified:** 2014-05-29_</span></span>

<span data-ttu-id="54926-104">在开始将用户迁移到 Lync Online 之前，应备份与要移动的帐户关联的用户数据。</span><span class="sxs-lookup"><span data-stu-id="54926-104">Before you start migrating users to Lync Online, you should backup the user data associated with the accounts to be moved.</span></span> <span data-ttu-id="54926-105">并不是所有用户数据都与用户帐户一起移动。</span><span class="sxs-lookup"><span data-stu-id="54926-105">Not all user data is moved with the user account.</span></span> <span data-ttu-id="54926-106">有关信息，请参阅[Lync Server 2013： data 中的备份和还原要求](lync-server-2013-backup-and-restoration-requirements-data.md)。</span><span class="sxs-lookup"><span data-stu-id="54926-106">For information, see [Backup and restoration requirements in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md).</span></span>

<div>

## <a name="migrate-user-settings-to-lync-online"></a><span data-ttu-id="54926-107">将用户设置迁移至 Lync Online</span><span class="sxs-lookup"><span data-stu-id="54926-107">Migrate User Settings to Lync Online</span></span>

<span data-ttu-id="54926-108">用户设置随用户帐户一起移动。</span><span class="sxs-lookup"><span data-stu-id="54926-108">User settings are moved with the user account.</span></span> <span data-ttu-id="54926-109">某些本地设置不会随用户帐户一起移动。</span><span class="sxs-lookup"><span data-stu-id="54926-109">Some on-premises settings are not moved with the user account.</span></span>

</div>

<div>

## <a name="moving-pilot-users-to-lync-online"></a><span data-ttu-id="54926-110">将试点用户移动到 Lync Online</span><span class="sxs-lookup"><span data-stu-id="54926-110">Moving Pilot Users to Lync Online</span></span>

<span data-ttu-id="54926-111">在开始将用户移动到 Lync Online 之前，您可能需要移动几个试点用户，以确认您的环境已正确配置。</span><span class="sxs-lookup"><span data-stu-id="54926-111">Before you begin to move users to Lync Online, you may want to move a few pilot users to confirm that your environment is correctly configured.</span></span> <span data-ttu-id="54926-112">然后，您可以在尝试移动其他用户之前验证 Lync 功能和服务是否按预期方式运行。</span><span class="sxs-lookup"><span data-stu-id="54926-112">You can then verify that Lync features and services function as expected before attempting to move additional users.</span></span>

<span data-ttu-id="54926-113">若要将本地用户移动到 Lync Online 租户，请使用 Microsoft Office 365 组织的管理员凭据在 Lync Server 命令行管理程序中运行以下 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="54926-113">To move an on-premises user to your Lync Online tenant, run the following cmdlets in the Lync Server Management Shell, using the administrator credentials for your Microsoft Office 365 organization.</span></span> <span data-ttu-id="54926-114">将 "username@contoso.com" 替换为要移动的用户的信息。</span><span class="sxs-lookup"><span data-stu-id="54926-114">Replace "username@contoso.com" with the information for the user that you want to move.</span></span>

   ```PowerShell
    $creds=Get-Credential
   ```

   ```PowerShell
    Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>
   ```

<span data-ttu-id="54926-115">为**HostedMigrationOverrideUrl**参数指定的 url 的格式必须是运行托管迁移服务的池的 url，格式如下： HTTPS://\<池 FQDN/hostedmigration/hostedmigrationservice.svc。\></span><span class="sxs-lookup"><span data-stu-id="54926-115">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format: Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc.</span></span>

<span data-ttu-id="54926-116">您可以通过查看 Office 365 组织帐户的 Lync Online 控制面板的 URL 来确定托管迁移服务的 URL。</span><span class="sxs-lookup"><span data-stu-id="54926-116">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Office 365 organization account.</span></span>

<span data-ttu-id="54926-117">**确定 Office 365 组织的托管迁移服务 URL**</span><span class="sxs-lookup"><span data-stu-id="54926-117">**To determine the Hosted Migration Service URL for your Office 365 organization**</span></span>

1.  <span data-ttu-id="54926-118">以管理员身份登录到 Office 365 组织。</span><span class="sxs-lookup"><span data-stu-id="54926-118">Login to your Office 365 organization as an administrator.</span></span>

2.  <span data-ttu-id="54926-119">打开**Lync 管理中心**。</span><span class="sxs-lookup"><span data-stu-id="54926-119">Open the **Lync admin center**.</span></span>

3.  <span data-ttu-id="54926-120">在 " **Lync 管理中心**" 显示的情况下，选择并将地址栏中的 URL 复制到**lync.com**。</span><span class="sxs-lookup"><span data-stu-id="54926-120">With the **Lync admin center** displayed, select and copy the URL in the address bar up to **lync.com**.</span></span> <span data-ttu-id="54926-121">示例 URL 的外观类似于以下内容：</span><span class="sxs-lookup"><span data-stu-id="54926-121">An example URL looks similar to the following:</span></span>
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  <span data-ttu-id="54926-122">将 URL 中的**webdir**替换为**admin**，从而产生以下结果：</span><span class="sxs-lookup"><span data-stu-id="54926-122">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>
    
    `https://admin0a.online.lync.com`

5.  <span data-ttu-id="54926-123">将以下字符串追加到 URL： **/HostedMigration/hostedmigrationservice.svc**。</span><span class="sxs-lookup"><span data-stu-id="54926-123">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
    
    <span data-ttu-id="54926-124">生成的 URL （ **HostedMigrationOverrideUrl**的值）应如下所示：</span><span class="sxs-lookup"><span data-stu-id="54926-124">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

<div>

## <a name="moving-users-to-lync-online"></a><span data-ttu-id="54926-125">将用户移动到 Lync Online</span><span class="sxs-lookup"><span data-stu-id="54926-125">Moving Users to Lync Online</span></span>

<span data-ttu-id="54926-126">您可以使用带有– Filter 参数的[get-csuser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet 来移动多个用户，以选择具有分配给用户帐户的特定属性的用户，如 RegistrarPool。</span><span class="sxs-lookup"><span data-stu-id="54926-126">You can move multiple users by using the [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) cmdlet with the –Filter parameter to select the users with a specific property assigned to the user accounts, such as RegistrarPool.</span></span> <span data-ttu-id="54926-127">然后，您可以通过管道将返回的用户通过管道传递到[get-csuser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) cmdlet，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="54926-127">You can then pipe the returned users to the [Move-CsUser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) cmdlet, as shown in the following example.</span></span>

    Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>

<span data-ttu-id="54926-128">您还可以使用– OU 参数检索指定 OU 中的所有用户，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="54926-128">You can also use the –OU parameter to retrieve all users in the specified OU, as shown in the following example.</span></span>

    Get-CsUser -OU "cn=hybridusers,cn=contoso.." | Move-CsUser -Target sipfed.online.lync.com -Credentials $creds -HostedMigrationOverrideUrl <URL>

</div>

<div>

## <a name="verify-lync-online-user-settings-and-features"></a><span data-ttu-id="54926-129">验证 Lync Online 用户设置和功能</span><span class="sxs-lookup"><span data-stu-id="54926-129">Verify Lync Online User Settings and Features</span></span>

<span data-ttu-id="54926-130">可通过以下方式验证用户是否已成功移动：</span><span class="sxs-lookup"><span data-stu-id="54926-130">You can verify that the user was moved successfully in the following ways:</span></span>

  - <span data-ttu-id="54926-p107">在 Lync Online 控制面板中查看用户的状态。用于内部用户和联机用户的可视指示器不同。</span><span class="sxs-lookup"><span data-stu-id="54926-p107">View the status of the user in the Lync Online Control Panel. The visual indicator for on-premises users and online users is different.</span></span>

  - <span data-ttu-id="54926-133">运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="54926-133">Run the following cmdlet:</span></span>
    
        Get-CsUser -Identity

</div>

</div>

<span> </span>

</div>

</div>

</div>

