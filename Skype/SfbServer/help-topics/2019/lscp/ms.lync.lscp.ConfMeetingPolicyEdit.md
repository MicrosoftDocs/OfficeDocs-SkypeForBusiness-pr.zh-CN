---
title: 会议策略创建新的或编辑现有的
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ConfMeetingPolicyEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: ebd2f120-b57a-4c94-9509-20e098f4b0f4
ROBOTS: NOINDEX, NOFOLLOW
description: 会议策略定义会议期间用户可用的特性和功能 (也称为会议) 。
ms.openlocfilehash: 97b022771f0077239475137496c222748b6ef828
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824882"
---
# <a name="conferencing-policy-create-new-or-edit-existing"></a><span data-ttu-id="0515d-103">会议策略：创建新的或编辑现有的</span><span class="sxs-lookup"><span data-stu-id="0515d-103">Conferencing Policy: Create New or Edit Existing</span></span>

<span data-ttu-id="0515d-104">会议策略定义会议期间用户可用的特性和功能 (也称为会议) 。</span><span class="sxs-lookup"><span data-stu-id="0515d-104">A Conferencing policy defines the features and capabilities that users have available during a conference (also known as meeting).</span></span>

## <a name="ui-reference"></a><span data-ttu-id="0515d-105">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="0515d-105">UI Reference</span></span>

<span data-ttu-id="0515d-106">下表介绍了该页上的各个字段。</span><span class="sxs-lookup"><span data-stu-id="0515d-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="0515d-107">**范围** 标识要创建或修改的会议策略的范围：全局、站点或用户。</span><span class="sxs-lookup"><span data-stu-id="0515d-107">**Scope** Identifies the scope of the conferencing policy that you are creating or modifying: global, site, or user.</span></span>

- <span data-ttu-id="0515d-108">**名称** 每个会议策略都需要一个名称。</span><span class="sxs-lookup"><span data-stu-id="0515d-108">**Name** Each conferencing policy requires a name.</span></span> <span data-ttu-id="0515d-109">默认情况下会命名全局和站点会议策略，并且无法更改该名称。</span><span class="sxs-lookup"><span data-stu-id="0515d-109">Global and site conferencing policies are named by default, and the name cannot be changed.</span></span> <span data-ttu-id="0515d-110">对于用户会议策略，请使用用于标识用户或用户组的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="0515d-110">For user conferencing policies, use a descriptive name that identifies the user or group of users.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0515d-111">保存会议策略后，将无法更改此名称。</span><span class="sxs-lookup"><span data-stu-id="0515d-111">After you save the conferencing policy, the name cannot be changed.</span></span>

- <span data-ttu-id="0515d-112">**说明** 此字段是可选的。</span><span class="sxs-lookup"><span data-stu-id="0515d-112">**Description** This field is optional.</span></span> <span data-ttu-id="0515d-113">使用它提供有关会议策略的其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="0515d-113">Use it to provide additional details about the conferencing policy.</span></span>

- <span data-ttu-id="0515d-114">**组织者策略** 本节中的设置适用于组织会议的用户。</span><span class="sxs-lookup"><span data-stu-id="0515d-114">**Organizer policy** The settings in this section apply to the user who organizes a conference.</span></span> <span data-ttu-id="0515d-115">如果选择了设置，则用户可以组织具有指定特征的会议。</span><span class="sxs-lookup"><span data-stu-id="0515d-115">If a setting is selected, the user can organize a conference that has the specified characteristic.</span></span> <span data-ttu-id="0515d-116">如果未选择设置，则用户无法组织具有此特征的会议。</span><span class="sxs-lookup"><span data-stu-id="0515d-116">If a setting is not selected, the user can't organize a conference with this characteristic.</span></span> <span data-ttu-id="0515d-117">这些设置无法确定用户作为其他会议的参与者有权访问哪些信息。</span><span class="sxs-lookup"><span data-stu-id="0515d-117">These settings do not determine what the user has access to as a participant in other conferences.</span></span>

    <span data-ttu-id="0515d-118">单击标签旁边的向上箭头或向下箭头可关闭或打开该部分。</span><span class="sxs-lookup"><span data-stu-id="0515d-118">Click the up arrow or down arrow next to the label to close or open the section.</span></span>

- <span data-ttu-id="0515d-119">**最大会议大小** 是允许参加会议的最大用户数。</span><span class="sxs-lookup"><span data-stu-id="0515d-119">**Maximum meeting size** the maximum number of users that are allowed at a conference.</span></span> <span data-ttu-id="0515d-120">默认情况下，最大会议大小为 250。</span><span class="sxs-lookup"><span data-stu-id="0515d-120">By default, the maximum conference size is 250.</span></span>

