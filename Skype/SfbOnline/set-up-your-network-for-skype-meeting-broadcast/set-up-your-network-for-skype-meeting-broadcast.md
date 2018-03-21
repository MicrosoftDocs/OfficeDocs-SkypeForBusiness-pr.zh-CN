---
title: "设置 Skype 会议直播网络"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.date: 01/22/2018
ms.topic: article
ms.assetid: dfa736b9-4920-4f48-b8c0-b5487ec6086f
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- SMB
description: Learn about the Skype Meeting Broadcast feature of Skype for Business Online that enables you to schedule, produce, and broadcast meetings or events to large online audiences up to 10,000 attendees.
ms.openlocfilehash: 262177a81066f6ee81cc0ebf1718eca70421ecc3
ms.sourcegitcommit: 371a699df0c13f44d2cb6511ba7eaafe047be92c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2018
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a><span data-ttu-id="e024f-103">设置 Skype 会议直播网络</span><span class="sxs-lookup"><span data-stu-id="e024f-103">Set up your network for Skype Meeting Broadcast</span></span>

<span data-ttu-id="e024f-104">[启用 Skype 会议广播](enable-skype-meeting-broadcast.md)Skype 会议广播之后，您需要配置您的网络。</span><span class="sxs-lookup"><span data-stu-id="e024f-104">After you [Enable Skype Meeting Broadcast](enable-skype-meeting-broadcast.md) Skype Meeting Broadcast, you need to configure your network.</span></span> <span data-ttu-id="e024f-105">如果要为您的公司外部的人员担任研讨会和其他广播，请执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="e024f-105">Do this step if you want to hold webinars and other broadcasts for people outside of your business.</span></span>
  
