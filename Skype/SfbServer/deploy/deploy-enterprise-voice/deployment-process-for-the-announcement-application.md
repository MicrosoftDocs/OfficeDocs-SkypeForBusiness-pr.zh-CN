---
title: Skype for Business Server 中的发布应用程序的部署过程
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Skype for business Server 企业版中发布应用程序的部署过程和步骤。
ms.openlocfilehash: 89f01ed4c9488aa74b07bfae41f3bf27032b552e
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767395"
---
# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server"></a><span data-ttu-id="7624b-103">Skype for Business Server 中的发布应用程序的部署过程</span><span class="sxs-lookup"><span data-stu-id="7624b-103">Deployment process for the Announcement application in Skype for Business Server</span></span>
 
<span data-ttu-id="7624b-104">Skype for business Server 企业版中发布应用程序的部署过程和步骤。</span><span class="sxs-lookup"><span data-stu-id="7624b-104">Deployment process and steps for Announcement application in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="7624b-105">"发布" 应用程序是一种企业语音功能，可让你配置调用未分配的扩展（对你的组织有效，但未分配给某个人或手机的扩展）所发生的情况。</span><span class="sxs-lookup"><span data-stu-id="7624b-105">The Announcement application is an Enterprise Voice feature that enables you to configure what happens to calls to unassigned extensions (extensions that are valid for your organization, but are not assigned to a person or a phone).</span></span> <span data-ttu-id="7624b-106">例如，可以将对未分配号码的呼叫配置为播放消息或转接至其他目标，或者同时执行这两种操作。</span><span class="sxs-lookup"><span data-stu-id="7624b-106">For example, you can configure calls to unassigned numbers to play a message, or to be transferred to a different destination, or both.</span></span>
  
<span data-ttu-id="7624b-107">在部署企业语音时，"发布" 应用程序作为 "响应组应用程序" 的一项功能安装在前端服务器或标准版服务器上。</span><span class="sxs-lookup"><span data-stu-id="7624b-107">The Announcement application is installed as a feature of Response Group application on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="7624b-108">需要上载音频文件或配置文本到语音转换 (TTS)，并配置未分配号码表来配置通知。</span><span class="sxs-lookup"><span data-stu-id="7624b-108">You need to configure Announcements by uploading your audio files or by configuring text-to-speech (TTS) and configuring the unassigned number table.</span></span>
  
<span data-ttu-id="7624b-109">本部分概述了部署公告应用程序所涉及的步骤。</span><span class="sxs-lookup"><span data-stu-id="7624b-109">This section provides an overview of the steps involved in deploying the Announcement application.</span></span> <span data-ttu-id="7624b-110">您必须先部署企业语音，然后才能配置公告。</span><span class="sxs-lookup"><span data-stu-id="7624b-110">You must deploy Enterprise Voice before you configure announcements.</span></span> <span data-ttu-id="7624b-111">部署 "企业语音" 时，安装并启用公告应用程序所需的组件。</span><span class="sxs-lookup"><span data-stu-id="7624b-111">The components required by the Announcement application are installed and enabled when you deploy Enterprise Voice.</span></span>
  
<span data-ttu-id="7624b-112">**通知部署过程**</span><span class="sxs-lookup"><span data-stu-id="7624b-112">**Announcement Deployment Process**</span></span>

|<span data-ttu-id="7624b-113">**阶段**</span><span class="sxs-lookup"><span data-stu-id="7624b-113">**Phase**</span></span>|<span data-ttu-id="7624b-114">**步骤**</span><span class="sxs-lookup"><span data-stu-id="7624b-114">**Steps**</span></span>|<span data-ttu-id="7624b-115">**Roles**</span><span class="sxs-lookup"><span data-stu-id="7624b-115">**Roles**</span></span>|<span data-ttu-id="7624b-116">**部署文档**</span><span class="sxs-lookup"><span data-stu-id="7624b-116">**Deployment documentation**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7624b-117">配置通知设置</span><span class="sxs-lookup"><span data-stu-id="7624b-117">Configure Announcement settings</span></span>  <br/> | <span data-ttu-id="7624b-118">通过录制并上载音频文件或使用文本到语音转换 (TTS) 来创建通知。</span><span class="sxs-lookup"><span data-stu-id="7624b-118">Create the announcement by recording and uploading audio files or by using text-to-speech (TTS).</span></span> <br/>  <span data-ttu-id="7624b-119">配置未分配号码表中的未分配号码范围，然后将其与相应的通知关联。</span><span class="sxs-lookup"><span data-stu-id="7624b-119">Configure the unassigned number ranges in the unassigned number table and associate them with the appropriate announcement.</span></span> <br/> |<span data-ttu-id="7624b-120">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="7624b-120">RTCUniversalServerAdmins</span></span>  <br/> <span data-ttu-id="7624b-121">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="7624b-121">CsVoiceAdministrator</span></span>  <br/> <span data-ttu-id="7624b-122">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="7624b-122">CsServerAdministrator</span></span>  <br/> <span data-ttu-id="7624b-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="7624b-123">CsAdministrator</span></span>  <br/> <span data-ttu-id="7624b-124">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="7624b-124">CsViewOnlyAdministrator</span></span>  <br/> |[<span data-ttu-id="7624b-125">在 Skype for Business 服务器中创建或删除公告</span><span class="sxs-lookup"><span data-stu-id="7624b-125">Create or delete an announcement in Skype for Business Server</span></span>](create-an-announcement.md) <br/> [<span data-ttu-id="7624b-126">在 Skype for Business 服务器中创建或修改未分配的号码范围</span><span class="sxs-lookup"><span data-stu-id="7624b-126">Create or modify an unassigned number range in Skype for Business Server</span></span>](create-or-modify-an-unassigned-number-range.md) <br/> |
|<span data-ttu-id="7624b-127">验证通知部署</span><span class="sxs-lookup"><span data-stu-id="7624b-127">Verify your Announcement deployment</span></span>  <br/> |<span data-ttu-id="7624b-128">通过侦听通知来进行测试以验证配置是否按预期工作。</span><span class="sxs-lookup"><span data-stu-id="7624b-128">Test by listening to announcements to verify that your configuration works as expected.</span></span>  <br/> |-  <br/> |[<span data-ttu-id="7624b-129">可选在 Skype for Business 中验证公告部署</span><span class="sxs-lookup"><span data-stu-id="7624b-129">(Optional) Verify Announcement deployment in Skype for Business</span></span>](optional-verify-announcement-deployment.md) <br/> |
   

