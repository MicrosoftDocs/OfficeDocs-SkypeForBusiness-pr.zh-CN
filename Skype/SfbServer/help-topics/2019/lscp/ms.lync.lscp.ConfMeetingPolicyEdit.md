---
title: 会议策略创建新的或编辑现有的
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.ConfMeetingPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ebd2f120-b57a-4c94-9509-20e098f4b0f4
ROBOTS: NOINDEX, NOFOLLOW
description: 会议策略定义会议期间用户可以使用的各种功能。
ms.openlocfilehash: 0a82ba29db52affab2371d6ce880c120487396c6
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41691387"
---
# <a name="conferencing-policy-create-new-or-edit-existing"></a><span data-ttu-id="0d099-103">会议策略：创建新的或编辑现有的</span><span class="sxs-lookup"><span data-stu-id="0d099-103">Conferencing Policy: Create New or Edit Existing</span></span>

<span data-ttu-id="0d099-104">会议策略定义会议期间用户可以使用的各种功能。</span><span class="sxs-lookup"><span data-stu-id="0d099-104">A Conferencing policy defines the features and capabilities that users have available during a conference (also known as meeting).</span></span>

## <a name="ui-reference"></a><span data-ttu-id="0d099-105">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="0d099-105">UI Reference</span></span>

<span data-ttu-id="0d099-106">下表介绍了该页上的各个字段。</span><span class="sxs-lookup"><span data-stu-id="0d099-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="0d099-107">**范围**标识要创建或修改的会议策略的范围：全局、网站或用户。</span><span class="sxs-lookup"><span data-stu-id="0d099-107">**Scope** Identifies the scope of the conferencing policy that you are creating or modifying: global, site, or user.</span></span>

- <span data-ttu-id="0d099-108">**名称**每个会议策略都需要一个名称。</span><span class="sxs-lookup"><span data-stu-id="0d099-108">**Name** Each conferencing policy requires a name.</span></span> <span data-ttu-id="0d099-109">全局和网站会议策略默认命名，不能更改名称。</span><span class="sxs-lookup"><span data-stu-id="0d099-109">Global and site conferencing policies are named by default, and the name cannot be changed.</span></span> <span data-ttu-id="0d099-110">对于用户会议策略，请使用标识用户或用户组的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="0d099-110">For user conferencing policies, use a descriptive name that identifies the user or group of users.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0d099-111">保存会议策略后，将无法更改此名称。</span><span class="sxs-lookup"><span data-stu-id="0d099-111">After you save the conferencing policy, the name cannot be changed.</span></span>

- <span data-ttu-id="0d099-112">**说明**此字段是可选的。</span><span class="sxs-lookup"><span data-stu-id="0d099-112">**Description** This field is optional.</span></span> <span data-ttu-id="0d099-113">使用它提供有关会议策略的其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="0d099-113">Use it to provide additional details about the conferencing policy.</span></span>

- <span data-ttu-id="0d099-114">**组织者策略**本部分中的设置适用于组织会议的用户。</span><span class="sxs-lookup"><span data-stu-id="0d099-114">**Organizer policy** The settings in this section apply to the user who organizes a conference.</span></span> <span data-ttu-id="0d099-115">如果选择了某个设置，则用户可以组织具有指定特征的会议。</span><span class="sxs-lookup"><span data-stu-id="0d099-115">If a setting is selected, the user can organize a conference that has the specified characteristic.</span></span> <span data-ttu-id="0d099-116">如果未选中某个设置，则用户无法使用此特征组织会议。</span><span class="sxs-lookup"><span data-stu-id="0d099-116">If a setting is not selected, the user can't organize a conference with this characteristic.</span></span> <span data-ttu-id="0d099-117">这些设置不确定用户在其他会议中有权访问的参与者。</span><span class="sxs-lookup"><span data-stu-id="0d099-117">These settings do not determine what the user has access to as a participant in other conferences.</span></span>

    <span data-ttu-id="0d099-118">单击标签旁边的向上箭头或向下箭头可关闭或打开该部分。</span><span class="sxs-lookup"><span data-stu-id="0d099-118">Click the up arrow or down arrow next to the label to close or open the section.</span></span>

- <span data-ttu-id="0d099-119">**最大会议大小**会议允许的最大用户数。</span><span class="sxs-lookup"><span data-stu-id="0d099-119">**Maximum meeting size** the maximum number of users that are allowed at a conference.</span></span> <span data-ttu-id="0d099-120">默认情况下，最大会议大小为 250。</span><span class="sxs-lookup"><span data-stu-id="0d099-120">By default, the maximum conference size is 250.</span></span>

