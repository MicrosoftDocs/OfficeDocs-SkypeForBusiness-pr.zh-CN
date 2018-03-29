---
title: 会议策略创建新模板或编辑现有的
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
ms.openlocfilehash: 7840eb2d30c40440d82d0cdc6d2bcf38ac894c4b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="conferencing-policy-create-new-or-edit-existing"></a><span data-ttu-id="89bad-103">会议策略：创建新的或编辑现有的</span><span class="sxs-lookup"><span data-stu-id="89bad-103">Conferencing Policy: Create New or Edit Existing</span></span>
 
<span data-ttu-id="89bad-104">会议策略定义会议期间用户可以使用的各种功能。</span><span class="sxs-lookup"><span data-stu-id="89bad-104">A Conferencing policy defines the features and capabilities that users have available during a conference (also known as meeting).</span></span>
  
## <a name="ui-reference"></a><span data-ttu-id="89bad-105">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="89bad-105">UI Reference</span></span>

<span data-ttu-id="89bad-106">下表介绍了该页上的各个字段。</span><span class="sxs-lookup"><span data-stu-id="89bad-106">The following list describes the fields on the page.</span></span>
  
- <span data-ttu-id="89bad-107">**作用域**标识要创建或修改的会议策略的作用域： 全局站点或用户。</span><span class="sxs-lookup"><span data-stu-id="89bad-107">**Scope** Identifies the scope of the conferencing policy that you are creating or modifying: global, site, or user.</span></span>
    
- <span data-ttu-id="89bad-108">**名称**每个会议策略需要一个名称。</span><span class="sxs-lookup"><span data-stu-id="89bad-108">**Name** Each conferencing policy requires a name.</span></span> <span data-ttu-id="89bad-109">默认情况下，称为全局和站点会议策略，名称不能更改。</span><span class="sxs-lookup"><span data-stu-id="89bad-109">Global and site conferencing policies are named by default, and the name cannot be changed.</span></span> <span data-ttu-id="89bad-110">对于用户会议策略，使用标识的用户组的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="89bad-110">For user conferencing policies, use a descriptive name that identifies the user or group of users.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="89bad-111">保存会议策略后，将无法更改此名称。</span><span class="sxs-lookup"><span data-stu-id="89bad-111">After you save the conferencing policy, the name cannot be changed.</span></span> 
  
- <span data-ttu-id="89bad-112">**说明**此字段是可选的。</span><span class="sxs-lookup"><span data-stu-id="89bad-112">**Description** This field is optional.</span></span> <span data-ttu-id="89bad-113">使用它来提供有关会议策略的其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="89bad-113">Use it to provide additional details about the conferencing policy.</span></span>
    
- <span data-ttu-id="89bad-114">**策略管理器**此部分中的设置将应用到的用户的组织会议。</span><span class="sxs-lookup"><span data-stu-id="89bad-114">**Organizer policy** The settings in this section apply to the user who organizes a conference.</span></span> <span data-ttu-id="89bad-115">如果选中某个设置，则用户可以组织会议具有指定的特性。</span><span class="sxs-lookup"><span data-stu-id="89bad-115">If a setting is selected, the user can organize a conference that has the specified characteristic.</span></span> <span data-ttu-id="89bad-116">如果不选择设置，用户不能组织会议具有此特征。</span><span class="sxs-lookup"><span data-stu-id="89bad-116">If a setting is not selected, the user can't organize a conference with this characteristic.</span></span> <span data-ttu-id="89bad-117">这些设置不会决定哪些用户有权访问其他会议的参加者。</span><span class="sxs-lookup"><span data-stu-id="89bad-117">These settings do not determine what the user has access to as a participant in other conferences.</span></span>
    
    <span data-ttu-id="89bad-118">单击标签旁边的向上箭头或向下箭头可关闭或打开该部分。</span><span class="sxs-lookup"><span data-stu-id="89bad-118">Click the up arrow or down arrow next to the label to close or open the section.</span></span>
    
- <span data-ttu-id="89bad-119">**会议的最大大小**的最大允许大会的用户数。</span><span class="sxs-lookup"><span data-stu-id="89bad-119">**Maximum meeting size** the maximum number of users that are allowed at a conference.</span></span> <span data-ttu-id="89bad-120">默认情况下，最大会议大小为 250。</span><span class="sxs-lookup"><span data-stu-id="89bad-120">By default, the maximum conference size is 250.</span></span>
    
