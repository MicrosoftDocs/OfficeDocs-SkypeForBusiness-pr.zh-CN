---
title: Lync Server 2013：创建或修改网站或用户组的电话拨入式会议 PIN 设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify dial-in conferencing PIN settings for a site or group of users
ms:assetid: c29bab5c-2b93-48e0-ae0b-29564daaff9a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412959(v=OCS.15)
ms:contentKeyID: 48185326
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b65d62514cabe64381fc002e4c7242c9a782acb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151754"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-dial-in-conferencing-pin-settings-in-lync-server-2013-for-a-site-or-group-of-users"></a><span data-ttu-id="afc6d-102">在 Lync Server 2013 中为一个站点或一组用户创建或修改电话拨入式会议 PIN 设置</span><span class="sxs-lookup"><span data-stu-id="afc6d-102">Create or modify dial-in conferencing PIN settings in Lync Server 2013 for a site or group of users</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="afc6d-103">_**上次修改的主题：** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="afc6d-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="afc6d-104">按照以下步骤创建或修改用户级别或站点级别电话拨入式会议的个人标识号 (PIN) 策略。</span><span class="sxs-lookup"><span data-stu-id="afc6d-104">Follow these steps to create or modify a user-level or a site-level dial-in conferencing personal identification number (PIN) policy.</span></span> <span data-ttu-id="afc6d-105">有关如何更改全局 PIN 策略的详细信息，请参阅[在 Lync Server 2013 中修改默认电话拨入式会议 PIN 设置](lync-server-2013-modify-the-default-dial-in-conferencing-pin-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="afc6d-105">For details about how to change the global PIN policy, see [Modify the default dial-in conferencing PIN settings in Lync Server 2013](lync-server-2013-modify-the-default-dial-in-conferencing-pin-settings.md).</span></span>

<div>

## <a name="to-create-a-user-or-site-pin-policy"></a><span data-ttu-id="afc6d-106">创建用户或站点 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="afc6d-106">To create a user or site PIN policy</span></span>

1.  <span data-ttu-id="afc6d-107">从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户，登录到您在其中部署了 Lync Server 2013 的网络中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="afc6d-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="afc6d-108">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="afc6d-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="afc6d-109">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="afc6d-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="afc6d-110">在左侧导航栏中，单击“会议”\*\*\*\*，然后单击“PIN 策略”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="afc6d-110">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>

4.  <span data-ttu-id="afc6d-111">在“PIN 策略”\*\*\*\* 页上，单击“新建”\*\*\*\*，然后执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="afc6d-111">On the **PIN Policy** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="afc6d-p103">要创建用户级别的策略，请单击“用户策略”\*\*\*\*。在“新建 PIN 策略”\*\*\*\* 的“名称”\*\*\*\* 中，键入描述该策略的名称。</span><span class="sxs-lookup"><span data-stu-id="afc6d-p103">To create a user-level policy, click **User policy**. In **New PIN Policy**, in **Name**, type a name that describes the policy.</span></span>
    
      - <span data-ttu-id="afc6d-p104">要创建站点级别的策略，请单击“站点策略”\*\*\*\*。在“选择站点”\*\*\*\* 搜索字段中，键入要为其创建策略的站点的全部或部分名称。在站点列表中，单击所需的站点，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="afc6d-p104">To create a site-level policy, click **Site policy**. In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy. In the list of sites, click the site you want, and then click **OK**.</span></span>

5.  <span data-ttu-id="afc6d-117">在“说明”\*\*\*\* 字段中，键入 PIN 策略的说明。</span><span class="sxs-lookup"><span data-stu-id="afc6d-117">In the **Description** field, type a description of the PIN policy.</span></span>

6.  <span data-ttu-id="afc6d-p105">在“最小 PIN 长度”\*\*\*\* 字段中，键入或选择希望允许的最小 PIN 长度。默认的最小长度为 5 位数。</span><span class="sxs-lookup"><span data-stu-id="afc6d-p105">In the **Minimum PIN length** field, type or select the minimum PIN length that you want to allow. The default minimum length is five digits.</span></span>