- <span data-ttu-id="0d099-121">**允许参与者邀请匿名用户**选中此复选框以允许用户邀请匿名用户加入会议。</span><span class="sxs-lookup"><span data-stu-id="0d099-121">**Allow participants to invite anonymous users** Select this check box to allow users to invite anonymous users to conferences.</span></span> <span data-ttu-id="0d099-122">匿名用户是在组织的 Active Directory 域服务中没有凭据的用户，因此没有经过身份验证的用户。</span><span class="sxs-lookup"><span data-stu-id="0d099-122">Anonymous users are users who do not have credentials in your organization's Active Directory Domain Services and who, therefore, are not authenticated.</span></span>

- <span data-ttu-id="0d099-123">**录制**指定参与者是否可以录制会议。</span><span class="sxs-lookup"><span data-stu-id="0d099-123">**Recording** Specify whether or not participants can record conferences.</span></span> <span data-ttu-id="0d099-124">选项为 "**无**" 或 "**启用录制**"。</span><span class="sxs-lookup"><span data-stu-id="0d099-124">The options are **None** or **Enable recording**.</span></span>

- <span data-ttu-id="0d099-125">**允许联盟和匿名参与者进行录制**选中此复选框以允许外部和未经身份验证的参与者录制会议。</span><span class="sxs-lookup"><span data-stu-id="0d099-125">**Allow federated and anonymous participants to record** Select this check box to allow external and unauthenticated participants to record conferences.</span></span>

- <span data-ttu-id="0d099-126">**音频/视频**指定参与者是否可以使用音频和视频：</span><span class="sxs-lookup"><span data-stu-id="0d099-126">**Audio/video** Specify whether participants can use audio and video:</span></span>

  - <span data-ttu-id="0d099-127">**无**选择此选项可防止使用音频和视频。</span><span class="sxs-lookup"><span data-stu-id="0d099-127">**None** Select this option to prevent the use of audio and video.</span></span>

  - <span data-ttu-id="0d099-128">**启用 IP 音频**选择此选项可允许使用音频，但不允许视频。</span><span class="sxs-lookup"><span data-stu-id="0d099-128">**Enable IP audio** Select this option to allow the use of audio but not video.</span></span>

  - <span data-ttu-id="0d099-129">**启用 IP 音频/视频**选择此选项可允许音频和视频。</span><span class="sxs-lookup"><span data-stu-id="0d099-129">**Enable IP audio/video** Select this option to allow both audio and video.</span></span>

- <span data-ttu-id="0d099-130">**启用 PSTN 电话拨入式会议**如果在 "**音频/视频**" 中启用音频，请选中此复选框以允许用户使用公共交换电话网络（PSTN）拨入会议。</span><span class="sxs-lookup"><span data-stu-id="0d099-130">**Enable PSTN dial-in conferencing** If you enabled audio in **Audio/video**, select this check box to allow users to dial in to conferences by using the public switched telephone network (PSTN).</span></span>

- <span data-ttu-id="0d099-131">**允许匿名参与者拨出**如果允许用户拨入会议，并且想要允许未经身份验证（匿名）用户使用拨出币种加入会议，请选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="0d099-131">**Allow anonymous participants to dial out** Select this check box if you allow users to dial in to conferences and you want to allow unauthenticated (anonymous) users to join a conference by using dial out phoning.</span></span> <span data-ttu-id="0d099-132">通过拨出式电话，会议服务器会呼叫用户，用户接听电话即可加入会议。</span><span class="sxs-lookup"><span data-stu-id="0d099-132">With dial-out phoning, the conference server calls the user, and the user answers the phone to join the conference.</span></span>

- <span data-ttu-id="0d099-133">**允许未启用企业语音的参与者拨出**如果在**音频/视频**中启用音频，请选中此复选框以允许未启用企业语音的用户使用拨出币种加入会议。</span><span class="sxs-lookup"><span data-stu-id="0d099-133">**Allow participants not enabled for Enterprise Voice to dial out** If you enabled audio in **Audio/video**, select this check box to allow users who are not enabled for Enterprise Voice to join a conference by using dial-out phoning.</span></span> <span data-ttu-id="0d099-134">使用拨出币种会议服务器对用户进行电话呼叫，然后用户应答手机加入会议。</span><span class="sxs-lookup"><span data-stu-id="0d099-134">With dial-out phoning the conferencing server telephones the user, and then the user answers the phone to join the conference.</span></span>

