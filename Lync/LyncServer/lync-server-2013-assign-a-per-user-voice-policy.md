---
title: Lync Server 2013：分配每用户语音策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user voice policy
ms:assetid: 9ee47ee7-1030-43b8-a4dc-bf685ea24659
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688155(v=OCS.15)
ms:contentKeyID: 49733758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1528ef6124193023a0e5938caac7b40c2c6187a2
ms.sourcegitcommit: 9b1c138b39fd87e239a7b1c5051f30c633e7d813
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/01/2020
ms.locfileid: "44943925"
---
# <a name="assign-a-per-user-voice-policy-in-lync-server-2013"></a><span data-ttu-id="2e99b-102">在 Lync Server 2013 中分配每用户语音策略</span><span class="sxs-lookup"><span data-stu-id="2e99b-102">Assign a per-user voice policy in Lync Server 2013</span></span>

 


<span data-ttu-id="2e99b-103">全局和网站级语音策略将自动分配给为企业语音启用的所有 Lync Server 2013 用户帐户。</span><span class="sxs-lookup"><span data-stu-id="2e99b-103">Global and site-level voice policies are automatically assigned to all Lync Server 2013 user accounts that are enabled for Enterprise Voice.</span></span> <span data-ttu-id="2e99b-104">您还可以使用 Lync Server 2013 控制面板或 Lync Server 2013 命令行管理程序将语音策略分配给特定用户。</span><span class="sxs-lookup"><span data-stu-id="2e99b-104">You can also assign voice policies to specific users by using either the Lync Server 2013 Control Panel or the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="2e99b-105">使用本主题中的过程将每个用户策略明确分配给 Lync Server 用户。</span><span class="sxs-lookup"><span data-stu-id="2e99b-105">Use the procedures in this topic to explicitly assign per-user policies to Lync Server users.</span></span>

## <a name="to-assign-a-user-specific-voice-policy-using-the-lync-server-control-panel"></a><span data-ttu-id="2e99b-106">使用 Lync Server 控制面板分配特定于用户的语音策略</span><span class="sxs-lookup"><span data-stu-id="2e99b-106">To assign a user-specific voice policy using the Lync Server Control Panel</span></span>

1.  <span data-ttu-id="2e99b-107">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="2e99b-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2e99b-108">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="2e99b-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2e99b-109">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="2e99b-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2e99b-110">在左侧导航栏中，单击“用户”\*\*\*\*，然后搜索要配置的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="2e99b-110">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="2e99b-111">在列出搜索结果的表中，单击相应的用户帐户，再单击“编辑”\*\*\*\*，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2e99b-111">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="2e99b-112">在“编辑 Lync Server 用户”\*\*\*\* 中的“语音策略”\*\*\*\* 下，选择要应用的用户策略。</span><span class="sxs-lookup"><span data-stu-id="2e99b-112">In **Edit Lync Server User** under **Voice policy**, select the user policy that you want to apply.</span></span>
    

    > [!NOTE]  
    > <span data-ttu-id="2e99b-113">" <STRONG> &lt; 自动 &gt; </STRONG> " 设置将应用默认服务器或全局策略设置。</span><span class="sxs-lookup"><span data-stu-id="2e99b-113">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server or global policy settings.</span></span>



## <a name="assign-per-user-voice-policies"></a><span data-ttu-id="2e99b-114">分配每用户语音策略</span><span class="sxs-lookup"><span data-stu-id="2e99b-114">Assign per-user voice policies</span></span>

<span data-ttu-id="2e99b-115">您可以使用 Windows PowerShell 和**set-csvoicepolicy** cmdlet 分配每用户语音策略。</span><span class="sxs-lookup"><span data-stu-id="2e99b-115">You can assign per-user voice policies by using Windows PowerShell and the **Grant-CsVoicePolicy** cmdlet.</span></span> <span data-ttu-id="2e99b-116">您可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2e99b-116">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="2e99b-117">若要了解如何使用远程 Windows PowerShell 连接到 Lync Server，请阅读此 Lync Server Windows PowerShell 博客文章：[快速入门：使用远程 PowerShell 管理 Microsoft Lync server 2010](https://go.microsoft.com/fwlink/p/?linkId=255876)。</span><span class="sxs-lookup"><span data-stu-id="2e99b-117">To learn about using remote Windows PowerShell to connect to Lync Server, read this Lync Server Windows PowerShell blog post: [Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span>

### <a name="assign-a-per-user-voice-policy-to-a-single-user"></a><span data-ttu-id="2e99b-118">为单个用户分配每用户语音策略</span><span class="sxs-lookup"><span data-stu-id="2e99b-118">Assign a per-user voice policy to a single user</span></span>

  - <span data-ttu-id="2e99b-119">以下命令向用户 Ken Myer 分配每用户语音策略 RedmondVoicePolicy。</span><span class="sxs-lookup"><span data-stu-id="2e99b-119">The following command assigns the per-user voice policy RedmondVoicePolicy to the user Ken Myer.</span></span>
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

## <a name="assign-a-per-user-voice-policy-to-multiple-users"></a><span data-ttu-id="2e99b-120">为多个用户分配每用户语音策略</span><span class="sxs-lookup"><span data-stu-id="2e99b-120">Assign a per-user voice policy to multiple users</span></span>

  - <span data-ttu-id="2e99b-121">此命令向在 Active Directory 的 Finance OU 中拥有帐户的所有用户分配每用户语音策略 FinanceVoicePolicy。</span><span class="sxs-lookup"><span data-stu-id="2e99b-121">This command assigns the per-user voice policy FinanceVoicePolicy to all the users who have accounts in the Finance OU in Active Directory.</span></span> <span data-ttu-id="2e99b-122">有关此命令中使用的 OU 参数的详细信息，请参阅[get-csuser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet 的相关文档。</span><span class="sxs-lookup"><span data-stu-id="2e99b-122">For more information on the OU parameter used in this command, see the documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) cmdlet.</span></span>
    
        Get-CsUser -OU "ou=Finance,ou=North America,dc=litwareinc,dc=com" | Grant-CsVoicePolicy -PolicyName "FinanceVoicePolicy"

## <a name="unassign-a-per-user-voice-policy"></a><span data-ttu-id="2e99b-123">取消分配每用户语音策略</span><span class="sxs-lookup"><span data-stu-id="2e99b-123">Unassign a per-user voice policy</span></span>

  - <span data-ttu-id="2e99b-p105">以下命令取消分配之前为 Ken Myer 分配的任何每用户语音策略。在取消分配每用户策略后，将自动使用全局策略或本地站点策略（如果有）管理 Ken Myer。站点策略优先于全局策略。</span><span class="sxs-lookup"><span data-stu-id="2e99b-p105">The following command unassigns any per-user voice policy previously assigned to Ken Myer. After the per-user policy is unassigned, Ken Myer will automatically be managed by using the global policy or, if one exists, his local site policy. A site policy takes precedence over the global policy.</span></span>
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName $Null

<span data-ttu-id="2e99b-127">有关详细信息，请参阅[set-csvoicepolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\)) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="2e99b-127">For more information, see the help topic for the [Grant-CsVoicePolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\)) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="2e99b-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2e99b-128">See Also</span></span>


[<span data-ttu-id="2e99b-129">在 Lync Server 2013 中禁用用户的企业语音</span><span class="sxs-lookup"><span data-stu-id="2e99b-129">Disable a user for Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-disable-a-user-for-enterprise-voice.md)  


[<span data-ttu-id="2e99b-130">Lync Server 2013 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="2e99b-130">Lync Server 2013 Management Shell</span></span>](lync-server-2013-lync-server-management-shell.md)

