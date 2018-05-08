---
title: Skype for Business Server 2015 中的通知应用程序部署过程
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
description: 部署过程和 Skype 中为 Business Server 企业语音的通知应用程序的步骤。
ms.openlocfilehash: 08a52569dede43bbe54b1bf7e62f37114ba68853
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server-2015"></a><span data-ttu-id="bea2f-103">Skype for Business Server 2015 中的通知应用程序部署过程</span><span class="sxs-lookup"><span data-stu-id="bea2f-103">Deployment process for the Announcement application in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="bea2f-104">部署过程和 Skype 中为 Business Server 企业语音的通知应用程序的步骤。</span><span class="sxs-lookup"><span data-stu-id="bea2f-104">Deployment process and steps for Announcement application in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="bea2f-105">通知应用程序是一种企业语音功能，使您能够配置呼叫未分配的分机号 （扩展可用于您的组织，但未分配给联系人或电话） 会发生什么情况。</span><span class="sxs-lookup"><span data-stu-id="bea2f-105">The Announcement application is an Enterprise Voice feature that enables you to configure what happens to calls to unassigned extensions (extensions that are valid for your organization, but are not assigned to a person or a phone).</span></span> <span data-ttu-id="bea2f-106">例如，可以将对未分配号码的呼叫配置为播放消息或转接至其他目标，或者同时执行这两种操作。</span><span class="sxs-lookup"><span data-stu-id="bea2f-106">For example, you can configure calls to unassigned numbers to play a message, or to be transferred to a different destination, or both.</span></span>
  
<span data-ttu-id="bea2f-107">部署企业语音时，将作为前端服务器或 Standard Edition 服务器上的响应组应用程序功能安装通知应用程序。</span><span class="sxs-lookup"><span data-stu-id="bea2f-107">The Announcement application is installed as a feature of Response Group application on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="bea2f-108">需要上载音频文件或配置文本到语音转换 (TTS)，并配置未分配号码表来配置通知。</span><span class="sxs-lookup"><span data-stu-id="bea2f-108">You need to configure Announcements by uploading your audio files or by configuring text-to-speech (TTS) and configuring the unassigned number table.</span></span>
  
<span data-ttu-id="bea2f-109">本节概述部署通知应用程序所涉及的步骤。</span><span class="sxs-lookup"><span data-stu-id="bea2f-109">This section provides an overview of the steps involved in deploying the Announcement application.</span></span> <span data-ttu-id="bea2f-110">配置通知之前，必须部署企业语音。</span><span class="sxs-lookup"><span data-stu-id="bea2f-110">You must deploy Enterprise Voice before you configure announcements.</span></span> <span data-ttu-id="bea2f-111">安装和部署企业语音时启用通知应用程序所需的组件。</span><span class="sxs-lookup"><span data-stu-id="bea2f-111">The components required by the Announcement application are installed and enabled when you deploy Enterprise Voice.</span></span>
  
<span data-ttu-id="bea2f-112">**通知部署过程**</span><span class="sxs-lookup"><span data-stu-id="bea2f-112">**Announcement Deployment Process**</span></span>

|<span data-ttu-id="bea2f-113">**阶段**</span><span class="sxs-lookup"><span data-stu-id="bea2f-113">**Phase**</span></span>|<span data-ttu-id="bea2f-114">**步骤**</span><span class="sxs-lookup"><span data-stu-id="bea2f-114">**Steps**</span></span>|<span data-ttu-id="bea2f-115">**角色**</span><span class="sxs-lookup"><span data-stu-id="bea2f-115">**Roles**</span></span>|<span data-ttu-id="bea2f-116">**部署文档**</span><span class="sxs-lookup"><span data-stu-id="bea2f-116">**Deployment documentation**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bea2f-117">配置通知设置</span><span class="sxs-lookup"><span data-stu-id="bea2f-117">Configure Announcement settings</span></span>  <br/> | <span data-ttu-id="bea2f-118">通过录制并上载音频文件或使用文本到语音转换 (TTS) 来创建通知。</span><span class="sxs-lookup"><span data-stu-id="bea2f-118">Create the announcement by recording and uploading audio files or by using text-to-speech (TTS).</span></span> <br/>  <span data-ttu-id="bea2f-119">配置未分配号码表中的未分配号码范围，然后将其与相应的通知关联。</span><span class="sxs-lookup"><span data-stu-id="bea2f-119">Configure the unassigned number ranges in the unassigned number table and associate them with the appropriate announcement.</span></span> <br/> |<span data-ttu-id="bea2f-120">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="bea2f-120">RTCUniversalServerAdmins</span></span>  <br/> <span data-ttu-id="bea2f-121">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="bea2f-121">CsVoiceAdministrator</span></span>  <br/> <span data-ttu-id="bea2f-122">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="bea2f-122">CsServerAdministrator</span></span>  <br/> <span data-ttu-id="bea2f-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="bea2f-123">CsAdministrator</span></span>  <br/> <span data-ttu-id="bea2f-124">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="bea2f-124">CsViewOnlyAdministrator</span></span>  <br/> |[<span data-ttu-id="bea2f-125">创建或删除业务服务器 2015年中 Skype 通知</span><span class="sxs-lookup"><span data-stu-id="bea2f-125">Create or delete an announcement in Skype for Business Server 2015</span></span>](create-an-announcement.md) <br/> [<span data-ttu-id="bea2f-126">创建或修改业务服务器 2015 Skype 中的未分配号码范围</span><span class="sxs-lookup"><span data-stu-id="bea2f-126">Create or modify an unassigned number range in Skype for Business Server 2015</span></span>](create-or-modify-an-unassigned-number-range.md) <br/> |
|<span data-ttu-id="bea2f-127">验证通知部署</span><span class="sxs-lookup"><span data-stu-id="bea2f-127">Verify your Announcement deployment</span></span>  <br/> |<span data-ttu-id="bea2f-128">通过侦听通知来进行测试以验证配置是否按预期工作。</span><span class="sxs-lookup"><span data-stu-id="bea2f-128">Test by listening to announcements to verify that your configuration works as expected.</span></span>  <br/> |-  <br/> |[<span data-ttu-id="bea2f-129">（可选）验证通知部署中的业务 2015 Skype</span><span class="sxs-lookup"><span data-stu-id="bea2f-129">(Optional) Verify Announcement deployment in Skype for Business 2015</span></span>](optional-verify-announcement-deployment.md) <br/> |
   

