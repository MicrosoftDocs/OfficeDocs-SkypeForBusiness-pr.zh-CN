---
title: 持久聊天服务器表详细信息
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c22d4a76-da50-49de-9038-e0ed7b8e1b58
description: 以下主题详细介绍每个持久聊天数据库架构表中的列。
ms.openlocfilehash: 016974ff261cd862b888158f729e4baaff504366
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20992796"
---
# <a name="persistent-chat-server-table-details"></a><span data-ttu-id="627bb-103">持久聊天服务器表详细信息</span><span class="sxs-lookup"><span data-stu-id="627bb-103">Persistent Chat Server table details</span></span>
 
<span data-ttu-id="627bb-104">以下主题详细介绍每个持久聊天数据库架构表中的列。</span><span class="sxs-lookup"><span data-stu-id="627bb-104">The following topics detail the columns in each of the Persistent Chat database schema tables.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="627bb-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="627bb-105">In this section</span></span>

- [<span data-ttu-id="627bb-106">tblADCookie</span><span class="sxs-lookup"><span data-stu-id="627bb-106">tblADCookie</span></span>](tbladcookie.md)
    
- [<span data-ttu-id="627bb-107">tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="627bb-107">tblPrincipalMemberDifference</span></span>](tblprincipalmemberdifference.md)
    
- [<span data-ttu-id="627bb-108">tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="627bb-108">tblADUpdates</span></span>](tbladupdates.md)
    
- [<span data-ttu-id="627bb-109">tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="627bb-109">tblPrincipalMembers</span></span>](tblprincipalmembers.md)
    
- [<span data-ttu-id="627bb-110">tblprincipalmeta 表</span><span class="sxs-lookup"><span data-stu-id="627bb-110">tblPrincipalMeta</span></span>](tblprincipalmeta.md)
    
- [<span data-ttu-id="627bb-111">tblSkippedAffiliations</span><span class="sxs-lookup"><span data-stu-id="627bb-111">tblSkippedAffiliations</span></span>](tblskippedaffiliations.md)
    
- [<span data-ttu-id="627bb-112">tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="627bb-112">tblPrincipalType</span></span>](tblprincipaltype.md)
    
- [<span data-ttu-id="627bb-113">tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="627bb-113">tblPrincipal</span></span>](tblprincipal.md)
    
- [<span data-ttu-id="627bb-114">tblPrincipalAffiliations</span><span class="sxs-lookup"><span data-stu-id="627bb-114">tblPrincipalAffiliations</span></span>](tblprincipalaffiliations.md)
    
- [<span data-ttu-id="627bb-115">tblNode</span><span class="sxs-lookup"><span data-stu-id="627bb-115">tblNode</span></span>](tblnode.md)
    
- [<span data-ttu-id="627bb-116">tblRoleType</span><span class="sxs-lookup"><span data-stu-id="627bb-116">tblRoleType</span></span>](tblroletype.md)
    
- [<span data-ttu-id="627bb-117">tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="627bb-117">tblScopePrincipal</span></span>](tblscopeprincipal.md)
    
- [<span data-ttu-id="627bb-118">tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="627bb-118">tblPrincipalRole</span></span>](tblprincipalrole.md)
    
- [<span data-ttu-id="627bb-119">tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="627bb-119">tblSiopWhiteList</span></span>](tblsiopwhitelist.md)
    
- [<span data-ttu-id="627bb-120">tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="627bb-120">tblEnumAttribute</span></span>](tblenumattribute.md)
    
- [<span data-ttu-id="627bb-121">tblenumvalue 表</span><span class="sxs-lookup"><span data-stu-id="627bb-121">tblEnumValue</span></span>](tblenumvalue.md)
    
- [<span data-ttu-id="627bb-122">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="627bb-122">tblPrincipalInvites</span></span>](tblprincipalinvites.md)
    
- [<span data-ttu-id="627bb-123">tblChat</span><span class="sxs-lookup"><span data-stu-id="627bb-123">tblChat</span></span>](tblchat.md)
    
- [<span data-ttu-id="627bb-124">tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="627bb-124">tblLastInviteId</span></span>](tbllastinviteid.md)
    
- [<span data-ttu-id="627bb-125">tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="627bb-125">tblLastChatId</span></span>](tbllastchatid.md)
    
- [<span data-ttu-id="627bb-126">tblPreference</span><span class="sxs-lookup"><span data-stu-id="627bb-126">tblPreference</span></span>](tblpreference.md)
    
- [<span data-ttu-id="627bb-127">tblFileToken</span><span class="sxs-lookup"><span data-stu-id="627bb-127">tblFileToken</span></span>](tblfiletoken.md)
    
- [<span data-ttu-id="627bb-128">tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="627bb-128">tblServerIdentity</span></span>](tblserveridentity.md)
    
- [<span data-ttu-id="627bb-129">tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="627bb-129">tblAdminLock</span></span>](tbladminlock.md)
    
- [<span data-ttu-id="627bb-130">tblSystemRevision</span><span class="sxs-lookup"><span data-stu-id="627bb-130">tblSystemRevision</span></span>](tblsystemrevision.md)
    
- [<span data-ttu-id="627bb-131">tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="627bb-131">tblActivePeers</span></span>](tblactivepeers.md)
    
- [<span data-ttu-id="627bb-132">tblConfig</span><span class="sxs-lookup"><span data-stu-id="627bb-132">tblConfig</span></span>](tblconfig.md)
    
- [<span data-ttu-id="627bb-133">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="627bb-133">tblComplianceData</span></span>](tblcompliancedata.md)
    
- [<span data-ttu-id="627bb-134">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="627bb-134">tblComplianceFanout</span></span>](tblcompliancefanout.md)
    
- [<span data-ttu-id="627bb-135">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="627bb-135">tblComplianceParticipant</span></span>](tblcomplianceparticipant.md)
    
- [<span data-ttu-id="627bb-136">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="627bb-136">tblComplianceState</span></span>](tblcompliancestate.md)
    

