---
title: 在 Skype for Business Server 2015 中测试电话拨入式会议
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4ccbfd4-6075-466f-b459-20561318803d
description: 摘要： 了解如何测试业务服务器 2015 Skype 在拨入会议。
ms.openlocfilehash: 9df525710513dbccc2fd488dc9bb5a6f7ed49200
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="test-dial-in-conferencing-in-skype-for-business-server-2015"></a><span data-ttu-id="a66a4-103">在 Skype for Business Server 2015 中测试电话拨入式会议</span><span class="sxs-lookup"><span data-stu-id="a66a4-103">Test dial-in conferencing in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a66a4-104">**摘要：**了解如何测试业务服务器 2015 Skype 在拨入会议。</span><span class="sxs-lookup"><span data-stu-id="a66a4-104">**Summary:** Learn how to test dial-in conferencing in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="a66a4-105">最终验证电话拨入式会议配置后，你可以搜索具有尚未被任何访问号码使用的电话拨入式会议区域的拨号计划，还可以搜索未指定电话拨入式会议区域的访问号码。</span><span class="sxs-lookup"><span data-stu-id="a66a4-105">As final verification of your dial-in conferencing configuration, you can search for dial plans that have a dial-in conferencing region that is not used by any access number and for access numbers that have not specified a dial-in conferencing region.</span></span> <span data-ttu-id="a66a4-106">你还应验证电话拨入式会议设置网页和拨入访问号码是否可以正常使用。</span><span class="sxs-lookup"><span data-stu-id="a66a4-106">You should also verify that the Dial-in Conferencing Settings webpage and the dial-in access numbers work correctly.</span></span>
  
## <a name="find-dial-plans-with-a-dial-in-conferencing-region-that-is-not-used-by-an-access-number"></a><span data-ttu-id="a66a4-107">查找具有尚未被访问号码使用的电话拨入式会议区域的拨号计划</span><span class="sxs-lookup"><span data-stu-id="a66a4-107">Find dial plans with a dial-in conferencing region that is not used by an access number</span></span>

1. <span data-ttu-id="a66a4-108">以  RTCUniversalServerAdmins  组成员或者  Cs-ServerAdministrator  或  CsAdministrator  角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="a66a4-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="a66a4-109">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="a66a4-109">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="a66a4-110">在命令提示符下，运行以下内容：</span><span class="sxs-lookup"><span data-stu-id="a66a4-110">Run the following at the command prompt:</span></span>
    
  ```
  Get-CsDialinConferencingAccessNumber -EmptyRegion
  ```

    <span data-ttu-id="a66a4-111">此 cmdlet 返回具有尚未被访问号码使用的电话拨入式会议区域的所有拨号计划。</span><span class="sxs-lookup"><span data-stu-id="a66a4-111">This cmdlet returns all of the dial plans that have a dial-in conferencing region that is not used by an access number.</span></span>
    
<span data-ttu-id="a66a4-112">有关详细信息，请参阅[获取 CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="a66a4-112">For more information, see [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="find-access-numbers-without-assigned-regions"></a><span data-ttu-id="a66a4-113">查找未分配区域的访问号码</span><span class="sxs-lookup"><span data-stu-id="a66a4-113">Find access numbers without assigned regions</span></span>

1. <span data-ttu-id="a66a4-114">以  RTCUniversalServerAdmins  组成员或者  Cs-ServerAdministrator  或  CsAdministrator  角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="a66a4-114">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="a66a4-115">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="a66a4-115">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="a66a4-116">在命令提示符下，运行以下内容：</span><span class="sxs-lookup"><span data-stu-id="a66a4-116">Run the following at the command prompt:</span></span>
    
  ```
  Get-CsDialinConferencingAccessNumber -Region NULL
  ```

    <span data-ttu-id="a66a4-117">此 cmdlet 返回尚未与区域关联的所有电话拨入式会议访问号码。</span><span class="sxs-lookup"><span data-stu-id="a66a4-117">This cmdlet returns all the dial-in conferencing access numbers that are not associated with a region.</span></span>
    
<span data-ttu-id="a66a4-118">有关详细信息，请参阅[获取 CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="a66a4-118">For more information, see [Get-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingaccessnumber?view=skype-ps).</span></span>
  
## <a name="test-webpage-and-access-numbers"></a><span data-ttu-id="a66a4-119">测试网页和访问号码</span><span class="sxs-lookup"><span data-stu-id="a66a4-119">Test webpage and access numbers</span></span>

<span data-ttu-id="a66a4-120">要验证“电话拨入式会议设置”网页和拨入访问号码是否工作正常，您需要执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a66a4-120">To verify that the Dial-in Conferencing Settings webpage and the dial-in access numbers work correctly, you need to do the following:</span></span>
  
- <span data-ttu-id="a66a4-121">通过登录简单 URL 来测试“电话拨入式会议设置”网页。</span><span class="sxs-lookup"><span data-stu-id="a66a4-121">Test the Dial-in Conferencing Settings webpage by signing in to the simple URL.</span></span>
    
- <span data-ttu-id="a66a4-p102">通过运行本主题后面的脚本来测试该访问号码在特定池中是否工作正常。此脚本模拟对访问号码的呼叫。要使用此脚本，需要提供该特定池承载的一个统一通信 (UC) 客户端的 SIP 地址和凭据。</span><span class="sxs-lookup"><span data-stu-id="a66a4-p102">Test that access numbers work correctly for a specific pool by running the script later in this topic. This script simulates calls to access numbers. You need the SIP address and credentials of one unified communications (UC) client that is hosted on the specific pool to use this script.</span></span>
    
### <a name="to-test-access-numbers-for-a-specific-pool"></a><span data-ttu-id="a66a4-125">测试特定池的访问号码</span><span class="sxs-lookup"><span data-stu-id="a66a4-125">To test access numbers for a specific pool</span></span>

1. <span data-ttu-id="a66a4-126">以  RTCUniversalServerAdmins  组成员或者  Cs-ServerAdministrator  或  CsAdministrator  角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="a66a4-126">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="a66a4-127">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="a66a4-127">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="a66a4-128">在命令提示符下，运行以下内容：</span><span class="sxs-lookup"><span data-stu-id="a66a4-128">Run the following at the command prompt:</span></span>
    
  ```
  $credentials = Get-Credential
   User name:  testuser1@contoso.com
   Password:  ********
Test-CsDialInConferencing -UserSipAddress sip:testuser1@contoso.com -UserCredential $credentials -TargetFqdn <serverName>.<domainName>.com -Verbose

  ```

    <span data-ttu-id="a66a4-129">得出的报告将显示 Success 或 Failure，以及具体的诊断信息。</span><span class="sxs-lookup"><span data-stu-id="a66a4-129">The resulting report shows either Success or Failure, along with specific diagnostic information.</span></span> <span data-ttu-id="a66a4-130">-详细标记提供更详细的有关数字找多少访问的信息以及有关它们的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a66a4-130">The -Verbose flag provides more detailed information about how many access numbers were found and details about them.</span></span>
    
<span data-ttu-id="a66a4-131">有关详细信息，请参阅[测试 CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="a66a4-131">For more information, see [Test-CsDialInConferencing](https://docs.microsoft.com/powershell/module/skype/test-csdialinconferencing?view=skype-ps).</span></span>
  

