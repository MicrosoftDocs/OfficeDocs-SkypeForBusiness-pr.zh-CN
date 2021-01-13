---
title: 旧版合并
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.LegacyMergeAddPicPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 085fde15-e33a-4d95-8d06-4da1d5d7c770
description: “Web 会议外部 FQDN”允许外部用户加入内部会议。 输入旧版边缘服务器的 Web 会议外部接口的完全限定的域名 (FQDN)。
ms.openlocfilehash: b49d8ed17bdc56050e00216c5506b85db2b1d3aa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832992"
---
# <a name="legacy-merge"></a><span data-ttu-id="cc5dc-104">旧版合并</span><span class="sxs-lookup"><span data-stu-id="cc5dc-104">Legacy Merge</span></span>

<span data-ttu-id="cc5dc-p102">“Web 会议外部 FQDN”允许外部用户加入内部会议。输入旧版边缘服务器的 Web 会议外部接口的完全限定的域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="cc5dc-p102">The **Web Conferencing external FQDN** permits external users to join on-premises meetings. Enter the fully qualified domain name (FQDN) of the web conferencing external interface of the legacy Edge Server.</span></span>

<span data-ttu-id="cc5dc-p103">**“外部 Web 会议外部端口”** 值 **“443”** 是为会议客户端配置的默认传输控制协议 (TCP) 会话初始协议 (SIP) 端口。如果未使用默认值，请更新 **“外部 Web 会议外部端口”** 值。</span><span class="sxs-lookup"><span data-stu-id="cc5dc-p103">The **External Web Conferencing external port** value of **443** is the default Transmission Control Protocol (TCP) Session Initiation Protocol (SIP) port configured for conferencing clients. If the default value was not used, update the **External Web Conferencing external port** value.</span></span>

<span data-ttu-id="cc5dc-109">如果计划将此边缘服务器用于联盟，请选中“此边缘池用于联盟和公共 IM 连接”复选框。</span><span class="sxs-lookup"><span data-stu-id="cc5dc-109">Select the **This Edge pool is used for federation and public IM connectivity** check box if you plan to use this Edge Server for federation.</span></span> <span data-ttu-id="cc5dc-110">如果部署了多台边缘服务器，则只会为其中一台边缘服务器启用联盟。</span><span class="sxs-lookup"><span data-stu-id="cc5dc-110">If you have multiple Edge Servers deployed, only one of them will be enabled for federation.</span></span> <span data-ttu-id="cc5dc-111">如果未选中此复选框，但之后决定要启用联盟，则必须再次运行拓扑生成器合并向导并发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="cc5dc-111">If you do not check this box and you decide later that you want to enable federation, you must run the Topology Builder Merge wizard again, as well as publish your topology.</span></span> <span data-ttu-id="cc5dc-112">有关详细信息，请参阅[Phase 4: Merge Topologies](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx)。</span><span class="sxs-lookup"><span data-stu-id="cc5dc-112">For details, see [Phase 4: Merge Topologies](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx).</span></span>


