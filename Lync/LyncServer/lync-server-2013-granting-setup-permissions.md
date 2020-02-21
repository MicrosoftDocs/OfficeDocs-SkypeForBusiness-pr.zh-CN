---
title: Lync Server 2013：授予安装程序权限
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
ms.openlocfilehash: 647590131702addb8363b42aaa7d49e299b63a47
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187659"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="granting-setup-permissions-in-lync-server-2013"></a><span data-ttu-id="0f59b-102">在 Lync Server 2013 中授予安装程序权限</span><span class="sxs-lookup"><span data-stu-id="0f59b-102">Granting setup permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f59b-103">_**上次修改的主题：** 2012-08-27_</span><span class="sxs-lookup"><span data-stu-id="0f59b-103">_**Topic Last Modified:** 2012-08-27_</span></span>

<span data-ttu-id="0f59b-104">您可使用 **Grant-CsSetupPermission** cmdlet 为指定 Active Directory 组织单位 (OU) 的 RTCUniversalServerAdmins 组添加读取、写入、ReadSPN 和 WriteSPN 权限。</span><span class="sxs-lookup"><span data-stu-id="0f59b-104">You can use the **Grant-CsSetupPermission** cmdlet to add Read, Write, ReadSPN, and WriteSPN permissions to the RTCUniversalServerAdmins group for a specified Active Directory organizational unit (OU).</span></span> <span data-ttu-id="0f59b-105">然后，该 OU 中的 RTCUniversalServerAdmins 组的成员可以在不是 Domain Admins 组成员的情况下，在指定域中安装运行 Lync Server 2013 的服务器。</span><span class="sxs-lookup"><span data-stu-id="0f59b-105">Then members of the RTCUniversalServerAdmins group in that OU can install servers running Lync Server 2013 in the specified domain without being members of the Domain Admins group.</span></span>

<span data-ttu-id="0f59b-106">使用 **Test-CsSetupPermission** cmdlet 验证您使用 **Grant-CsSetupPermission** cmdlet 设置的权限。</span><span class="sxs-lookup"><span data-stu-id="0f59b-106">Use the **Test-CsSetupPermission** cmdlet to verify the permissions you set up by using the **Grant-CsSetupPermission** cmdlet.</span></span>

<span data-ttu-id="0f59b-107">可以使用 **Revoke-CsSetupPermission** cmdlet 删除您使用 **Grant-CsSetupPermission** cmdlet 授予的权限。</span><span class="sxs-lookup"><span data-stu-id="0f59b-107">You can use the **Revoke-CsSetupPermission** cmdlet to remove permissions that you granted by using the **Grant-CsSetupPermission** cmdlet.</span></span>

<div>

## <a name="to-grant-setup-permissions"></a><span data-ttu-id="0f59b-108">授予安装权限</span><span class="sxs-lookup"><span data-stu-id="0f59b-108">To grant setup permissions</span></span>

1.  <span data-ttu-id="0f59b-109">登录到要在其中授予安装程序权限的域中运行 Lync Server 2013 的计算机。</span><span class="sxs-lookup"><span data-stu-id="0f59b-109">Log on to a computer running Lync Server 2013 in the domain where you want to grant setup permissions.</span></span> <span data-ttu-id="0f59b-110">如果该 OU 位于不同的子域中，请使用 Domain Admins 组或 Enterprise Admins 组成员的帐户。</span><span class="sxs-lookup"><span data-stu-id="0f59b-110">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="0f59b-111">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0f59b-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="0f59b-112">以</span><span class="sxs-lookup"><span data-stu-id="0f59b-112">Run:</span></span>
    
        Grant-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    <span data-ttu-id="0f59b-p103">可以相对于指定域的默认命名上下文指定 ComputerOu 参数（例如，CN=computers）。或者，可以将此参数指定为完整的 OU 可分辨名称 (DN)（例如，“CN=computers,DC=Contoso,DC=com”）。在后一种情况下，必须指定与所指定的域相一致的 OU DN。</span><span class="sxs-lookup"><span data-stu-id="0f59b-p103">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers). Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com"). In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="0f59b-116">如果不指定 Domain 参数，则默认值为本地域。</span><span class="sxs-lookup"><span data-stu-id="0f59b-116">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-verify-setup-permissions"></a><span data-ttu-id="0f59b-117">验证安装权限</span><span class="sxs-lookup"><span data-stu-id="0f59b-117">To verify setup permissions</span></span>

1.  <span data-ttu-id="0f59b-118">在您想要验证您使用**CsSetupPermission** cmdlet 授予的安装程序权限的域中，登录到运行 Lync Server 2013 的计算机。</span><span class="sxs-lookup"><span data-stu-id="0f59b-118">Log on to a computer running Lync Server 2013 in the domain where you want to verify setup permissions that you granted by using the **Grant-CsSetupPermission** cmdlet.</span></span> <span data-ttu-id="0f59b-119">如果该 OU 位于不同的子域中，请使用 Domain Admins 组或 Enterprise Admins 组成员的帐户。</span><span class="sxs-lookup"><span data-stu-id="0f59b-119">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="0f59b-120">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0f59b-120">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="0f59b-121">以</span><span class="sxs-lookup"><span data-stu-id="0f59b-121">Run:</span></span>
    
        Test-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="0f59b-p105">可以相对于指定域的默认命名上下文指定 ComputerOu 参数（例如，CN=computers）。或者，可以将此参数指定为完整的 OU 可分辨名称 (DN)（例如，“CN=computers,DC=Contoso,DC=com”）。在后一种情况下，必须指定与所指定的域相一致的 OU DN。</span><span class="sxs-lookup"><span data-stu-id="0f59b-p105">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers). Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com"). In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="0f59b-125">如果不指定 Domain 参数，则默认值为本地域。</span><span class="sxs-lookup"><span data-stu-id="0f59b-125">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-revoke-setup-permissions"></a><span data-ttu-id="0f59b-126">撤消安装权限</span><span class="sxs-lookup"><span data-stu-id="0f59b-126">To revoke setup permissions</span></span>

1.  <span data-ttu-id="0f59b-127">登录到要吊销**CsSetupPermission** cmdlet 授予的安装程序权限的域中运行 Lync Server 2013 的计算机。</span><span class="sxs-lookup"><span data-stu-id="0f59b-127">Log on to a computer running Lync Server 2013 in the domain where you want to revoke setup permissions that were granted by the **Grant-CsSetupPermission** cmdlet.</span></span> <span data-ttu-id="0f59b-128">如果该 OU 位于不同的子域中，请使用 Domain Admins 组或 Enterprise Admins 组成员的帐户。</span><span class="sxs-lookup"><span data-stu-id="0f59b-128">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="0f59b-129">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0f59b-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="0f59b-130">以</span><span class="sxs-lookup"><span data-stu-id="0f59b-130">Run:</span></span>
    
        Revoke-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    <span data-ttu-id="0f59b-p107">可以相对于指定域的默认命名上下文指定 ComputerOu 参数（例如，CN=computers）。或者，可以将此参数指定为完整的 OU 可分辨名称 (DN)（例如，“CN=computers,DC=Contoso,DC=com”）。在后一种情况下，必须指定与所指定的域相一致的 OU DN。</span><span class="sxs-lookup"><span data-stu-id="0f59b-p107">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers). Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com"). In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="0f59b-134">如果不指定 Domain 参数，则默认值为本地域。</span><span class="sxs-lookup"><span data-stu-id="0f59b-134">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

