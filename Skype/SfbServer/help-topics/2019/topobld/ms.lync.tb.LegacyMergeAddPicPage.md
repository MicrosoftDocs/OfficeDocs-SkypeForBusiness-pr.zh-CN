---
title: 旧版合并
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.LegacyMergeAddPicPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 085fde15-e33a-4d95-8d06-4da1d5d7c770
ROBOTS: NOINDEX, NOFOLLOW
description: Web 会议外部 FQDN 允许外部用户加入本地会议。 输入旧版 Edge 服务器的 web 会议外部接口的完全限定的域名（FQDN）。
ms.openlocfilehash: 1f2a1e9ca3d3ca20b7b0fe6832a0e394d7fac5ce
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41688335"
---
# <a name="legacy-merge"></a><span data-ttu-id="9ca24-104">旧版合并</span><span class="sxs-lookup"><span data-stu-id="9ca24-104">Legacy Merge</span></span>

<span data-ttu-id="9ca24-105">**Web 会议外部 FQDN**允许外部用户加入本地会议。</span><span class="sxs-lookup"><span data-stu-id="9ca24-105">The **Web Conferencing external FQDN** permits external users to join on-premises meetings.</span></span> <span data-ttu-id="9ca24-106">输入旧版 Edge 服务器的 web 会议外部接口的完全限定的域名（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="9ca24-106">Enter the fully qualified domain name (FQDN) of the web conferencing external interface of the legacy Edge Server.</span></span>

<span data-ttu-id="9ca24-107">**443**的**外部 Web 会议外部端口**值是为会议客户端配置的默认传输控制协议（TCP）会话初始协议（SIP）端口。</span><span class="sxs-lookup"><span data-stu-id="9ca24-107">The **External Web Conferencing external port** value of **443** is the default Transmission Control Protocol (TCP) Session Initiation Protocol (SIP) port configured for conferencing clients.</span></span> <span data-ttu-id="9ca24-108">如果未使用默认值，请更新 "**外部 Web 会议外部端口**" 值。</span><span class="sxs-lookup"><span data-stu-id="9ca24-108">If the default value was not used, update the **External Web Conferencing external port** value.</span></span>

<span data-ttu-id="9ca24-109">如果计划将此 edge 服务器用于联盟，请选中 "**此边缘池用于联盟和公用 IM 连接**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="9ca24-109">Select the **This Edge pool is used for federation and public IM connectivity** check box if you plan to use this Edge Server for federation.</span></span> <span data-ttu-id="9ca24-110">如果您部署了多个边缘服务器，则仅为联盟启用其中一个。</span><span class="sxs-lookup"><span data-stu-id="9ca24-110">If you have multiple Edge Servers deployed, only one of them will be enabled for federation.</span></span> <span data-ttu-id="9ca24-111">如果未选中此框，并且你稍后决定要启用联盟，则必须再次运行拓扑生成器合并向导，并发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="9ca24-111">If you do not check this box and you decide later that you want to enable federation, you must run the Topology Builder Merge wizard again, as well as publish your topology.</span></span> <span data-ttu-id="9ca24-112">有关详细信息，请参阅[第4阶段：合并拓扑](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx)。</span><span class="sxs-lookup"><span data-stu-id="9ca24-112">For details, see [Phase 4: Merge Topologies](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx).</span></span>