7.  <span data-ttu-id="afc6d-p106">为了能够指定锁定用户前允许的最大登录尝试次数，请选中“指定最大登录尝试数”\*\*\*\* 复选框。如果未选择此选项，允许的最大尝试次数将根据 PIN 长度自动确定。默认情况下，最大尝试次数自动确定。</span><span class="sxs-lookup"><span data-stu-id="afc6d-p106">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>

8.  <span data-ttu-id="afc6d-123">如果选中了“指定最大登录尝试数”\*\*\*\* 复选框，请在“最大登录尝试次数”\*\*\*\* 中键入或选择希望允许的最大登录尝试次数。</span><span class="sxs-lookup"><span data-stu-id="afc6d-123">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>

9.  <span data-ttu-id="afc6d-p107">要使 PIN 过期，请选中“启用 PIN 有效期”\*\*\*\* 复选框。如果未选择此选项，PIN 将永不过期。默认情况下，PIN 永不过期。</span><span class="sxs-lookup"><span data-stu-id="afc6d-p107">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>

10. <span data-ttu-id="afc6d-127">如果选中了“启用 PIN 有效期”\*\*\*\* 复选框，请在“PIN 有效期(天)”\*\*\*\* 中键入或选择 PIN 保持有效的天数。</span><span class="sxs-lookup"><span data-stu-id="afc6d-127">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>

11. <span data-ttu-id="afc6d-p108">在“PIN 历史记录计数”\*\*\*\* 中，键入用户可以重复使用某个 PIN 之前，必须创建的 PIN 数目。默认情况下，用户可以重复使用其 PIN。</span><span class="sxs-lookup"><span data-stu-id="afc6d-p108">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>

12. <span data-ttu-id="afc6d-p109">要允许在 PIN 中使用数字的通用模式，如连续数字和重复数字集，请选中“允许通用模式”\*\*\*\* 复选框。如果未选择此选项，则仅允许使用数字的复杂模式。默认情况下，仅允许使用数字的复杂模式。</span><span class="sxs-lookup"><span data-stu-id="afc6d-p109">To allow common patterns of digits in PINs, such as sequential numbers and repetitive sets of numbers, select the **Allow common patterns** check box. If you do not select this option, only complex patterns of digits are allowed. By default, only complex patterns of digits are allowed.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="afc6d-133">我们建议您不要允许使用通用模式。</span><span class="sxs-lookup"><span data-stu-id="afc6d-133">We recommend that you do not allow common patterns.</span></span>

    
    </div>

13. <span data-ttu-id="afc6d-134">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="afc6d-134">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-change-a-user-or-site-pin-policy"></a><span data-ttu-id="afc6d-135">更改用户或站点 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="afc6d-135">To change a user or site PIN policy</span></span>

1.  <span data-ttu-id="afc6d-136">从作为 RTCUniversalServerAdmins 组成员的用户帐户（或具有等效的用户权限）或分配给 CsServerAdministrator 或 CsAdministrator 角色的用户，登录到您在其中部署了 Lync Server 2013 的网络中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="afc6d-136">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="afc6d-137">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="afc6d-137">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="afc6d-138">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="afc6d-138">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="afc6d-139">在左侧导航栏中，单击“会议”\*\*\*\*，然后单击“PIN 策略”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="afc6d-139">In the left navigation bar, click **Conferencing**, and then click **PIN Policy**.</span></span>

4.  <span data-ttu-id="afc6d-140">在“PIN 策略”\*\*\*\* 页上，单击要更改的 PIN 策略，再单击“编辑”\*\*\*\*，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="afc6d-140">On the **PIN Policy** page, click the PIN policy that you want to change, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="afc6d-141">在“编辑 PIN 策略”\*\*\*\* 中，修改任意策略设置（不能修改的策略名称除外）。</span><span class="sxs-lookup"><span data-stu-id="afc6d-141">In **Edit PIN Policy**, modify any of the policy settings (except for the policy name, which cannot be modified).</span></span>

6.  <span data-ttu-id="afc6d-142">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="afc6d-142">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