- <span data-ttu-id="89bad-121">**允许匿名用户邀请参与者**选中此复选框可以允许用户以匿名用户邀请到会议。</span><span class="sxs-lookup"><span data-stu-id="89bad-121">**Allow participants to invite anonymous users** Select this check box to allow users to invite anonymous users to conferences.</span></span> <span data-ttu-id="89bad-122">匿名用户将因此没有在您的组织的 Active Directory 域服务和人员、 凭据、 未经过身份验证的用户。</span><span class="sxs-lookup"><span data-stu-id="89bad-122">Anonymous users are users who do not have credentials in your organization's Active Directory Domain Services and who, therefore, are not authenticated.</span></span>
    
- <span data-ttu-id="89bad-123">**记录**指定参与者能记录会议。</span><span class="sxs-lookup"><span data-stu-id="89bad-123">**Recording** Specify whether or not participants can record conferences.</span></span> <span data-ttu-id="89bad-124">选项为**None** ，或**启用录制**。</span><span class="sxs-lookup"><span data-stu-id="89bad-124">The options are **None** or **Enable recording**.</span></span>
    
- <span data-ttu-id="89bad-125">**允许联盟和匿名参与者记录**选中此复选框可以允许外部和未经身份验证到记录会议的参与者。</span><span class="sxs-lookup"><span data-stu-id="89bad-125">**Allow federated and anonymous participants to record** Select this check box to allow external and unauthenticated participants to record conferences.</span></span>
    
- <span data-ttu-id="89bad-126">**音频/视频**指定与会者是否可以使用音频和视频：</span><span class="sxs-lookup"><span data-stu-id="89bad-126">**Audio/video** Specify whether participants can use audio and video:</span></span>
    
  - <span data-ttu-id="89bad-127">**无**选择此选项可防止使用的音频和视频。</span><span class="sxs-lookup"><span data-stu-id="89bad-127">**None** Select this option to prevent the use of audio and video.</span></span>
    
  - <span data-ttu-id="89bad-128">**启用 IP 音频**选择此选项可允许使用的音频，但无视频。</span><span class="sxs-lookup"><span data-stu-id="89bad-128">**Enable IP audio** Select this option to allow the use of audio but not video.</span></span>
    
  - <span data-ttu-id="89bad-129">**启用 IP 音频/视频**选择此选项可允许音频和视频。</span><span class="sxs-lookup"><span data-stu-id="89bad-129">**Enable IP audio/video** Select this option to allow both audio and video.</span></span>
    
- <span data-ttu-id="89bad-130">**启用 PSTN 拨入会议**如果启用**音频/视频**中的音频，请选择此复选框可以允许用户通过使用公共交换的电话网 (PSTN) 拨号加入会议。</span><span class="sxs-lookup"><span data-stu-id="89bad-130">**Enable PSTN dial-in conferencing** If you enabled audio in **Audio/video**, select this check box to allow users to dial in to conferences by using the public switched telephone network (PSTN).</span></span>
    
- <span data-ttu-id="89bad-131">**允许匿名参与者拨出**如果您允许用户拨号加入会议，您想要允许未经身份验证的用户 （匿名） 通过拨出打电话参加的会议，请选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="89bad-131">**Allow anonymous participants to dial out** Select this check box if you allow users to dial in to conferences and you want to allow unauthenticated (anonymous) users to join a conference by using dial out phoning.</span></span> <span data-ttu-id="89bad-132">通过拨出式电话，会议服务器会呼叫用户，用户接听电话即可加入会议。</span><span class="sxs-lookup"><span data-stu-id="89bad-132">With dial-out phoning, the conference server calls the user, and the user answers the phone to join the conference.</span></span>
    
- <span data-ttu-id="89bad-133">**允许参与者不能启用企业语音，拨出**如果启用**音频/视频**中的音频，则选择此复选框可允许用户未启用企业语音，通过拨出打电话加入会议。</span><span class="sxs-lookup"><span data-stu-id="89bad-133">**Allow participants not enabled for Enterprise Voice to dial out** If you enabled audio in **Audio/video**, select this check box to allow users who are not enabled for Enterprise Voice to join a conference by using dial-out phoning.</span></span> <span data-ttu-id="89bad-134">使用拨出打电话会议服务器电话用户，然后用户应答电话参加会议。</span><span class="sxs-lookup"><span data-stu-id="89bad-134">With dial-out phoning the conferencing server telephones the user, and then the user answers the phone to join the conference.</span></span>
    
