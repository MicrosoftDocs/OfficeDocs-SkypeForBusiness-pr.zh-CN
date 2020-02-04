---
title: 设置 Skype 会议直播网络
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.topic: article
ms.assetid: dfa736b9-4920-4f48-b8c0-b5487ec6086f
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- SMB
description: Learn about the Skype Meeting Broadcast feature of Skype for Business Online that enables you to schedule, produce, and broadcast meetings or events to large online audiences up to 10,000 attendees.
ms.openlocfilehash: 05e970e7859b361a4ec8c9656aedbe54f0de6f4f
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41706117"
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a><span data-ttu-id="36b3d-103">设置 Skype 会议直播网络</span><span class="sxs-lookup"><span data-stu-id="36b3d-103">Set up your network for Skype Meeting Broadcast</span></span>

<span data-ttu-id="36b3d-104">[启用 Skype 会议直播](enable-skype-meeting-broadcast.md)Skype 会议直播后，您需要配置您的网络。</span><span class="sxs-lookup"><span data-stu-id="36b3d-104">After you [Enable Skype Meeting Broadcast](enable-skype-meeting-broadcast.md) Skype Meeting Broadcast, you need to configure your network.</span></span> <span data-ttu-id="36b3d-105">如果要为您的企业外部的人员保留网络研讨会和其他广播，请执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="36b3d-105">Do this step if you want to hold webinars and other broadcasts for people outside of your business.</span></span>