- <span data-ttu-id="0515d-121">**允许参与者邀请匿名用户** 选中此复选框可允许用户邀请匿名用户参加会议。</span><span class="sxs-lookup"><span data-stu-id="0515d-121">**Allow participants to invite anonymous users** Select this check box to allow users to invite anonymous users to conferences.</span></span> <span data-ttu-id="0515d-122">匿名用户是在你的组织的 Active Directory 域服务中没有凭据，因此未经过身份验证的用户。</span><span class="sxs-lookup"><span data-stu-id="0515d-122">Anonymous users are users who do not have credentials in your organization's Active Directory Domain Services and who, therefore, are not authenticated.</span></span>

- <span data-ttu-id="0515d-123">**录制** 指定参与者是否可以录制会议。</span><span class="sxs-lookup"><span data-stu-id="0515d-123">**Recording** Specify whether or not participants can record conferences.</span></span> <span data-ttu-id="0515d-124">选项为 **"无"** 或 **"启用录制"。**</span><span class="sxs-lookup"><span data-stu-id="0515d-124">The options are **None** or **Enable recording**.</span></span>

- <span data-ttu-id="0515d-125">**允许联盟参与者和匿名参与者录制** 选中此复选框可允许外部和未经身份验证的参与者录制会议。</span><span class="sxs-lookup"><span data-stu-id="0515d-125">**Allow federated and anonymous participants to record** Select this check box to allow external and unauthenticated participants to record conferences.</span></span>

- <span data-ttu-id="0515d-126">**音频/视频** 指定参与者是否可以使用音频和视频：</span><span class="sxs-lookup"><span data-stu-id="0515d-126">**Audio/video** Specify whether participants can use audio and video:</span></span>

  - <span data-ttu-id="0515d-127">**无** 选择此选项可阻止使用音频和视频。</span><span class="sxs-lookup"><span data-stu-id="0515d-127">**None** Select this option to prevent the use of audio and video.</span></span>

  - <span data-ttu-id="0515d-128">**启用 IP 音频** 选择此选项可允许使用音频，但不允许使用视频。</span><span class="sxs-lookup"><span data-stu-id="0515d-128">**Enable IP audio** Select this option to allow the use of audio but not video.</span></span>

  - <span data-ttu-id="0515d-129">**启用 IP 音频/视频** 选择此选项可同时允许音频和视频。</span><span class="sxs-lookup"><span data-stu-id="0515d-129">**Enable IP audio/video** Select this option to allow both audio and video.</span></span>

- <span data-ttu-id="0515d-130">**启用 PSTN 电话拨入式会议** 如果在音频 **/** 视频中启用音频，请选中此复选框以允许用户使用 PSTN 电话交换网或 PSTN (拨入) 。</span><span class="sxs-lookup"><span data-stu-id="0515d-130">**Enable PSTN dial-in conferencing** If you enabled audio in **Audio/video**, select this check box to allow users to dial in to conferences by using the public switched telephone network (PSTN).</span></span>

- <span data-ttu-id="0515d-131">**允许匿名参与者拨出** 如果允许用户拨入会议，并且希望允许未经身份验证的 (匿名) 用户使用拨出式电话加入会议，请选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="0515d-131">**Allow anonymous participants to dial out** Select this check box if you allow users to dial in to conferences and you want to allow unauthenticated (anonymous) users to join a conference by using dial out phoning.</span></span> <span data-ttu-id="0515d-132">通过拨出式电话，会议服务器会呼叫用户，用户接听电话即可加入会议。</span><span class="sxs-lookup"><span data-stu-id="0515d-132">With dial-out phoning, the conference server calls the user, and the user answers the phone to join the conference.</span></span>

- <span data-ttu-id="0515d-133">**允许参与者无法企业语音拨出** 如果在音频 **/** 视频中启用音频，请选中此复选框以允许未启用 企业语音 的用户使用拨出式电话加入会议。</span><span class="sxs-lookup"><span data-stu-id="0515d-133">**Allow participants not enabled for Enterprise Voice to dial out** If you enabled audio in **Audio/video**, select this check box to allow users who are not enabled for Enterprise Voice to join a conference by using dial-out phoning.</span></span> <span data-ttu-id="0515d-134">通过拨出式电话，会议服务器会呼叫用户，然后用户接听电话以加入会议。</span><span class="sxs-lookup"><span data-stu-id="0515d-134">With dial-out phoning the conferencing server telephones the user, and then the user answers the phone to join the conference.</span></span>

