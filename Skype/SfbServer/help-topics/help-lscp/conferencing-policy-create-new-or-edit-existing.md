---
title: 会议策略创建新的或编辑现有的
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ConfMeetingPolicyEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ebd2f120-b57a-4c94-9509-20e098f4b0f4
description: 会议策略定义会议期间用户可以使用的各种功能。
ms.openlocfilehash: 393ced559593f63068dd8cf0761096330b8c4544
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32234705"
---
# <a name="conferencing-policy-create-new-or-edit-existing"></a><span data-ttu-id="8a1aa-103">会议策略：创建新的或编辑现有的</span><span class="sxs-lookup"><span data-stu-id="8a1aa-103">Conferencing Policy: Create New or Edit Existing</span></span>

<span data-ttu-id="8a1aa-104">会议策略定义会议期间用户可以使用的各种功能。</span><span class="sxs-lookup"><span data-stu-id="8a1aa-104">A Conferencing policy defines the features and capabilities that users have available during a conference (also known as meeting).</span></span>

## <a name="ui-reference"></a><span data-ttu-id="8a1aa-105">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="8a1aa-105">UI Reference</span></span>

<span data-ttu-id="8a1aa-106">下表介绍了该页上的各个字段。</span><span class="sxs-lookup"><span data-stu-id="8a1aa-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="8a1aa-107">**范围**标识您正在创建或修改的会议策略的范围： 全局、 站点或用户。</span><span class="sxs-lookup"><span data-stu-id="8a1aa-107">**Scope** Identifies the scope of the conferencing policy that you are creating or modifying: global, site, or user.</span></span>

- <span data-ttu-id="8a1aa-108">**名称**每个会议策略要求一个名称。</span><span class="sxs-lookup"><span data-stu-id="8a1aa-108">**Name** Each conferencing policy requires a name.</span></span> <span data-ttu-id="8a1aa-109">全局和站点会议策略默认情况下，命名为和无法更改此名称。</span><span class="sxs-lookup"><span data-stu-id="8a1aa-109">Global and site conferencing policies are named by default, and the name cannot be changed.</span></span> <span data-ttu-id="8a1aa-110">对于用户会议策略，使用标识的用户组的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="8a1aa-110">For user conferencing policies, use a descriptive name that identifies the user or group of users.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8a1aa-111">保存会议策略后，将无法更改此名称。</span><span class="sxs-lookup"><span data-stu-id="8a1aa-111">After you save the conferencing policy, the name cannot be changed.</span></span>

- <span data-ttu-id="8a1aa-112">**说明**此字段是可选的。</span><span class="sxs-lookup"><span data-stu-id="8a1aa-112">**Description** This field is optional.</span></span> <span data-ttu-id="8a1aa-113">使用它来提供有关会议策略的其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="8a1aa-113">Use it to provide additional details about the conferencing policy.</span></span>

- <span data-ttu-id="8a1aa-114">**组织者策略**此部分中的设置应用于组织会议的用户。</span><span class="sxs-lookup"><span data-stu-id="8a1aa-114">**Organizer policy** The settings in this section apply to the user who organizes a conference.</span></span> <span data-ttu-id="8a1aa-115">如果选择设置时，用户可以组织会议的具有指定的特征。</span><span class="sxs-lookup"><span data-stu-id="8a1aa-115">If a setting is selected, the user can organize a conference that has the specified characteristic.</span></span> <span data-ttu-id="8a1aa-116">如果未选择设置，则用户无法组织具有以下特征的会议。</span><span class="sxs-lookup"><span data-stu-id="8a1aa-116">If a setting is not selected, the user can't organize a conference with this characteristic.</span></span> <span data-ttu-id="8a1aa-117">这些设置不会确定哪些用户有权访问作为中其他会议参与者。</span><span class="sxs-lookup"><span data-stu-id="8a1aa-117">These settings do not determine what the user has access to as a participant in other conferences.</span></span>

    <span data-ttu-id="8a1aa-118">单击标签旁边的向上箭头或向下箭头可关闭或打开该部分。</span><span class="sxs-lookup"><span data-stu-id="8a1aa-118">Click the up arrow or down arrow next to the label to close or open the section.</span></span>

- <span data-ttu-id="8a1aa-119">**最大会议大小**的最大允许在会议的用户数。</span><span class="sxs-lookup"><span data-stu-id="8a1aa-119">**Maximum meeting size** the maximum number of users that are allowed at a conference.</span></span> <span data-ttu-id="8a1aa-120">默认情况下，最大会议大小为 250。</span><span class="sxs-lookup"><span data-stu-id="8a1aa-120">By default, the maximum conference size is 250.</span></span>

