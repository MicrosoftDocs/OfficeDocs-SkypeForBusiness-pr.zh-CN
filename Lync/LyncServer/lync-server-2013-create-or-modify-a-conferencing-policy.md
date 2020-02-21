---
title: Lync Server 2013：创建或修改会议策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a conferencing policy
ms:assetid: e2974030-2c0a-4634-91e8-93f4e2d674d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721910(v=OCS.15)
ms:contentKeyID: 49733844
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 522f1d1240e73775ae1f0976556b882ba00fe1d3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180069"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-conferencing-policy-in-lync-server-2013"></a><span data-ttu-id="1d022-102">在 Lync Server 2013 中创建或修改会议策略</span><span class="sxs-lookup"><span data-stu-id="1d022-102">Create or modify a conferencing policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1d022-103">_**上次修改的主题：** 2013-02-07_</span><span class="sxs-lookup"><span data-stu-id="1d022-103">_**Topic Last Modified:** 2013-02-07_</span></span>

<span data-ttu-id="1d022-104">按照以下步骤创建用户级别或站点级别会议策略。</span><span class="sxs-lookup"><span data-stu-id="1d022-104">Follow these steps to create a user-level or a site-level conferencing policy.</span></span> <span data-ttu-id="1d022-105">有关如何向用户分配用户级别策略的详细信息，请参阅[在 Lync Server 2013 中分配每用户会议策略](lync-server-2013-assign-a-per-user-conferencing-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="1d022-105">For details about how to assign a user-level policy to a user, see [Assign a per-user conferencing policy in Lync Server 2013](lync-server-2013-assign-a-per-user-conferencing-policy.md).</span></span> <span data-ttu-id="1d022-106">有关所有可用会议策略设置的列表，请参阅[Lync Server 2013 的会议策略设置参考](lync-server-2013-conferencing-policy-settings-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="1d022-106">For a list of all available conferencing policy settings, see [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span></span>

<div>

## <a name="to-create-a-new-user-or-site-policy"></a><span data-ttu-id="1d022-107">创建新的用户或站点策略</span><span class="sxs-lookup"><span data-stu-id="1d022-107">To create a new user or site policy</span></span>

1.  <span data-ttu-id="1d022-108">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="1d022-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1d022-109">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="1d022-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1d022-110">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="1d022-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1d022-111">在左侧导航栏中，单击“会议”\*\*\*\*，然后单击“会议策略”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1d022-111">In the left navigation bar, click **Conferencing** and then click **Conferencing Policy**.</span></span>

4.  <span data-ttu-id="1d022-112">单击“新建”\*\*\*\*，然后执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="1d022-112">Click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="1d022-p103">要创建用户级别的策略，请单击“用户策略”\*\*\*\*。在“新建会议策略”\*\*\*\* 中的“名称”\*\*\*\* 字段，键入策略的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="1d022-p103">To create a user-level policy, click **User policy**. In **New Conferencing Policy**, in **Name**, type a descriptive name for the policy.</span></span>
    
      - <span data-ttu-id="1d022-p104">要创建站点级别的策略，请单击“站点策略”\*\*\*\*。在“选择站点”\*\*\*\* 搜索字段中，键入要为其创建策略的站点的全部或部分名称。在站点列表中，单击所需的站点，然后单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1d022-p104">To create a site-level policy, click **Site policy**. In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy. In the list of sites, click the site that you want, and then click **OK**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="1d022-118">站点名称将成为会议策略名称，且无法更改。</span><span class="sxs-lookup"><span data-stu-id="1d022-118">The site name becomes the conferencing policy name, and it cannot be changed.</span></span>

        
        </div>

5.  <span data-ttu-id="1d022-119">在“说明”\*\*\*\* 中，键入策略的说明。</span><span class="sxs-lookup"><span data-stu-id="1d022-119">In **Description**, type a description for the policy.</span></span>

6.  <span data-ttu-id="1d022-p105">在“组织者策略”\*\*\*\* 下的“最大会议大小”\*\*\*\* 中，键入允许参加一次会议的最大用户数。默认情况下，最大会议大小为 250。</span><span class="sxs-lookup"><span data-stu-id="1d022-p105">Under **Organizer policy**, in **Maximum meeting size**, type the maximum number of users that you want to allow at a meeting. By default, the maximum meeting size is 250.</span></span>

7.  <span data-ttu-id="1d022-122">要阻止用户邀请匿名用户参加会议，请清除 **“允许参与者邀请匿名用户”** 复选框。</span><span class="sxs-lookup"><span data-stu-id="1d022-122">To prevent users from inviting anonymous users to meetings, clear the **Allow participants to invite anonymous users** check box.</span></span> <span data-ttu-id="1d022-123">匿名用户是在组织的 Active Directory 域服务中没有凭据的用户，因此未经过身份验证的用户。</span><span class="sxs-lookup"><span data-stu-id="1d022-123">Anonymous users are users who do not have credentials in your organization’s Active Directory Domain Services and who, therefore, are not authenticated.</span></span> <span data-ttu-id="1d022-124">默认情况下，用户可以邀请匿名用户参加会议。</span><span class="sxs-lookup"><span data-stu-id="1d022-124">By default, users can invite anonymous users to meetings.</span></span>

8.  <span data-ttu-id="1d022-125">在 **“录制”** 中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="1d022-125">In **Recording**, do one of the following:</span></span>
    
      - <span data-ttu-id="1d022-p107">要阻止参与者录制会议，请单击 **“无”**。这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="1d022-p107">To prevent participants from recording meetings, click **None**. This is the default setting.</span></span>
    
      - <span data-ttu-id="1d022-128">要允许参与者录制会议，请单击 **“启用录制”**。</span><span class="sxs-lookup"><span data-stu-id="1d022-128">To allow participants to record meetings, click **Enable recording**.</span></span>

9.  <span data-ttu-id="1d022-p108">要允许外部参与者录制会议，请选中 **“允许联盟参与者和匿名参与者录制”** 复选框。默认为阻止外部参与者录制会议。</span><span class="sxs-lookup"><span data-stu-id="1d022-p108">To allow external participants to record meetings, select the **Allow federated and anonymous participants to record** check box. The default is to prevent external participants from recording meetings.</span></span>

10. <span data-ttu-id="1d022-131">在 **“音频/视频”** 中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="1d022-131">In **Audio/video**, do one of the following:</span></span>
    
      - <span data-ttu-id="1d022-132">要阻止使用音频和视频，请单击 **“无”**。</span><span class="sxs-lookup"><span data-stu-id="1d022-132">To prevent the use of audio and video, click **None**.</span></span>
    
      - <span data-ttu-id="1d022-133">要允许使用音频但不允许使用视频，请单击 **“启用 IP 音频”**。</span><span class="sxs-lookup"><span data-stu-id="1d022-133">To allow the use of audio but not video, click **Enable IP audio**.</span></span>
    
      - <span data-ttu-id="1d022-p109">要允许使用音频和视频，请单击 **“启用 IP 音频/视频”**。这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="1d022-p109">To allow the use of audio and video, click **Enable IP audio/video**. This is the default setting.</span></span>

11. <span data-ttu-id="1d022-136">如果在 **“音频/视频”** 中选择允许使用音频，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="1d022-136">If you chose to allow the use of audio in **Audio/video**, do the following:</span></span>
    
      - <span data-ttu-id="1d022-p110">要阻止用户通过电话拨入加入会议，请清除 **“启用 PSTN 电话拨入式会议”** 复选框。默认情况下，用户可以通过使用公用电话交换网 (PSTN) 进行电话拨入来加入会议。</span><span class="sxs-lookup"><span data-stu-id="1d022-p110">To prevent users from joining the meeting by dialing in, clear the **Enable PSTN dial-in conferencing** check box. By default, users can dial in to meetings by using the public switched telephone network (PSTN).</span></span>
    
      - <span data-ttu-id="1d022-p111">如果您允许用户通过电话拨入加入会议并允许未经身份验证的（匿名）用户通过拨出式电话加入会议，请选中“允许匿名参与者拨出”\*\*\*\* 复选框。通过拨出式电话，会议服务器会呼叫用户，用户接听电话即可加入会议。默认情况下，匿名用户无法通过拨出式电话加入会议。</span><span class="sxs-lookup"><span data-stu-id="1d022-p111">If you allow users to dial in to meetings and you want to allow unauthenticated (anonymous) users to join a meeting by using dial out phoning, select the **Allow anonymous participants to dial out** check box. With dial-out phoning, the conference server calls the user, and the user answers the phone to join the meeting. By default, anonymous users cannot join a meeting by using dial-out phoning.</span></span>

12. <span data-ttu-id="1d022-142">如果您选择允许使用“音频/视频”\*\*\*\* 中的视频，请选中“允许多个视频流”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1d022-142">If you chose to allow the use of video in **Audio/video**, check **Allow multiple video streams** .</span></span>

13. <span data-ttu-id="1d022-143">在“数据协作”\*\*\*\* 中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="1d022-143">In **Data collaboration**, do one of the following:</span></span>
    
      - <span data-ttu-id="1d022-144">要阻止数据协作，请单击 **“无”**。</span><span class="sxs-lookup"><span data-stu-id="1d022-144">To prevent data collaboration, click **None**.</span></span>
    
      - <span data-ttu-id="1d022-p112">要允许数据协作，请单击 **“启用数据协作”**。这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="1d022-p112">To allow data collaboration, click **Enable data collaboration**. This is the default setting.</span></span>

14. <span data-ttu-id="1d022-147">如果在 **“数据协作”** 中选择允许数据协作，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="1d022-147">If you chose to allow data collaboration in **Data collaboration**, do the following:</span></span>
    
      - <span data-ttu-id="1d022-p113">要阻止外部下载，请清除 **“允许联盟参与者和匿名参与者下载内容”** 复选框。默认情况下，外部用户可以下载内容。</span><span class="sxs-lookup"><span data-stu-id="1d022-p113">To prevent external downloads, clear the **Allow federated and anonymous participants to download content** check box. By default, external users can download content.</span></span>
    
      - <span data-ttu-id="1d022-p114">要阻止文件传输，请清除“允许参与者传输文件”\*\*\*\* 复选框。默认情况下，用户可以传输文件。</span><span class="sxs-lookup"><span data-stu-id="1d022-p114">To prevent file transfers, clear the **Allow participants to transfer files** check box. By default, users can transfer files.</span></span>
    
      - <span data-ttu-id="1d022-p115">要阻止使用批注，请清除“启用批注”\*\*\*\* 复选框。要使用共享的 PowerPoint 演示文稿中的批注，请清除“启用 PowerPoint 批注”\*\*\*\*。默认情况下，允许使用批注。</span><span class="sxs-lookup"><span data-stu-id="1d022-p115">To prevent the use of annotations, clear the **Enable annotations** check box. To the use of annotations in shard PowerPoint presentations, clear the **Enable PowerPoint annotations**. By default, annotations are allowed.</span></span>
    
      - <span data-ttu-id="1d022-p116">要阻止使用投票，请清除“启用投票”\*\*\*\* 复选框。默认情况下，允许使用投票。</span><span class="sxs-lookup"><span data-stu-id="1d022-p116">To prevent the use of polls, clear the **Enable polls** check box. By default, polls are allowed.</span></span>

15. <span data-ttu-id="1d022-157">在 **“应用程序共享”** 中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="1d022-157">In **Application sharing**, do one of the following:</span></span>
    
      - <span data-ttu-id="1d022-158">要阻止使用应用程序共享，请单击 **“禁用应用程序共享”**。</span><span class="sxs-lookup"><span data-stu-id="1d022-158">To prevent the use of application sharing, click **Disable application sharing**.</span></span>
    
      - <span data-ttu-id="1d022-p117">要允许使用应用程序共享，请单击 **“启用应用程序共享”**。这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="1d022-p117">To allow the use of application sharing, click **Enable application sharing**. This is the default setting.</span></span>

16. <span data-ttu-id="1d022-161">如果在 **“应用程序共享”** 中选择允许应用程序共享，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="1d022-161">If you chose to allow application sharing in **Application sharing**, do the following:</span></span>
    
      - <span data-ttu-id="1d022-p118">要阻止会议参与者控制应用程序共享，请清除 **“允许参与者获得控制权”** 复选框。默认情况下，参与者可以控制应用程序共享。</span><span class="sxs-lookup"><span data-stu-id="1d022-p118">To prevent meeting participants from taking control of application sharing, clear the **Allow participants to take control** check box. By default, participants can take control of application sharing.</span></span>
    
      - <span data-ttu-id="1d022-p119">如果选择允许会议参与者控制应用程序共享，请选中 **“允许联盟参与者和匿名参与者获得控制权”** 复选框以允许外部用户控制应用程序共享。默认情况下，外部用户不能控制应用程序共享。</span><span class="sxs-lookup"><span data-stu-id="1d022-p119">If you chose to allow meeting participants to take control of application sharing, select the **Allow federated and anonymous participants to take control** check box to allow external users to take control of application sharing. By default, external users cannot take control of application sharing.</span></span>

17. <span data-ttu-id="1d022-166">在 **“参与者策略”** 下，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="1d022-166">Under **Participant policy**, do one of the following:</span></span>
    
      - <span data-ttu-id="1d022-167">要同时阻止应用程序共享和桌面共享，请单击 **“禁用应用程序共享和桌面共享”**。</span><span class="sxs-lookup"><span data-stu-id="1d022-167">To prevent both application sharing and desktop sharing, click **Disable application and desktop sharing**.</span></span>
    
      - <span data-ttu-id="1d022-168">要允许应用程序共享但不允许桌面共享，请单击 **“启用应用程序共享”**。</span><span class="sxs-lookup"><span data-stu-id="1d022-168">To allow application sharing but not desktop sharing, click **Enable application sharing**.</span></span>
    
      - <span data-ttu-id="1d022-p120">要同时允许应用程序共享和桌面共享，请单击 **“启用应用程序共享和桌面共享”**。这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="1d022-p120">To allow both application sharing and desktop sharing, click **Enable application and desktop sharing**. This is the default setting.</span></span>

18. <span data-ttu-id="1d022-p121">要阻止对等文件传输，请清除 **“启用对等文件传输”** 复选框。默认情况下，允许对等文件传输。</span><span class="sxs-lookup"><span data-stu-id="1d022-p121">To prevent peer-to-peer file transfers, clear the **Enable peer-to-peer file transfer** check box. By default, peer-to-peer file transfers are allowed.</span></span>

19. <span data-ttu-id="1d022-p122">要允许对等录制，请选中“启用对等录制”\*\*\*\* 复选框。默认情况下，不允许对等录制。</span><span class="sxs-lookup"><span data-stu-id="1d022-p122">To allow peer-to-peer recording, select the **Enable peer-to-peer recording** check box. By default, peer-to-peer recording is not allowed.</span></span>

20. <span data-ttu-id="1d022-p123">要允许参与者加入多个视频流，请选中“允许参与者加入多个视频流”\*\*\*\* 复选框，默认情况下，允许多个视频流。</span><span class="sxs-lookup"><span data-stu-id="1d022-p123">To allow participants to join with multiple video streams, select the **Enable participants to join with multiple video streams** check box. By default, multiple video streams are allowed.</span></span>

21. <span data-ttu-id="1d022-177">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1d022-177">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-an-existing-user-or-site-policy"></a><span data-ttu-id="1d022-178">修改现有用户或站点策略</span><span class="sxs-lookup"><span data-stu-id="1d022-178">To modify an existing user or site policy</span></span>

1.  <span data-ttu-id="1d022-179">使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="1d022-179">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1d022-180">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="1d022-180">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1d022-181">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="1d022-181">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1d022-182">在左侧导航栏中，单击“会议”\*\*\*\*，然后单击“会议策略”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1d022-182">In the left navigation bar, click **Conferencing** and then click **Conferencing Policy**.</span></span>

4.  <span data-ttu-id="1d022-183">在会议策略列表中，单击要更改的策略，单击“编辑”\*\*\*\*，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1d022-183">In the list of conferencing policies, click the policy that you want to change, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="1d022-184">在“编辑会议策略”\*\*\*\* 中，修改任意策略设置（不能修改的策略名称除外）。</span><span class="sxs-lookup"><span data-stu-id="1d022-184">In **Edit Conferencing Policy**, modify any of the policy settings, except for the policy name, which cannot be modified.</span></span>

6.  <span data-ttu-id="1d022-185">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1d022-185">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