- <span data-ttu-id="0515d-135">**允许多个视频流** 如果在音频/视频中启用 **视频**，请选中此复选框以允许用户使用库视图视频组织会议。</span><span class="sxs-lookup"><span data-stu-id="0515d-135">**Allow multiple video streams** If you enabled video in **Audio/video**, select this check box to allow users to organize conferences with Gallery View video.</span></span> <span data-ttu-id="0515d-136">选中此复选框后，此设置允许用户组织发送多个视频流的会议。</span><span class="sxs-lookup"><span data-stu-id="0515d-136">When this check box is selected, this setting allows users to organize conferences that send multiple video streams.</span></span> <span data-ttu-id="0515d-137">未选中此复选框时，用户只能组织发送单个视频流的会议。</span><span class="sxs-lookup"><span data-stu-id="0515d-137">When this check box is not selected, users can only organize conferences that send a single video stream.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0515d-p110">此选项可确定会议支持的视频流类型。但不能确定参与者能否收到多个视频流。“允许参与者加入多个视频流”选项可确定参与者能否收到多个视频流。</span><span class="sxs-lookup"><span data-stu-id="0515d-p110">This option determines the type of video stream supported by the conference. It does not determine whether participants can receive multiple video streams. The **Enable participants to join with multiple video streams** option determines whether participants can receive multiple video streams.</span></span>

- <span data-ttu-id="0515d-141">**数据协作** 指定会议是否允许数据协作。</span><span class="sxs-lookup"><span data-stu-id="0515d-141">**Data collaboration** Specify whether or not the conference allows data collaboration.</span></span> <span data-ttu-id="0515d-142">选项为 **"无"\*\*\*\*或"启用数据协作"。**</span><span class="sxs-lookup"><span data-stu-id="0515d-142">The options are **None** or **Enable data collaboration**.</span></span>

    <span data-ttu-id="0515d-143">以下设置适用于数据协作：</span><span class="sxs-lookup"><span data-stu-id="0515d-143">The following settings apply to data collaboration:</span></span>

  - <span data-ttu-id="0515d-144">**允许联盟参与者和匿名参与者下载内容** 如果允许数据协作，请选中此复选框以允许外部和未经身份验证的用户从会议下载内容，如幻灯片或讲义。</span><span class="sxs-lookup"><span data-stu-id="0515d-144">**Allow federated and anonymous participants to download content** If you allow data collaboration, select this check box to allow external and unauthenticated users to download content, such as slides or handouts, from a conference.</span></span>

  - <span data-ttu-id="0515d-145">**允许参与者传输文件** 如果允许数据协作，请选中此复选框以允许在会议期间将文件传输给所有参与者。</span><span class="sxs-lookup"><span data-stu-id="0515d-145">**Allow participants to transfer files** If you allow data collaboration, select this check box to allow file transfers to all participants during a conference.</span></span>

  - <span data-ttu-id="0515d-146">**启用批注** 如果允许数据协作，请选中此复选框以允许参与者对会议期间共享的内容进行屏幕注释。</span><span class="sxs-lookup"><span data-stu-id="0515d-146">**Enable annotations** If you allow data collaboration, select this check box to allow participants to make on-screen annotations on content shared during the conference.</span></span>

  - <span data-ttu-id="0515d-147">**启用 PowerPoint 批注** 如果允许批注，请选中此复选框以允许参与者在会议期间共享的 PowerPoint 幻灯片中进行批注。</span><span class="sxs-lookup"><span data-stu-id="0515d-147">**Enable PowerPoint annotations** If you allow annotation, select this check box to allow participants to make annotations in PowerPoint slides shared during the conference.</span></span>

  - <span data-ttu-id="0515d-148">**启用投票** 如果允许数据协作，请选中此复选框以允许参与者在会议期间进行投票。</span><span class="sxs-lookup"><span data-stu-id="0515d-148">**Enable polls** If you allow data collaboration, select this check box to allow participants to hold a poll during a conference.</span></span>

- <span data-ttu-id="0515d-149">**应用程序共享** 指定会议是否允许应用程序共享。</span><span class="sxs-lookup"><span data-stu-id="0515d-149">**Application sharing** Specify whether or not the conference allows application sharing.</span></span> <span data-ttu-id="0515d-150">选项为 **"禁用应用程序共享"或\*\*\*\*"启用应用程序共享"。**</span><span class="sxs-lookup"><span data-stu-id="0515d-150">The options are **Disable application sharing** or **Enable application sharing**.</span></span>

    <span data-ttu-id="0515d-151">以下设置适用于应用程序共享：</span><span class="sxs-lookup"><span data-stu-id="0515d-151">The following settings apply to application sharing:</span></span>

  - <span data-ttu-id="0515d-152">**允许参与者获得控制权** 如果允许应用程序共享，请选中此复选框以允许参与者控制会议期间共享的应用程序或桌面。</span><span class="sxs-lookup"><span data-stu-id="0515d-152">**Allow participants to take control** If you allow application sharing, select this check box to allow participants to take control of applications or desktops that are shared during the conference.</span></span>

  - <span data-ttu-id="0515d-153">**允许联盟参与者和匿名参与者获得控制权** 如果允许应用程序共享，请选中此复选框以允许外部参与者和未经身份验证的参与者控制会议期间共享的应用程序或桌面。</span><span class="sxs-lookup"><span data-stu-id="0515d-153">**Allow federated and anonymous participants to take control** If you allow application sharing, select this check box to allow external and unauthenticated participants to take control of applications or desktops that are shared during the conference.</span></span>