- <span data-ttu-id="0d099-135">**允许多个视频流**如果在 "**音频/视频**" 中启用视频，请选中此复选框以允许用户利用库视图视频组织会议。</span><span class="sxs-lookup"><span data-stu-id="0d099-135">**Allow multiple video streams** If you enabled video in **Audio/video**, select this check box to allow users to organize conferences with Gallery View video.</span></span> <span data-ttu-id="0d099-136">选中此复选框后，此设置允许用户组织发送多个视频流的会议。</span><span class="sxs-lookup"><span data-stu-id="0d099-136">When this check box is selected, this setting allows users to organize conferences that send multiple video streams.</span></span> <span data-ttu-id="0d099-137">如果未选中此复选框，则用户只能对发送单个视频流的会议进行组织。</span><span class="sxs-lookup"><span data-stu-id="0d099-137">When this check box is not selected, users can only organize conferences that send a single video stream.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0d099-p110">此选项可确定会议支持的视频流类型。但不能确定参与者能否收到多个视频流。“**允许参与者加入多个视频流**”选项可确定参与者能否收到多个视频流。</span><span class="sxs-lookup"><span data-stu-id="0d099-p110">This option determines the type of video stream supported by the conference. It does not determine whether participants can receive multiple video streams. The **Enable participants to join with multiple video streams** option determines whether participants can receive multiple video streams.</span></span>

- <span data-ttu-id="0d099-141">**数据协作**指定会议是否允许数据协作。</span><span class="sxs-lookup"><span data-stu-id="0d099-141">**Data collaboration** Specify whether or not the conference allows data collaboration.</span></span> <span data-ttu-id="0d099-142">选项为 "**无**" 或 "**启用数据协作**"。</span><span class="sxs-lookup"><span data-stu-id="0d099-142">The options are **None** or **Enable data collaboration**.</span></span>

    <span data-ttu-id="0d099-143">以下设置适用于数据协作：</span><span class="sxs-lookup"><span data-stu-id="0d099-143">The following settings apply to data collaboration:</span></span>

  - <span data-ttu-id="0d099-144">**允许联盟和匿名参与者下载内容**如果你允许数据协作，请选中此复选框以允许外部和未经身份验证的用户从会议中下载幻灯片或讲义等内容。</span><span class="sxs-lookup"><span data-stu-id="0d099-144">**Allow federated and anonymous participants to download content** If you allow data collaboration, select this check box to allow external and unauthenticated users to download content, such as slides or handouts, from a conference.</span></span>

  - <span data-ttu-id="0d099-145">**允许参与者传输文件**如果你允许数据协作，请选中此复选框以允许在会议期间向所有参与者传送文件。</span><span class="sxs-lookup"><span data-stu-id="0d099-145">**Allow participants to transfer files** If you allow data collaboration, select this check box to allow file transfers to all participants during a conference.</span></span>

  - <span data-ttu-id="0d099-146">**启用注释**如果你允许数据协作，请选中此复选框以允许参与者在会议期间共享的内容上进行屏幕注释。</span><span class="sxs-lookup"><span data-stu-id="0d099-146">**Enable annotations** If you allow data collaboration, select this check box to allow participants to make on-screen annotations on content shared during the conference.</span></span>

  - <span data-ttu-id="0d099-147">**启用 PowerPoint 注释**如果你允许批注，请选中此复选框以允许参与者在会议期间共享的 PowerPoint 幻灯片中进行注释。</span><span class="sxs-lookup"><span data-stu-id="0d099-147">**Enable PowerPoint annotations** If you allow annotation, select this check box to allow participants to make annotations in PowerPoint slides shared during the conference.</span></span>

  - <span data-ttu-id="0d099-148">**启用投票**如果你允许数据协作，请选中此复选框以允许参与者在会议期间召开投票。</span><span class="sxs-lookup"><span data-stu-id="0d099-148">**Enable polls** If you allow data collaboration, select this check box to allow participants to hold a poll during a conference.</span></span>

- <span data-ttu-id="0d099-149">**应用程序共享**指定会议是否允许应用程序共享。</span><span class="sxs-lookup"><span data-stu-id="0d099-149">**Application sharing** Specify whether or not the conference allows application sharing.</span></span> <span data-ttu-id="0d099-150">选项为 "**禁用应用程序共享**" 或 "**启用应用程序共享**"。</span><span class="sxs-lookup"><span data-stu-id="0d099-150">The options are **Disable application sharing** or **Enable application sharing**.</span></span>

    <span data-ttu-id="0d099-151">以下设置适用于应用程序共享：</span><span class="sxs-lookup"><span data-stu-id="0d099-151">The following settings apply to application sharing:</span></span>

  - <span data-ttu-id="0d099-152">**允许参与者获得控制权**如果允许应用程序共享，请选中此复选框以允许参与者控制在会议期间共享的应用程序或桌面。</span><span class="sxs-lookup"><span data-stu-id="0d099-152">**Allow participants to take control** If you allow application sharing, select this check box to allow participants to take control of applications or desktops that are shared during the conference.</span></span>

  - <span data-ttu-id="0d099-153">**允许联盟和匿名参与者获得控制权**如果允许应用程序共享，请选中此复选框以允许外部和未经身份验证的参与者控制在会议期间共享的应用程序或桌面。</span><span class="sxs-lookup"><span data-stu-id="0d099-153">**Allow federated and anonymous participants to take control** If you allow application sharing, select this check box to allow external and unauthenticated participants to take control of applications or desktops that are shared during the conference.</span></span>