- <span data-ttu-id="8a1aa-121">**允许参与者邀请匿名用户**选中此复选框可允许用户邀请匿名用户参加会议。</span><span class="sxs-lookup"><span data-stu-id="8a1aa-121">**Allow participants to invite anonymous users** Select this check box to allow users to invite anonymous users to conferences.</span></span> <span data-ttu-id="8a1aa-122">匿名用户是用户不具有凭据在贵组织的 Active Directory 域服务和用户，因此，不进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="8a1aa-122">Anonymous users are users who do not have credentials in your organization's Active Directory Domain Services and who, therefore, are not authenticated.</span></span>

- <span data-ttu-id="8a1aa-123">**录制**指定参与者可以录制会议。</span><span class="sxs-lookup"><span data-stu-id="8a1aa-123">**Recording** Specify whether or not participants can record conferences.</span></span> <span data-ttu-id="8a1aa-124">选项为**None**或**启用录制**。</span><span class="sxs-lookup"><span data-stu-id="8a1aa-124">The options are **None** or **Enable recording**.</span></span>

- <span data-ttu-id="8a1aa-125">**允许联盟和匿名参与者录制**选中此复选框可允许外部和未经身份验证的参与者，记录会议。</span><span class="sxs-lookup"><span data-stu-id="8a1aa-125">**Allow federated and anonymous participants to record** Select this check box to allow external and unauthenticated participants to record conferences.</span></span>

- <span data-ttu-id="8a1aa-126">**音频/视频**指定参与者可以使用音频和视频：</span><span class="sxs-lookup"><span data-stu-id="8a1aa-126">**Audio/video** Specify whether participants can use audio and video:</span></span>

  - <span data-ttu-id="8a1aa-127">**无**选择此选项可阻止使用音频和视频。</span><span class="sxs-lookup"><span data-stu-id="8a1aa-127">**None** Select this option to prevent the use of audio and video.</span></span>

  - <span data-ttu-id="8a1aa-128">**启用 IP 音频**选择此选项可允许使用音频但不能使用视频。</span><span class="sxs-lookup"><span data-stu-id="8a1aa-128">**Enable IP audio** Select this option to allow the use of audio but not video.</span></span>

  - <span data-ttu-id="8a1aa-129">**启用 IP 音频/视频**选择此选项可允许使用音频和视频。</span><span class="sxs-lookup"><span data-stu-id="8a1aa-129">**Enable IP audio/video** Select this option to allow both audio and video.</span></span>

- <span data-ttu-id="8a1aa-130">**启用 PSTN 电话拨入式会议**如果您启用了**音频/视频**中的音频，选中此复选框可允许用户使用公用电话交换网 (PSTN) 拨号加入会议。</span><span class="sxs-lookup"><span data-stu-id="8a1aa-130">**Enable PSTN dial-in conferencing** If you enabled audio in **Audio/video**, select this check box to allow users to dial in to conferences by using the public switched telephone network (PSTN).</span></span>

- <span data-ttu-id="8a1aa-131">**允许匿名参与者拨出**如果允许用户电话拨入会议，并且您希望允许未经身份验证 （匿名） 用户使用电话拨出打电话加入会议，请选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="8a1aa-131">**Allow anonymous participants to dial out** Select this check box if you allow users to dial in to conferences and you want to allow unauthenticated (anonymous) users to join a conference by using dial out phoning.</span></span> <span data-ttu-id="8a1aa-132">通过拨出式电话，会议服务器会呼叫用户，用户接听电话即可加入会议。</span><span class="sxs-lookup"><span data-stu-id="8a1aa-132">With dial-out phoning, the conference server calls the user, and the user answers the phone to join the conference.</span></span>

- <span data-ttu-id="8a1aa-133">**允许参与者未启用企业语音即可发起电话拨出**如果您启用了**音频/视频**中的音频，选中此复选框可允许用户未启用企业语音使用电话拨出式打电话加入会议。</span><span class="sxs-lookup"><span data-stu-id="8a1aa-133">**Allow participants not enabled for Enterprise Voice to dial out** If you enabled audio in **Audio/video**, select this check box to allow users who are not enabled for Enterprise Voice to join a conference by using dial-out phoning.</span></span> <span data-ttu-id="8a1aa-134">使用电话拨出式打电话会议服务器电话用户和用户然后接听电话即可加入会议。</span><span class="sxs-lookup"><span data-stu-id="8a1aa-134">With dial-out phoning the conferencing server telephones the user, and then the user answers the phone to join the conference.</span></span>

