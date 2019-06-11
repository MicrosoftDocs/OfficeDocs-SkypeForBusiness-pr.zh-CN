---
title: Lync Server 2013：授予组织单位权限
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Granting organizational unit permissions
ms:assetid: 95ee5ffa-39b1-4d80-87a2-27bb364f7396
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398763(v=OCS.15)
ms:contentKeyID: 48184849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c65ff483fbb9c63d4eaca31eca47c9093d229438
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830120"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="granting-organizational-unit-permissions-in-lync-server-2013"></a><span data-ttu-id="41bdc-102">在 Lync Server 2013 中授予组织单位权限</span><span class="sxs-lookup"><span data-stu-id="41bdc-102">Granting organizational unit permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41bdc-103">_**主题上次修改时间:** 2012-05-14_</span><span class="sxs-lookup"><span data-stu-id="41bdc-103">_**Topic Last Modified:** 2012-05-14_</span></span>

<span data-ttu-id="41bdc-104">你可以使用**CsOuPermission** cmdlet 向指定组织单位 (ou) 中的对象授予权限, 以便林准备创建的 RTC 通用组的成员可以访问它们而不是域管理员组的成员.</span><span class="sxs-lookup"><span data-stu-id="41bdc-104">You can use the **Grant-CsOuPermission** cmdlet to grant permissions to objects in specified organizational units (OUs) so that members of the RTC universal groups created by forest preparation can access them without being members of the Domain Admins group.</span></span> <span data-ttu-id="41bdc-105">添加到指定 OU 的权限与**Enable-CsAdDomain** cmdlet 在域准备期间添加到计算机和用户容器的权限相同。</span><span class="sxs-lookup"><span data-stu-id="41bdc-105">The permissions added to the specified OU are the same permissions that the **Enable-CsAdDomain** cmdlet adds to the computers and users containers during domain preparation.</span></span>

<span data-ttu-id="41bdc-106">使用**CsOuPermission** cmdlet 验证你通过使用**CsOuPermission** cmdlet 设置的权限。</span><span class="sxs-lookup"><span data-stu-id="41bdc-106">Use the **Test-CsOuPermission** cmdlet to verify the permissions you set up by using the **Grant-CsOuPermission** cmdlet.</span></span>

<span data-ttu-id="41bdc-107">你可以使用**CsOuPermission** cmdlet 删除你使用**CsOuPermission** cmdlet 授予的权限。</span><span class="sxs-lookup"><span data-stu-id="41bdc-107">You can use the **Revoke-CsOuPermission** cmdlet to remove permissions that you granted by using the **Grant-CsOuPermission** cmdlet.</span></span>

<div>

## <a name="to-grant-ou-permissions"></a><span data-ttu-id="41bdc-108">授予 OU 权限</span><span class="sxs-lookup"><span data-stu-id="41bdc-108">To grant OU permissions</span></span>

1.  <span data-ttu-id="41bdc-109">在要向其授予 OU 权限的域中登录到运行 Lync Server 2013 的计算机。</span><span class="sxs-lookup"><span data-stu-id="41bdc-109">Log on to a computer running Lync Server 2013 in the domain where you want to grant OU permissions.</span></span> <span data-ttu-id="41bdc-110">如果 OU 位于不同的子域中, 请使用作为域管理员组成员或企业管理员组成员的帐户。</span><span class="sxs-lookup"><span data-stu-id="41bdc-110">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="41bdc-111">启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="41bdc-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="41bdc-112">运行：</span><span class="sxs-lookup"><span data-stu-id="41bdc-112">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="41bdc-113">如果不指定 Domain 参数, 则默认值为本地域。</span><span class="sxs-lookup"><span data-stu-id="41bdc-113">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-verify-ou-permissions"></a><span data-ttu-id="41bdc-114">验证 OU 权限</span><span class="sxs-lookup"><span data-stu-id="41bdc-114">To verify OU permissions</span></span>

1.  <span data-ttu-id="41bdc-115">在要验证你使用**CsOuPermission** cmdlet 授予的 OU 权限的域中, 登录到运行 Lync Server 2013 的计算机。</span><span class="sxs-lookup"><span data-stu-id="41bdc-115">Log on to a computer running Lync Server 2013 in the domain where you want to verify OU permissions that you granted by using the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="41bdc-116">如果 OU 位于不同的子域中, 请使用作为域管理员组成员或企业管理员组成员的帐户。</span><span class="sxs-lookup"><span data-stu-id="41bdc-116">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="41bdc-117">启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="41bdc-117">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="41bdc-118">运行：</span><span class="sxs-lookup"><span data-stu-id="41bdc-118">Run:</span></span>
    
        Test-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="41bdc-119">如果不指定 Domain 参数, 则默认值为本地域。</span><span class="sxs-lookup"><span data-stu-id="41bdc-119">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

<div>

## <a name="to-revoke-ou-permissions"></a><span data-ttu-id="41bdc-120">撤消 OU 权限</span><span class="sxs-lookup"><span data-stu-id="41bdc-120">To revoke OU permissions</span></span>

1.  <span data-ttu-id="41bdc-121">在要吊销**CsOuPermission** cmdlet 授予的 OU 权限的域中, 登录到运行 Lync Server 2013 的计算机。</span><span class="sxs-lookup"><span data-stu-id="41bdc-121">Log on to a computer running Lync Server 2013 in the domain where you want to revoke OU permissions that were granted by the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="41bdc-122">如果 OU 位于不同的子域中, 请使用作为域管理员组成员或企业管理员组成员的帐户。</span><span class="sxs-lookup"><span data-stu-id="41bdc-122">Use an account that is a member of the Domain Admins group or the Enterprise Admins group if the OU is in a different child domain.</span></span>

2.  <span data-ttu-id="41bdc-123">启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="41bdc-123">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="41bdc-124">运行：</span><span class="sxs-lookup"><span data-stu-id="41bdc-124">Run:</span></span>
    
        Revoke-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> -OU <DN of the OU> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="41bdc-125">如果不指定 Domain 参数, 则默认值为本地域。</span><span class="sxs-lookup"><span data-stu-id="41bdc-125">If you do not specify the Domain parameter, the default value is the local domain.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