- <span data-ttu-id="89bad-135">**允许多个视频流**如果启用**音频/视频**中的视频，请选择此复选框可允许用户组织库视图视频会议。</span><span class="sxs-lookup"><span data-stu-id="89bad-135">**Allow multiple video streams** If you enabled video in **Audio/video**, select this check box to allow users to organize conferences with Gallery View video.</span></span> <span data-ttu-id="89bad-136">当选中此复选框时，此设置将允许用户组织发送多个视频流的会议。</span><span class="sxs-lookup"><span data-stu-id="89bad-136">When this check box is selected, this setting allows users to organize conferences that send multiple video streams.</span></span> <span data-ttu-id="89bad-137">如果未选中此复选框，用户可以只组织发送单个视频流的会议。</span><span class="sxs-lookup"><span data-stu-id="89bad-137">When this check box is not selected, users can only organize conferences that send a single video stream.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="89bad-p110">此选项可确定会议支持的视频流类型。但不能确定参与者能否收到多个视频流。“**允许参与者加入多个视频流**”选项可确定参与者能否收到多个视频流。</span><span class="sxs-lookup"><span data-stu-id="89bad-p110">This option determines the type of video stream supported by the conference. It does not determine whether participants can receive multiple video streams. The **Enable participants to join with multiple video streams** option determines whether participants can receive multiple video streams.</span></span>
  
- <span data-ttu-id="89bad-141">**数据协作**指定会议允许数据协作。</span><span class="sxs-lookup"><span data-stu-id="89bad-141">**Data collaboration** Specify whether or not the conference allows data collaboration.</span></span> <span data-ttu-id="89bad-142">选项为**None**或**进行数据协作**。</span><span class="sxs-lookup"><span data-stu-id="89bad-142">The options are **None** or **Enable data collaboration**.</span></span>
    
    <span data-ttu-id="89bad-143">以下设置适用于数据协作：</span><span class="sxs-lookup"><span data-stu-id="89bad-143">The following settings apply to data collaboration:</span></span>
    
  - <span data-ttu-id="89bad-144">**允许联盟和匿名参与者下载内容**如果您允许数据协作，则选择此复选框可以允许外部和未经授权用户下载内容，如幻灯片或讲义，从会议。</span><span class="sxs-lookup"><span data-stu-id="89bad-144">**Allow federated and anonymous participants to download content** If you allow data collaboration, select this check box to allow external and unauthenticated users to download content, such as slides or handouts, from a conference.</span></span>
    
  - <span data-ttu-id="89bad-145">**允许参与者传输文件**如果允许数据协作，请选中此复选框可以允许在会议期间向所有参与者的文件传输。</span><span class="sxs-lookup"><span data-stu-id="89bad-145">**Allow participants to transfer files** If you allow data collaboration, select this check box to allow file transfers to all participants during a conference.</span></span>
    
  - <span data-ttu-id="89bad-146">**启用注释**如果您允许数据协作时，选中此复选框可以允许参加人作屏幕上在会议过程中的共享内容的批注。</span><span class="sxs-lookup"><span data-stu-id="89bad-146">**Enable annotations** If you allow data collaboration, select this check box to allow participants to make on-screen annotations on content shared during the conference.</span></span>
    
  - <span data-ttu-id="89bad-147">**启用 PowerPoint 批注**如果允许注释，请选中此复选框可允许参与者在会议过程中共享的 PowerPoint 幻灯片中添加批注。</span><span class="sxs-lookup"><span data-stu-id="89bad-147">**Enable PowerPoint annotations** If you allow annotation, select this check box to allow participants to make annotations in PowerPoint slides shared during the conference.</span></span>
    
  - <span data-ttu-id="89bad-148">**启用轮询**如果允许数据协作，请选中此复选框可允许参与者在会议过程中包含民意测验。</span><span class="sxs-lookup"><span data-stu-id="89bad-148">**Enable polls** If you allow data collaboration, select this check box to allow participants to hold a poll during a conference.</span></span>
    
- <span data-ttu-id="89bad-149">**应用程序共享**指定会议允许应用程序共享。</span><span class="sxs-lookup"><span data-stu-id="89bad-149">**Application sharing** Specify whether or not the conference allows application sharing.</span></span> <span data-ttu-id="89bad-150">选项将**禁用应用程序共享**或**启用应用程序共享**。</span><span class="sxs-lookup"><span data-stu-id="89bad-150">The options are **Disable application sharing** or **Enable application sharing**.</span></span>
    
    <span data-ttu-id="89bad-151">以下设置适用于应用程序共享：</span><span class="sxs-lookup"><span data-stu-id="89bad-151">The following settings apply to application sharing:</span></span>
    
  - <span data-ttu-id="89bad-152">**允许参与者控制**如果您允许应用程序共享，则选择此复选框可允许参与者能够控制应用程序或在会议中共享桌面。</span><span class="sxs-lookup"><span data-stu-id="89bad-152">**Allow participants to take control** If you allow application sharing, select this check box to allow participants to take control of applications or desktops that are shared during the conference.</span></span>
    
  - <span data-ttu-id="89bad-153">**允许联盟和匿名参与者能够控制**如果您允许应用程序共享，则选择此复选框可以允许外部和未经身份验证的参与者能够控制应用程序或在会议中共享桌面。</span><span class="sxs-lookup"><span data-stu-id="89bad-153">**Allow federated and anonymous participants to take control** If you allow application sharing, select this check box to allow external and unauthenticated participants to take control of applications or desktops that are shared during the conference.</span></span>
    
