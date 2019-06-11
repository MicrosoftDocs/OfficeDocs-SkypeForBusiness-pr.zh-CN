---
title: Lync Server 2013：授予安装权限
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Granting setup permissions
ms:assetid: 15982bfe-6844-44f6-815a-72dcaf0e4d21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398225(v=OCS.15)
ms:contentKeyID: 48183491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 751ec9ba024780344596bfc0513c15f7e9eafec7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830118"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="granting-setup-permissions-in-lync-server-2013"></a><span data-ttu-id="5a99d-102">在 Lync Server 2013 中授予安装权限</span><span class="sxs-lookup"><span data-stu-id="5a99d-102">Granting setup permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5a99d-103">_**主题上次修改时间:** 2012-08-27_</span><span class="sxs-lookup"><span data-stu-id="5a99d-103">_**Topic Last Modified:** 2012-08-27_</span></span>

<span data-ttu-id="5a99d-104">你可以使用**CsSetupPermission** cmdlet 向指定的 Active Directory 组织单位 (OU) 的 RTCUniversalServerAdmins 组添加读取、写入、ReadSPN 和 WriteSPN 权限。</span><span class="sxs-lookup"><span data-stu-id="5a99d-104">You can use the **Grant-CsSetupPermission** cmdlet to add Read, Write, ReadSPN, and WriteSPN permissions to the RTCUniversalServerAdmins group for a specified Active Directory organizational unit (OU).</span></span> <span data-ttu-id="5a99d-105">然后, 该 OU 中的 RTCUniversalServerAdmins 组的成员可以在指定域中安装运行 Lync Server 2013 的服务器, 而不是域管理员组的成员。</span><span class="sxs-lookup"><span data-stu-id="5a99d-105">Then members of the RTCUniversalServerAdmins group in that OU can install servers running Lync Server 2013 in the specified domain without being members of the Domain Admins group.</span></span>

<span data-ttu-id="5a99d-106">使用**CsSetupPermission** cmdlet 验证你通过使用**CsSetupPermission** cmdlet 设置的权限。</span><span class="sxs-lookup"><span data-stu-id="5a99d-106">Use the **Test-CsSetupPermission** cmdlet to verify the permissions you set up by using the **Grant-CsSetupPermission** cmdlet.</span></span>

<span data-ttu-id="5a99d-107">你可以使用**CsSetupPermission** cmdlet 删除你使用**CsSetupPermission** cmdlet 授予的权限。</span><span class="sxs-lookup"><span data-stu-id="5a99d-107">You can use the **Revoke-CsSetupPermission** cmdlet to remove permissions that you granted by using the **Grant-CsSetupPermission** cmdlet.</span></span>

<div>

## <a name="to-grant-setup-permissions"></a><span data-ttu-id="5a99d-108">授予设置权限</span><span class="sxs-lookup"><span data-stu-id="5a99d-108">To grant setup permissions</span></span>

1.  <span data-ttu-id="5a99d-109">在要授予设置权限的域中登录到运行 Lync Server 2013 的计算机。</span><span class="sxs-lookup"><span data-stu-id="5a99d-109">Log on to a computer running Lync Server 2013 in the domain where you want to grant setup permissions.</span></span> <span data-ttu-id="5a99d-110">如果 OU 位于不同的子域中, 请使用作为域管理员组成员或企业管理员组成员的帐户。</span><span class="sxs-lookup"><span data-stu-id="5a99d-110">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="5a99d-111">启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="5a99d-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="5a99d-112">运行：</span><span class="sxs-lookup"><span data-stu-id="5a99d-112">Run:</span></span>
    
        Grant-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    <span data-ttu-id="5a99d-113">你可以将 ComputerOu 参数指定为相对于指定域的默认命名上下文 (例如, CN = 计算机)。</span><span class="sxs-lookup"><span data-stu-id="5a99d-113">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers).</span></span> <span data-ttu-id="5a99d-114">或者, 你可以将此参数指定为完整的 OU 可分辨名称 (DN) (例如, "CN = 计算机, DC = Contoso, DC = com")。</span><span class="sxs-lookup"><span data-stu-id="5a99d-114">Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com").</span></span> <span data-ttu-id="5a99d-115">在后一种情况下, 你必须指定与你指定的域一致的 OU DN。</span><span class="sxs-lookup"><span data-stu-id="5a99d-115">In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="5a99d-116">如果不指定 Domain 参数, 则默认值为本地域。</span><span class="sxs-lookup"><span data-stu-id="5a99d-116">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-verify-setup-permissions"></a><span data-ttu-id="5a99d-117">验证设置权限</span><span class="sxs-lookup"><span data-stu-id="5a99d-117">To verify setup permissions</span></span>

