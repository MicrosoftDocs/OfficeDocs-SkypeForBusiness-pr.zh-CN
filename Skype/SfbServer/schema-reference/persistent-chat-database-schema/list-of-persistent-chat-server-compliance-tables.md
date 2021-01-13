---
title: Skype for Business Server 中的持久聊天服务器合规性表列表
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: 持久聊天合规性数据库架构由下表组成。
ms.openlocfilehash: 8fa9c47c2abd28922716cd42c5ff150ddd975393
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813052"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a><span data-ttu-id="b93b5-103">Skype for Business Server 中的持久聊天服务器合规性表列表</span><span class="sxs-lookup"><span data-stu-id="b93b5-103">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>
 
<span data-ttu-id="b93b5-104">持久聊天合规性数据库架构由下表组成。</span><span class="sxs-lookup"><span data-stu-id="b93b5-104">The Persistent Chat compliance database schema consists of the following tables.</span></span>
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a><span data-ttu-id="b93b5-105">持久聊天服务器合规性表的列表</span><span class="sxs-lookup"><span data-stu-id="b93b5-105">List of Persistent Chat Server Compliance Tables</span></span>

|<span data-ttu-id="b93b5-106">**Table**</span><span class="sxs-lookup"><span data-stu-id="b93b5-106">**Table**</span></span>|<span data-ttu-id="b93b5-107">**说明**</span><span class="sxs-lookup"><span data-stu-id="b93b5-107">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="b93b5-108">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="b93b5-108">tblComplianceData</span></span>](tblcompliancedata.md) <br/> |<span data-ttu-id="b93b5-109">包含已配置的适配器尚未处理的合规性事件。</span><span class="sxs-lookup"><span data-stu-id="b93b5-109">Contains the compliance events that have not yet been processed by the configured adapter.</span></span>  <br/> <span data-ttu-id="b93b5-110">此表包括与持久聊天相关的事件，如聊天消息和文件下载。</span><span class="sxs-lookup"><span data-stu-id="b93b5-110">This table includes Persistent Chat-related events, such as chat messages and file downloads.</span></span> <span data-ttu-id="b93b5-111"> (参与者事件由 tblComplianceParticipant 表.) </span><span class="sxs-lookup"><span data-stu-id="b93b5-111">(Participant events are tracked by the tblComplianceParticipant table.)</span></span>  <br/> <span data-ttu-id="b93b5-112">（处理该表中的事件的服务器列在 tblComplianceFanout 表中。）</span><span class="sxs-lookup"><span data-stu-id="b93b5-112">(The servers that processed the events in this table are listed in the tblComplianceFanout table.)</span></span>  <br/> |
|[<span data-ttu-id="b93b5-113">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="b93b5-113">tblComplianceFanout</span></span>](tblcompliancefanout.md) <br/> |<span data-ttu-id="b93b5-114">包含处理合规性事件的服务器。</span><span class="sxs-lookup"><span data-stu-id="b93b5-114">Contains the servers that processed a compliance event.</span></span> <span data-ttu-id="b93b5-115">该表与 tblComplianceData 表联系紧密。</span><span class="sxs-lookup"><span data-stu-id="b93b5-115">This table is tightly coupled with the tblComplianceData table.</span></span>  <br/> |
|[<span data-ttu-id="b93b5-116">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="b93b5-116">tblComplianceParticipant</span></span>](tblcomplianceparticipant.md) <br/> |<span data-ttu-id="b93b5-117">包含每个聊天服务和每台服务器的当前参与者。</span><span class="sxs-lookup"><span data-stu-id="b93b5-117">Contains current participants per chat service and per server.</span></span> <span data-ttu-id="b93b5-118">它基于从持久聊天服务收到的加入和部分合规性事件进行维护。</span><span class="sxs-lookup"><span data-stu-id="b93b5-118">It is maintained based on join and part compliance events received from the Persistent Chat service.</span></span>  <br/> |
|[<span data-ttu-id="b93b5-119">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="b93b5-119">tblComplianceState</span></span>](tblcompliancestate.md) <br/> |<span data-ttu-id="b93b5-120">包含池范围的合规性状态信息。</span><span class="sxs-lookup"><span data-stu-id="b93b5-120">Contains pool-wide compliance state information.</span></span>  <br/> |
   

