---
title: 配置会议中的业务服务器 Skype 的与会页面
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6537765e-4384-416f-92f1-a7f3b39ebe56
description: 摘要： 了解如何配置会议中的业务服务器 Skype 的与会页面。
ms.openlocfilehash: 4ed89d07b85072ba86fc89db33e4902b97373d11
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33913333"
---
# <a name="configure-the-meeting-join-page-in-skype-for-business-server"></a><span data-ttu-id="bfe95-103">配置会议中的业务服务器 Skype 的与会页面</span><span class="sxs-lookup"><span data-stu-id="bfe95-103">Configure the meeting join page in Skype for Business Server</span></span>
 
<span data-ttu-id="bfe95-104">**摘要：** 了解如何配置会议中的业务服务器 Skype 的与会页面。</span><span class="sxs-lookup"><span data-stu-id="bfe95-104">**Summary:** Learn how to configure the meeting join page in Skype for Business Server.</span></span>
  
<span data-ttu-id="bfe95-105">当用户单击会议请求中，会议中的会议链接与会页面检测业务客户端 Skype 是否已安装在用户计算机上。</span><span class="sxs-lookup"><span data-stu-id="bfe95-105">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Skype for Business client is already installed on the user's computer.</span></span> <span data-ttu-id="bfe95-106">如果已安装客户端，客户端将打开并加入会议。</span><span class="sxs-lookup"><span data-stu-id="bfe95-106">If a client is already installed, the client opens and joins the meeting.</span></span> <span data-ttu-id="bfe95-107">如果未安装客户端，则默认情况下，for Business Skype 客户端将打开。</span><span class="sxs-lookup"><span data-stu-id="bfe95-107">If a client is not installed, by default the Skype for Business client opens.</span></span> 
  
## <a name="configure-the-meeting-join-page"></a><span data-ttu-id="bfe95-108">配置与会页面</span><span class="sxs-lookup"><span data-stu-id="bfe95-108">Configure the meeting join page</span></span>

<span data-ttu-id="bfe95-109">您可以修改的行为的与会页面如果您想要允许用户加入与其他版本的客户端的会议。</span><span class="sxs-lookup"><span data-stu-id="bfe95-109">You can modify the behavior of the meeting join page if you want to allow users to join meetings with other versions of the client.</span></span> <span data-ttu-id="bfe95-110">这些配置选项均已从 Skype 的业务 Server Control Panel，但使用 Set-cswebserviceconfiguration cmdlet 对其进行配置。</span><span class="sxs-lookup"><span data-stu-id="bfe95-110">These configuration options have been removed from the Skype for Business Server Control Panel, but you configure them by using the Set-CsWebServiceConfiguration cmdlet.</span></span>
  
<span data-ttu-id="bfe95-111">**会议加入页面 Set-cswebserviceconfiguration 参数**</span><span class="sxs-lookup"><span data-stu-id="bfe95-111">**Meeting Join Page Set-CsWebServiceConfiguration parameters**</span></span>

|<span data-ttu-id="bfe95-112">**Set-cswebserviceconfiguration 参数**</span><span class="sxs-lookup"><span data-stu-id="bfe95-112">**Set-CsWebServiceConfiguration parameter**</span></span>|<span data-ttu-id="bfe95-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="bfe95-113">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bfe95-114">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="bfe95-114">ShowJoinUsingLegacyClientLink</span></span>  <br/> |<span data-ttu-id="bfe95-115">此参数已被弃用业务服务器与 Skype 的内部部署版本一起使用。</span><span class="sxs-lookup"><span data-stu-id="bfe95-115">This parameter has been deprecated for use with the on-premises version of Skype for Business Server.</span></span>  <br/> <span data-ttu-id="bfe95-116">如果设置为 True，而不使用客户端应用程序加入会议的用户 Skype for Business 将有机会通过其当前的客户端应用程序加入会议。</span><span class="sxs-lookup"><span data-stu-id="bfe95-116">If set to True, users joining a meeting by using a client application other than Skype for Business will be given the opportunity to join the meeting by using their current client application.</span></span> <span data-ttu-id="bfe95-117">默认值为 False。</span><span class="sxs-lookup"><span data-stu-id="bfe95-117">The default value is False.</span></span>  <br/> |
|<span data-ttu-id="bfe95-118">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="bfe95-118">ShowAlternateJoinOptionsExpanded</span></span>  <br/> |<span data-ttu-id="bfe95-119">此参数已被弃用业务服务器与 Skype 的内部部署版本一起使用。</span><span class="sxs-lookup"><span data-stu-id="bfe95-119">This parameter has been deprecated for use with the on-premises version of Skype for Business Server.</span></span>  <br/>  <span data-ttu-id="bfe95-120">如果设置为 True，备用选项用于加入联机会议自动扩展和向用户显示。</span><span class="sxs-lookup"><span data-stu-id="bfe95-120">If set to True, alternate options for joining an online conference are automatically expanded and shown to users.</span></span> <span data-ttu-id="bfe95-121">如果设置为 False （默认值），这些选项会可用，但用户会显示为自己的选项的列表。</span><span class="sxs-lookup"><span data-stu-id="bfe95-121">If set to False (the default value), these options will be available, but the user will have to display the list of options for themselves.</span></span>  <br/> |
   

