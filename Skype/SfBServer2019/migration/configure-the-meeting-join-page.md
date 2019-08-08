---
title: 配置与会页面
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: End User
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 当用户单击会议请求中的会议链接时, "会议加入" 页面将检测用户计算机上已安装的客户端。 如果已安装客户端, 该客户端将打开并加入会议。 如果未安装客户端, 则默认情况下将打开 Web 应用。
ms.openlocfilehash: 1bab2dff25db94b36c41e5824401777006760bfc
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239324"
---
# <a name="configure-the-meeting-join-page"></a><span data-ttu-id="4f015-105">配置与会页面</span><span class="sxs-lookup"><span data-stu-id="4f015-105">Configure the meeting join page</span></span>

<span data-ttu-id="4f015-106">当用户单击会议请求中的会议链接时, "会议加入" 页面将检测用户计算机上已安装的客户端。</span><span class="sxs-lookup"><span data-stu-id="4f015-106">When a user clicks a meeting link in a meeting request, the meeting join page detects which client is already installed on the user's computer.</span></span> <span data-ttu-id="4f015-107">如果已安装客户端, 该客户端将打开并加入会议。</span><span class="sxs-lookup"><span data-stu-id="4f015-107">If a client is already installed, that client opens and joins the meeting.</span></span> <span data-ttu-id="4f015-108">如果未安装客户端, 则默认情况下将打开 Web 应用。</span><span class="sxs-lookup"><span data-stu-id="4f015-108">If a client is not installed, by default the Web App opens.</span></span>
  
<span data-ttu-id="4f015-109">如果您希望允许用户加入会议, 则可以修改会议加入页面的行为。</span><span class="sxs-lookup"><span data-stu-id="4f015-109">You can modify the behavior of the meeting join page if you want to allow users to join meetings.</span></span> <span data-ttu-id="4f015-110">这些配置选项已从控制面板中删除, 但你可以使用 CsWebServiceConfiguration cmdlet 对其进行配置。</span><span class="sxs-lookup"><span data-stu-id="4f015-110">These configuration options have been removed from the Control Panel, but you configure them by using the CsWebServiceConfiguration cmdlet.</span></span>
  
<span data-ttu-id="4f015-111">**会议加入页 CsWebServiceConfiguration 参数**</span><span class="sxs-lookup"><span data-stu-id="4f015-111">**Meeting Join Page CsWebServiceConfiguration Parameters**</span></span>

|<span data-ttu-id="4f015-112">**CsWebServiceConfiguration 参数**</span><span class="sxs-lookup"><span data-stu-id="4f015-112">**CsWebServiceConfiguration Parameter**</span></span>|<span data-ttu-id="4f015-113">**说明**</span><span class="sxs-lookup"><span data-stu-id="4f015-113">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4f015-114">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="4f015-114">ShowJoinUsingLegacyClientLink</span></span>  <br/> |<span data-ttu-id="4f015-115">如果设置为 True, 则通过使用 Lync 之外的客户端应用程序加入会议的用户将有机会加入会议。</span><span class="sxs-lookup"><span data-stu-id="4f015-115">If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting.</span></span> <span data-ttu-id="4f015-116">默认值为 False。</span><span class="sxs-lookup"><span data-stu-id="4f015-116">The default value is False.</span></span>  <br/> |
|<span data-ttu-id="4f015-117">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="4f015-117">ShowAlternateJoinOptionsExpanded</span></span>  <br/> |<span data-ttu-id="4f015-118">当设置为 True 时, 用于加入联机会议的备用选项将自动展开并向用户显示。</span><span class="sxs-lookup"><span data-stu-id="4f015-118">When set to True, alternate options for joining an online conference will automatically be expanded and shown to users.</span></span> <span data-ttu-id="4f015-119">当设置为 False (默认值) 时, 这些选项将可用, 但用户将必须显示其自身的选项列表。</span><span class="sxs-lookup"><span data-stu-id="4f015-119">When set to False (the default value), these options will be available, but the user will have to display the list of options for themselves.</span></span>  <br/> |
   
### <a name="to-configure-the-meeting-join-page-by-using-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="4f015-120">使用 Skype for Business Server 2019 命令行管理程序配置会议加入页面</span><span class="sxs-lookup"><span data-stu-id="4f015-120">To configure the meeting join page by using Skype for Business Server 2019 Management Shell</span></span>

1. <span data-ttu-id="4f015-121">启动 Skype for Business Server 2019 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft skype for business server 2019**", 然后单击 " **skype for business 服务器管理外壳程序**"。</span><span class="sxs-lookup"><span data-stu-id="4f015-121">Start the Skype for Business Server 2019 Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="4f015-122">运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="4f015-122">Run the following cmdlet:</span></span> 
    
   ```
   Get-CsWebServiceConfiguration
   ```

    <span data-ttu-id="4f015-123">此 cmdlet 返回 web 服务配置设置。</span><span class="sxs-lookup"><span data-stu-id="4f015-123">This cmdlet returns the web service configuration settings.</span></span>
    
3. <span data-ttu-id="4f015-124">运行以下命令, 将参数设置为 True 或 False, 具体取决于你的首选项 (有关此 cmdlet 的参数的详细信息, 请参阅[Skype For Business Server Management Shell](../../SfbServer/manage/management-shell.md)文档):</span><span class="sxs-lookup"><span data-stu-id="4f015-124">Run the following command, with the parameters set to True or False, depending on your preference (for details about the parameters for this cmdlet, see the [Skype for Business Server Management Shell](../../SfbServer/manage/management-shell.md) documentation):</span></span>
    
   ```
   Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True
   ```


