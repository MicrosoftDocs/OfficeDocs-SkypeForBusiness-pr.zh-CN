---
title: 旧版合并
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.LegacyMergeAddPicPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 085fde15-e33a-4d95-8d06-4da1d5d7c770
ROBOTS: NOINDEX, NOFOLLOW
description: Web 会议外部 FQDN 允许外部用户加入本地会议。 输入旧版 Edge 服务器的 web 会议外部接口的完全限定的域名（FQDN）。
ms.openlocfilehash: 8572436ac1f72b5aed611dbaee53e93b68e98e81
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41795363"
---
# <a name="legacy-merge"></a><span data-ttu-id="c7a00-104">旧版合并</span><span class="sxs-lookup"><span data-stu-id="c7a00-104">Legacy Merge</span></span>

<span data-ttu-id="c7a00-105">**Web 会议外部 FQDN**允许外部用户加入本地会议。</span><span class="sxs-lookup"><span data-stu-id="c7a00-105">The **Web Conferencing external FQDN** permits external users to join on-premises meetings.</span></span> <span data-ttu-id="c7a00-106">输入旧版 Edge 服务器的 web 会议外部接口的完全限定的域名（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="c7a00-106">Enter the fully qualified domain name (FQDN) of the web conferencing external interface of the legacy Edge Server.</span></span>

<span data-ttu-id="c7a00-107">**443**的**外部 Web 会议外部端口**值是为会议客户端配置的默认传输控制协议（TCP）会话初始协议（SIP）端口。</span><span class="sxs-lookup"><span data-stu-id="c7a00-107">The **External Web Conferencing external port** value of **443** is the default Transmission Control Protocol (TCP) Session Initiation Protocol (SIP) port configured for conferencing clients.</span></span> <span data-ttu-id="c7a00-108">如果未使用默认值，请更新 "**外部 Web 会议外部端口**" 值。</span><span class="sxs-lookup"><span data-stu-id="c7a00-108">If the default value was not used, update the **External Web Conferencing external port** value.</span></span>

<span data-ttu-id="c7a00-109">如果计划将此 edge 服务器用于联盟，请选中 "**此边缘池用于联盟和公用 IM 连接**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="c7a00-109">Select the **This Edge pool is used for federation and public IM connectivity** check box if you plan to use this Edge Server for federation.</span></span> <span data-ttu-id="c7a00-110">如果您部署了多个边缘服务器，则仅为联盟启用其中一个。</span><span class="sxs-lookup"><span data-stu-id="c7a00-110">If you have multiple Edge Servers deployed, only one of them will be enabled for federation.</span></span> <span data-ttu-id="c7a00-111">如果未选中此框，并且你稍后决定要启用联盟，则必须再次运行拓扑生成器合并向导，并发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="c7a00-111">If you do not check this box and you decide later that you want to enable federation, you must run the Topology Builder Merge wizard again, as well as publish your topology.</span></span> <span data-ttu-id="c7a00-112">有关详细信息，请参阅[第4阶段：合并拓扑](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx)。</span><span class="sxs-lookup"><span data-stu-id="c7a00-112">For details, see [Phase 4: Merge Topologies](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx).</span></span>


