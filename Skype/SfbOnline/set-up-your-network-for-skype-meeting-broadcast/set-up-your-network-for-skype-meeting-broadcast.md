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
ms.openlocfilehash: 513b6f8d677550557293855389eff29dc61c21c1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51106508"
---
# <a name="set-up-your-network-for-skype-meeting-broadcast"></a><span data-ttu-id="85159-103">设置 Skype 会议直播网络</span><span class="sxs-lookup"><span data-stu-id="85159-103">Set up your network for Skype Meeting Broadcast</span></span>

<span data-ttu-id="85159-104">启用 [Skype 会议直播 Skype](enable-skype-meeting-broadcast.md) 会议直播后，需要配置网络。</span><span class="sxs-lookup"><span data-stu-id="85159-104">After you [Enable Skype Meeting Broadcast](enable-skype-meeting-broadcast.md) Skype Meeting Broadcast, you need to configure your network.</span></span> <span data-ttu-id="85159-105">如果要为企业外部人员举办网络研讨会和其他直播，请执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="85159-105">Do this step if you want to hold webinars and other broadcasts for people outside of your business.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="85159-106">Skype for Business Online 将于 2021 年 7 月 31 日停用，此时将结束对该服务的访问。</span><span class="sxs-lookup"><span data-stu-id="85159-106">Skype for Business Online is retiring on July 31, 2021, at which time access to the service will end.</span></span> <span data-ttu-id="85159-107">我们鼓励客户开始升级到 Microsoft Teams，这是 Microsoft 365 中通信和团队合作的核心客户端。</span><span class="sxs-lookup"><span data-stu-id="85159-107">We encourage customers to begin the upgrade to Microsoft Teams, the core client for communications and teamwork in Microsoft 365.</span></span>

