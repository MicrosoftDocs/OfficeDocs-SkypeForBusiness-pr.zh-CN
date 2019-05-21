---
title: 持久聊天服务器表详细信息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c22d4a76-da50-49de-9038-e0ed7b8e1b58
description: 以下主题详细介绍了每个持久聊天数据库架构表中的列。
ms.openlocfilehash: 3ac401577bae294324b0f0feb82e611522b2610b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295592"
---
# <a name="persistent-chat-server-table-details"></a><span data-ttu-id="348d5-103">持久聊天服务器表详细信息</span><span class="sxs-lookup"><span data-stu-id="348d5-103">Persistent Chat Server table details</span></span>
 
<span data-ttu-id="348d5-104">以下主题详细介绍了每个持久聊天数据库架构表中的列。</span><span class="sxs-lookup"><span data-stu-id="348d5-104">The following topics detail the columns in each of the Persistent Chat database schema tables.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="348d5-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="348d5-105">In this section</span></span>

- [<span data-ttu-id="348d5-106">tblADCookie</span><span class="sxs-lookup"><span data-stu-id="348d5-106">tblADCookie</span></span>](tbladcookie.md)
    
- [<span data-ttu-id="348d5-107">tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="348d5-107">tblPrincipalMemberDifference</span></span>](tblprincipalmemberdifference.md)
    
- [<span data-ttu-id="348d5-108">tblADUpdates</span><span class="sxs-lookup"><span data-stu-id="348d5-108">tblADUpdates</span></span>](tbladupdates.md)
    
- [<span data-ttu-id="348d5-109">tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="348d5-109">tblPrincipalMembers</span></span>](tblprincipalmembers.md)
    
- [<span data-ttu-id="348d5-110">tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="348d5-110">tblPrincipalMeta</span></span>](tblprincipalmeta.md)
    
- [<span data-ttu-id="348d5-111">tblSkippedAffiliations</span><span class="sxs-lookup"><span data-stu-id="348d5-111">tblSkippedAffiliations</span></span>](tblskippedaffiliations.md)
    
- [<span data-ttu-id="348d5-112">tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="348d5-112">tblPrincipalType</span></span>](tblprincipaltype.md)
    
- [<span data-ttu-id="348d5-113">tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="348d5-113">tblPrincipal</span></span>](tblprincipal.md)
    
- [<span data-ttu-id="348d5-114">tblPrincipalAffiliations</span><span class="sxs-lookup"><span data-stu-id="348d5-114">tblPrincipalAffiliations</span></span>](tblprincipalaffiliations.md)
    
- [<span data-ttu-id="348d5-115">tblNode</span><span class="sxs-lookup"><span data-stu-id="348d5-115">tblNode</span></span>](tblnode.md)
    
- [<span data-ttu-id="348d5-116">tblRoleType</span><span class="sxs-lookup"><span data-stu-id="348d5-116">tblRoleType</span></span>](tblroletype.md)
    
- [<span data-ttu-id="348d5-117">tblScopePrincipal</span><span class="sxs-lookup"><span data-stu-id="348d5-117">tblScopePrincipal</span></span>](tblscopeprincipal.md)
    
- [<span data-ttu-id="348d5-118">tblPrincipalRole</span><span class="sxs-lookup"><span data-stu-id="348d5-118">tblPrincipalRole</span></span>](tblprincipalrole.md)
    
- [<span data-ttu-id="348d5-119">tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="348d5-119">tblSiopWhiteList</span></span>](tblsiopwhitelist.md)
    
- [<span data-ttu-id="348d5-120">tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="348d5-120">tblEnumAttribute</span></span>](tblenumattribute.md)
    
- [<span data-ttu-id="348d5-121">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="348d5-121">tblEnumValue</span></span>](tblenumvalue.md)
    
- [<span data-ttu-id="348d5-122">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="348d5-122">tblPrincipalInvites</span></span>](tblprincipalinvites.md)
    
- [<span data-ttu-id="348d5-123">tblChat</span><span class="sxs-lookup"><span data-stu-id="348d5-123">tblChat</span></span>](tblchat.md)
    
- [<span data-ttu-id="348d5-124">tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="348d5-124">tblLastInviteId</span></span>](tbllastinviteid.md)
    
- [<span data-ttu-id="348d5-125">tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="348d5-125">tblLastChatId</span></span>](tbllastchatid.md)
    
- [<span data-ttu-id="348d5-126">tblPreference</span><span class="sxs-lookup"><span data-stu-id="348d5-126">tblPreference</span></span>](tblpreference.md)
    
- [<span data-ttu-id="348d5-127">tblFileToken</span><span class="sxs-lookup"><span data-stu-id="348d5-127">tblFileToken</span></span>](tblfiletoken.md)
    
- [<span data-ttu-id="348d5-128">tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="348d5-128">tblServerIdentity</span></span>](tblserveridentity.md)
    
- [<span data-ttu-id="348d5-129">tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="348d5-129">tblAdminLock</span></span>](tbladminlock.md)
    
- [<span data-ttu-id="348d5-130">tblSystemRevision</span><span class="sxs-lookup"><span data-stu-id="348d5-130">tblSystemRevision</span></span>](tblsystemrevision.md)
    
- [<span data-ttu-id="348d5-131">tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="348d5-131">tblActivePeers</span></span>](tblactivepeers.md)
    
- [<span data-ttu-id="348d5-132">tblConfig</span><span class="sxs-lookup"><span data-stu-id="348d5-132">tblConfig</span></span>](tblconfig.md)
    
- [<span data-ttu-id="348d5-133">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="348d5-133">tblComplianceData</span></span>](tblcompliancedata.md)
    
- [<span data-ttu-id="348d5-134">tblComplianceFanout</span><span class="sxs-lookup"><span data-stu-id="348d5-134">tblComplianceFanout</span></span>](tblcompliancefanout.md)
    
- [<span data-ttu-id="348d5-135">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="348d5-135">tblComplianceParticipant</span></span>](tblcomplianceparticipant.md)
    
- [<span data-ttu-id="348d5-136">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="348d5-136">tblComplianceState</span></span>](tblcompliancestate.md)
    

