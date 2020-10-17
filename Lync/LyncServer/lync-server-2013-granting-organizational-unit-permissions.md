---
title: Lync Server 2013：授予组织单位权限
description: Lync Server 2013：授予组织单位权限。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting organizational unit permissions
ms:assetid: 95ee5ffa-39b1-4d80-87a2-27bb364f7396
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398763(v=OCS.15)
ms:contentKeyID: 48184849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47ad862241e409190620afa7dbf4fa73adf339de
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554508"
---
# <a name="granting-organizational-unit-permissions-in-lync-server-2013"></a><span data-ttu-id="4239b-103">在 Lync Server 2013 中授予组织单位权限</span><span class="sxs-lookup"><span data-stu-id="4239b-103">Granting organizational unit permissions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4239b-104">_**上次修改的主题：** 2012-05-14_</span><span class="sxs-lookup"><span data-stu-id="4239b-104">_**Topic Last Modified:** 2012-05-14_</span></span>

<span data-ttu-id="4239b-105">您可以使用 **CsOuPermission** cmdlet 向指定组织单位 (ou 中的对象授予权限) 这样，由林准备创建的 RTC 通用组的成员就可以在不是 Domain Admins 组成员的情况下访问这些对象。</span><span class="sxs-lookup"><span data-stu-id="4239b-105">You can use the **Grant-CsOuPermission** cmdlet to grant permissions to objects in specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access them without being members of the Domain Admins group.</span></span> <span data-ttu-id="4239b-106">添加到指定 OU 的权限与 **CsAdDomain** cmdlet 在域准备期间添加到计算机和用户容器的权限相同。</span><span class="sxs-lookup"><span data-stu-id="4239b-106">The permissions added to the specified OU are the same permissions that the **Enable-CsAdDomain** cmdlet adds to the computers and users containers during domain preparation.</span></span>

<span data-ttu-id="4239b-107">使用 **CsOuPermission** cmdlet 可以验证您使用 **CsOuPermission** cmdlet 设置的权限。</span><span class="sxs-lookup"><span data-stu-id="4239b-107">Use the **Test-CsOuPermission** cmdlet to verify the permissions you set up by using the **Grant-CsOuPermission** cmdlet.</span></span>

<span data-ttu-id="4239b-108">您可以使用 **CsOuPermission** cmdlet 删除通过使用 **CsOuPermission** cmdlet 授予的权限。</span><span class="sxs-lookup"><span data-stu-id="4239b-108">You can use the **Revoke-CsOuPermission** cmdlet to remove permissions that you granted by using the **Grant-CsOuPermission** cmdlet.</span></span>

<div>

## <a name="to-grant-ou-permissions"></a><span data-ttu-id="4239b-109">授予 OU 权限</span><span class="sxs-lookup"><span data-stu-id="4239b-109">To grant OU permissions</span></span>

1.  <span data-ttu-id="4239b-110">登录到要在其中授予 OU 权限的域中运行 Lync Server 2013 的计算机。</span><span class="sxs-lookup"><span data-stu-id="4239b-110">Log on to a computer running Lync Server 2013 in the domain where you want to grant OU permissions.</span></span> <span data-ttu-id="4239b-111">如果该 OU 位于不同的子域中，请使用 Domain Admins 组或 Enterprise Admins 组成员的帐户。</span><span class="sxs-lookup"><span data-stu-id="4239b-111">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="4239b-112">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4239b-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="4239b-113">以</span><span class="sxs-lookup"><span data-stu-id="4239b-113">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="4239b-114">如果不指定 Domain 参数，则默认值为本地域。</span><span class="sxs-lookup"><span data-stu-id="4239b-114">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-verify-ou-permissions"></a><span data-ttu-id="4239b-115">验证 OU 权限</span><span class="sxs-lookup"><span data-stu-id="4239b-115">To verify OU permissions</span></span>

1.  <span data-ttu-id="4239b-116">在要验证您使用 **CsOuPermission** cmdlet 授予的 OU 权限的域中，登录到运行 Lync Server 2013 的计算机。</span><span class="sxs-lookup"><span data-stu-id="4239b-116">Log on to a computer running Lync Server 2013 in the domain where you want to verify OU permissions that you granted by using the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="4239b-117">如果该 OU 位于不同的子域中，请使用 Domain Admins 组或 Enterprise Admins 组成员的帐户。</span><span class="sxs-lookup"><span data-stu-id="4239b-117">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="4239b-118">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4239b-118">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="4239b-119">以</span><span class="sxs-lookup"><span data-stu-id="4239b-119">Run:</span></span>
    
        Test-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="4239b-120">如果不指定 Domain 参数，则默认值为本地域。</span><span class="sxs-lookup"><span data-stu-id="4239b-120">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-revoke-ou-permissions"></a><span data-ttu-id="4239b-121">撤消 OU 权限</span><span class="sxs-lookup"><span data-stu-id="4239b-121">To revoke OU permissions</span></span>

1.  <span data-ttu-id="4239b-122">登录到要撤消 **CsOuPermission** cmdlet 授予的 OU 权限的域中运行 Lync Server 2013 的计算机。</span><span class="sxs-lookup"><span data-stu-id="4239b-122">Log on to a computer running Lync Server 2013 in the domain where you want to revoke OU permissions that were granted by the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="4239b-123">如果该 OU 位于不同的子域中，请使用 Domain Admins 组或 Enterprise Admins 组成员的帐户。</span><span class="sxs-lookup"><span data-stu-id="4239b-123">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="4239b-124">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4239b-124">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="4239b-125">以</span><span class="sxs-lookup"><span data-stu-id="4239b-125">Run:</span></span>
    
        Revoke-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="4239b-126">如果不指定 Domain 参数，则默认值为本地域。</span><span class="sxs-lookup"><span data-stu-id="4239b-126">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