<span data-ttu-id="85159-108">如果你没有配置防火墙方面的经验，请考虑聘用 [Microsoft 合作伙伴](https://go.microsoft.com/fwlink/?linkid=391089)为你执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="85159-108">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>

<span data-ttu-id="85159-109">若要跳过此步骤，改为将另一个企业添加到联合身份验证，以便你可以邀请他们加入直播，请按照允许用户联系外部 Skype for Business 用户中的 [步骤操作](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md)。</span><span class="sxs-lookup"><span data-stu-id="85159-109">To skip this step and instead add another business to your federation so you can invite them to broadcasts, follow the steps in [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span>

## <a name="step-1-set-up-allowed-domains"></a><span data-ttu-id="85159-110">步骤 1：设置允许的域</span><span class="sxs-lookup"><span data-stu-id="85159-110">Step 1: Set up allowed domains</span></span>

<span data-ttu-id="85159-111">使用以下 **方法** 之一设置允许的域：</span><span class="sxs-lookup"><span data-stu-id="85159-111">Use **one** of the following methods to set up allowed domains:</span></span>

## #

 <span data-ttu-id="85159-112">**方法 1：使用管理中心**</span><span class="sxs-lookup"><span data-stu-id="85159-112">**Method 1: Use the admin center**</span></span>

1. <span data-ttu-id="85159-113">转到管理中心，然后在左侧导航中，单击"设置服务加载项"，  >  然后选择 **"Skype for Business"。\*\*\*\*&amp;**</span><span class="sxs-lookup"><span data-stu-id="85159-113">Go to the admin center and then in the left nav, click **Settings** > **Services &amp; add-ins**, and then choose **Skype for Business**.</span></span>

2. <span data-ttu-id="85159-114">在"**外部** 共享"页面上的"域例外"下，选择"阻止所有域（除 ）"，然后输入以下域，用逗号分隔 (，) ：</span><span class="sxs-lookup"><span data-stu-id="85159-114">On the **External sharing** page under **Domain exceptions**, select **All domains are blocked except**, and enter the following domains, separated with a comma (,):</span></span>

   - <span data-ttu-id="85159-115">noammeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="85159-115">noammeetings.lync.com</span></span>

   - <span data-ttu-id="85159-116">emeameetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="85159-116">emeameetings.lync.com</span></span>

   - <span data-ttu-id="85159-117">apacmeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="85159-117">apacmeetings.lync.com</span></span>

   - <span data-ttu-id="85159-118">resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="85159-118">resources.lync.com</span></span>

3. <span data-ttu-id="85159-119">单击" **保存**"。</span><span class="sxs-lookup"><span data-stu-id="85159-119">Click **Save**.</span></span>

## #

 <span data-ttu-id="85159-120">**方法 2：使用Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="85159-120">**Method 2: Use Windows PowerShell**</span></span>

- <span data-ttu-id="85159-121">在"**开始"菜单中**，右键 **Windows PowerShell** 并单击"**以管理员角色运行"。**</span><span class="sxs-lookup"><span data-stu-id="85159-121">From the **Start Menu**, right-click **Windows PowerShell** and click **Run as administrator**.</span></span> <span data-ttu-id="85159-122">In the **Windows PowerShell** window, type each line and press Enter.</span><span class="sxs-lookup"><span data-stu-id="85159-122">In the **Windows PowerShell** window, type each line and press Enter.</span></span>

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

## <a name="step-2-add-skype-meeting-broadcast-domains-urls-and-ip-addresses"></a><span data-ttu-id="85159-123">步骤 2：添加 Skype 会议直播域、URL 和 IP 地址</span><span class="sxs-lookup"><span data-stu-id="85159-123">Step 2: Add Skype Meeting Broadcast domains, URLs, and IP addresses</span></span>

<span data-ttu-id="85159-124">设置过程的第二步是先添加所需的域，然后添加 Skype 会议直播正常工作所需的 IP 地址和 URL。</span><span class="sxs-lookup"><span data-stu-id="85159-124">The second step in the setup process is for you to first add domains that are needed and then add IP addresses and URLs that are required for Skype Meeting Broadcast to work.</span></span>

- <span data-ttu-id="85159-125">**通过在此处查看** 所需的 Skype for Business Online 终结点 URL 和 IP 地址，添加 [所需的 URL 和 IP 地址](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo)。</span><span class="sxs-lookup"><span data-stu-id="85159-125">**Add the required Skype for Business Online endpoint URLs and IP addresses by seeing which ones are required** [here](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_lyo).</span></span>

## <a name="set-up-skype-meeting-broadcast-in-hybrid-deployments-and-organizations"></a><span data-ttu-id="85159-126">在混合部署和组织中设置 Skype 会议直播</span><span class="sxs-lookup"><span data-stu-id="85159-126">Set up Skype Meeting Broadcast in Hybrid deployments and organizations</span></span>

<span data-ttu-id="85159-127">如果你有 Skype for Business Online 组织和 Lync Server 2010、Microsoft Lync Server 2013 和 Skype for Business Server 2015 本地部署，并且用户同时在线和本地，除了上述设置步骤之外，还需要执行其他设置步骤，以使你的本地组织能够与 Skype for Business Online 通信并允许你的所有用户加入 Skype 会议直播。</span><span class="sxs-lookup"><span data-stu-id="85159-127">If you have a Skype for Business Online organization and an on-premises deployment of Lync Server 2010, Microsoft Lync Server 2013, and Skype for Business Server 2015 and have users both online and on-premises, there are other setup steps that you will need to do in addition to the ones above to enable your on-premises organization to communicate with Skype for Business Online and allow all your users to join a Skype Meeting Broadcast.</span></span> <span data-ttu-id="85159-128">若要查看具体要求，请参阅[为 Skype 会议直播配置本地部署](../../SfbServer/deploy/configure-skype-meeting-broadcast.md)。</span><span class="sxs-lookup"><span data-stu-id="85159-128">To see what those requirements are, see [Configure your on-premises deployment for Skype Meeting Broadcast](../../SfbServer/deploy/configure-skype-meeting-broadcast.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="85159-129">相关主题</span><span class="sxs-lookup"><span data-stu-id="85159-129">Related topics</span></span>

[<span data-ttu-id="85159-130">启用 Skype 会议直播</span><span class="sxs-lookup"><span data-stu-id="85159-130">Enable Skype Meeting Broadcast</span></span>](enable-skype-meeting-broadcast.md)

[<span data-ttu-id="85159-131">Office 365 URL 和 IP 地址范围</span><span class="sxs-lookup"><span data-stu-id="85159-131">Office 365 URLs and IP address ranges</span></span>](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[<span data-ttu-id="85159-132">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="85159-132">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)