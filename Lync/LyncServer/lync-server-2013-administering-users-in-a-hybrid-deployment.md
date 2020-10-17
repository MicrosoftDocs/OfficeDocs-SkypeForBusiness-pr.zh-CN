---
title: Lync Server 2013：在混合部署中管理用户
description: Lync Server 2013：在混合部署中管理用户。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Administering users in a hybrid deployment
ms:assetid: 6924ed7b-30a9-4be7-b952-90655625f2c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204967(v=OCS.15)
ms:contentKeyID: 48184381
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f1d7684a9f56eb013574a985ded0313378621c2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552988"
---
# <a name="administering-users-in-a-hybrid-lync-server-2013-deployment"></a><span data-ttu-id="8887f-103">在混合 Lync Server 2013 部署中管理用户</span><span class="sxs-lookup"><span data-stu-id="8887f-103">Administering users in a hybrid Lync Server 2013 deployment</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8887f-104">_**上次修改的主题：** 2014-05-29_</span><span class="sxs-lookup"><span data-stu-id="8887f-104">_**Topic Last Modified:** 2014-05-29_</span></span>

<span data-ttu-id="8887f-105">您可以使用 Microsoft 365 管理中心提供的用户管理功能来管理迁移到 Lync Online 的用户的用户设置和策略。</span><span class="sxs-lookup"><span data-stu-id="8887f-105">You can manage user settings and policies for users migrated to Lync Online by using the User Management features available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="8887f-106">必须使用租户管理员帐户登录才能执行管理任务。</span><span class="sxs-lookup"><span data-stu-id="8887f-106">You must sign in by using your tenant administrator account to perform administration tasks.</span></span>

<div>

## <a name="moving-users-back-to-on-premises"></a><span data-ttu-id="8887f-107">将用户移回本地部署</span><span class="sxs-lookup"><span data-stu-id="8887f-107">Moving Users Back to On-premises</span></span>

<div class="">


> [!IMPORTANT]  
> <span data-ttu-id="8887f-108">此部分仅适用于为本地 Lync 创建和启用的用户，然后将从本地部署移动到 Lync Online。</span><span class="sxs-lookup"><span data-stu-id="8887f-108">This section applies only to users that were created and enabled for Lync on-premises and then moved from an on-premises deployment to Lync Online.</span></span> <span data-ttu-id="8887f-109">如果要移动在 Lync Online 中创建的用户 (并且在本地部署中未启用 Lync) 请参阅在 <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Lync Server 2013 中将用户从 Lync Online 移动到 lync 本地</A>。</span><span class="sxs-lookup"><span data-stu-id="8887f-109">If you want to move users that were created in Lync Online (and not ever enabled for Lync in an on-premises deployment) see, <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Moving users from Lync Online to Lync on-premises in Lync Server 2013</A>.</span></span>



</div>

  - <span data-ttu-id="8887f-110">运行以下 cmdlet 以将用户从 Lync Online 移动回本地 Lync：</span><span class="sxs-lookup"><span data-stu-id="8887f-110">Run the following cmdlets to move a user from Lync Online back to Lync on-premises:</span></span>
    
       ```PowerShell
        $cred=Get-Credential
       ```
    
       ```PowerShell
        Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
       ```

<span data-ttu-id="8887f-111">为 **HostedMigrationOverrideUrl** 参数指定的 url 的格式必须是运行托管迁移服务的池的 url，格式如下：</span><span class="sxs-lookup"><span data-stu-id="8887f-111">The format of the URL specified for the **HostedMigrationOverrideUrl** parameter must be the URL to the pool where the Hosted Migration service is running, in the following format:</span></span>

<span data-ttu-id="8887f-112">Https:// \<Pool FQDN\> /hostedmigration/hostedmigrationservice.svc。</span><span class="sxs-lookup"><span data-stu-id="8887f-112">Https://\<Pool FQDN\>/HostedMigration/hostedmigrationService.svc.</span></span> <span data-ttu-id="8887f-113">您可以通过查看适用于 Microsoft 365 或 Office 365 组织帐户的 Lync Online 控制面板的 URL 来确定托管迁移服务的 URL。</span><span class="sxs-lookup"><span data-stu-id="8887f-113">You can determine the URL to the Hosted Migration Service by viewing the URL for the Lync Online Control Panel for your Microsoft 365 or Office 365 organization account.</span></span>

<span data-ttu-id="8887f-114">**确定 Microsoft 365 或 Office 365 组织的托管迁移服务 URL**</span><span class="sxs-lookup"><span data-stu-id="8887f-114">**To determine the Hosted Migration Service URL for your Microsoft 365 or Office 365 organization**</span></span>

1.  <span data-ttu-id="8887f-115">以管理员身份登录组织。</span><span class="sxs-lookup"><span data-stu-id="8887f-115">Log in to your organization as an administrator.</span></span>

2.  <span data-ttu-id="8887f-116">打开 **Lync 管理中心**。</span><span class="sxs-lookup"><span data-stu-id="8887f-116">Open the **Lync admin center**.</span></span>

3.  <span data-ttu-id="8887f-117">在 " **Lync 管理中心** " 显示的情况下，选择并将地址栏中的 URL 复制到 **lync.com**。</span><span class="sxs-lookup"><span data-stu-id="8887f-117">With the **Lync admin center** displayed, select and copy the URL in the address bar up to **lync.com**.</span></span> <span data-ttu-id="8887f-118">示例 URL 的外观类似于以下内容：</span><span class="sxs-lookup"><span data-stu-id="8887f-118">An example URL looks similar to the following:</span></span>
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  <span data-ttu-id="8887f-119">将 URL 中的 **webdir** 替换为 **admin**，从而产生以下结果：</span><span class="sxs-lookup"><span data-stu-id="8887f-119">Replace **webdir** in the URL with **admin**, resulting in the following:</span></span>
    
    `https://admin0a.online.lync.com`

5.  <span data-ttu-id="8887f-120">将以下字符串追加到 URL： **/HostedMigration/hostedmigrationservice.svc**。</span><span class="sxs-lookup"><span data-stu-id="8887f-120">Append the following string to the URL: **/HostedMigration/hostedmigrationservice.svc**.</span></span>
    
    <span data-ttu-id="8887f-121">生成的 URL （ **HostedMigrationOverrideUrl**的值）应如下所示：</span><span class="sxs-lookup"><span data-stu-id="8887f-121">The resulting URL, which is the value of the **HostedMigrationOverrideUrl**, should look like the following:</span></span>
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

</div>

<span> </span>

</div>

</div>

</div>