<span data-ttu-id="36b3d-106">如果你没有配置防火墙方面的经验，请考虑聘用 [Microsoft 合作伙伴](https://go.microsoft.com/fwlink/?linkid=391089)为你执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="36b3d-106">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>

<span data-ttu-id="36b3d-107">若要跳过此步骤，改为将其他企业添加到联盟，以便邀请他们进行广播，请按照[允许用户联系外部 Skype For business 用户](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)中的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="36b3d-107">To skip this step and instead add another business to your federation so you can invite them to broadcasts, follow the steps in [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span>

## <a name="step-1-set-up-allowed-domains"></a><span data-ttu-id="36b3d-108">步骤1：设置允许的域</span><span class="sxs-lookup"><span data-stu-id="36b3d-108">Step 1: Set up allowed domains</span></span>

<span data-ttu-id="36b3d-109">使用下列方法**之一**设置允许的域：</span><span class="sxs-lookup"><span data-stu-id="36b3d-109">Use **one** of the following methods to set up allowed domains:</span></span>

## #

 <span data-ttu-id="36b3d-110">**方法1：使用管理中心**</span><span class="sxs-lookup"><span data-stu-id="36b3d-110">**Method 1: Use the admin center**</span></span>

1. <span data-ttu-id="36b3d-111">转到管理中心，然后在左侧导航栏中，单击 "**设置** > **服务&amp;加载项**"，然后选择 " **Skype for**business"。</span><span class="sxs-lookup"><span data-stu-id="36b3d-111">Go to the admin center and then in the left nav, click **Settings** > **Services &amp; add-ins**, and then choose **Skype for Business**.</span></span>

2. <span data-ttu-id="36b3d-112">在 "**外部共享**" 页面上的 "**域例外**" 下，选择 "**所有域均被阻止，但不**包括"，然后输入以逗号（，）分隔的以下域：</span><span class="sxs-lookup"><span data-stu-id="36b3d-112">On the **External sharing** page under **Domain exceptions**, select **All domains are blocked except**, and enter the following domains, separated with a comma (,):</span></span>

   - <span data-ttu-id="36b3d-113">noammeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="36b3d-113">noammeetings.lync.com</span></span>

   - <span data-ttu-id="36b3d-114">emeameetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="36b3d-114">emeameetings.lync.com</span></span>

   - <span data-ttu-id="36b3d-115">apacmeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="36b3d-115">apacmeetings.lync.com</span></span>

   - <span data-ttu-id="36b3d-116">resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="36b3d-116">resources.lync.com</span></span>

3. <span data-ttu-id="36b3d-117">单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="36b3d-117">Click **Save**.</span></span>

## #

 <span data-ttu-id="36b3d-118">**方法2：使用 Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="36b3d-118">**Method 2: Use Windows PowerShell**</span></span>

- <span data-ttu-id="36b3d-119">在 "**开始" 菜单**上，右键单击 " **Windows PowerShell** "，然后单击 "**以管理员身份运行**"。</span><span class="sxs-lookup"><span data-stu-id="36b3d-119">From the **Start Menu**, right-click **Windows PowerShell** and click **Run as administrator**.</span></span> <span data-ttu-id="36b3d-120">In the **Windows PowerShell** window, type each line and press Enter.</span><span class="sxs-lookup"><span data-stu-id="36b3d-120">In the **Windows PowerShell** window, type each line and press Enter.</span></span>

  ```PowerShell
  $r = New-CsEdgeDomainPattern -Domain "noammeetings.lync.com"
  ```

  ```PowerShell
  $s = New-CsEdgeDomainPattern -Domain "emeameetings.lync.com"
  ```

  ```PowerShell
  $t = New-CsEdgeDomainPattern -Domain "apacmeetings.lync.com"
  ```

  ```PowerShell
  $n = New-CsEdgeDomainPattern -Domain "resources.lync.com"
  ```

  ```PowerShell
  $newAllowList = New-CsEdgeAllowList -AllowedDomain $r,$s,$t,$n
  ```

  ```PowerShell
  Set-CsTenantFederationConfiguration -AllowedDomains $newAllowList
  ```

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a><span data-ttu-id="36b3d-121">步骤2：添加 Skype 会议直播域、Url 和 IP 地址</span><span class="sxs-lookup"><span data-stu-id="36b3d-121">Step 2: Add Skype Meeting Broadcast domains, URLs, and IP addresses</span></span>

<span data-ttu-id="36b3d-122">安装过程中的第二个步骤是：首先添加所需的域，然后添加要使用的 Skype 会议直播所需的 IP 地址和 Url。</span><span class="sxs-lookup"><span data-stu-id="36b3d-122">The second step in the setup process is for you to first add domains that are needed and then add IP addresses and URLs that are required for Skype Meeting Broadcast to work.</span></span>

- <span data-ttu-id="36b3d-123">**通过查看此处需要的内容，添加所需的 Skype For Business Online 终结点 url 和 IP 地址** [](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo)。</span><span class="sxs-lookup"><span data-stu-id="36b3d-123">**Add the required Skype for Business Online endpoint URLs and IP addresses by seeing which ones are required** [here](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).</span></span>

## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a><span data-ttu-id="36b3d-124">在混合部署和组织中设置 Skype 会议直播</span><span class="sxs-lookup"><span data-stu-id="36b3d-124">Set up Skype Meeting Broadcast in Hybrid deployments and organizations</span></span>

<span data-ttu-id="36b3d-125">如果你有 Skype for Business Online 组织和 Lync Server 2010、Microsoft Lync Server 2013 和 Skype for Business Server 2015 的本地部署，并且用户已联机和本地使用，则需要执行其他设置步骤除了上面的组织，让您的本地组织能够与 Skype for business Online 通信，并允许所有用户加入 Skype 会议直播。</span><span class="sxs-lookup"><span data-stu-id="36b3d-125">If you have a Skype for Business Online organization and an on-premises deployment of Lync Server 2010, Microsoft Lync Server 2013, and Skype for Business Server 2015 and have users both online and on-premises, there are other setup steps that you will need to do in addition to the ones above to enable your on-premises organization to communicate with Skype for Business Online and allow all your users to join a Skype Meeting Broadcast.</span></span> <span data-ttu-id="36b3d-126">若要查看具体要求，请参阅[为 Skype 会议直播配置本地部署](https://go.microsoft.com/fwlink/?LinkId=617070)。</span><span class="sxs-lookup"><span data-stu-id="36b3d-126">To see what those requirements are, see [Configure your on-premises deployment for Skype Meeting Broadcast](https://go.microsoft.com/fwlink/?LinkId=617070).</span></span>

## <a name="related-topics"></a><span data-ttu-id="36b3d-127">相关主题</span><span class="sxs-lookup"><span data-stu-id="36b3d-127">Related topics</span></span>

[<span data-ttu-id="36b3d-128">启用 Skype 会议直播</span><span class="sxs-lookup"><span data-stu-id="36b3d-128">Enable Skype Meeting Broadcast</span></span>](enable-skype-meeting-broadcast.md)

[<span data-ttu-id="36b3d-129">Office 365 URL 和 IP 地址范围</span><span class="sxs-lookup"><span data-stu-id="36b3d-129">Office 365 URLs and IP address ranges</span></span>](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[<span data-ttu-id="36b3d-130">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="36b3d-130">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)



