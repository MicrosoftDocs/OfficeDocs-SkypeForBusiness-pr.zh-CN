---
title: 在 Skype for Business Server 中配置与会页面
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6537765e-4384-416f-92f1-a7f3b39ebe56
description: 摘要：了解如何在 Skype for Business Server 中配置与会页面。
ms.openlocfilehash: 247664a3ff4bbc4ee055775d26f1d077b662752b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828032"
---
# <a name="configure-the-meeting-join-page-in-skype-for-business-server"></a><span data-ttu-id="8f32c-103">在 Skype for Business Server 中配置与会页面</span><span class="sxs-lookup"><span data-stu-id="8f32c-103">Configure the meeting join page in Skype for Business Server</span></span>
 
<span data-ttu-id="8f32c-104">**摘要：** 了解如何在 Skype for Business Server 中配置与会页面。</span><span class="sxs-lookup"><span data-stu-id="8f32c-104">**Summary:** Learn how to configure the meeting join page in Skype for Business Server.</span></span>
  
<span data-ttu-id="8f32c-105">当用户在会议请求中单击会议链接时，与会页面将检测用户计算机上是否已安装 Skype for Business 客户端。</span><span class="sxs-lookup"><span data-stu-id="8f32c-105">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Skype for Business client is already installed on the user's computer.</span></span> <span data-ttu-id="8f32c-106">如果已安装客户端，则将打开该客户端并加入会议。</span><span class="sxs-lookup"><span data-stu-id="8f32c-106">If a client is already installed, the client opens and joins the meeting.</span></span> <span data-ttu-id="8f32c-107">如果未安装客户端，则默认情况下将打开 Skype for Business 客户端。</span><span class="sxs-lookup"><span data-stu-id="8f32c-107">If a client is not installed, by default the Skype for Business client opens.</span></span> 
  
## <a name="configure-the-meeting-join-page"></a><span data-ttu-id="8f32c-108">配置会议加入页面</span><span class="sxs-lookup"><span data-stu-id="8f32c-108">Configure the meeting join page</span></span>

<span data-ttu-id="8f32c-109">如果要允许用户使用客户端的其他版本加入会议，可以修改与会页面的行为。</span><span class="sxs-lookup"><span data-stu-id="8f32c-109">You can modify the behavior of the meeting join page if you want to allow users to join meetings with other versions of the client.</span></span> <span data-ttu-id="8f32c-110">这些配置选项已从 Skype for Business Server 控制面板中删除，但您可以使用 Set-CsWebServiceConfiguration cmdlet 进行配置。</span><span class="sxs-lookup"><span data-stu-id="8f32c-110">These configuration options have been removed from the Skype for Business Server Control Panel, but you configure them by using the Set-CsWebServiceConfiguration cmdlet.</span></span>
  
<span data-ttu-id="8f32c-111">**与会页面Set-CsWebServiceConfiguration参数**</span><span class="sxs-lookup"><span data-stu-id="8f32c-111">**Meeting Join Page Set-CsWebServiceConfiguration parameters**</span></span>

|<span data-ttu-id="8f32c-112">**Set-CsWebServiceConfiguration 参数**</span><span class="sxs-lookup"><span data-stu-id="8f32c-112">**Set-CsWebServiceConfiguration parameter**</span></span>|<span data-ttu-id="8f32c-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="8f32c-113">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8f32c-114">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="8f32c-114">ShowJoinUsingLegacyClientLink</span></span>  <br/> |<span data-ttu-id="8f32c-115">此参数已弃用，以用于本地版本的 Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="8f32c-115">This parameter has been deprecated for use with the on-premises version of Skype for Business Server.</span></span>  <br/> <span data-ttu-id="8f32c-116">如果设置为 True，则使用除 Skype for Business 外的其他客户端应用程序加入会议的用户将有机会使用其当前客户端应用程序加入会议。</span><span class="sxs-lookup"><span data-stu-id="8f32c-116">If set to True, users joining a meeting by using a client application other than Skype for Business will be given the opportunity to join the meeting by using their current client application.</span></span> <span data-ttu-id="8f32c-117">默认值为 False。</span><span class="sxs-lookup"><span data-stu-id="8f32c-117">The default value is False.</span></span>  <br/> |
|<span data-ttu-id="8f32c-118">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="8f32c-118">ShowAlternateJoinOptionsExpanded</span></span>  <br/> |<span data-ttu-id="8f32c-119">此参数已弃用，以用于本地版本的 Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="8f32c-119">This parameter has been deprecated for use with the on-premises version of Skype for Business Server.</span></span>  <br/>  <span data-ttu-id="8f32c-120">如果设置为 True，则用于加入联机会议的备用选项将自动展开并显示给用户。</span><span class="sxs-lookup"><span data-stu-id="8f32c-120">If set to True, alternate options for joining an online conference are automatically expanded and shown to users.</span></span> <span data-ttu-id="8f32c-121">如果设置为 False (默认值) ，这些选项将可用，但用户必须自行显示选项列表。</span><span class="sxs-lookup"><span data-stu-id="8f32c-121">If set to False (the default value), these options will be available, but the user will have to display the list of options for themselves.</span></span>  <br/> |
   

