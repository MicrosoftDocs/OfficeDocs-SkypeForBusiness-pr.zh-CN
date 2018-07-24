---
title: 旧版合并
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.LegacyMergeAddPicPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 085fde15-e33a-4d95-8d06-4da1d5d7c770
ROBOTS: NOINDEX, NOFOLLOW
description: Web 会议的外部 FQDN 允许外部用户可以加入内部会议。 输入旧边缘服务器的 web 会议外部接口的完全限定的域名 (FQDN)。
ms.openlocfilehash: 7ba81731c463196eda4c47dc615f27eb15246259
ms.sourcegitcommit: 1f7299f535ec6b34f92301b4abc14d8922492eeb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "21069622"
---
# <a name="legacy-merge"></a><span data-ttu-id="7ef90-104">旧版合并</span><span class="sxs-lookup"><span data-stu-id="7ef90-104">Legacy Merge</span></span>
 
<span data-ttu-id="7ef90-105">**Web 会议的外部 FQDN**允许外部用户可以加入内部会议。</span><span class="sxs-lookup"><span data-stu-id="7ef90-105">The **Web Conferencing external FQDN** permits external users to join on-premises meetings.</span></span> <span data-ttu-id="7ef90-106">输入旧边缘服务器的 web 会议外部接口的完全限定的域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="7ef90-106">Enter the fully qualified domain name (FQDN) of the web conferencing external interface of the legacy Edge Server.</span></span>
  
<span data-ttu-id="7ef90-107">**外部 Web 会议的外部端口** **443**的值是为会议客户端配置的默认传输控制协议 (TCP) 会话初始协议 (SIP) 端口。</span><span class="sxs-lookup"><span data-stu-id="7ef90-107">The **External Web Conferencing external port** value of **443** is the default Transmission Control Protocol (TCP) Session Initiation Protocol (SIP) port configured for conferencing clients.</span></span> <span data-ttu-id="7ef90-108">如果不使用默认值，更新**外部 Web 会议的外部端口**值。</span><span class="sxs-lookup"><span data-stu-id="7ef90-108">If the default value was not used, update the **External Web Conferencing external port** value.</span></span>
  
<span data-ttu-id="7ef90-109">如果您打算对联盟使用此边缘服务器，请选择**此边缘池用于联盟和公共 IM 连接**复选框。</span><span class="sxs-lookup"><span data-stu-id="7ef90-109">Select the **This Edge pool is used for federation and public IM connectivity** check box if you plan to use this Edge Server for federation.</span></span> <span data-ttu-id="7ef90-110">如果您有多台边缘服务器部署，其中的一个仅将启用联盟。</span><span class="sxs-lookup"><span data-stu-id="7ef90-110">If you have multiple Edge Servers deployed, only one of them will be enabled for federation.</span></span> <span data-ttu-id="7ef90-111">如果不选中此框，并且您以后决定要启用联盟，您必须再次运行拓扑生成器合并向导，以及发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="7ef90-111">If you do not check this box and you decide later that you want to enable federation, you must run the Topology Builder Merge wizard again, as well as publish your topology.</span></span> <span data-ttu-id="7ef90-112">有关详细信息，请参阅[第 4 阶段： 合并拓扑](http://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx)。</span><span class="sxs-lookup"><span data-stu-id="7ef90-112">For details, see [Phase 4: Merge Topologies](http://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx).</span></span>
  