- <span data-ttu-id="0d099-154">**参与者策略**本部分中的设置适用于在会议或两方会话中作为参与者的用户。</span><span class="sxs-lookup"><span data-stu-id="0d099-154">**Participant policy** The settings in this section apply to users as participants in a conference or two-party session.</span></span> <span data-ttu-id="0d099-155">由于以下设置是每用户设置，因此会议或两方会话中的一个用户可能与同一会议或两方会话中的另一用户具有不同的功能。</span><span class="sxs-lookup"><span data-stu-id="0d099-155">Because the following settings are per-user settings, one user in a conference or two-party session may have different capabilities than another user in the same conference or two-party session.</span></span>

    <span data-ttu-id="0d099-156">单击标签旁边的向上箭头或向下箭头可关闭或打开该部分。</span><span class="sxs-lookup"><span data-stu-id="0d099-156">Click the up arrow or down arrow next to the label to close or open the section.</span></span>

- <span data-ttu-id="0d099-p114">选择“**启用应用程序和桌面共享**”可允许用户在参与会议或两方会话时共享应用程序或各自的桌面。选择“**禁用应用程序和桌面共享**”可阻止用户在参与会议或两方会话时共享应用程序或各自的桌面。</span><span class="sxs-lookup"><span data-stu-id="0d099-p114">Select **Enable application and desktop sharing** to allow users to share applications or their desktop while participating in a conference or two-party session. Select **Disable application and desktop sharing** to prevent users from sharing applications or their desktop while participating in a conference or two-party session.</span></span>

- <span data-ttu-id="0d099-159">**启用对等文件传输**选中此复选框可在会议或两方会话期间允许用户对个人的文件传输（即，不涉及所有参与者的文件传输）。</span><span class="sxs-lookup"><span data-stu-id="0d099-159">**Enable peer-to-peer file transfer** Select this check box to allow person-to-person file transfers (that is, file transfers that do not involve all participants) during a conference or two-party session.</span></span>

- <span data-ttu-id="0d099-160">**启用对等录制**选中此复选框以允许用户录制两方会议。</span><span class="sxs-lookup"><span data-stu-id="0d099-160">**Enable peer-to-peer recording** Select this check box to allow users to record two-party sessions.</span></span>

- <span data-ttu-id="0d099-161">**允许参与者使用多个视频流进行加入**选中此复选框可允许参与者在允许会议的会议中查看库视图视频。</span><span class="sxs-lookup"><span data-stu-id="0d099-161">**Enable participants to join with multiple video streams** Select this check box to allow participants to receive Gallery View video in conferences that allow it.</span></span> <span data-ttu-id="0d099-162">如果未选择此选项，参与者只能接收单个视频流，无论会议允许的内容如何。</span><span class="sxs-lookup"><span data-stu-id="0d099-162">If this option is not selected, participants can only receive a single video stream regardless of what the conference allows.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0d099-163">“**允许多个视频流**”确定会议是否允许多个视频流。</span><span class="sxs-lookup"><span data-stu-id="0d099-163">The **Allow multiple video streams** determines whether a conference allows multiple video streams.</span></span>

<span data-ttu-id="0d099-p116">有关会议特性和功能的详细信息，请参阅规划文档中的[Overview of Conferencing](https://technet.microsoft.com/library/5bb90e69-3d4f-4d59-a1ee-2550de84439f.aspx)。有关使用会议策略的详细信息，请参阅操作文档中的[Conferencing Policies](https://technet.microsoft.com/library/8f92eb7c-ee66-4df6-a726-4bff93b122cb.aspx)。</span><span class="sxs-lookup"><span data-stu-id="0d099-p116">For details about conferencing features and capabilities, see [Overview of Conferencing](https://technet.microsoft.com/library/5bb90e69-3d4f-4d59-a1ee-2550de84439f.aspx) in the Planning documentation. For details about working with conferencing policies, see [Conferencing Policies](https://technet.microsoft.com/library/8f92eb7c-ee66-4df6-a726-4bff93b122cb.aspx) in the Operations documentation.</span></span>