- <span data-ttu-id="8a1aa-135">**允许多个视频流**如果您启用了**音频/视频**中的视频，选中此复选框可允许用户组织使用库视图视频会议。</span><span class="sxs-lookup"><span data-stu-id="8a1aa-135">**Allow multiple video streams** If you enabled video in **Audio/video**, select this check box to allow users to organize conferences with Gallery View video.</span></span> <span data-ttu-id="8a1aa-136">选中此复选框后，此设置将允许用户组织发送多个视频流的会议。</span><span class="sxs-lookup"><span data-stu-id="8a1aa-136">When this check box is selected, this setting allows users to organize conferences that send multiple video streams.</span></span> <span data-ttu-id="8a1aa-137">当不选中此复选框时，用户可以仅组织发送单个的视频流的会议。</span><span class="sxs-lookup"><span data-stu-id="8a1aa-137">When this check box is not selected, users can only organize conferences that send a single video stream.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8a1aa-p110">此选项可确定会议支持的视频流类型。但不能确定参与者能否收到多个视频流。“**允许参与者加入多个视频流**”选项可确定参与者能否收到多个视频流。</span><span class="sxs-lookup"><span data-stu-id="8a1aa-p110">This option determines the type of video stream supported by the conference. It does not determine whether participants can receive multiple video streams. The **Enable participants to join with multiple video streams** option determines whether participants can receive multiple video streams.</span></span>

- <span data-ttu-id="8a1aa-141">**数据协作**指定会议允许数据协作。</span><span class="sxs-lookup"><span data-stu-id="8a1aa-141">**Data collaboration** Specify whether or not the conference allows data collaboration.</span></span> <span data-ttu-id="8a1aa-142">选项为**None**或**启用数据协作**。</span><span class="sxs-lookup"><span data-stu-id="8a1aa-142">The options are **None** or **Enable data collaboration**.</span></span>

    <span data-ttu-id="8a1aa-143">以下设置适用于数据协作：</span><span class="sxs-lookup"><span data-stu-id="8a1aa-143">The following settings apply to data collaboration:</span></span>

  - <span data-ttu-id="8a1aa-144">**允许联盟和匿名参与者下载内容**如果允许数据协作，请选中此复选框可允许外部和未经身份验证用户下载内容，例如幻灯片或讲义的人员，从会议。</span><span class="sxs-lookup"><span data-stu-id="8a1aa-144">**Allow federated and anonymous participants to download content** If you allow data collaboration, select this check box to allow external and unauthenticated users to download content, such as slides or handouts, from a conference.</span></span>

  - <span data-ttu-id="8a1aa-145">**允许参与者传输文件**如果允许数据协作，请选中此复选框可允许在会议期间向所有参与者的文件传输。</span><span class="sxs-lookup"><span data-stu-id="8a1aa-145">**Allow participants to transfer files** If you allow data collaboration, select this check box to allow file transfers to all participants during a conference.</span></span>

  - <span data-ttu-id="8a1aa-146">**启用批注**如果允许数据协作，请选中此复选框可允许参与者进行屏幕注释对会议期间共享的内容。</span><span class="sxs-lookup"><span data-stu-id="8a1aa-146">**Enable annotations** If you allow data collaboration, select this check box to allow participants to make on-screen annotations on content shared during the conference.</span></span>

  - <span data-ttu-id="8a1aa-147">**启用 PowerPoint 注释**如果允许注释，请选中此复选框可允许参与者在会议期间共享 PowerPoint 幻灯片进行注释。</span><span class="sxs-lookup"><span data-stu-id="8a1aa-147">**Enable PowerPoint annotations** If you allow annotation, select this check box to allow participants to make annotations in PowerPoint slides shared during the conference.</span></span>

  - <span data-ttu-id="8a1aa-148">**启用投票**如果允许数据协作，请选中此复选框可允许参与者在会议期间举行投票。</span><span class="sxs-lookup"><span data-stu-id="8a1aa-148">**Enable polls** If you allow data collaboration, select this check box to allow participants to hold a poll during a conference.</span></span>

- <span data-ttu-id="8a1aa-149">**应用程序共享**指定会议允许应用程序共享。</span><span class="sxs-lookup"><span data-stu-id="8a1aa-149">**Application sharing** Specify whether or not the conference allows application sharing.</span></span> <span data-ttu-id="8a1aa-150">**禁用应用程序共享**或**启用应用程序共享**的选项。</span><span class="sxs-lookup"><span data-stu-id="8a1aa-150">The options are **Disable application sharing** or **Enable application sharing**.</span></span>

    <span data-ttu-id="8a1aa-151">以下设置适用于应用程序共享：</span><span class="sxs-lookup"><span data-stu-id="8a1aa-151">The following settings apply to application sharing:</span></span>

  - <span data-ttu-id="8a1aa-152">**允许参与者获得控制权**如果您允许应用程序共享，请选中此复选框可允许参与者获得应用程序或会议期间共享桌面的控制权。</span><span class="sxs-lookup"><span data-stu-id="8a1aa-152">**Allow participants to take control** If you allow application sharing, select this check box to allow participants to take control of applications or desktops that are shared during the conference.</span></span>

  - <span data-ttu-id="8a1aa-153">**允许联盟和匿名参与者获得控制权**如果您允许应用程序共享，请选中此复选框可允许外部和未经身份验证的参与者，获取应用程序或会议期间共享桌面的控制权。</span><span class="sxs-lookup"><span data-stu-id="8a1aa-153">**Allow federated and anonymous participants to take control** If you allow application sharing, select this check box to allow external and unauthenticated participants to take control of applications or desktops that are shared during the conference.</span></span>

