---
title: 配置会议加入页在 Skype 的业务服务器 2015年
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6537765e-4384-416f-92f1-a7f3b39ebe56
description: 摘要： 了解如何配置会议业务服务器 2015年的 Skype 连接页。
ms.openlocfilehash: c0b3ed39fc2f7a1a48635353cc1db673a4bd1cd5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-the-meeting-join-page-in-skype-for-business-server-2015"></a><span data-ttu-id="fa69a-103">配置会议加入页在 Skype 的业务服务器 2015年</span><span class="sxs-lookup"><span data-stu-id="fa69a-103">Configure the meeting join page in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="fa69a-104">**摘要：**了解如何配置会议业务服务器 2015年的 Skype 连接页。</span><span class="sxs-lookup"><span data-stu-id="fa69a-104">**Summary:** Learn how to configure the meeting join page in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="fa69a-105">当用户单击会议链接在会议要求中，会议加入页检测 Skype 业务客户端是否已安装在用户的计算机上。</span><span class="sxs-lookup"><span data-stu-id="fa69a-105">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Skype for Business client is already installed on the user's computer.</span></span> <span data-ttu-id="fa69a-106">如果已安装客户端，客户端将打开，并加入会议。</span><span class="sxs-lookup"><span data-stu-id="fa69a-106">If a client is already installed, the client opens and joins the meeting.</span></span> <span data-ttu-id="fa69a-107">如果未安装客户端，则默认情况下的业务客户端的 Skype 2015 版本打开。</span><span class="sxs-lookup"><span data-stu-id="fa69a-107">If a client is not installed, by default the 2015 version of Skype for Business client opens.</span></span> 
  
## <a name="configure-the-meeting-join-page"></a><span data-ttu-id="fa69a-108">配置会议加入页</span><span class="sxs-lookup"><span data-stu-id="fa69a-108">Configure the meeting join page</span></span>

<span data-ttu-id="fa69a-109">您可以修改行为的会议加入页，如果您希望允许用户加入会议与其他版本的客户端。</span><span class="sxs-lookup"><span data-stu-id="fa69a-109">You can modify the behavior of the meeting join page if you want to allow users to join meetings with other versions of the client.</span></span> <span data-ttu-id="fa69a-110">这些配置选项已从中移除 Skype 业务服务器控制面板，但将它们配置通过使用一组 CsWebServiceConfiguration cmdlet。</span><span class="sxs-lookup"><span data-stu-id="fa69a-110">These configuration options have been removed from the Skype for Business Server Control Panel, but you configure them by using the Set-CsWebServiceConfiguration cmdlet.</span></span>
  
<span data-ttu-id="fa69a-111">**会议加入页集 CsWebServiceConfiguration 参数**</span><span class="sxs-lookup"><span data-stu-id="fa69a-111">**Meeting Join Page Set-CsWebServiceConfiguration parameters**</span></span>

|<span data-ttu-id="fa69a-112">**一组 CsWebServiceConfiguration 参数**</span><span class="sxs-lookup"><span data-stu-id="fa69a-112">**Set-CsWebServiceConfiguration parameter**</span></span>|<span data-ttu-id="fa69a-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="fa69a-113">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fa69a-114">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="fa69a-114">ShowJoinUsingLegacyClientLink</span></span>  <br/> |<span data-ttu-id="fa69a-115">此参数用于内部部署版本的 Skype 业务服务器 2015年已弃用。</span><span class="sxs-lookup"><span data-stu-id="fa69a-115">This parameter has been deprecated for use with the on-premises version of Skype for Business Server 2015.</span></span>  <br/> <span data-ttu-id="fa69a-116">如果设置为 True，用户加入会议，而不使用客户端应用程序业务的 Skype 将有机会通过其当前的客户端应用程序中加入会议。</span><span class="sxs-lookup"><span data-stu-id="fa69a-116">If set to True, users joining a meeting by using a client application other than Skype for Business will be given the opportunity to join the meeting by using their current client application.</span></span> <span data-ttu-id="fa69a-117">默认值为 False。</span><span class="sxs-lookup"><span data-stu-id="fa69a-117">The default value is False.</span></span>  <br/> |
|<span data-ttu-id="fa69a-118">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="fa69a-118">ShowAlternateJoinOptionsExpanded</span></span>  <br/> |<span data-ttu-id="fa69a-119">此参数用于内部部署版本的 Skype 业务服务器 2015年已弃用。</span><span class="sxs-lookup"><span data-stu-id="fa69a-119">This parameter has been deprecated for use with the on-premises version of Skype for Business Server 2015.</span></span>  <br/>  <span data-ttu-id="fa69a-120">如果设置为 True 时，备用选项适用于： 加入一个联机会议自动展开并显示给用户。</span><span class="sxs-lookup"><span data-stu-id="fa69a-120">If set to True, alternate options for joining an online conference are automatically expanded and shown to users.</span></span> <span data-ttu-id="fa69a-121">如果设置为 False （默认值），这些选项将可用，但用户必须要显示自己的选项的列表。</span><span class="sxs-lookup"><span data-stu-id="fa69a-121">If set to False (the default value), these options will be available, but the user will have to display the list of options for themselves.</span></span>  <br/> |
   

