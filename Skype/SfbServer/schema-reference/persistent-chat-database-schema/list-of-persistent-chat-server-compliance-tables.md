---
title: 持久聊天服务器合规性中的表列表 Skype 业务服务器
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: 持久聊天合规性数据库架构由以下表组成。
ms.openlocfilehash: 18c35cc71da43dcf25bb477e81a2471b483ee86d
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874313"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a><span data-ttu-id="0e59b-103">持久聊天服务器合规性中的表列表 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="0e59b-103">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>
 
<span data-ttu-id="0e59b-104">持久聊天合规性数据库架构由以下表组成。</span><span class="sxs-lookup"><span data-stu-id="0e59b-104">The Persistent Chat compliance database schema consists of the following tables.</span></span>
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a><span data-ttu-id="0e59b-105">持久聊天服务器合规性表的列表</span><span class="sxs-lookup"><span data-stu-id="0e59b-105">List of Persistent Chat Server Compliance Tables</span></span>

|<span data-ttu-id="0e59b-106">**表格**</span><span class="sxs-lookup"><span data-stu-id="0e59b-106">**Table**</span></span>|<span data-ttu-id="0e59b-107">**说明**</span><span class="sxs-lookup"><span data-stu-id="0e59b-107">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="0e59b-108">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="0e59b-108">tblComplianceData</span></span>](tblcompliancedata.md) <br/> |<span data-ttu-id="0e59b-109">包含配置的适配器尚未处理的合规性事件。</span><span class="sxs-lookup"><span data-stu-id="0e59b-109">Contains the compliance events that have not yet been processed by the configured adapter.</span></span>  <br/> <span data-ttu-id="0e59b-110">此表包含持久聊天相关的事件，如聊天消息和文件下载。</span><span class="sxs-lookup"><span data-stu-id="0e59b-110">This table includes Persistent Chat-related events, such as chat messages and file downloads.</span></span> <span data-ttu-id="0e59b-111">（参与者事件跟踪由 tblComplianceParticipant 表。）</span><span class="sxs-lookup"><span data-stu-id="0e59b-111">(Participant events are tracked by the tblComplianceParticipant table.)</span></span>  <br/> <span data-ttu-id="0e59b-112">（处理该表中的事件的服务器排列 tblComplianceFanout 表中。）</span><span class="sxs-lookup"><span data-stu-id="0e59b-112">(The servers that processed the events in this table are listed in the tblComplianceFanout table.)</span></span>  <br/> |
|[<span data-ttu-id="0e59b-113">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="0e59b-113">tblComplianceFanout</span></span>](tblcompliancefanout.md) <br/> |<span data-ttu-id="0e59b-114">包含处理合规性事件的服务器。</span><span class="sxs-lookup"><span data-stu-id="0e59b-114">Contains the servers that processed a compliance event.</span></span> <span data-ttu-id="0e59b-115">此表紧密结合 tblComplianceData 表。</span><span class="sxs-lookup"><span data-stu-id="0e59b-115">This table is tightly coupled with the tblComplianceData table.</span></span>  <br/> |
|[<span data-ttu-id="0e59b-116">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="0e59b-116">tblComplianceParticipant</span></span>](tblcomplianceparticipant.md) <br/> |<span data-ttu-id="0e59b-117">包含每个聊天服务和每台服务器的当前参与者。</span><span class="sxs-lookup"><span data-stu-id="0e59b-117">Contains current participants per chat service and per server.</span></span> <span data-ttu-id="0e59b-118">维护根据从持久聊天服务接收的联接和部件合规性事件。</span><span class="sxs-lookup"><span data-stu-id="0e59b-118">It is maintained based on join and part compliance events received from the Persistent Chat service.</span></span>  <br/> |
|[<span data-ttu-id="0e59b-119">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="0e59b-119">tblComplianceState</span></span>](tblcompliancestate.md) <br/> |<span data-ttu-id="0e59b-120">包含池范围的合规性状态信息。</span><span class="sxs-lookup"><span data-stu-id="0e59b-120">Contains pool-wide compliance state information.</span></span>  <br/> |
   

