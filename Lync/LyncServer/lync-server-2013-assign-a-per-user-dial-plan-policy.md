---
title: Lync Server 2013：分配每个用户的拨号计划策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user dial plan policy
ms:assetid: 9fea861f-7770-4cae-9b1f-2a960595bfc9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688156(v=OCS.15)
ms:contentKeyID: 49733760
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f2bc62981a69b1260ba5f2fbaeabc112553b85f5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722962"
---
# <a name="assign-a-per-user-dial-plan-policy-in-lync-server-2013"></a><span data-ttu-id="d96a9-102">在 Lync Server 2013 中分配每个用户的拨号计划策略</span><span class="sxs-lookup"><span data-stu-id="d96a9-102">Assign a per-user dial plan policy in Lync Server 2013</span></span>

 


<span data-ttu-id="d96a9-103">若要为企业语音的用户和电话拨入式会议的用户完成用户帐户配置，必须为用户分配一个拨号计划。</span><span class="sxs-lookup"><span data-stu-id="d96a9-103">To complete user account configuration for either users of Enterprise Voice or users of dial-in conferencing, the user must be assigned a dial plan.</span></span> <span data-ttu-id="d96a9-104">用户帐户将自动使用全局拨号计划，或者，如果存在，则当你没有明确分配现有的每用户拨号计划时，网站级别的拨号计划将自动使用。</span><span class="sxs-lookup"><span data-stu-id="d96a9-104">User accounts will automatically use the global dial plan or, if one exists, the site-level dial plan when you do not explicitly assign an existing per-user dial plan.</span></span> <span data-ttu-id="d96a9-105">如果要对所有已启用企业语音的用户使用全局或网站拨号计划，则可以跳过此部分。</span><span class="sxs-lookup"><span data-stu-id="d96a9-105">If you want to use the global or site dial plan for all users that are enabled for Enterprise Voice, you can skip this section.</span></span>

## <a name="to-assign-a-dial-plan-by-using-the-lync-server-2013-control-panel"></a><span data-ttu-id="d96a9-106">使用 Lync Server 2013 "控制面板" 分配拨号计划</span><span class="sxs-lookup"><span data-stu-id="d96a9-106">To assign a dial plan by using the Lync Server 2013 Control Panel</span></span>

1.  <span data-ttu-id="d96a9-107">使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="d96a9-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d96a9-108">打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="d96a9-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d96a9-109">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="d96a9-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d96a9-110">在左导航栏中，单击“用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d96a9-110">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="d96a9-111">在“搜索用户”\*\*\*\* 框中，键入要启用的用户帐户的显示名称、名字、姓氏、安全帐户管理器 (SAM) 帐户名、SIP 地址或线路统一资源标识符 (URI) 的全部或第一部分，然后单击“查找”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d96a9-111">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5.  <span data-ttu-id="d96a9-112">在表中，单击要分配拨号计划的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="d96a9-112">In the table, click the user account that you want to assign a dial plan.</span></span>

6.  <span data-ttu-id="d96a9-113">在“编辑”\*\*\*\* 菜单上，单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d96a9-113">On the **Edit** menu, click **Show details**.</span></span>

7.  <span data-ttu-id="d96a9-114">在 "**编辑 Lync Server 用户**" 页面上的 "**电话服务**" 下，单击 "**企业语音**"。</span><span class="sxs-lookup"><span data-stu-id="d96a9-114">On the **Edit Lync Server User** page, under **Telephony**, click **Enterprise Voice**.</span></span>

8.  <span data-ttu-id="d96a9-115">单击 "**拨号计划策略**"，然后选择所需的拨号计划。</span><span class="sxs-lookup"><span data-stu-id="d96a9-115">Click **Dial plan policy**, and then choose the desired dial plan.</span></span>

9.  <span data-ttu-id="d96a9-116">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="d96a9-116">Click **Commit**.</span></span>

<span data-ttu-id="d96a9-117">有关配置拨号计划的详细信息，请参阅[在 Lync Server 2013 中配置拨号计划](lync-server-2013-configuring-dial-plans.md)主题。</span><span class="sxs-lookup"><span data-stu-id="d96a9-117">For details about configuring dial plans, see the [Configuring dial plans in Lync Server 2013](lync-server-2013-configuring-dial-plans.md) topic.</span></span>

