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
ms.openlocfilehash: 893205127b6b1ccba958a0882c3aa0d1360a7c06
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730562"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="introduction"></a><span data-ttu-id="ffc1b-102">简介</span><span class="sxs-lookup"><span data-stu-id="ffc1b-102">Introduction</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ffc1b-103">_**主题上次修改时间：** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="ffc1b-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="ffc1b-104">Lync Server 2013 应力和性能工具（称为 LyncPerfTool）可模拟以下类型的用户负载：</span><span class="sxs-lookup"><span data-stu-id="ffc1b-104">The Lync Server 2013 Stress and Performance Tool (referred to as LyncPerfTool) can simulate user load of the following types:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ffc1b-105">即时消息（IM）和状态</span><span class="sxs-lookup"><span data-stu-id="ffc1b-105">Instant messaging (IM) and presence</span></span></p></td>
<td><p><span data-ttu-id="ffc1b-106">音频会议</span><span class="sxs-lookup"><span data-stu-id="ffc1b-106">Audio conferencing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffc1b-107">应用程序共享</span><span class="sxs-lookup"><span data-stu-id="ffc1b-107">Application sharing</span></span></p></td>
<td><p><span data-ttu-id="ffc1b-108">IP 语音（VoIP），包括公共交换电话网络（PSTN）模拟</span><span class="sxs-lookup"><span data-stu-id="ffc1b-108">Voice over IP (VoIP), including public switched telephone network (PSTN) simulation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ffc1b-109">Web Access 客户端会议</span><span class="sxs-lookup"><span data-stu-id="ffc1b-109">Web Access Client conferencing</span></span></p></td>
<td><p><span data-ttu-id="ffc1b-110">Microsoft Lync 2013 助理</span><span class="sxs-lookup"><span data-stu-id="ffc1b-110">Microsoft Lync 2013 Attendant</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffc1b-111">响应组</span><span class="sxs-lookup"><span data-stu-id="ffc1b-111">Response Groups</span></span></p></td>
<td><p><span data-ttu-id="ffc1b-112">通讯组列表扩展</span><span class="sxs-lookup"><span data-stu-id="ffc1b-112">Distribution list expansion</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ffc1b-113">通讯簿下载和通讯簿查询</span><span class="sxs-lookup"><span data-stu-id="ffc1b-113">Address book download and address book query</span></span></p></td>
<td><p><span data-ttu-id="ffc1b-114">增强的9-1-1 （E9-1）呼叫和位置配置文件（拨号计划）</span><span class="sxs-lookup"><span data-stu-id="ffc1b-114">Enhanced 9-1-1 (E9-1-1) calls and location profile (dial plan)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffc1b-115">重视</span><span class="sxs-lookup"><span data-stu-id="ffc1b-115">MultiView</span></span></p></td>
<td><p><span data-ttu-id="ffc1b-116">查看来自会议的多个流</span><span class="sxs-lookup"><span data-stu-id="ffc1b-116">Viewing multiple streams from a conference</span></span></p></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ffc1b-117">Lync Server 2013 应力和性能工具仅支持通过高级配置进行跨池负载生成和联盟。</span><span class="sxs-lookup"><span data-stu-id="ffc1b-117">The Lync Server 2013 Stress and Performance Tool supports cross-pool load generation and federation through advanced configuration only.</span></span>

<span data-ttu-id="ffc1b-118">该工具还不会模拟以下客户端的用户负载：</span><span class="sxs-lookup"><span data-stu-id="ffc1b-118">The tool also does not simulate user load for the following clients:</span></span>

  - <span data-ttu-id="ffc1b-119">Office Live Meeting 2007</span><span class="sxs-lookup"><span data-stu-id="ffc1b-119">Office Live Meeting 2007</span></span>

  - <span data-ttu-id="ffc1b-120">Lync 2013 持久聊天</span><span class="sxs-lookup"><span data-stu-id="ffc1b-120">Lync 2013 Persistent Chat</span></span>

