---
title: Lync Server 2013：删除现有客户端版本策略规则
description: Lync Server 2013：删除现有客户端版本策略规则。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing client version policy rule
ms:assetid: 2fe351c4-d78b-47d5-af49-d47ee5e0fe42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ923066(v=OCS.15)
ms:contentKeyID: 50675352
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 48cb2dc6458406c988bdc2626fc000c7a9bf5d16
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553648"
---
# <a name="delete-an-existing-client-version-policy-rule-in-lync-server-2013"></a><span data-ttu-id="6343a-103">在 Lync Server 2013 中删除现有客户端版本策略规则</span><span class="sxs-lookup"><span data-stu-id="6343a-103">Delete an existing client version policy rule in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6343a-104">_**上次修改的主题：** 2013-01-21_</span><span class="sxs-lookup"><span data-stu-id="6343a-104">_**Topic Last Modified:** 2013-01-21_</span></span>

<span data-ttu-id="6343a-105">客户端版本策略由一组客户端版本策略规则组成。</span><span class="sxs-lookup"><span data-stu-id="6343a-105">A client version policy is made up of a set of client version policy rules.</span></span> <span data-ttu-id="6343a-106">这些规则定义在用户尝试使用特定客户端和客户端版本登录时应采取的操作。</span><span class="sxs-lookup"><span data-stu-id="6343a-106">These rules define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span> <span data-ttu-id="6343a-107">您可以从 Lync Server 2013 控制面板中删除客户端版本策略中的单个规则。</span><span class="sxs-lookup"><span data-stu-id="6343a-107">You can delete individual rules from a client version policy from Lync Server 2013 Control Panel.</span></span>

<div>

## <a name="to-delete-client-version-policy-rules-with-lync-server-control-panel"></a><span data-ttu-id="6343a-108">使用 Lync Server 控制面板删除客户端版本策略规则</span><span class="sxs-lookup"><span data-stu-id="6343a-108">To delete client version policy rules with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="6343a-109">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="6343a-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="6343a-110">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="6343a-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6343a-111">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="6343a-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6343a-112">在左侧导航栏中，单击 " **客户端**"，然后单击 " **客户端版本策略** 导航" 按钮。</span><span class="sxs-lookup"><span data-stu-id="6343a-112">In the left navigation bar, click **Clients**, and then click the **Client Version Policy** navigation button.</span></span>

4.  <span data-ttu-id="6343a-113">在 " **客户端版本策略** " 页上，双击要删除的规则的客户端版本策略。</span><span class="sxs-lookup"><span data-stu-id="6343a-113">On the **Client Version Policy** page, double-click the client version policy for the rule you want to delete.</span></span>

5.  <span data-ttu-id="6343a-114">这些规则将显示在 " **编辑客户端版本策略** " 页上。</span><span class="sxs-lookup"><span data-stu-id="6343a-114">The rules appear on the **Edit Client Version Policy** page.</span></span> <span data-ttu-id="6343a-115">若要删除规则，请选择该规则，然后单击 " **删除**"。</span><span class="sxs-lookup"><span data-stu-id="6343a-115">To delete a rule, select the rule, and then click **Remove**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

