---
title: 在 Skype for Business 服务器中配置会议加入页面
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6537765e-4384-416f-92f1-a7f3b39ebe56
description: '摘要: 了解如何在 Skype for Business 服务器中配置会议加入页面。'
ms.openlocfilehash: 30e220f2a1745aea0a77e3ec3ff491b842a2b221
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34283723"
---
# <a name="configure-the-meeting-join-page-in-skype-for-business-server"></a><span data-ttu-id="a72f0-103">在 Skype for Business 服务器中配置会议加入页面</span><span class="sxs-lookup"><span data-stu-id="a72f0-103">Configure the meeting join page in Skype for Business Server</span></span>
 
<span data-ttu-id="a72f0-104">**摘要:** 了解如何在 Skype for Business 服务器中配置会议加入页面。</span><span class="sxs-lookup"><span data-stu-id="a72f0-104">**Summary:** Learn how to configure the meeting join page in Skype for Business Server.</span></span>
  
<span data-ttu-id="a72f0-105">当用户单击会议请求中的会议链接时, "会议加入" 页面将检测用户计算机上是否已安装 Skype for Business 客户端。</span><span class="sxs-lookup"><span data-stu-id="a72f0-105">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Skype for Business client is already installed on the user's computer.</span></span> <span data-ttu-id="a72f0-106">如果已安装客户端, 客户端将打开并加入会议。</span><span class="sxs-lookup"><span data-stu-id="a72f0-106">If a client is already installed, the client opens and joins the meeting.</span></span> <span data-ttu-id="a72f0-107">如果未安装客户端, 则默认情况下会打开 Skype for Business 客户端。</span><span class="sxs-lookup"><span data-stu-id="a72f0-107">If a client is not installed, by default the Skype for Business client opens.</span></span> 
  
## <a name="configure-the-meeting-join-page"></a><span data-ttu-id="a72f0-108">配置与会页面</span><span class="sxs-lookup"><span data-stu-id="a72f0-108">Configure the meeting join page</span></span>

<span data-ttu-id="a72f0-109">如果你希望允许用户加入与其他版本的客户端的会议, 则可以修改会议加入页面的行为。</span><span class="sxs-lookup"><span data-stu-id="a72f0-109">You can modify the behavior of the meeting join page if you want to allow users to join meetings with other versions of the client.</span></span> <span data-ttu-id="a72f0-110">这些配置选项已从 Skype for Business 服务器控制面板中删除, 但你可以使用 CsWebServiceConfiguration cmdlet 对其进行配置。</span><span class="sxs-lookup"><span data-stu-id="a72f0-110">These configuration options have been removed from the Skype for Business Server Control Panel, but you configure them by using the Set-CsWebServiceConfiguration cmdlet.</span></span>
  
<span data-ttu-id="a72f0-111">**会议加入页面设置-CsWebServiceConfiguration 参数**</span><span class="sxs-lookup"><span data-stu-id="a72f0-111">**Meeting Join Page Set-CsWebServiceConfiguration parameters**</span></span>

|<span data-ttu-id="a72f0-112">**CsWebServiceConfiguration 参数**</span><span class="sxs-lookup"><span data-stu-id="a72f0-112">**Set-CsWebServiceConfiguration parameter**</span></span>|<span data-ttu-id="a72f0-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="a72f0-113">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a72f0-114">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="a72f0-114">ShowJoinUsingLegacyClientLink</span></span>  <br/> |<span data-ttu-id="a72f0-115">此参数已弃用, 用于 Skype for business Server 的本地版本。</span><span class="sxs-lookup"><span data-stu-id="a72f0-115">This parameter has been deprecated for use with the on-premises version of Skype for Business Server.</span></span>  <br/> <span data-ttu-id="a72f0-116">如果设置为 True, 则通过使用 Skype for Business 之外的客户端应用程序加入会议的用户将有机会通过使用其当前客户端应用程序加入会议。</span><span class="sxs-lookup"><span data-stu-id="a72f0-116">If set to True, users joining a meeting by using a client application other than Skype for Business will be given the opportunity to join the meeting by using their current client application.</span></span> <span data-ttu-id="a72f0-117">默认值为 False。</span><span class="sxs-lookup"><span data-stu-id="a72f0-117">The default value is False.</span></span>  <br/> |
|<span data-ttu-id="a72f0-118">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="a72f0-118">ShowAlternateJoinOptionsExpanded</span></span>  <br/> |<span data-ttu-id="a72f0-119">此参数已弃用, 用于 Skype for business Server 的本地版本。</span><span class="sxs-lookup"><span data-stu-id="a72f0-119">This parameter has been deprecated for use with the on-premises version of Skype for Business Server.</span></span>  <br/>  <span data-ttu-id="a72f0-120">如果设置为 True, 则自动展开并向用户显示用于加入联机会议的备用选项。</span><span class="sxs-lookup"><span data-stu-id="a72f0-120">If set to True, alternate options for joining an online conference are automatically expanded and shown to users.</span></span> <span data-ttu-id="a72f0-121">如果设置为 False (默认值), 则可以使用这些选项, 但用户将必须为自己显示选项列表。</span><span class="sxs-lookup"><span data-stu-id="a72f0-121">If set to False (the default value), these options will be available, but the user will have to display the list of options for themselves.</span></span>  <br/> |
   

