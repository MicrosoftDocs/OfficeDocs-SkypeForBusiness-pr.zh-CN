---
title: 持久聊天服务器表详细信息
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c22d4a76-da50-49de-9038-e0ed7b8e1b58
description: 下面的主题详细介绍每个持久聊天数据库架构表中的列。
ms.openlocfilehash: a7dc2f9cc545627630286d6166adf47fbb8c4c57
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="persistent-chat-server-table-details"></a><span data-ttu-id="248a7-103">持久聊天服务器表详细信息</span><span class="sxs-lookup"><span data-stu-id="248a7-103">Persistent Chat Server table details</span></span>
 
<span data-ttu-id="248a7-104">下面的主题详细介绍每个持久聊天数据库架构表中的列。</span><span class="sxs-lookup"><span data-stu-id="248a7-104">The following topics detail the columns in each of the Persistent Chat database schema tables.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="248a7-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="248a7-105">In this section</span></span>

- [<span data-ttu-id="248a7-106">tblADCookie</span><span class="sxs-lookup"><span data-stu-id="248a7-106">tblADCookie</span></span>](tbladcookie.md)
    
- [<span data-ttu-id="248a7-107">tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="248a7-107">tblPrincipalMemberDifference</span></span>](tblprincipalmemberdifference.md)
    
- [<span data-ttu-id="248a7-108">tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="248a7-108">tblADUpdates</span></span>](tbladupdates.md)
    
- [<span data-ttu-id="248a7-109">tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="248a7-109">tblPrincipalMembers</span></span>](tblprincipalmembers.md)
    
- [<span data-ttu-id="248a7-110">tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="248a7-110">tblPrincipalMeta</span></span>](tblprincipalmeta.md)
    
- [<span data-ttu-id="248a7-111">tblSkippedAffiliations</span><span class="sxs-lookup"><span data-stu-id="248a7-111">tblSkippedAffiliations</span></span>](tblskippedaffiliations.md)
    
- [<span data-ttu-id="248a7-112">tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="248a7-112">tblPrincipalType</span></span>](tblprincipaltype.md)
    
- [<span data-ttu-id="248a7-113">tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="248a7-113">tblPrincipal</span></span>](tblprincipal.md)
    
- [<span data-ttu-id="248a7-114">tblPrincipalAffiliations</span><span class="sxs-lookup"><span data-stu-id="248a7-114">tblPrincipalAffiliations</span></span>](tblprincipalaffiliations.md)
    
- [<span data-ttu-id="248a7-115">tblNode</span><span class="sxs-lookup"><span data-stu-id="248a7-115">tblNode</span></span>](tblnode.md)
    
- [<span data-ttu-id="248a7-116">tblRoleType</span><span class="sxs-lookup"><span data-stu-id="248a7-116">tblRoleType</span></span>](tblroletype.md)
    
- [<span data-ttu-id="248a7-117">tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="248a7-117">tblScopePrincipal</span></span>](tblscopeprincipal.md)
    
- [<span data-ttu-id="248a7-118">tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="248a7-118">tblPrincipalRole</span></span>](tblprincipalrole.md)
    
- [<span data-ttu-id="248a7-119">tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="248a7-119">tblSiopWhiteList</span></span>](tblsiopwhitelist.md)
    
- [<span data-ttu-id="248a7-120">tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="248a7-120">tblEnumAttribute</span></span>](tblenumattribute.md)
    
- [<span data-ttu-id="248a7-121">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="248a7-121">tblEnumValue</span></span>](tblenumvalue.md)
    
- [<span data-ttu-id="248a7-122">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="248a7-122">tblPrincipalInvites</span></span>](tblprincipalinvites.md)
    
- [<span data-ttu-id="248a7-123">tblChat</span><span class="sxs-lookup"><span data-stu-id="248a7-123">tblChat</span></span>](tblchat.md)
    
- [<span data-ttu-id="248a7-124">tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="248a7-124">tblLastInviteId</span></span>](tbllastinviteid.md)
    
- [<span data-ttu-id="248a7-125">tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="248a7-125">tblLastChatId</span></span>](tbllastchatid.md)
    
- [<span data-ttu-id="248a7-126">tblPreference</span><span class="sxs-lookup"><span data-stu-id="248a7-126">tblPreference</span></span>](tblpreference.md)
    
- [<span data-ttu-id="248a7-127">tblFileToken</span><span class="sxs-lookup"><span data-stu-id="248a7-127">tblFileToken</span></span>](tblfiletoken.md)
    
- [<span data-ttu-id="248a7-128">tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="248a7-128">tblServerIdentity</span></span>](tblserveridentity.md)
    
- [<span data-ttu-id="248a7-129">tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="248a7-129">tblAdminLock</span></span>](tbladminlock.md)
    
- [<span data-ttu-id="248a7-130">tblSystemRevision</span><span class="sxs-lookup"><span data-stu-id="248a7-130">tblSystemRevision</span></span>](tblsystemrevision.md)
    
- [<span data-ttu-id="248a7-131">tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="248a7-131">tblActivePeers</span></span>](tblactivepeers.md)
    
- [<span data-ttu-id="248a7-132">tblConfig</span><span class="sxs-lookup"><span data-stu-id="248a7-132">tblConfig</span></span>](tblconfig.md)
    
- [<span data-ttu-id="248a7-133">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="248a7-133">tblComplianceData</span></span>](tblcompliancedata.md)
    
- [<span data-ttu-id="248a7-134">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="248a7-134">tblComplianceFanout</span></span>](tblcompliancefanout.md)
    
- [<span data-ttu-id="248a7-135">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="248a7-135">tblComplianceParticipant</span></span>](tblcomplianceparticipant.md)
    
- [<span data-ttu-id="248a7-136">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="248a7-136">tblComplianceState</span></span>](tblcompliancestate.md)
    

