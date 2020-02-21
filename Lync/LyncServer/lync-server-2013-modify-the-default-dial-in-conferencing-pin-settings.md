---
title: Lync Server 2013：修改默认电话拨入式会议 PIN 设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify the default dial-in conferencing PIN settings
ms:assetid: 2d110e94-ad29-4755-b17f-d8c2da9b78a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425780(v=OCS.15)
ms:contentKeyID: 48183712
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 086273f7326e5dc95862080d1635cec94d8ac499
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217288"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="modify-the-default-dial-in-conferencing-pin-settings-in-lync-server-2013"></a><span data-ttu-id="cdece-102">在 Lync Server 2013 中修改默认电话拨入式会议 PIN 设置</span><span class="sxs-lookup"><span data-stu-id="cdece-102">Modify the default dial-in conferencing PIN settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cdece-103">_**上次修改的主题：** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="cdece-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="cdece-104">全局 PIN 策略在林级别定义电话拨入式会议 PIN 的规则。</span><span class="sxs-lookup"><span data-stu-id="cdece-104">The global PIN policy defines the rules for dial-in conferencing PINs at the forest level.</span></span> <span data-ttu-id="cdece-105">按照以下步骤修改全局电话拨入式会议 PIN 策略。</span><span class="sxs-lookup"><span data-stu-id="cdece-105">Follow these steps to modify the global dial-in conferencing PIN policy.</span></span> <span data-ttu-id="cdece-106">有关在站点或用户级别创建或修改电话拨入式会议 PIN 策略的详细信息，请参阅[在 Lync Server 2013 for a site or users 组中创建或修改电话拨入式会议 pin 设置](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md)。</span><span class="sxs-lookup"><span data-stu-id="cdece-106">For details about creating or modifying a dial-in conferencing PIN policy at the site or user level, see [Create or modify dial-in conferencing PIN settings in Lync Server 2013 for a site or group of users](lync-server-2013-create-or-modify-dial-in-conferencing-pin-settings-for-a-site-or-group-of-users.md).</span></span>

<div>

## <a name="to-modify-the-global-pin-policy"></a><span data-ttu-id="cdece-107">修改全局 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="cdece-107">To modify the global PIN policy</span></span>

1.  <span data-ttu-id="cdece-108">从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户，登录到您在其中部署了 Lync Server 2013 的网络中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="cdece-108">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="cdece-109">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="cdece-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="cdece-110">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="cdece-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="cdece-111">在左侧导航栏中，单击“会议”\*\*\*\*，然后单击“PIN 策略”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cdece-111">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>

4.  <span data-ttu-id="cdece-112">在“PIN 策略”\*\*\*\* 页上，单击“全局”\*\*\*\* 策略，再单击“编辑”\*\*\*\*，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cdece-112">On the **PIN Policy** page, click the **Global** policy, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="cdece-p103">在“编辑 PIN 策略”\*\*\*\* 的“最小 PIN 长度”\*\*\*\* 中，键入或选择希望允许的最小 PIN 长度。默认的最小长度为 5 位数。</span><span class="sxs-lookup"><span data-stu-id="cdece-p103">In **Edit PIN Policy**, in **Minimum PIN length**, type or select the minimum PIN length that you want to allow. The default minimum length is five digits.</span></span>

6.  <span data-ttu-id="cdece-p104">为了能够指定锁定用户前允许的最大登录尝试次数，请选中“指定最大登录尝试数”\*\*\*\* 复选框。如果未选择此选项，允许的最大尝试次数将根据 PIN 长度自动确定。默认情况下，最大尝试次数自动确定。</span><span class="sxs-lookup"><span data-stu-id="cdece-p104">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>

7.  <span data-ttu-id="cdece-118">如果选中了“指定最大登录尝试数”\*\*\*\* 复选框，请在“最大登录尝试次数”\*\*\*\* 中键入或选择希望允许的最大登录尝试次数。</span><span class="sxs-lookup"><span data-stu-id="cdece-118">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>

8.  <span data-ttu-id="cdece-p105">要使 PIN 过期，请选中“启用 PIN 有效期”\*\*\*\* 复选框。如果未选择此选项，PIN 将永不过期。默认情况下，PIN 永不过期。</span><span class="sxs-lookup"><span data-stu-id="cdece-p105">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>

9.  <span data-ttu-id="cdece-122">如果选中了“启用 PIN 有效期”\*\*\*\* 复选框，请在“PIN 有效期(天)”\*\*\*\* 中键入或选择 PIN 保持有效的天数。</span><span class="sxs-lookup"><span data-stu-id="cdece-122">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>

10. <span data-ttu-id="cdece-p106">在“PIN 历史记录计数”\*\*\*\* 中，键入用户可以重复使用某个 PIN 之前，必须创建的 PIN 数目。默认情况下，用户可以重复使用其 PIN。</span><span class="sxs-lookup"><span data-stu-id="cdece-p106">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>

11. <span data-ttu-id="cdece-p107">要允许在 PIN 中使用数字的通用模式，如连续数字和重复数字集，请选中“允许通用模式”\*\*\*\* 复选框。如果未选择此选项，则仅允许使用数字的复杂模式。默认情况下，仅允许使用数字的复杂模式。</span><span class="sxs-lookup"><span data-stu-id="cdece-p107">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box. If you do not select this option, only complex patterns of digits are allowed. By default, only complex patterns of digits are allowed.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="cdece-128">我们建议您不要允许使用通用模式。</span><span class="sxs-lookup"><span data-stu-id="cdece-128">We recommend that you do not allow common patterns.</span></span>

    
    </div>

12. <span data-ttu-id="cdece-129">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="cdece-129">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

