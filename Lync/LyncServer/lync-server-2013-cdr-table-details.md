---
title: Lync Server 2013： CDR 表详细信息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: CDR table details
ms:assetid: 896198f5-672b-48ea-852f-0211c0c90857
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398693(v=OCS.15)
ms:contentKeyID: 48184730
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 32b48f6a03c0663277404876f538ae2f15d1bc38
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008504"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="cdr-table-details-in-lync-server-2013"></a><span data-ttu-id="f5c48-102">Lync Server 2013 中的 CDR 表详细信息</span><span class="sxs-lookup"><span data-stu-id="f5c48-102">CDR table details in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5c48-103">_**上次修改的主题：** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="f5c48-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="f5c48-104">以下主题详细介绍了每个呼叫详细记录 (CDR) 数据库架构表中的列。</span><span class="sxs-lookup"><span data-stu-id="f5c48-104">The following topics detail the columns in each of the call detail records (CDR) database schema tables.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f5c48-105">本部分内容</span><span class="sxs-lookup"><span data-stu-id="f5c48-105">In This Section</span></span>

  - [<span data-ttu-id="f5c48-106">Lync Server 2013 中的应用程序表</span><span class="sxs-lookup"><span data-stu-id="f5c48-106">Application table in Lync Server 2013</span></span>](lync-server-2013-application-table.md)

  - [<span data-ttu-id="f5c48-107">Lync Server 2013 中的 CallPriorities 表</span><span class="sxs-lookup"><span data-stu-id="f5c48-107">CallPriorities table in Lync Server 2013</span></span>](lync-server-2013-callpriorities-table.md)

  - [<span data-ttu-id="f5c48-108">Lync Server 2013 中的 CallType 表</span><span class="sxs-lookup"><span data-stu-id="f5c48-108">CallType table in Lync Server 2013</span></span>](lync-server-2013-calltype-table.md)

  - [<span data-ttu-id="f5c48-109">Lync Server 2013 中的 ClientVersions 表</span><span class="sxs-lookup"><span data-stu-id="f5c48-109">ClientVersions table in Lync Server 2013</span></span>](lync-server-2013-clientversions-table.md)

  - [<span data-ttu-id="f5c48-110">Lync Server 2013 中的 ConferenceJoinTimeThresholds 表</span><span class="sxs-lookup"><span data-stu-id="f5c48-110">ConferenceJoinTimeThresholds table in Lync Server 2013</span></span>](lync-server-2013-conferencejointimethresholds-table.md)

  - [<span data-ttu-id="f5c48-111">Lync Server 2013 中的 ConferenceMessageCount 表</span><span class="sxs-lookup"><span data-stu-id="f5c48-111">ConferenceMessageCount table in Lync Server 2013</span></span>](lync-server-2013-conferencemessagecount-table.md)

  - [<span data-ttu-id="f5c48-112">Lync Server 2013 中的 "会议" 表</span><span class="sxs-lookup"><span data-stu-id="f5c48-112">Conferences table in Lync Server 2013</span></span>](lync-server-2013-conferences-table.md)

  - [<span data-ttu-id="f5c48-113">Lync Server 2013 中的 ConferenceSessionDetails 表</span><span class="sxs-lookup"><span data-stu-id="f5c48-113">ConferenceSessionDetails table in Lync Server 2013</span></span>](lync-server-2013-conferencesessiondetails-table.md)

  - [<span data-ttu-id="f5c48-114">Lync Server 2013 中的 ConferenceUris 表</span><span class="sxs-lookup"><span data-stu-id="f5c48-114">ConferenceUris table in Lync Server 2013</span></span>](lync-server-2013-conferenceuris-table.md)

  - [<span data-ttu-id="f5c48-115">Lync Server 2013 中的 ContentTypes 表</span><span class="sxs-lookup"><span data-stu-id="f5c48-115">ContentTypes table in Lync Server 2013</span></span>](lync-server-2013-contenttypes-table.md)

  - [<span data-ttu-id="f5c48-116">Lync Server 2013 中的 DeRegisterType 表</span><span class="sxs-lookup"><span data-stu-id="f5c48-116">DeRegisterType table in Lync Server 2013</span></span>](lync-server-2013-deregistertype-table.md)

  - [<span data-ttu-id="f5c48-117">Lync Server 2013 中的 "设备" 表</span><span class="sxs-lookup"><span data-stu-id="f5c48-117">Devices table in Lync Server 2013</span></span>](lync-server-2013-devices-table.md)

  - [<span data-ttu-id="f5c48-118">Lync Server 2013 中的对话框表</span><span class="sxs-lookup"><span data-stu-id="f5c48-118">Dialogs table in Lync Server 2013</span></span>](lync-server-2013-dialogs-table.md)

  - [<span data-ttu-id="f5c48-119">Lync Server 2013 中的 EdgeServers 表</span><span class="sxs-lookup"><span data-stu-id="f5c48-119">EdgeServers table in Lync Server 2013</span></span>](lync-server-2013-edgeservers-table.md)

  - [<span data-ttu-id="f5c48-120">Lync Server 2013 中的 ErrorCategory 表</span><span class="sxs-lookup"><span data-stu-id="f5c48-120">ErrorCategory table in Lync Server 2013</span></span>](lync-server-2013-errorcategory-table.md)

  - [<span data-ttu-id="f5c48-121">Lync Server 2013 中的 ErrorDef 表</span><span class="sxs-lookup"><span data-stu-id="f5c48-121">ErrorDef table in Lync Server 2013</span></span>](lync-server-2013-errordef-table.md)

  - [<span data-ttu-id="f5c48-122">Lync Server 2013 中的 ErrorReport 表</span><span class="sxs-lookup"><span data-stu-id="f5c48-122">ErrorReport table in Lync Server 2013</span></span>](lync-server-2013-errorreport-table.md)

  - [<span data-ttu-id="f5c48-123">Lync Server 2013 中的 FileTransfers 表</span><span class="sxs-lookup"><span data-stu-id="f5c48-123">FileTransfers table in Lync Server 2013</span></span>](lync-server-2013-filetransfers-table.md)

  - [<span data-ttu-id="f5c48-124">Lync Server 2013 中的 FocusJoinsAndLeaves 表</span><span class="sxs-lookup"><span data-stu-id="f5c48-124">FocusJoinsAndLeaves table in Lync Server 2013</span></span>](lync-server-2013-focusjoinsandleaves-table.md)

  - [<span data-ttu-id="f5c48-125">Lync Server 2013 中的前端表</span><span class="sxs-lookup"><span data-stu-id="f5c48-125">FrontEnd table in Lync Server 2013</span></span>](lync-server-2013-frontend-table.md)

  - [<span data-ttu-id="f5c48-126">Lync Server 2013 中的网关表</span><span class="sxs-lookup"><span data-stu-id="f5c48-126">Gateways table in Lync Server 2013</span></span>](lync-server-2013-gateways-table.md)

  - [<span data-ttu-id="f5c48-127">Lync Server 2013 中的 HardwareVersions 表</span><span class="sxs-lookup"><span data-stu-id="f5c48-127">HardwareVersions table in Lync Server 2013</span></span>](lync-server-2013-hardwareversions-table.md)

  - [<span data-ttu-id="f5c48-128">Lync Server 2013 中的 IMReportSummary 表</span><span class="sxs-lookup"><span data-stu-id="f5c48-128">IMReportSummary table in Lync Server 2013</span></span>](lync-server-2013-imreportsummary-table.md)

  - [<span data-ttu-id="f5c48-129">Lync Server 2013 中的位置表</span><span class="sxs-lookup"><span data-stu-id="f5c48-129">Locations table in Lync Server 2013</span></span>](lync-server-2013-locations-table.md)

  - [<span data-ttu-id="f5c48-130">Lync Server 2013 中的 "制造商" 表</span><span class="sxs-lookup"><span data-stu-id="f5c48-130">Manufacturers table in Lync Server 2013</span></span>](lync-server-2013-manufacturers-table.md)

  - [<span data-ttu-id="f5c48-131">Lync Server 2013 中的 McuJoinsAndLeaves 表</span><span class="sxs-lookup"><span data-stu-id="f5c48-131">McuJoinsAndLeaves table in Lync Server 2013</span></span>](lync-server-2013-mcujoinsandleaves-table.md)

  - [<span data-ttu-id="f5c48-132">Lync Server 2013 中的 mcu 表</span><span class="sxs-lookup"><span data-stu-id="f5c48-132">Mcus table in Lync Server 2013</span></span>](lync-server-2013-mcus-table.md)

  - [<span data-ttu-id="f5c48-133">Lync Server 2013 中的媒体表</span><span class="sxs-lookup"><span data-stu-id="f5c48-133">Media table in Lync Server 2013</span></span>](lync-server-2013-media-table.md)

  - [<span data-ttu-id="f5c48-134">Lync Server 2013 中的 MediaList 表</span><span class="sxs-lookup"><span data-stu-id="f5c48-134">MediaList table in Lync Server 2013</span></span>](lync-server-2013-medialist-table.md)

  - [<span data-ttu-id="f5c48-135">Lync Server 2013 中的 MediationServers 表</span><span class="sxs-lookup"><span data-stu-id="f5c48-135">MediationServers table in Lync Server 2013</span></span>](lync-server-2013-mediationservers-table.md)

  - [<span data-ttu-id="f5c48-136">Lync Server 2013 中的 MSMQProcessing 表</span><span class="sxs-lookup"><span data-stu-id="f5c48-136">MSMQProcessing table in Lync Server 2013</span></span>](lync-server-2013-msmqprocessing-table.md)

  - [<span data-ttu-id="f5c48-137">Lync Server 2013 中的电话表</span><span class="sxs-lookup"><span data-stu-id="f5c48-137">Phones table in Lync Server 2013</span></span>](lync-server-2013-phones-table.md)

  - [<span data-ttu-id="f5c48-138">Lync Server 2013 中的 pool 表</span><span class="sxs-lookup"><span data-stu-id="f5c48-138">Pools table in Lync Server 2013</span></span>](lync-server-2013-pools-table.md)

  - [<span data-ttu-id="f5c48-139">Lync Server 2013 中的 ProgressReport 表</span><span class="sxs-lookup"><span data-stu-id="f5c48-139">ProgressReport table in Lync Server 2013</span></span>](lync-server-2013-progressreport-table.md)

  - [<span data-ttu-id="f5c48-140">Lync Server 2013 中的 PurgeSettings 表</span><span class="sxs-lookup"><span data-stu-id="f5c48-140">PurgeSettings table in Lync Server 2013</span></span>](lync-server-2013-purgesettings-table.md)

  - [<span data-ttu-id="f5c48-141">Lync Server 2013 中的注册表</span><span class="sxs-lookup"><span data-stu-id="f5c48-141">Registration table in Lync Server 2013</span></span>](lync-server-2013-registration-table.md)

  - [<span data-ttu-id="f5c48-142">Lync Server 2013 中的 Roles 表</span><span class="sxs-lookup"><span data-stu-id="f5c48-142">Roles table in Lync Server 2013</span></span>](lync-server-2013-roles-table.md)

  - [<span data-ttu-id="f5c48-143">Lync Server 2013 中的 "服务器" 表</span><span class="sxs-lookup"><span data-stu-id="f5c48-143">Servers table in Lync Server 2013</span></span>](lync-server-2013-servers-table.md)

  - [<span data-ttu-id="f5c48-144">Lync Server 2013 中的 SessionDetails 表</span><span class="sxs-lookup"><span data-stu-id="f5c48-144">SessionDetails table in Lync Server 2013</span></span>](lync-server-2013-sessiondetails-table.md)

  - [<span data-ttu-id="f5c48-145">Lync Server 2013 中的 SIPResponseMetaData 表</span><span class="sxs-lookup"><span data-stu-id="f5c48-145">SIPResponseMetaData table in Lync Server 2013</span></span>](lync-server-2013-sipresponsemetadata-table.md)

  - [<span data-ttu-id="f5c48-146">Lync Server 2013 中的 Syndicators 表</span><span class="sxs-lookup"><span data-stu-id="f5c48-146">Syndicators table in Lync Server 2013</span></span>](lync-server-2013-syndicators-table.md)

  - [<span data-ttu-id="f5c48-147">Lync Server 2013 中的 SyndicatorsTenantMap 表</span><span class="sxs-lookup"><span data-stu-id="f5c48-147">SyndicatorsTenantMap table in Lync Server 2013</span></span>](lync-server-2013-syndicatorstenantmap-table.md)

  - [<span data-ttu-id="f5c48-148">Lync Server 2013 中的任务表</span><span class="sxs-lookup"><span data-stu-id="f5c48-148">Task table in Lync Server 2013</span></span>](lync-server-2013-task-table.md)

  - [<span data-ttu-id="f5c48-149">Lync Server 2013 中的租户表</span><span class="sxs-lookup"><span data-stu-id="f5c48-149">Tenants table in Lync Server 2013</span></span>](lync-server-2013-tenants-table.md)

  - [<span data-ttu-id="f5c48-150">Lync Server 2013 中的 UriTypes 表</span><span class="sxs-lookup"><span data-stu-id="f5c48-150">UriTypes table in Lync Server 2013</span></span>](lync-server-2013-uritypes-table.md)

  - [<span data-ttu-id="f5c48-151">Lync Server 2013 中的 Users 表</span><span class="sxs-lookup"><span data-stu-id="f5c48-151">Users table in Lync Server 2013</span></span>](lync-server-2013-users-table.md)

  - [<span data-ttu-id="f5c48-152">Lync Server 2013 中的 UserAgentDef 表</span><span class="sxs-lookup"><span data-stu-id="f5c48-152">UserAgentDef table in Lync Server 2013</span></span>](lync-server-2013-useragentdef-table.md)

  - [<span data-ttu-id="f5c48-153">Lync Server 2013 中的 UserStatistics 表</span><span class="sxs-lookup"><span data-stu-id="f5c48-153">UserStatistics table in Lync Server 2013</span></span>](lync-server-2013-userstatistics-table.md)

  - [<span data-ttu-id="f5c48-154">Lync Server 2013 中的 VoipDetails 表</span><span class="sxs-lookup"><span data-stu-id="f5c48-154">VoipDetails table in Lync Server 2013</span></span>](lync-server-2013-voipdetails-table.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

