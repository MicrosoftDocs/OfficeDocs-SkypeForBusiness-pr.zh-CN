---
title: Lync Server 2013：授予组织单位权限
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
ms.openlocfilehash: 945fdfcb6b1f8e8a977bec079b920e13e932e942
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048393"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="granting-organizational-unit-permissions-in-lync-server-2013"></a><span data-ttu-id="81fcc-102">在 Lync Server 2013 中授予组织单位权限</span><span class="sxs-lookup"><span data-stu-id="81fcc-102">Granting organizational unit permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81fcc-103">_**上次修改的主题：** 2012-05-14_</span><span class="sxs-lookup"><span data-stu-id="81fcc-103">_**Topic Last Modified:** 2012-05-14_</span></span>

<span data-ttu-id="81fcc-104">您可以使用**CsOuPermission** cmdlet 向指定组织单位（ou）中的对象授予权限，以便林准备创建的 RTC 通用组的成员可以在不是 Domain Admins 组成员的情况下对其进行访问。</span><span class="sxs-lookup"><span data-stu-id="81fcc-104">You can use the **Grant-CsOuPermission** cmdlet to grant permissions to objects in specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access them without being members of the Domain Admins group.</span></span> <span data-ttu-id="81fcc-105">添加到指定 OU 的权限与**CsAdDomain** cmdlet 在域准备期间添加到计算机和用户容器的权限相同。</span><span class="sxs-lookup"><span data-stu-id="81fcc-105">The permissions added to the specified OU are the same permissions that the **Enable-CsAdDomain** cmdlet adds to the computers and users containers during domain preparation.</span></span>

<span data-ttu-id="81fcc-106">使用**CsOuPermission** cmdlet 可以验证您使用**CsOuPermission** cmdlet 设置的权限。</span><span class="sxs-lookup"><span data-stu-id="81fcc-106">Use the **Test-CsOuPermission** cmdlet to verify the permissions you set up by using the **Grant-CsOuPermission** cmdlet.</span></span>

<span data-ttu-id="81fcc-107">您可以使用**CsOuPermission** cmdlet 删除通过使用**CsOuPermission** cmdlet 授予的权限。</span><span class="sxs-lookup"><span data-stu-id="81fcc-107">You can use the **Revoke-CsOuPermission** cmdlet to remove permissions that you granted by using the **Grant-CsOuPermission** cmdlet.</span></span>

<div>

## <a name="to-grant-ou-permissions"></a><span data-ttu-id="81fcc-108">授予 OU 权限</span><span class="sxs-lookup"><span data-stu-id="81fcc-108">To grant OU permissions</span></span>

1.  <span data-ttu-id="81fcc-109">登录到要在其中授予 OU 权限的域中运行 Lync Server 2013 的计算机。</span><span class="sxs-lookup"><span data-stu-id="81fcc-109">Log on to a computer running Lync Server 2013 in the domain where you want to grant OU permissions.</span></span> <span data-ttu-id="81fcc-110">如果该 OU 位于不同的子域中，请使用 Domain Admins 组或 Enterprise Admins 组成员的帐户。</span><span class="sxs-lookup"><span data-stu-id="81fcc-110">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="81fcc-111">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="81fcc-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="81fcc-112">以</span><span class="sxs-lookup"><span data-stu-id="81fcc-112">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="81fcc-113">如果不指定 Domain 参数，则默认值为本地域。</span><span class="sxs-lookup"><span data-stu-id="81fcc-113">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-verify-ou-permissions"></a><span data-ttu-id="81fcc-114">验证 OU 权限</span><span class="sxs-lookup"><span data-stu-id="81fcc-114">To verify OU permissions</span></span>

1.  <span data-ttu-id="81fcc-115">在要验证您使用**CsOuPermission** cmdlet 授予的 OU 权限的域中，登录到运行 Lync Server 2013 的计算机。</span><span class="sxs-lookup"><span data-stu-id="81fcc-115">Log on to a computer running Lync Server 2013 in the domain where you want to verify OU permissions that you granted by using the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="81fcc-116">如果该 OU 位于不同的子域中，请使用 Domain Admins 组或 Enterprise Admins 组成员的帐户。</span><span class="sxs-lookup"><span data-stu-id="81fcc-116">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="81fcc-117">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="81fcc-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="81fcc-118">以</span><span class="sxs-lookup"><span data-stu-id="81fcc-118">Run:</span></span>
    
        Test-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="81fcc-119">如果不指定 Domain 参数，则默认值为本地域。</span><span class="sxs-lookup"><span data-stu-id="81fcc-119">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-revoke-ou-permissions"></a><span data-ttu-id="81fcc-120">撤消 OU 权限</span><span class="sxs-lookup"><span data-stu-id="81fcc-120">To revoke OU permissions</span></span>

1.  <span data-ttu-id="81fcc-121">登录到要撤消**CsOuPermission** cmdlet 授予的 OU 权限的域中运行 Lync Server 2013 的计算机。</span><span class="sxs-lookup"><span data-stu-id="81fcc-121">Log on to a computer running Lync Server 2013 in the domain where you want to revoke OU permissions that were granted by the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="81fcc-122">如果该 OU 位于不同的子域中，请使用 Domain Admins 组或 Enterprise Admins 组成员的帐户。</span><span class="sxs-lookup"><span data-stu-id="81fcc-122">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="81fcc-123">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="81fcc-123">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="81fcc-124">以</span><span class="sxs-lookup"><span data-stu-id="81fcc-124">Run:</span></span>
    
        Revoke-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="81fcc-125">如果不指定 Domain 参数，则默认值为本地域。</span><span class="sxs-lookup"><span data-stu-id="81fcc-125">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

