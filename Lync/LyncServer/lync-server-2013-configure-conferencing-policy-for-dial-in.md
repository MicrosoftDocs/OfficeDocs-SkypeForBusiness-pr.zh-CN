---
title: Lync Server 2013：配置电话拨入式会议策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure conferencing policy for dial-in
ms:assetid: 9bf926d6-0248-4352-98c3-9c5a333debbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398810(v=OCS.15)
ms:contentKeyID: 48184979
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56faf9cb55312beec0714eb84757d92989b1b3ad
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028653"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-conferencing-policy-for-dial-in-in-lync-server-2013"></a><span data-ttu-id="bcc77-102">在 Lync Server 2013 中配置电话拨入式会议策略</span><span class="sxs-lookup"><span data-stu-id="bcc77-102">Configure conferencing policy for dial-in in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bcc77-103">_**上次修改的主题：** 2014-03-21_</span><span class="sxs-lookup"><span data-stu-id="bcc77-103">_**Topic Last Modified:** 2014-03-21_</span></span>

<span data-ttu-id="bcc77-p101">会议策略是一种用户帐户设置，用于指定参与者的会议体验。您可以创建具有站点作用域或用户作用域的会议策略。会议策略设置包含会议安排和参与会议的多个方面。一些会议策略设置支持参与者参加电话拨入式会议。当您配置电话拨入式会议时，应该确认已针对组织正确设置了这些字段，并根据需要进行修改。</span><span class="sxs-lookup"><span data-stu-id="bcc77-p101">Conferencing policy is a user account setting that specifies the conferencing experience for participants. You can create conferencing policies with a site scope or a user scope. Conferencing policy settings encompass many aspects of conference scheduling and participation. Several conferencing policy settings support dial-in conferencing for participants. When you configure dial-in conferencing, you should verify that these fields are set appropriately for your organization, and modify them as necessary.</span></span>

<span data-ttu-id="bcc77-109">请验证会议策略中的下列字段：</span><span class="sxs-lookup"><span data-stu-id="bcc77-109">Verify the following fields in your conferencing policy:</span></span>

  - <span data-ttu-id="bcc77-110">**允许参与者邀请匿名用户**   此设置允许会议组织者将匿名（即未经身份验证）参与者邀请参加会议。</span><span class="sxs-lookup"><span data-stu-id="bcc77-110">**Allow participants to invite anonymous users**   This setting allows meeting organizers to invite anonymous (that is, unauthenticated) participants to meetings.</span></span> <span data-ttu-id="bcc77-111">对于电话拨入式会议，此设置是可选的。</span><span class="sxs-lookup"><span data-stu-id="bcc77-111">This setting is optional for dial-in conferencing.</span></span> <span data-ttu-id="bcc77-112">默认情况下，此设置在默认全局会议策略中处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="bcc77-112">This setting is selected by default in the default global conferencing policy.</span></span>

  - <span data-ttu-id="bcc77-113">**启用 PSTN 电话拨入式会议**   此设置允许用户通过从 PSTN 拨入来加入会议的音频部分。</span><span class="sxs-lookup"><span data-stu-id="bcc77-113">**Enable PSTN dial-in conferencing**   This setting allows users to join the audio portion of a conference by dialing in from the PSTN.</span></span> <span data-ttu-id="bcc77-114">电话拨入式会议需要此设置。</span><span class="sxs-lookup"><span data-stu-id="bcc77-114">This setting is required for dial-in conferencing.</span></span> <span data-ttu-id="bcc77-115">默认情况下，此设置在默认全局会议策略中处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="bcc77-115">This setting is selected by default in the default global conferencing policy.</span></span>

  - <span data-ttu-id="bcc77-116">**允许匿名参与者拨出**   此设置允许已加入会议的匿名用户拨出到电话号码，以加入会议的音频部分。</span><span class="sxs-lookup"><span data-stu-id="bcc77-116">**Allow anonymous participants to dial out**   This setting allows anonymous users who are already joined to the meeting to dial out to a phone number to join the audio portion of the conference.</span></span> <span data-ttu-id="bcc77-117">对于电话拨入式会议，此设置是可选的。</span><span class="sxs-lookup"><span data-stu-id="bcc77-117">This setting is optional for dial-in conferencing.</span></span> <span data-ttu-id="bcc77-118">默认情况下，不会在默认全局会议策略中选中此设置。</span><span class="sxs-lookup"><span data-stu-id="bcc77-118">This setting is not selected by default in the default global conferencing policy.</span></span>

  - <span data-ttu-id="bcc77-119">**允许参与者未启用企业语音若要拨出**   此设置，则允许未启用企业语音的会议参与者和组织者拨打电话号码以加入会议的音频部分。</span><span class="sxs-lookup"><span data-stu-id="bcc77-119">**Allow participants not enabled for Enterprise Voice to dial out**   This setting allows meeting participants and organizers that are not enabled for Enterprise Voice to dial out to a phone number to join the audio portion of the conference.</span></span> <span data-ttu-id="bcc77-120">拨出呼叫是根据组织者分配的语音策略进行授权的。</span><span class="sxs-lookup"><span data-stu-id="bcc77-120">The dial-out call is authorized based on the organizer’s assigned voice policy.</span></span> <span data-ttu-id="bcc77-121">默认情况下，不会在默认全局会议策略中选中此设置。</span><span class="sxs-lookup"><span data-stu-id="bcc77-121">This setting is not selected by default in the default global conferencing policy.</span></span> <span data-ttu-id="bcc77-122">设置默认值为禁用。</span><span class="sxs-lookup"><span data-stu-id="bcc77-122">The setting default value is disabled.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bcc77-123">若要启用此功能，没有为企业语音启用的会议组织者应为其分配适当的语音策略，以授权来自该用户组织的会议的任何拨出。</span><span class="sxs-lookup"><span data-stu-id="bcc77-123">To enable this capability, a meeting organizer that is not enabled for Enterprise Voice should have an appropriate voice policy assigned to them to authorize any dial-out from a conference organized by that user.</span></span> <span data-ttu-id="bcc77-124">可以从 Lync Server 命令行管理程序向未启用企业语音的用户分配语音策略。</span><span class="sxs-lookup"><span data-stu-id="bcc77-124">A voice policy can be assigned to a user that is not enabled for Enterprise Voice from the Lync Server Management Shell.</span></span> <span data-ttu-id="bcc77-125">如果用户没有明确分配给他的语音策略，则站点语音策略将用于授权拨出请求。</span><span class="sxs-lookup"><span data-stu-id="bcc77-125">If the user does not have a voice policy explicitly assigned to him, the site voice policy will be used to authorize the dial-out request.</span></span> <span data-ttu-id="bcc77-126">如果没有网站语音策略，则将使用全局语音策略。&nbsp;</span><span class="sxs-lookup"><span data-stu-id="bcc77-126">If there is no site voice policy, the global voice policy will be used.&nbsp;</span></span>

    
    </div>

