---
title: 简介
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Introduction
ms:assetid: 276395be-93df-4a16-97e2-cb468cd0f2e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945588(v=OCS.15)
ms:contentKeyID: 51541414
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 912c6a1704438106a3ffbb178d9f03a536489757
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204558"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="introduction"></a><span data-ttu-id="fa0ac-102">介绍</span><span class="sxs-lookup"><span data-stu-id="fa0ac-102">Introduction</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fa0ac-103">_**上次修改的主题：** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="fa0ac-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="fa0ac-104">Lync Server 2013 压力和性能工具（称为 "LyncPerfTool"）可以模拟用户对以下类型的负载：</span><span class="sxs-lookup"><span data-stu-id="fa0ac-104">The Lync Server 2013 Stress and Performance Tool (referred to as LyncPerfTool) can simulate user load of the following types:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fa0ac-105">即时消息 (IM) 和状态</span><span class="sxs-lookup"><span data-stu-id="fa0ac-105">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="fa0ac-106">音频会议</span><span class="sxs-lookup"><span data-stu-id="fa0ac-106">Audio conferencing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa0ac-107">应用程序共享</span><span class="sxs-lookup"><span data-stu-id="fa0ac-107">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="fa0ac-108">IP 语音（VoIP），包括公用电话交换电话网络（PSTN）模拟</span><span class="sxs-lookup"><span data-stu-id="fa0ac-108">Voice over IP (VoIP), including public switched telephone network (PSTN) simulation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa0ac-109">Web Access 客户端会议</span><span class="sxs-lookup"><span data-stu-id="fa0ac-109">Web Access Client conferencing</span></span></p></td>
<td><p><span data-ttu-id="fa0ac-110">Microsoft Lync 2013 助理</span><span class="sxs-lookup"><span data-stu-id="fa0ac-110">Microsoft Lync 2013 Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa0ac-111">响应组</span><span class="sxs-lookup"><span data-stu-id="fa0ac-111">Response Groups</span></span></p></td>
<td><p><span data-ttu-id="fa0ac-112">通讯组列表展开</span><span class="sxs-lookup"><span data-stu-id="fa0ac-112">Distribution list expansion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa0ac-113">通讯簿下载和通讯簿查询</span><span class="sxs-lookup"><span data-stu-id="fa0ac-113">Address book download and address book query</span></span></p></td>
<td><p><span data-ttu-id="fa0ac-114">增强型9-1-1 （E9-1-1）呼叫和位置配置文件（拨号计划）</span><span class="sxs-lookup"><span data-stu-id="fa0ac-114">Enhanced 9-1-1 (E9-1-1) calls and location profile (dial plan)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa0ac-115">重视</span><span class="sxs-lookup"><span data-stu-id="fa0ac-115">MultiView</span></span></p></td>
<td><p><span data-ttu-id="fa0ac-116">查看来自会议的多个流</span><span class="sxs-lookup"><span data-stu-id="fa0ac-116">Viewing multiple streams from a conference</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fa0ac-117">Lync Server 2013 压力和性能工具仅支持通过高级配置的跨池负载生成和联盟。</span><span class="sxs-lookup"><span data-stu-id="fa0ac-117">The Lync Server 2013 Stress and Performance Tool supports cross-pool load generation and federation through advanced configuration only.</span></span>

<span data-ttu-id="fa0ac-118">该工具也不会模拟以下客户端的用户负载：</span><span class="sxs-lookup"><span data-stu-id="fa0ac-118">The tool also does not simulate user load for the following clients:</span></span>

  - <span data-ttu-id="fa0ac-119">Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="fa0ac-119">Office Live Meeting 2007</span></span>

  - <span data-ttu-id="fa0ac-120">Lync 2013 持久聊天</span><span class="sxs-lookup"><span data-stu-id="fa0ac-120">Lync 2013 Persistent Chat</span></span>

