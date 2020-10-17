---
title: Lync Server 2013：授予安装程序权限
description: Lync Server 2013：授予安装程序权限。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Granting setup permissions
ms:assetid: 15982bfe-6844-44f6-815a-72dcaf0e4d21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398225(v=OCS.15)
ms:contentKeyID: 48183491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5523494219d07907caeefc1bd139c41856effa54
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554478"
---
# <a name="granting-setup-permissions-in-lync-server-2013"></a><span data-ttu-id="cb9e1-103">在 Lync Server 2013 中授予安装程序权限</span><span class="sxs-lookup"><span data-stu-id="cb9e1-103">Granting setup permissions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cb9e1-104">_**上次修改的主题：** 2012-08-27_</span><span class="sxs-lookup"><span data-stu-id="cb9e1-104">_**Topic Last Modified:** 2012-08-27_</span></span>

<span data-ttu-id="cb9e1-105">您可使用 **Grant-CsSetupPermission** cmdlet 为指定 Active Directory 组织单位 (OU) 的 RTCUniversalServerAdmins 组添加读取、写入、ReadSPN 和 WriteSPN 权限。</span><span class="sxs-lookup"><span data-stu-id="cb9e1-105">You can use the **Grant-CsSetupPermission** cmdlet to add Read, Write, ReadSPN, and WriteSPN permissions to the RTCUniversalServerAdmins group for a specified Active Directory organizational unit (OU).</span></span> <span data-ttu-id="cb9e1-106">然后，该 OU 中的 RTCUniversalServerAdmins 组的成员可以在不是 Domain Admins 组成员的情况下，在指定域中安装运行 Lync Server 2013 的服务器。</span><span class="sxs-lookup"><span data-stu-id="cb9e1-106">Then members of the RTCUniversalServerAdmins group in that OU can install servers running Lync Server 2013 in the specified domain without being members of the Domain Admins group.</span></span>

<span data-ttu-id="cb9e1-107">使用 **Test-CsSetupPermission** cmdlet 验证您使用 **Grant-CsSetupPermission** cmdlet 设置的权限。</span><span class="sxs-lookup"><span data-stu-id="cb9e1-107">Use the **Test-CsSetupPermission** cmdlet to verify the permissions you set up by using the **Grant-CsSetupPermission** cmdlet.</span></span>

<span data-ttu-id="cb9e1-108">可以使用 **Revoke-CsSetupPermission** cmdlet 删除您使用 **Grant-CsSetupPermission** cmdlet 授予的权限。</span><span class="sxs-lookup"><span data-stu-id="cb9e1-108">You can use the **Revoke-CsSetupPermission** cmdlet to remove permissions that you granted by using the **Grant-CsSetupPermission** cmdlet.</span></span>

<div>

## <a name="to-grant-setup-permissions"></a><span data-ttu-id="cb9e1-109">授予安装权限</span><span class="sxs-lookup"><span data-stu-id="cb9e1-109">To grant setup permissions</span></span>

1.  <span data-ttu-id="cb9e1-110">登录到要在其中授予安装程序权限的域中运行 Lync Server 2013 的计算机。</span><span class="sxs-lookup"><span data-stu-id="cb9e1-110">Log on to a computer running Lync Server 2013 in the domain where you want to grant setup permissions.</span></span> <span data-ttu-id="cb9e1-111">如果该 OU 位于不同的子域中，请使用 Domain Admins 组或 Enterprise Admins 组成员的帐户。</span><span class="sxs-lookup"><span data-stu-id="cb9e1-111">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="cb9e1-112">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cb9e1-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="cb9e1-113">以</span><span class="sxs-lookup"><span data-stu-id="cb9e1-113">Run:</span></span>
    
        Grant-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    <span data-ttu-id="cb9e1-p103">可以相对于指定域的默认命名上下文指定 ComputerOu 参数（例如，CN=computers）。或者，可以将此参数指定为完整的 OU 可分辨名称 (DN)（例如，“CN=computers,DC=Contoso,DC=com”）。在后一种情况下，必须指定与所指定的域相一致的 OU DN。</span><span class="sxs-lookup"><span data-stu-id="cb9e1-p103">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers). Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com"). In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="cb9e1-117">如果不指定 Domain 参数，则默认值为本地域。</span><span class="sxs-lookup"><span data-stu-id="cb9e1-117">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-verify-setup-permissions"></a><span data-ttu-id="cb9e1-118">验证安装权限</span><span class="sxs-lookup"><span data-stu-id="cb9e1-118">To verify setup permissions</span></span>

1.  <span data-ttu-id="cb9e1-119">在您想要验证您使用 **CsSetupPermission** cmdlet 授予的安装程序权限的域中，登录到运行 Lync Server 2013 的计算机。</span><span class="sxs-lookup"><span data-stu-id="cb9e1-119">Log on to a computer running Lync Server 2013 in the domain where you want to verify setup permissions that you granted by using the **Grant-CsSetupPermission** cmdlet.</span></span> <span data-ttu-id="cb9e1-120">如果该 OU 位于不同的子域中，请使用 Domain Admins 组或 Enterprise Admins 组成员的帐户。</span><span class="sxs-lookup"><span data-stu-id="cb9e1-120">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="cb9e1-121">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cb9e1-121">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="cb9e1-122">以</span><span class="sxs-lookup"><span data-stu-id="cb9e1-122">Run:</span></span>
    
        Test-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="cb9e1-p105">可以相对于指定域的默认命名上下文指定 ComputerOu 参数（例如，CN=computers）。或者，可以将此参数指定为完整的 OU 可分辨名称 (DN)（例如，“CN=computers,DC=Contoso,DC=com”）。在后一种情况下，必须指定与所指定的域相一致的 OU DN。</span><span class="sxs-lookup"><span data-stu-id="cb9e1-p105">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers). Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com"). In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="cb9e1-126">如果不指定 Domain 参数，则默认值为本地域。</span><span class="sxs-lookup"><span data-stu-id="cb9e1-126">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-revoke-setup-permissions"></a><span data-ttu-id="cb9e1-127">撤消安装权限</span><span class="sxs-lookup"><span data-stu-id="cb9e1-127">To revoke setup permissions</span></span>

1.  <span data-ttu-id="cb9e1-128">登录到要吊销 **CsSetupPermission** cmdlet 授予的安装程序权限的域中运行 Lync Server 2013 的计算机。</span><span class="sxs-lookup"><span data-stu-id="cb9e1-128">Log on to a computer running Lync Server 2013 in the domain where you want to revoke setup permissions that were granted by the **Grant-CsSetupPermission** cmdlet.</span></span> <span data-ttu-id="cb9e1-129">如果该 OU 位于不同的子域中，请使用 Domain Admins 组或 Enterprise Admins 组成员的帐户。</span><span class="sxs-lookup"><span data-stu-id="cb9e1-129">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="cb9e1-130">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cb9e1-130">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="cb9e1-131">以</span><span class="sxs-lookup"><span data-stu-id="cb9e1-131">Run:</span></span>
    
        Revoke-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    <span data-ttu-id="cb9e1-p107">可以相对于指定域的默认命名上下文指定 ComputerOu 参数（例如，CN=computers）。或者，可以将此参数指定为完整的 OU 可分辨名称 (DN)（例如，“CN=computers,DC=Contoso,DC=com”）。在后一种情况下，必须指定与所指定的域相一致的 OU DN。</span><span class="sxs-lookup"><span data-stu-id="cb9e1-p107">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers). Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com"). In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="cb9e1-135">如果不指定 Domain 参数，则默认值为本地域。</span><span class="sxs-lookup"><span data-stu-id="cb9e1-135">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