<span data-ttu-id="bcc77-127">本节中的过程解释如何修改会议策略。</span><span class="sxs-lookup"><span data-stu-id="bcc77-127">The procedure in this section explains how to modify conferencing policy.</span></span> <span data-ttu-id="bcc77-128">有关如何配置在默认会议策略中定义参与者体验的所有设置的详细信息，请参阅[在 Lync Server 2013 中创建或修改会议配置设置的集合](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="bcc77-128">For details about how to configure all of the settings that define the participant experience in the default conferencing policy, see [Create or modify a collection of meeting configuration settings in Lync Server 2013](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md).</span></span> <span data-ttu-id="bcc77-129">有关如何为特定用户或用户组创建会议策略的详细信息，请参阅[在 Lync Server 2013 中创建或修改会议策略](lync-server-2013-create-or-modify-a-conferencing-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="bcc77-129">For details about how to create a conferencing policy for a specific user or group of users, see [Create or modify a conferencing policy in Lync Server 2013](lync-server-2013-create-or-modify-a-conferencing-policy.md).</span></span> <span data-ttu-id="bcc77-130">有关所有可用会议策略设置的列表，请参阅[Lync Server 2013 的会议策略设置参考](lync-server-2013-conferencing-policy-settings-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="bcc77-130">For a list of all available conferencing policy settings, see [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span></span>

<div>

## <a name="to-modify-the-conferencing-policy-for-dial-in"></a><span data-ttu-id="bcc77-131">修改拨入的会议策略</span><span class="sxs-lookup"><span data-stu-id="bcc77-131">To modify the conferencing policy for dial-in</span></span>

1.  <span data-ttu-id="bcc77-132">以 RTCUniversalServerAdmins 组成员或者 **Cs-ServerAdministrator** 或 **CsAdministrator** 角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="bcc77-132">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="bcc77-133">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="bcc77-133">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="bcc77-134">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="bcc77-134">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="bcc77-135">在左侧导航栏中，单击“会议”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bcc77-135">In the left navigation bar, click **Conferencing**.</span></span>

4.  <span data-ttu-id="bcc77-136">在“会议策略”\*\*\*\* 选项卡上，双击会议策略名称打开“编辑会议策略”\*\*\*\* 对话框。</span><span class="sxs-lookup"><span data-stu-id="bcc77-136">On the **Conferencing Policy** tab, double-click a conferencing policy name to open the **Edit Conferencing Policy** dialog box.</span></span>

5.  <span data-ttu-id="bcc77-137">确认电话拨入式会议的字段适合您的组织，并根据需要修改设置。</span><span class="sxs-lookup"><span data-stu-id="bcc77-137">Verify that the fields for dial-in conferencing are appropriate for your organization, and modify the settings if necessary.</span></span>

6.  <span data-ttu-id="bcc77-138">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="bcc77-138">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

