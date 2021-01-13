---
title: Skype for Business Server 中的通知应用程序的部署过程
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
description: Skype for Business Server 企业语音 中的通知应用程序的部署过程和企业语音。
ms.openlocfilehash: cfb1436f22681b45de5c399907d4776a9d1db5de
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812302"
---
# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server"></a><span data-ttu-id="f4c58-103">Skype for Business Server 中的通知应用程序的部署过程</span><span class="sxs-lookup"><span data-stu-id="f4c58-103">Deployment process for the Announcement application in Skype for Business Server</span></span>
 
<span data-ttu-id="f4c58-104">Skype for Business Server 企业语音 中的通知应用程序的部署过程和企业语音。</span><span class="sxs-lookup"><span data-stu-id="f4c58-104">Deployment process and steps for Announcement application in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="f4c58-105">通知应用程序是一项 企业语音 功能，它使您能够配置对未分配分机 (分机的调用会发生什么情况，这些分机对您的组织有效，但不分配给人员或电话) 。</span><span class="sxs-lookup"><span data-stu-id="f4c58-105">The Announcement application is an Enterprise Voice feature that enables you to configure what happens to calls to unassigned extensions (extensions that are valid for your organization, but are not assigned to a person or a phone).</span></span> <span data-ttu-id="f4c58-106">例如，可以将对未分配号码的呼叫配置为播放消息或转接至其他目标，或者同时执行这两种操作。</span><span class="sxs-lookup"><span data-stu-id="f4c58-106">For example, you can configure calls to unassigned numbers to play a message, or to be transferred to a different destination, or both.</span></span>
  
<span data-ttu-id="f4c58-107">部署通知应用程序时，通知应用程序作为响应组应用程序的一项功能安装在前端服务器或 Standard Edition 服务器上企业语音。</span><span class="sxs-lookup"><span data-stu-id="f4c58-107">The Announcement application is installed as a feature of Response Group application on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="f4c58-108">需要通过上载音频文件或配置文本到语音转换 (TTS) 和配置未分配号码表来配置通知。</span><span class="sxs-lookup"><span data-stu-id="f4c58-108">You need to configure Announcements by uploading your audio files or by configuring text-to-speech (TTS) and configuring the unassigned number table.</span></span>
  
<span data-ttu-id="f4c58-109">本节概述了部署通知应用程序所涉及的步骤。</span><span class="sxs-lookup"><span data-stu-id="f4c58-109">This section provides an overview of the steps involved in deploying the Announcement application.</span></span> <span data-ttu-id="f4c58-110">在配置企业语音之前，必须部署此策略。</span><span class="sxs-lookup"><span data-stu-id="f4c58-110">You must deploy Enterprise Voice before you configure announcements.</span></span> <span data-ttu-id="f4c58-111">部署通知应用程序所需的组件时，将安装并启用企业语音。</span><span class="sxs-lookup"><span data-stu-id="f4c58-111">The components required by the Announcement application are installed and enabled when you deploy Enterprise Voice.</span></span>
  
<span data-ttu-id="f4c58-112">**通知部署过程**</span><span class="sxs-lookup"><span data-stu-id="f4c58-112">**Announcement Deployment Process**</span></span>

|<span data-ttu-id="f4c58-113">**阶段**</span><span class="sxs-lookup"><span data-stu-id="f4c58-113">**Phase**</span></span>|<span data-ttu-id="f4c58-114">**步骤**</span><span class="sxs-lookup"><span data-stu-id="f4c58-114">**Steps**</span></span>|<span data-ttu-id="f4c58-115">**Roles**</span><span class="sxs-lookup"><span data-stu-id="f4c58-115">**Roles**</span></span>|<span data-ttu-id="f4c58-116">**部署文档**</span><span class="sxs-lookup"><span data-stu-id="f4c58-116">**Deployment documentation**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f4c58-117">配置通知设置</span><span class="sxs-lookup"><span data-stu-id="f4c58-117">Configure Announcement settings</span></span>  <br/> | <span data-ttu-id="f4c58-118">通过录制并上载音频文件或使用文本到语音转换 (TTS) 来创建通知。</span><span class="sxs-lookup"><span data-stu-id="f4c58-118">Create the announcement by recording and uploading audio files or by using text-to-speech (TTS).</span></span> <br/>  <span data-ttu-id="f4c58-119">配置未分配号码表中的未分配号码范围，然后将其与相应的通知关联。</span><span class="sxs-lookup"><span data-stu-id="f4c58-119">Configure the unassigned number ranges in the unassigned number table and associate them with the appropriate announcement.</span></span> <br/> |<span data-ttu-id="f4c58-120">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="f4c58-120">RTCUniversalServerAdmins</span></span>  <br/> <span data-ttu-id="f4c58-121">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="f4c58-121">CsVoiceAdministrator</span></span>  <br/> <span data-ttu-id="f4c58-122">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="f4c58-122">CsServerAdministrator</span></span>  <br/> <span data-ttu-id="f4c58-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="f4c58-123">CsAdministrator</span></span>  <br/> <span data-ttu-id="f4c58-124">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="f4c58-124">CsViewOnlyAdministrator</span></span>  <br/> |[<span data-ttu-id="f4c58-125">在 Skype for Business Server 中创建或删除通知</span><span class="sxs-lookup"><span data-stu-id="f4c58-125">Create or delete an announcement in Skype for Business Server</span></span>](create-an-announcement.md) <br/> [<span data-ttu-id="f4c58-126">在 Skype for Business Server 中创建或修改未分配号码范围</span><span class="sxs-lookup"><span data-stu-id="f4c58-126">Create or modify an unassigned number range in Skype for Business Server</span></span>](create-or-modify-an-unassigned-number-range.md) <br/> |
|<span data-ttu-id="f4c58-127">验证通知部署</span><span class="sxs-lookup"><span data-stu-id="f4c58-127">Verify your Announcement deployment</span></span>  <br/> |<span data-ttu-id="f4c58-128">通过侦听通知来进行测试以验证配置是否按预期工作。</span><span class="sxs-lookup"><span data-stu-id="f4c58-128">Test by listening to announcements to verify that your configuration works as expected.</span></span>  <br/> |-  <br/> |[<span data-ttu-id="f4c58-129"> (可选) Skype for Business 中的验证通知部署</span><span class="sxs-lookup"><span data-stu-id="f4c58-129">(Optional) Verify Announcement deployment in Skype for Business</span></span>](optional-verify-announcement-deployment.md) <br/> |
   