- <span data-ttu-id="89bad-154">**参与者的策略**此部分中的设置适用于用户作为一个会议或两方会话中的参与者。</span><span class="sxs-lookup"><span data-stu-id="89bad-154">**Participant policy** The settings in this section apply to users as participants in a conference or two-party session.</span></span> <span data-ttu-id="89bad-155">由于下列设置每个用户的设置，在会议或两方会话中的一个用户可能具有不同的功能，比在同一个会议或两方会话中的其他用户。</span><span class="sxs-lookup"><span data-stu-id="89bad-155">Because the following settings are per-user settings, one user in a conference or two-party session may have different capabilities than another user in the same conference or two-party session.</span></span>
    
    <span data-ttu-id="89bad-156">单击标签旁边的向上箭头或向下箭头可关闭或打开该部分。</span><span class="sxs-lookup"><span data-stu-id="89bad-156">Click the up arrow or down arrow next to the label to close or open the section.</span></span>
    
- <span data-ttu-id="89bad-p114">选择“**启用应用程序和桌面共享**”可允许用户在参与会议或两方会话时共享应用程序或各自的桌面。选择“**禁用应用程序和桌面共享**”可阻止用户在参与会议或两方会话时共享应用程序或各自的桌面。</span><span class="sxs-lookup"><span data-stu-id="89bad-p114">Select **Enable application and desktop sharing** to allow users to share applications or their desktop while participating in a conference or two-party session. Select **Disable application and desktop sharing** to prevent users from sharing applications or their desktop while participating in a conference or two-party session.</span></span>
    
- <span data-ttu-id="89bad-159">**启用对等文件传输**选中此复选框可在会议或两方会话期间允许各种个人文件传输 （即，不涉及所有参与者的文件传输）。</span><span class="sxs-lookup"><span data-stu-id="89bad-159">**Enable peer-to-peer file transfer** Select this check box to allow person-to-person file transfers (that is, file transfers that do not involve all participants) during a conference or two-party session.</span></span>
    
- <span data-ttu-id="89bad-160">**启用对等录制**选中此复选框以允许用户录制两方会话。</span><span class="sxs-lookup"><span data-stu-id="89bad-160">**Enable peer-to-peer recording** Select this check box to allow users to record two-party sessions.</span></span>
    
- <span data-ttu-id="89bad-161">**使参与者参加多个视频流**选中此复选框可允许参与者在会议，从而让它接收图片库视图视频。</span><span class="sxs-lookup"><span data-stu-id="89bad-161">**Enable participants to join with multiple video streams** Select this check box to allow participants to receive Gallery View video in conferences that allow it.</span></span> <span data-ttu-id="89bad-162">如果未选中此选项，参与者只能接收而不考虑大会的允许单个视频流。</span><span class="sxs-lookup"><span data-stu-id="89bad-162">If this option is not selected, participants can only receive a single video stream regardless of what the conference allows.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="89bad-163">“**允许多个视频流**”确定会议是否允许多个视频流。</span><span class="sxs-lookup"><span data-stu-id="89bad-163">The **Allow multiple video streams** determines whether a conference allows multiple video streams.</span></span>
  
<span data-ttu-id="89bad-164">有关会议的特性和功能的详细信息，请参阅规划文档中[概述的会议](http://technet.microsoft.com/library/5bb90e69-3d4f-4d59-a1ee-2550de84439f.aspx)。</span><span class="sxs-lookup"><span data-stu-id="89bad-164">For details about conferencing features and capabilities, see [Overview of Conferencing](http://technet.microsoft.com/library/5bb90e69-3d4f-4d59-a1ee-2550de84439f.aspx) in the Planning documentation.</span></span> <span data-ttu-id="89bad-165">有关使用会议策略的详细信息，请参阅操作文档中的[策略会议](http://technet.microsoft.com/library/8f92eb7c-ee66-4df6-a726-4bff93b122cb.aspx)。</span><span class="sxs-lookup"><span data-stu-id="89bad-165">For details about working with conferencing policies, see [Conferencing Policies](http://technet.microsoft.com/library/8f92eb7c-ee66-4df6-a726-4bff93b122cb.aspx) in the Operations documentation.</span></span>
  