<span data-ttu-id="fa0ac-121">因此，Lync Server 2013 的压力和性能工具将不支持测试以下组件：</span><span class="sxs-lookup"><span data-stu-id="fa0ac-121">As a result, the Lync Server 2013 Stress and Performance Tool will not support testing the following components:</span></span>

  - <span data-ttu-id="fa0ac-122">Lync 2013 持久聊天</span><span class="sxs-lookup"><span data-stu-id="fa0ac-122">Lync 2013 Persistent Chat</span></span>

  - <span data-ttu-id="fa0ac-123">Exchange 集成方案</span><span class="sxs-lookup"><span data-stu-id="fa0ac-123">Exchange integration scenarios</span></span>

<div>

## <a name="applications-and-files-included-with-the-lync-server-2013-stress-and-performance-tool"></a><span data-ttu-id="fa0ac-124">Lync Server 2013 压力和性能工具附带的应用程序和文件</span><span class="sxs-lookup"><span data-stu-id="fa0ac-124">Applications and Files Included with the Lync Server 2013 Stress and Performance Tool</span></span>

<span data-ttu-id="fa0ac-125">Lync Server 2013 压力和性能工具中包含以下应用程序：</span><span class="sxs-lookup"><span data-stu-id="fa0ac-125">The following applications are included in the Lync Server 2013 Stress and Performance Tool:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fa0ac-126">工具</span><span class="sxs-lookup"><span data-stu-id="fa0ac-126">Tool</span></span></th>
<th><span data-ttu-id="fa0ac-127">说明</span><span class="sxs-lookup"><span data-stu-id="fa0ac-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fa0ac-128">UserProvisioningTool</span><span class="sxs-lookup"><span data-stu-id="fa0ac-128">UserProvisioningTool.exe</span></span></p></td>
<td><p><span data-ttu-id="fa0ac-129">Lync Server 2013 用户预配工具。</span><span class="sxs-lookup"><span data-stu-id="fa0ac-129">The Lync Server 2013 User Provisioning tool.</span></span> <span data-ttu-id="fa0ac-130">此工具用于创建用户和联系人。</span><span class="sxs-lookup"><span data-stu-id="fa0ac-130">This tool is used to create users and contacts.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa0ac-131">UserProfileGenerator</span><span class="sxs-lookup"><span data-stu-id="fa0ac-131">UserProfileGenerator.exe</span></span></p></td>
<td><p><span data-ttu-id="fa0ac-132">Lync Server 2013 加载配置工具。</span><span class="sxs-lookup"><span data-stu-id="fa0ac-132">The Lync Server 2013 Load Configuration Tool.</span></span> <span data-ttu-id="fa0ac-133">此工具用于配置要模拟的用户负载的特征。</span><span class="sxs-lookup"><span data-stu-id="fa0ac-133">This tool is used to configure the characteristics of the user load to simulate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa0ac-134">LyncPerfTool</span><span class="sxs-lookup"><span data-stu-id="fa0ac-134">LyncPerfTool.exe</span></span></p></td>
<td><p><span data-ttu-id="fa0ac-135">Lync Server 2013 压力和性能工具。</span><span class="sxs-lookup"><span data-stu-id="fa0ac-135">The Lync Server 2013 Stress and Performance Tool.</span></span> <span data-ttu-id="fa0ac-136">LyncPerfTool 是模拟用户负载的工具。</span><span class="sxs-lookup"><span data-stu-id="fa0ac-136">LyncPerfTool is the tool that simulates the user load.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fa0ac-137">默认的 tmx</span><span class="sxs-lookup"><span data-stu-id="fa0ac-137">Default.tmx</span></span></p></td>
<td><p><span data-ttu-id="fa0ac-138">默认情况下，使用 Lync Server 2013 日志记录工具时需要使用 tmx。</span><span class="sxs-lookup"><span data-stu-id="fa0ac-138">Default.tmx is required to use the Lync Server 2013 Logging Tool.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fa0ac-139">示例预配脚本</span><span class="sxs-lookup"><span data-stu-id="fa0ac-139">Example provisioning scripts</span></span></p></td>
<td><p><span data-ttu-id="fa0ac-140">这些示例用于根据特定方案配置用于运行负载测试的拓扑</span><span class="sxs-lookup"><span data-stu-id="fa0ac-140">These examples are used to configure the topology for running load tests, based on specific scenarios</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