1.  <span data-ttu-id="5a99d-118">在要验证使用**CsSetupPermission** cmdlet 授予的设置权限的域中, 登录到运行 Lync Server 2013 的计算机。</span><span class="sxs-lookup"><span data-stu-id="5a99d-118">Log on to a computer running Lync Server 2013 in the domain where you want to verify setup permissions that you granted by using the **Grant-CsSetupPermission** cmdlet.</span></span> <span data-ttu-id="5a99d-119">如果 OU 位于不同的子域中, 请使用作为域管理员组成员或企业管理员组成员的帐户。</span><span class="sxs-lookup"><span data-stu-id="5a99d-119">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="5a99d-120">启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="5a99d-120">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="5a99d-121">运行：</span><span class="sxs-lookup"><span data-stu-id="5a99d-121">Run:</span></span>
    
        Test-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="5a99d-122">你可以将 ComputerOu 参数指定为相对于指定域的默认命名上下文 (例如, CN = 计算机)。</span><span class="sxs-lookup"><span data-stu-id="5a99d-122">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers).</span></span> <span data-ttu-id="5a99d-123">或者, 你可以将此参数指定为完整的 OU 可分辨名称 (DN) (例如, "CN = 计算机, DC = Contoso, DC = com")。</span><span class="sxs-lookup"><span data-stu-id="5a99d-123">Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com").</span></span> <span data-ttu-id="5a99d-124">在后一种情况下, 你必须指定与你指定的域一致的 OU DN。</span><span class="sxs-lookup"><span data-stu-id="5a99d-124">In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="5a99d-125">如果不指定 Domain 参数, 则默认值为本地域。</span><span class="sxs-lookup"><span data-stu-id="5a99d-125">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-revoke-setup-permissions"></a><span data-ttu-id="5a99d-126">撤销设置权限</span><span class="sxs-lookup"><span data-stu-id="5a99d-126">To revoke setup permissions</span></span>

1.  <span data-ttu-id="5a99d-127">在要吊销**CsSetupPermission** cmdlet 授予的设置权限的域中, 登录到运行 Lync Server 2013 的计算机。</span><span class="sxs-lookup"><span data-stu-id="5a99d-127">Log on to a computer running Lync Server 2013 in the domain where you want to revoke setup permissions that were granted by the **Grant-CsSetupPermission** cmdlet.</span></span> <span data-ttu-id="5a99d-128">如果 OU 位于不同的子域中, 请使用作为域管理员组成员或企业管理员组成员的帐户。</span><span class="sxs-lookup"><span data-stu-id="5a99d-128">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="5a99d-129">启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="5a99d-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="5a99d-130">运行：</span><span class="sxs-lookup"><span data-stu-id="5a99d-130">Run:</span></span>
    
        Revoke-CsSetupPermission -ComputerOu <DN of the OU or container where the computer objects that will run Lync Server reside > [-Domain <Domain FQDN>]
    
    <span data-ttu-id="5a99d-131">你可以将 ComputerOu 参数指定为相对于指定域的默认命名上下文 (例如, CN = 计算机)。</span><span class="sxs-lookup"><span data-stu-id="5a99d-131">You can specify the ComputerOu parameter as relative to the default naming context of the specified domain (for example, CN=computers).</span></span> <span data-ttu-id="5a99d-132">或者, 你可以将此参数指定为完整的 OU 可分辨名称 (DN) (例如, "CN = 计算机, DC = Contoso, DC = com")。</span><span class="sxs-lookup"><span data-stu-id="5a99d-132">Alternatively, you can specify this parameter as the full OU distinguished name (DN) (for example, "CN=computers,DC=Contoso,DC=com").</span></span> <span data-ttu-id="5a99d-133">在后一种情况下, 你必须指定与你指定的域一致的 OU DN。</span><span class="sxs-lookup"><span data-stu-id="5a99d-133">In the latter case, you must specify an OU DN that is consistent with the domain you specify.</span></span>
    
    <span data-ttu-id="5a99d-134">如果不指定 Domain 参数, 则默认值为本地域。</span><span class="sxs-lookup"><span data-stu-id="5a99d-134">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

