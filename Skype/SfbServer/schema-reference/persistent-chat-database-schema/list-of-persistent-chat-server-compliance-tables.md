---
title: 持久聊天服务器合规性中的表列表 Skype 业务服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: 持久聊天合规性数据库架构由以下表组成。
ms.openlocfilehash: e17b2e52bdeb65ff4c77377cb913da212f20ecf0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929887"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a><span data-ttu-id="c06a8-103">持久聊天服务器合规性中的表列表 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="c06a8-103">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>
 
<span data-ttu-id="c06a8-104">持久聊天合规性数据库架构由以下表组成。</span><span class="sxs-lookup"><span data-stu-id="c06a8-104">The Persistent Chat compliance database schema consists of the following tables.</span></span>
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a><span data-ttu-id="c06a8-105">持久聊天服务器合规性表的列表</span><span class="sxs-lookup"><span data-stu-id="c06a8-105">List of Persistent Chat Server Compliance Tables</span></span>

|<span data-ttu-id="c06a8-106">**表格**</span><span class="sxs-lookup"><span data-stu-id="c06a8-106">**Table**</span></span>|<span data-ttu-id="c06a8-107">**说明**</span><span class="sxs-lookup"><span data-stu-id="c06a8-107">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="c06a8-108">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="c06a8-108">tblComplianceData</span></span>](tblcompliancedata.md) <br/> |<span data-ttu-id="c06a8-109">包含配置的适配器尚未处理的合规性事件。</span><span class="sxs-lookup"><span data-stu-id="c06a8-109">Contains the compliance events that have not yet been processed by the configured adapter.</span></span>  <br/> <span data-ttu-id="c06a8-110">此表包含持久聊天相关的事件，如聊天消息和文件下载。</span><span class="sxs-lookup"><span data-stu-id="c06a8-110">This table includes Persistent Chat-related events, such as chat messages and file downloads.</span></span> <span data-ttu-id="c06a8-111">（参与者事件跟踪由 tblComplianceParticipant 表。）</span><span class="sxs-lookup"><span data-stu-id="c06a8-111">(Participant events are tracked by the tblComplianceParticipant table.)</span></span>  <br/> <span data-ttu-id="c06a8-112">（处理该表中的事件的服务器排列 tblComplianceFanout 表中。）</span><span class="sxs-lookup"><span data-stu-id="c06a8-112">(The servers that processed the events in this table are listed in the tblComplianceFanout table.)</span></span>  <br/> |
|[<span data-ttu-id="c06a8-113">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="c06a8-113">tblComplianceFanout</span></span>](tblcompliancefanout.md) <br/> |<span data-ttu-id="c06a8-114">包含处理合规性事件的服务器。</span><span class="sxs-lookup"><span data-stu-id="c06a8-114">Contains the servers that processed a compliance event.</span></span> <span data-ttu-id="c06a8-115">此表紧密结合 tblComplianceData 表。</span><span class="sxs-lookup"><span data-stu-id="c06a8-115">This table is tightly coupled with the tblComplianceData table.</span></span>  <br/> |
|[<span data-ttu-id="c06a8-116">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="c06a8-116">tblComplianceParticipant</span></span>](tblcomplianceparticipant.md) <br/> |<span data-ttu-id="c06a8-117">包含每个聊天服务和每台服务器的当前参与者。</span><span class="sxs-lookup"><span data-stu-id="c06a8-117">Contains current participants per chat service and per server.</span></span> <span data-ttu-id="c06a8-118">维护根据从持久聊天服务接收的联接和部件合规性事件。</span><span class="sxs-lookup"><span data-stu-id="c06a8-118">It is maintained based on join and part compliance events received from the Persistent Chat service.</span></span>  <br/> |
|[<span data-ttu-id="c06a8-119">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="c06a8-119">tblComplianceState</span></span>](tblcompliancestate.md) <br/> |<span data-ttu-id="c06a8-120">包含池范围的合规性状态信息。</span><span class="sxs-lookup"><span data-stu-id="c06a8-120">Contains pool-wide compliance state information.</span></span>  <br/> |
   

