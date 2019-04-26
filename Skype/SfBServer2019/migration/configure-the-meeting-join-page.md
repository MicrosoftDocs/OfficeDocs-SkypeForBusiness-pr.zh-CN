---
title: 配置与会页面
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: End User
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 当用户单击会议请求中，会议中的会议链接与会页面检测用户的计算机上已安装的客户端。 如果已安装客户端，该客户端将打开并加入会议。 如果未安装客户端，则默认情况下 Web 应用程序将打开。
ms.openlocfilehash: 88ae915318505efef6ae716a17217aaa1e7b12df
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32238714"
---
# <a name="configure-the-meeting-join-page"></a><span data-ttu-id="1d8c2-105">配置与会页面</span><span class="sxs-lookup"><span data-stu-id="1d8c2-105">Configure the meeting join page</span></span>

<span data-ttu-id="1d8c2-106">当用户单击会议请求中，会议中的会议链接与会页面检测用户的计算机上已安装的客户端。</span><span class="sxs-lookup"><span data-stu-id="1d8c2-106">When a user clicks a meeting link in a meeting request, the meeting join page detects which client is already installed on the user's computer.</span></span> <span data-ttu-id="1d8c2-107">如果已安装客户端，该客户端将打开并加入会议。</span><span class="sxs-lookup"><span data-stu-id="1d8c2-107">If a client is already installed, that client opens and joins the meeting.</span></span> <span data-ttu-id="1d8c2-108">如果未安装客户端，则默认情况下 Web 应用程序将打开。</span><span class="sxs-lookup"><span data-stu-id="1d8c2-108">If a client is not installed, by default the Web App opens.</span></span>
  
<span data-ttu-id="1d8c2-109">您可以修改的行为的与会页面如果您想要允许用户加入会议。</span><span class="sxs-lookup"><span data-stu-id="1d8c2-109">You can modify the behavior of the meeting join page if you want to allow users to join meetings.</span></span> <span data-ttu-id="1d8c2-110">已从控制面板中，这些配置选项，但使用 CsWebServiceConfiguration cmdlet 对其进行配置。</span><span class="sxs-lookup"><span data-stu-id="1d8c2-110">These configuration options have been removed from the Control Panel, but you configure them by using the CsWebServiceConfiguration cmdlet.</span></span>
  
<span data-ttu-id="1d8c2-111">**会议加入页面 CsWebServiceConfiguration 参数**</span><span class="sxs-lookup"><span data-stu-id="1d8c2-111">**Meeting Join Page CsWebServiceConfiguration Parameters**</span></span>

|<span data-ttu-id="1d8c2-112">**CsWebServiceConfiguration 参数**</span><span class="sxs-lookup"><span data-stu-id="1d8c2-112">**CsWebServiceConfiguration Parameter**</span></span>|<span data-ttu-id="1d8c2-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="1d8c2-113">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1d8c2-114">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="1d8c2-114">ShowJoinUsingLegacyClientLink</span></span>  <br/> |<span data-ttu-id="1d8c2-115">如果设置为 True，通过使用除 Lync 以外的客户端应用程序加入会议的用户将有机会加入会议。</span><span class="sxs-lookup"><span data-stu-id="1d8c2-115">If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting.</span></span> <span data-ttu-id="1d8c2-116">默认值为 False。</span><span class="sxs-lookup"><span data-stu-id="1d8c2-116">The default value is False.</span></span>  <br/> |
|<span data-ttu-id="1d8c2-117">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="1d8c2-117">ShowAlternateJoinOptionsExpanded</span></span>  <br/> |<span data-ttu-id="1d8c2-118">当设置为 true，则加入联机会议将自动展开和向用户显示的备用选项。</span><span class="sxs-lookup"><span data-stu-id="1d8c2-118">When set to True, alternate options for joining an online conference will automatically be expanded and shown to users.</span></span> <span data-ttu-id="1d8c2-119">设置为 False （默认值） 时，这些选项将可用，但用户会显示为自己的选项的列表。</span><span class="sxs-lookup"><span data-stu-id="1d8c2-119">When set to False (the default value), these options will be available, but the user will have to display the list of options for themselves.</span></span>  <br/> |
   
### <a name="to-configure-the-meeting-join-page-by-using-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="1d8c2-120">若要将会议配置为使用适用于业务服务器 2019年命令行管理程序 Skype 的与会页面</span><span class="sxs-lookup"><span data-stu-id="1d8c2-120">To configure the meeting join page by using Skype for Business Server 2019 Management Shell</span></span>

1. <span data-ttu-id="1d8c2-121">为业务服务器 2019年命令行管理程序启动 Skype： 单击**开始**，单击**所有程序**，都单击**Microsoft Skype 的业务服务器 2019年**，，然后都单击**Skype 的业务 Server Management Shell**。</span><span class="sxs-lookup"><span data-stu-id="1d8c2-121">Start the Skype for Business Server 2019 Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="1d8c2-122">运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="1d8c2-122">Run the following cmdlet:</span></span> 
    
   ```
   Get-CsWebServiceConfiguration
   ```

    <span data-ttu-id="1d8c2-123">此 cmdlet 返回 web 服务配置设置。</span><span class="sxs-lookup"><span data-stu-id="1d8c2-123">This cmdlet returns the web service configuration settings.</span></span>
    
3. <span data-ttu-id="1d8c2-124">运行以下命令，与参数设置为 True 或 False，具体取决于您的首选项 （有关此 cmdlet 的参数的详细信息，请参阅[Business Server Management Shell 的 Skype](../../SfbServer/manage/management-shell.md)文档）：</span><span class="sxs-lookup"><span data-stu-id="1d8c2-124">Run the following command, with the parameters set to True or False, depending on your preference (for details about the parameters for this cmdlet, see the [Skype for Business Server Management Shell](../../SfbServer/manage/management-shell.md) documentation):</span></span>
    
   ```
   Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True
   ```


