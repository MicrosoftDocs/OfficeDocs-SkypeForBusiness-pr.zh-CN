---
title: 旧版合并
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.LegacyMergeAddPicPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 085fde15-e33a-4d95-8d06-4da1d5d7c770
description: Web 会议的外部 FQDN 允许外部用户可以加入内部会议。 输入旧边缘服务器的 web 会议外部接口的完全限定的域名 (FQDN)。
ms.openlocfilehash: 09bba6fa5532e85572a1272fde59dc0a1f7a9c1e
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2018
---
# <a name="legacy-merge"></a><span data-ttu-id="487f9-104">旧版合并</span><span class="sxs-lookup"><span data-stu-id="487f9-104">Legacy Merge</span></span>
 
<span data-ttu-id="487f9-105">**Web 会议的外部 FQDN**允许外部用户可以加入内部会议。</span><span class="sxs-lookup"><span data-stu-id="487f9-105">The **Web Conferencing external FQDN** permits external users to join on-premises meetings.</span></span> <span data-ttu-id="487f9-106">输入旧边缘服务器的 web 会议外部接口的完全限定的域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="487f9-106">Enter the fully qualified domain name (FQDN) of the web conferencing external interface of the legacy Edge Server.</span></span>
  
<span data-ttu-id="487f9-107">**外部 Web 会议的外部端口** **443**的值是为会议客户端配置的默认传输控制协议 (TCP) 会话初始协议 (SIP) 端口。</span><span class="sxs-lookup"><span data-stu-id="487f9-107">The **External Web Conferencing external port** value of **443** is the default Transmission Control Protocol (TCP) Session Initiation Protocol (SIP) port configured for conferencing clients.</span></span> <span data-ttu-id="487f9-108">如果不使用默认值，更新**外部 Web 会议的外部端口**值。</span><span class="sxs-lookup"><span data-stu-id="487f9-108">If the default value was not used, update the **External Web Conferencing external port** value.</span></span>
  
<span data-ttu-id="487f9-109">如果您打算对联盟使用此边缘服务器，请选择**此边缘池用于联盟和公共 IM 连接**复选框。</span><span class="sxs-lookup"><span data-stu-id="487f9-109">Select the **This Edge pool is used for federation and public IM connectivity** check box if you plan to use this Edge Server for federation.</span></span> <span data-ttu-id="487f9-110">如果您有多台边缘服务器部署，其中的一个仅将启用联盟。</span><span class="sxs-lookup"><span data-stu-id="487f9-110">If you have multiple Edge Servers deployed, only one of them will be enabled for federation.</span></span> <span data-ttu-id="487f9-111">如果不选中此框，并且您以后决定要启用联盟，您必须再次运行拓扑生成器合并向导，以及发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="487f9-111">If you do not check this box and you decide later that you want to enable federation, you must run the Topology Builder Merge wizard again, as well as publish your topology.</span></span> <span data-ttu-id="487f9-112">有关详细信息，请参阅[第 4 阶段： 合并拓扑](http://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx)。</span><span class="sxs-lookup"><span data-stu-id="487f9-112">For details, see [Phase 4: Merge Topologies](http://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx).</span></span>
  