- <span data-ttu-id="8a1aa-154">**参与者策略**此部分中的设置应用于用户作为会议或两方会话中的参与者。</span><span class="sxs-lookup"><span data-stu-id="8a1aa-154">**Participant policy** The settings in this section apply to users as participants in a conference or two-party session.</span></span> <span data-ttu-id="8a1aa-155">以下设置是每个用户设置，因为会议或两方会话中的一个用户可能比在同一个会议或两方会话中的另一个用户的不同功能。</span><span class="sxs-lookup"><span data-stu-id="8a1aa-155">Because the following settings are per-user settings, one user in a conference or two-party session may have different capabilities than another user in the same conference or two-party session.</span></span>

    <span data-ttu-id="8a1aa-156">单击标签旁边的向上箭头或向下箭头可关闭或打开该部分。</span><span class="sxs-lookup"><span data-stu-id="8a1aa-156">Click the up arrow or down arrow next to the label to close or open the section.</span></span>

- <span data-ttu-id="8a1aa-p114">选择“**启用应用程序和桌面共享**”可允许用户在参与会议或两方会话时共享应用程序或各自的桌面。选择“**禁用应用程序和桌面共享**”可阻止用户在参与会议或两方会话时共享应用程序或各自的桌面。</span><span class="sxs-lookup"><span data-stu-id="8a1aa-p114">Select **Enable application and desktop sharing** to allow users to share applications or their desktop while participating in a conference or two-party session. Select **Disable application and desktop sharing** to prevent users from sharing applications or their desktop while participating in a conference or two-party session.</span></span>

- <span data-ttu-id="8a1aa-159">**启用对等文件传输**选中此复选框，以允许会议或两方会话期间进行个人到个人文件传输 （即不涉及所有参与者的文件传输）。</span><span class="sxs-lookup"><span data-stu-id="8a1aa-159">**Enable peer-to-peer file transfer** Select this check box to allow person-to-person file transfers (that is, file transfers that do not involve all participants) during a conference or two-party session.</span></span>

- <span data-ttu-id="8a1aa-160">**启用对等录制**选中此复选框可允许用户录制两方会话。</span><span class="sxs-lookup"><span data-stu-id="8a1aa-160">**Enable peer-to-peer recording** Select this check box to allow users to record two-party sessions.</span></span>

- <span data-ttu-id="8a1aa-161">**使参与者加入与多个视频流**选中此复选框可允许参与者在其允许的会议中接收库视图视频。</span><span class="sxs-lookup"><span data-stu-id="8a1aa-161">**Enable participants to join with multiple video streams** Select this check box to allow participants to receive Gallery View video in conferences that allow it.</span></span> <span data-ttu-id="8a1aa-162">如果未选择此选项，参与者可以仅接收无论会议的允许单个视频流。</span><span class="sxs-lookup"><span data-stu-id="8a1aa-162">If this option is not selected, participants can only receive a single video stream regardless of what the conference allows.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8a1aa-163">“**允许多个视频流**”确定会议是否允许多个视频流。</span><span class="sxs-lookup"><span data-stu-id="8a1aa-163">The **Allow multiple video streams** determines whether a conference allows multiple video streams.</span></span>

<span data-ttu-id="8a1aa-p116">有关会议特性和功能的详细信息，请参阅规划文档中的[Overview of Conferencing](https://technet.microsoft.com/library/5bb90e69-3d4f-4d59-a1ee-2550de84439f.aspx)。有关使用会议策略的详细信息，请参阅操作文档中的[Conferencing Policies](https://technet.microsoft.com/library/8f92eb7c-ee66-4df6-a726-4bff93b122cb.aspx)。</span><span class="sxs-lookup"><span data-stu-id="8a1aa-p116">For details about conferencing features and capabilities, see [Overview of Conferencing](https://technet.microsoft.com/library/5bb90e69-3d4f-4d59-a1ee-2550de84439f.aspx) in the Planning documentation. For details about working with conferencing policies, see [Conferencing Policies](https://technet.microsoft.com/library/8f92eb7c-ee66-4df6-a726-4bff93b122cb.aspx) in the Operations documentation.</span></span>