## <a name="assign-a-per-user-dial-plan-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d96a9-118">使用 Windows PowerShell Cmdlet 分配每用户拨号计划</span><span class="sxs-lookup"><span data-stu-id="d96a9-118">Assign a Per-User Dial Plan by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="d96a9-119">你可以使用 Windows PowerShell 和**CsdialPlan** cmdlet 分配每用户拨号计划。</span><span class="sxs-lookup"><span data-stu-id="d96a9-119">You can assign per-user dial plans with Windows PowerShell and the **Grant-CsdialPlan** cmdlet.</span></span> <span data-ttu-id="d96a9-120">你可以从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d96a9-120">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="d96a9-121">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="d96a9-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

## <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a><span data-ttu-id="d96a9-122">将每用户拨号计划分配给单个用户</span><span class="sxs-lookup"><span data-stu-id="d96a9-122">To assign a per-user dial plan to a single user</span></span>

  - <span data-ttu-id="d96a9-123">以下命令将每用户拨号计划 RedmondDialPlan 分配给用户 Ken Myer。</span><span class="sxs-lookup"><span data-stu-id="d96a9-123">The following command assigns the per-user dial plan RedmondDialPlan to the user Ken Myer.</span></span>
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"

## <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a><span data-ttu-id="d96a9-124">将每用户拨号计划分配给多个用户</span><span class="sxs-lookup"><span data-stu-id="d96a9-124">To assign a per-user dial plan to multiple users</span></span>

  - <span data-ttu-id="d96a9-125">此命令将每个用户的拨号计划 RedmondDialPlan 分配给在雷蒙德市的所有工作用户。</span><span class="sxs-lookup"><span data-stu-id="d96a9-125">This command assigns the per-user dial plan RedmondDialPlan to all the users who work in the city of Redmond.</span></span> <span data-ttu-id="d96a9-126">有关此命令中使用的 LdapFilter 参数的详细信息，请参阅[move-csuser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) cmdlet 的文档。</span><span class="sxs-lookup"><span data-stu-id="d96a9-126">For more information on the LdapFilter parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"

## <a name="to-unassign-a-per-user-dial-plan"></a><span data-ttu-id="d96a9-127">取消分配每用户拨号计划</span><span class="sxs-lookup"><span data-stu-id="d96a9-127">To unassign a per-user dial plan</span></span>

  - <span data-ttu-id="d96a9-128">以下命令取消之前分配给 Ken Myer 的任何每用户拨号计划。</span><span class="sxs-lookup"><span data-stu-id="d96a9-128">The following command unassigns any per-user dial plan previously assigned to Ken Myer.</span></span> <span data-ttu-id="d96a9-129">未分配每用户拨号计划后，Ken Myer 将通过使用全局拨号计划、本地网站拨号计划（如果有）或分配给其注册机构或 PSTN 网关的服务范围内的拨号计划自动进行管理。</span><span class="sxs-lookup"><span data-stu-id="d96a9-129">After the per-user dial plan is unassigned, Ken Myer will automatically be managed by using the global dial plan, his local site dial plan (if one exists), or the service-scope dial plan assigned to his Registrar or PSTN gateway.</span></span> <span data-ttu-id="d96a9-130">服务范围拨号计划优先于任何网站拨号计划，并且网站拨号计划优先于全局拨号计划。</span><span class="sxs-lookup"><span data-stu-id="d96a9-130">A service scope dial plan takes precedence over any site dial plan, and a site dial plan takes precedence over the global dial plan.</span></span>
    
        Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="d96a9-131">有关详细信息，请参阅[CsDialPlan](https://technet.microsoft.com/en-us/library/gg398547\(v=ocs.15\)) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="d96a9-131">For more information, see the help topic for the [Grant-CsDialPlan](https://technet.microsoft.com/en-us/library/gg398547\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="d96a9-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d96a9-132">See Also</span></span>


[<span data-ttu-id="d96a9-133">在 Lync Server 2013 中配置拨号计划</span><span class="sxs-lookup"><span data-stu-id="d96a9-133">Configuring dial plans in Lync Server 2013</span></span>](lync-server-2013-configuring-dial-plans.md)  
[<span data-ttu-id="d96a9-134">为 Lync Server 2013 启用的用户帐户</span><span class="sxs-lookup"><span data-stu-id="d96a9-134">User accounts enabled for Lync Server 2013</span></span>](lync-server-2013-user-accounts-enabled-for-lync-server.md)

