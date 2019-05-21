---
title: Skype for Business 服务器中持久聊天服务器合规性表的列表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8563446e-90cc-47cc-8a8e-4883decfe195
description: 持久聊天合规性数据库架构由下表组成。
ms.openlocfilehash: 92c87ee2783eb8ec064e017b5c3c5b0f6cb893a5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295655"
---
# <a name="list-of-persistent-chat-server-compliance-tables-in-skype-for-business-server"></a><span data-ttu-id="21b11-103">Skype for Business 服务器中持久聊天服务器合规性表的列表</span><span class="sxs-lookup"><span data-stu-id="21b11-103">List of Persistent Chat Server compliance tables in Skype for Business Server</span></span>
 
<span data-ttu-id="21b11-104">持久聊天合规性数据库架构由下表组成。</span><span class="sxs-lookup"><span data-stu-id="21b11-104">The Persistent Chat compliance database schema consists of the following tables.</span></span>
  
## <a name="list-of-persistent-chat-server-compliance-tables"></a><span data-ttu-id="21b11-105">持久聊天服务器合规性表列表</span><span class="sxs-lookup"><span data-stu-id="21b11-105">List of Persistent Chat Server Compliance Tables</span></span>

|<span data-ttu-id="21b11-106">**表格**</span><span class="sxs-lookup"><span data-stu-id="21b11-106">**Table**</span></span>|<span data-ttu-id="21b11-107">**说明**</span><span class="sxs-lookup"><span data-stu-id="21b11-107">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="21b11-108">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="21b11-108">tblComplianceData</span></span>](tblcompliancedata.md) <br/> |<span data-ttu-id="21b11-109">包含已配置的适配器尚未处理的合规性事件。</span><span class="sxs-lookup"><span data-stu-id="21b11-109">Contains the compliance events that have not yet been processed by the configured adapter.</span></span>  <br/> <span data-ttu-id="21b11-110">此表包括与聊天相关的持久事件, 例如聊天消息和文件下载。</span><span class="sxs-lookup"><span data-stu-id="21b11-110">This table includes Persistent Chat-related events, such as chat messages and file downloads.</span></span> <span data-ttu-id="21b11-111">(参与者事件由 tblComplianceParticipant 表跟踪。)</span><span class="sxs-lookup"><span data-stu-id="21b11-111">(Participant events are tracked by the tblComplianceParticipant table.)</span></span>  <br/> <span data-ttu-id="21b11-112">(处理此表中的事件的服务器在 tblComplianceFanout 表中列出。)</span><span class="sxs-lookup"><span data-stu-id="21b11-112">(The servers that processed the events in this table are listed in the tblComplianceFanout table.)</span></span>  <br/> |
|[<span data-ttu-id="21b11-113">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="21b11-113">tblComplianceFanout</span></span>](tblcompliancefanout.md) <br/> |<span data-ttu-id="21b11-114">包含处理合规性事件的服务器。</span><span class="sxs-lookup"><span data-stu-id="21b11-114">Contains the servers that processed a compliance event.</span></span> <span data-ttu-id="21b11-115">此表与 tblComplianceData 表紧密耦合。</span><span class="sxs-lookup"><span data-stu-id="21b11-115">This table is tightly coupled with the tblComplianceData table.</span></span>  <br/> |
|[<span data-ttu-id="21b11-116">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="21b11-116">tblComplianceParticipant</span></span>](tblcomplianceparticipant.md) <br/> |<span data-ttu-id="21b11-117">包含每个聊天服务和每台服务器的当前参与者。</span><span class="sxs-lookup"><span data-stu-id="21b11-117">Contains current participants per chat service and per server.</span></span> <span data-ttu-id="21b11-118">它根据从持久聊天服务接收的联接和部件合规性事件进行维护。</span><span class="sxs-lookup"><span data-stu-id="21b11-118">It is maintained based on join and part compliance events received from the Persistent Chat service.</span></span>  <br/> |
|[<span data-ttu-id="21b11-119">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="21b11-119">tblComplianceState</span></span>](tblcompliancestate.md) <br/> |<span data-ttu-id="21b11-120">包含池范围的合规性状态信息。</span><span class="sxs-lookup"><span data-stu-id="21b11-120">Contains pool-wide compliance state information.</span></span>  <br/> |
   