<span data-ttu-id="ffc1b-121">因此，Lync Server 2013 应力和性能工具将不支持测试以下组件：</span><span class="sxs-lookup"><span data-stu-id="ffc1b-121">As a result, the Lync Server 2013 Stress and Performance Tool will not support testing the following components:</span></span>

  - <span data-ttu-id="ffc1b-122">Lync 2013 持久聊天</span><span class="sxs-lookup"><span data-stu-id="ffc1b-122">Lync 2013 Persistent Chat</span></span>

  - <span data-ttu-id="ffc1b-123">Exchange 集成方案</span><span class="sxs-lookup"><span data-stu-id="ffc1b-123">Exchange integration scenarios</span></span>

<div>

## <a name="applications-and-files-included-with-the-lync-server-2013-stress-and-performance-tool"></a><span data-ttu-id="ffc1b-124">Lync Server 2013 应力和性能工具附带的应用程序和文件</span><span class="sxs-lookup"><span data-stu-id="ffc1b-124">Applications and Files Included with the Lync Server 2013 Stress and Performance Tool</span></span>

<span data-ttu-id="ffc1b-125">Lync Server 2013 应力和性能工具中包含下列应用程序：</span><span class="sxs-lookup"><span data-stu-id="ffc1b-125">The following applications are included in the Lync Server 2013 Stress and Performance Tool:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ffc1b-126">工具</span><span class="sxs-lookup"><span data-stu-id="ffc1b-126">Tool</span></span></th>
<th><span data-ttu-id="ffc1b-127">说明</span><span class="sxs-lookup"><span data-stu-id="ffc1b-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ffc1b-128">UserProvisioningTool</span><span class="sxs-lookup"><span data-stu-id="ffc1b-128">UserProvisioningTool.exe</span></span></p></td>
<td><p><span data-ttu-id="ffc1b-129">Lync Server 2013 用户预配工具。</span><span class="sxs-lookup"><span data-stu-id="ffc1b-129">The Lync Server 2013 User Provisioning tool.</span></span> <span data-ttu-id="ffc1b-130">此工具用于创建用户和联系人。</span><span class="sxs-lookup"><span data-stu-id="ffc1b-130">This tool is used to create users and contacts.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffc1b-131">UserProfileGenerator</span><span class="sxs-lookup"><span data-stu-id="ffc1b-131">UserProfileGenerator.exe</span></span></p></td>
<td><p><span data-ttu-id="ffc1b-132">Lync Server 2013 加载配置工具。</span><span class="sxs-lookup"><span data-stu-id="ffc1b-132">The Lync Server 2013 Load Configuration Tool.</span></span> <span data-ttu-id="ffc1b-133">此工具用于配置要模拟的用户负载的特征。</span><span class="sxs-lookup"><span data-stu-id="ffc1b-133">This tool is used to configure the characteristics of the user load to simulate.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ffc1b-134">LyncPerfTool</span><span class="sxs-lookup"><span data-stu-id="ffc1b-134">LyncPerfTool.exe</span></span></p></td>
<td><p><span data-ttu-id="ffc1b-135">Lync Server 2013 应力和性能工具。</span><span class="sxs-lookup"><span data-stu-id="ffc1b-135">The Lync Server 2013 Stress and Performance Tool.</span></span> <span data-ttu-id="ffc1b-136">LyncPerfTool 是模拟用户负载的工具。</span><span class="sxs-lookup"><span data-stu-id="ffc1b-136">LyncPerfTool is the tool that simulates the user load.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ffc1b-137">默认的 tmx</span><span class="sxs-lookup"><span data-stu-id="ffc1b-137">Default.tmx</span></span></p></td>
<td><p><span data-ttu-id="ffc1b-138">使用 Lync Server 2013 日志记录工具需要使用默认的 tmx。</span><span class="sxs-lookup"><span data-stu-id="ffc1b-138">Default.tmx is required to use the Lync Server 2013 Logging Tool.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ffc1b-139">预配脚本示例</span><span class="sxs-lookup"><span data-stu-id="ffc1b-139">Example provisioning scripts</span></span></p></td>
<td><p><span data-ttu-id="ffc1b-140">这些示例用于根据特定方案配置用于运行负载测试的拓扑</span><span class="sxs-lookup"><span data-stu-id="ffc1b-140">These examples are used to configure the topology for running load tests, based on specific scenarios</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

