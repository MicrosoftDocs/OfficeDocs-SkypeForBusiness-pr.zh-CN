---
title: 持久的聊天服务器的法规遵从性中的表列表 Skype 业务服务器
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: 持续聊天的法规遵从性数据库架构包含，以下各表。
ms.openlocfilehash: 801e8d5457a26ef968f700df16a68d36560548c5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a><span data-ttu-id="a958d-103">持久的聊天服务器的法规遵从性中的表列表 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="a958d-103">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>
 
<span data-ttu-id="a958d-104">持续聊天的法规遵从性数据库架构包含，以下各表。</span><span class="sxs-lookup"><span data-stu-id="a958d-104">The Persistent Chat compliance database schema consists of the following tables.</span></span>
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a><span data-ttu-id="a958d-105">持久的聊天服务器的法规遵从性表的列表</span><span class="sxs-lookup"><span data-stu-id="a958d-105">List of Persistent Chat Server Compliance Tables</span></span>

|<span data-ttu-id="a958d-106">**表**</span><span class="sxs-lookup"><span data-stu-id="a958d-106">**Table**</span></span>|<span data-ttu-id="a958d-107">**说明**</span><span class="sxs-lookup"><span data-stu-id="a958d-107">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="a958d-108">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="a958d-108">tblComplianceData</span></span>](tblcompliancedata.md) <br/> |<span data-ttu-id="a958d-109">包含配置适配器尚未处理的法规遵从性事件。</span><span class="sxs-lookup"><span data-stu-id="a958d-109">Contains the compliance events that have not yet been processed by the configured adapter.</span></span>  <br/> <span data-ttu-id="a958d-110">此表包括持久聊天相关的事件，如聊天消息和文件下载。</span><span class="sxs-lookup"><span data-stu-id="a958d-110">This table includes Persistent Chat-related events, such as chat messages and file downloads.</span></span> <span data-ttu-id="a958d-111">（参与者事件进行跟踪的 tblComplianceParticipant 表。）</span><span class="sxs-lookup"><span data-stu-id="a958d-111">(Participant events are tracked by the tblComplianceParticipant table.)</span></span>  <br/> <span data-ttu-id="a958d-112">（服务器处理此表中的事件表中列出 tblComplianceFanout。）</span><span class="sxs-lookup"><span data-stu-id="a958d-112">(The servers that processed the events in this table are listed in the tblComplianceFanout table.)</span></span>  <br/> |
|[<span data-ttu-id="a958d-113">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="a958d-113">tblComplianceFanout</span></span>](tblcompliancefanout.md) <br/> |<span data-ttu-id="a958d-114">包含处理法规遵从性事件的服务器。</span><span class="sxs-lookup"><span data-stu-id="a958d-114">Contains the servers that processed a compliance event.</span></span> <span data-ttu-id="a958d-115">此表被紧密关联的 tblComplianceData 表。</span><span class="sxs-lookup"><span data-stu-id="a958d-115">This table is tightly coupled with the tblComplianceData table.</span></span>  <br/> |
|[<span data-ttu-id="a958d-116">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="a958d-116">tblComplianceParticipant</span></span>](tblcomplianceparticipant.md) <br/> |<span data-ttu-id="a958d-117">包含当前参与者每个聊天服务，每个服务器。</span><span class="sxs-lookup"><span data-stu-id="a958d-117">Contains current participants per chat service and per server.</span></span> <span data-ttu-id="a958d-118">它维护基于联接和部分从持久聊天服务接收到的法规遵从性事件。</span><span class="sxs-lookup"><span data-stu-id="a958d-118">It is maintained based on join and part compliance events received from the Persistent Chat service.</span></span>  <br/> |
|[<span data-ttu-id="a958d-119">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="a958d-119">tblComplianceState</span></span>](tblcompliancestate.md) <br/> |<span data-ttu-id="a958d-120">包含池范围的法规遵从性状态的信息。</span><span class="sxs-lookup"><span data-stu-id="a958d-120">Contains pool-wide compliance state information.</span></span>  <br/> |
   