<span data-ttu-id="e024f-106">如果你没有配置防火墙方面的经验，请考虑聘用 [Microsoft 合作伙伴](https://go.microsoft.com/fwlink/?linkid=391089)为你执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="e024f-106">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>
  
<span data-ttu-id="e024f-107">若要跳过此步骤，以便对广播邀请到您联盟改为添加另一个业务按照中[允许用户与外部的业务用户的 Skype](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)的步骤。</span><span class="sxs-lookup"><span data-stu-id="e024f-107">To skip this step and instead add another business to your federation so you can invite them to broadcasts, follow the steps in [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span>
  
## <a name="step-1-set-up-allowed-domains"></a><span data-ttu-id="e024f-108">步骤 1： 设置允许域</span><span class="sxs-lookup"><span data-stu-id="e024f-108">Step 1: Set up allowed domains</span></span>

<span data-ttu-id="e024f-109">使用**一个**下列方法之一来设置允许的域：</span><span class="sxs-lookup"><span data-stu-id="e024f-109">Use **one** of the following methods to set up allowed domains:</span></span>
  
### 

 <span data-ttu-id="e024f-110">**方法 1： 使用 Office 365 管理中心**</span><span class="sxs-lookup"><span data-stu-id="e024f-110">**Method 1: Use the Office 365 admin center**</span></span>
  
1. <span data-ttu-id="e024f-111">请转到**Office 365 管理的中心**，然后在左侧的导航中，单击**设置** > **服务&amp;的外接程序**，然后选择**为公司 Skype**。</span><span class="sxs-lookup"><span data-stu-id="e024f-111">Go to the **Office 365 admin center** and then in the left nav, click **Settings** > **Services &amp; add-ins**, and then choose **Skype for Business**.</span></span>
    
2. <span data-ttu-id="e024f-112">在**域的例外情况**下**外部共享**页中，选择**所有域都被都阻止，但**，并输入下面的域中，使用逗号 （，） 分隔：</span><span class="sxs-lookup"><span data-stu-id="e024f-112">On the **External sharing** page under **Domain exceptions**, select **All domains are blocked except**, and enter the following domains, separated with a comma (,):</span></span>
    
  - <span data-ttu-id="e024f-113">noammeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="e024f-113">noammeetings.lync.com</span></span>
    
  - <span data-ttu-id="e024f-114">emeameetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="e024f-114">emeameetings.lync.com</span></span>
    
  - <span data-ttu-id="e024f-115">apacmeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="e024f-115">apacmeetings.lync.com</span></span>
    
  - <span data-ttu-id="e024f-116">resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="e024f-116">resources.lync.com</span></span>
    
3. <span data-ttu-id="e024f-117">单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="e024f-117">Click **Save**.</span></span>
    
### 

 <span data-ttu-id="e024f-118">**方法 2： 使用 Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="e024f-118">**Method 2: Use Windows PowerShell**</span></span>
  
- <span data-ttu-id="e024f-119">从**开始菜单**中，用鼠标右键单击**Windows PowerShell** ，单击**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="e024f-119">From the **Start Menu**, right-click **Windows PowerShell** and click **Run as administrator**.</span></span> <span data-ttu-id="e024f-120">In the **Windows PowerShell** window, type each line and press Enter.</span><span class="sxs-lookup"><span data-stu-id="e024f-120">In the **Windows PowerShell** window, type each line and press Enter.</span></span>
    
  ```
  $r = New-CsEdgeDomainPattern -Domain "noammeetings.lync.com"
  ```

  ```
  $s = New-CsEdgeDomainPattern -Domain "emeameetings.lync.com"
  ```

  ```
  $t = New-CsEdgeDomainPattern -Domain "apacmeetings.lync.com"
  ```

  ```
  $n = New-CsEdgeDomainPattern -Domain "resources.lync.com"
  ```

  ```
  $newAllowList = New-CsEdgeAllowList -AllowedDomain $r,$s,$t,$n
  ```

  ```
  Set-CsTenantFederationConfiguration -AllowedDomains $newAllowList
  ```

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a><span data-ttu-id="e024f-121">步骤 2： 添加 Skype 会议广播域、 Url 和 IP 地址</span><span class="sxs-lookup"><span data-stu-id="e024f-121">Step 2: Add Skype Meeting Broadcast domains, URLs, and IP addresses</span></span>

<span data-ttu-id="e024f-122">在安装过程中的第二步是第一次添加域的需要然后添加 IP 地址和 Url 所需的 Skype 会议广播工作。</span><span class="sxs-lookup"><span data-stu-id="e024f-122">The second step in the setup process is for you to first add domains that are needed and then add IP addresses and URLs that are required for Skype Meeting Broadcast to work.</span></span>
  
- <span data-ttu-id="e024f-123">**添加所需的 Skype 的在线业务的端点 Url，都需要通过查看哪些 IP 地址**[这里](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo)。</span><span class="sxs-lookup"><span data-stu-id="e024f-123">**Add the required Skype for Business Online endpoint URLs and IP addresses by seeing which ones are required**[here](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).</span></span>
    
## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a><span data-ttu-id="e024f-124">在混合部署和组织中设置 Skype 会议直播</span><span class="sxs-lookup"><span data-stu-id="e024f-124">Set up Skype Meeting Broadcast in Hybrid deployments and organizations</span></span>

<span data-ttu-id="e024f-125">如果您具有的业务服务器 2015年 Skype 的在线业务的组织和内部部署 Lync Server 2010、 Microsoft Lync Server 2013 和 Skype 和具有两个用户在线，内部，有需要为在其他安装步骤除了上面来使您的内部组织与 Skype 通信业务在线，并允许所有的用户能够创建并加入 Skype 会议广播的。</span><span class="sxs-lookup"><span data-stu-id="e024f-125">If you have a Skype for Business Online organization and an on-premises deployment of Lync Server 2010, Microsoft Lync Server 2013, and Skype for Business Server 2015 and have users both online and on-premises, there are other setup steps that you will need to do in addition to the ones above to enable your on-premises organization to communicate with Skype for Business Online and allow all of your users to be able to create and join a Skype Meeting Broadcast.</span></span> <span data-ttu-id="e024f-126">若要查看具体要求，请参阅[为 Skype 会议直播配置本地部署](https://go.microsoft.com/fwlink/?LinkId=617070)。</span><span class="sxs-lookup"><span data-stu-id="e024f-126">To see what those requirements are, see [Configure your on-premises deployment for Skype Meeting Broadcast](https://go.microsoft.com/fwlink/?LinkId=617070).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="e024f-127">相关主题</span><span class="sxs-lookup"><span data-stu-id="e024f-127">Related topics</span></span>

[<span data-ttu-id="e024f-128">启用 Skype 会议直播</span><span class="sxs-lookup"><span data-stu-id="e024f-128">Enable Skype Meeting Broadcast</span></span>](enable-skype-meeting-broadcast.md)
  
[<span data-ttu-id="e024f-129">Office 365 URL 和 IP 地址范围</span><span class="sxs-lookup"><span data-stu-id="e024f-129">Office 365 URLs and IP address ranges</span></span>](http://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[<span data-ttu-id="e024f-130">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="e024f-130">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
## <a name="feedback"></a><span data-ttu-id="e024f-131">反馈意见？</span><span class="sxs-lookup"><span data-stu-id="e024f-131">Feedback?</span></span>
<span data-ttu-id="e024f-132">提供产品反馈意见或让我们知道我们所执行的信息，请参阅[Skype 业务反馈](https://www.skypefeedback.com)。</span><span class="sxs-lookup"><span data-stu-id="e024f-132">To provide product feedback or to let us know how we're doing, see [Skype for Business Feedback](https://www.skypefeedback.com).</span></span>