- <span data-ttu-id="0515d-154">**参与者策略** 本节中的设置适用于作为会议或双方会话的参与者的用户。</span><span class="sxs-lookup"><span data-stu-id="0515d-154">**Participant policy** The settings in this section apply to users as participants in a conference or two-party session.</span></span> <span data-ttu-id="0515d-155">由于以下设置是每用户设置，因此会议或两方会话中的一个用户的功能可能不同于同一会议或两方会话中的其他用户。</span><span class="sxs-lookup"><span data-stu-id="0515d-155">Because the following settings are per-user settings, one user in a conference or two-party session may have different capabilities than another user in the same conference or two-party session.</span></span>

    <span data-ttu-id="0515d-156">单击标签旁边的向上箭头或向下箭头可关闭或打开该部分。</span><span class="sxs-lookup"><span data-stu-id="0515d-156">Click the up arrow or down arrow next to the label to close or open the section.</span></span>

- <span data-ttu-id="0515d-p114">选择“启用应用程序和桌面共享”可允许用户在参与会议或两方会话时共享应用程序或各自的桌面。选择“禁用应用程序和桌面共享”可阻止用户在参与会议或两方会话时共享应用程序或各自的桌面。</span><span class="sxs-lookup"><span data-stu-id="0515d-p114">Select **Enable application and desktop sharing** to allow users to share applications or their desktop while participating in a conference or two-party session. Select **Disable application and desktop sharing** to prevent users from sharing applications or their desktop while participating in a conference or two-party session.</span></span>

- <span data-ttu-id="0515d-159">**启用对等文件传输** 选中此复选框可允许个人到个人 (，即不涉及会议或两方会话期间) 参与者的文件传输。</span><span class="sxs-lookup"><span data-stu-id="0515d-159">**Enable peer-to-peer file transfer** Select this check box to allow person-to-person file transfers (that is, file transfers that do not involve all participants) during a conference or two-party session.</span></span>

- <span data-ttu-id="0515d-160">**启用对等录制** 选中此复选框可允许用户录制双方会话。</span><span class="sxs-lookup"><span data-stu-id="0515d-160">**Enable peer-to-peer recording** Select this check box to allow users to record two-party sessions.</span></span>

- <span data-ttu-id="0515d-161">**允许参与者加入多个视频流** 选中此复选框可允许参与者在允许库视图的会议接收库视图视频。</span><span class="sxs-lookup"><span data-stu-id="0515d-161">**Enable participants to join with multiple video streams** Select this check box to allow participants to receive Gallery View video in conferences that allow it.</span></span> <span data-ttu-id="0515d-162">如果未选择此选项，则参与者只能接收单个视频流，无论会议允许什么内容。</span><span class="sxs-lookup"><span data-stu-id="0515d-162">If this option is not selected, participants can only receive a single video stream regardless of what the conference allows.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0515d-163">“允许多个视频流”确定会议是否允许多个视频流。</span><span class="sxs-lookup"><span data-stu-id="0515d-163">The **Allow multiple video streams** determines whether a conference allows multiple video streams.</span></span>

<span data-ttu-id="0515d-164">有关会议特性和功能的详细信息，请参阅规划文档中的[Overview of Conferencing](https://technet.microsoft.com/library/5bb90e69-3d4f-4d59-a1ee-2550de84439f.aspx)。</span><span class="sxs-lookup"><span data-stu-id="0515d-164">For details about conferencing features and capabilities, see [Overview of Conferencing](https://technet.microsoft.com/library/5bb90e69-3d4f-4d59-a1ee-2550de84439f.aspx) in the Planning documentation.</span></span> <span data-ttu-id="0515d-165">有关使用会议策略的详细信息，请参阅操作文档中的[Conferencing Policies](https://technet.microsoft.com/library/8f92eb7c-ee66-4df6-a726-4bff93b122cb.aspx)。</span><span class="sxs-lookup"><span data-stu-id="0515d-165">For details about working with conferencing policies, see [Conferencing Policies](https://technet.microsoft.com/library/8f92eb7c-ee66-4df6-a726-4bff93b122cb.aspx) in the Operations documentation.</span></span>


