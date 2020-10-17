---
title: Lync Server 2013：备份和还原要求：数据
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Backup and restoration requirements: data'
ms:assetid: ecfb8e4d-cb4f-476d-9772-4486bd683c04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202194(v=OCS.15)
ms:contentKeyID: 51541526
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8431e16e976f0ad189205f0c42c04d50e6936e90
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527039"
---
# <a name="backup-and-restoration-requirements-in-lync-server-2013-data"></a><span data-ttu-id="e0160-102">Lync Server 2013 中的备份和还原要求： data</span><span class="sxs-lookup"><span data-stu-id="e0160-102">Backup and restoration requirements in Lync Server 2013: data</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e0160-103">_**上次修改的主题：** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="e0160-103">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="e0160-104">Lync Server 使用存储在数据库中的设置和配置信息，以及存储在数据库和文件存储中的数据。</span><span class="sxs-lookup"><span data-stu-id="e0160-104">Lync Server uses settings and configuration information that are stored in databases, and data that is stored in databases and file stores.</span></span> <span data-ttu-id="e0160-105">本主题介绍在您的组织遇到故障或中断时，需要备份以恢复服务的数据，同时还标识了需要单独备份的 Lync Server 所使用的数据和组件。</span><span class="sxs-lookup"><span data-stu-id="e0160-105">This topic describes the data that you need to back up to be able to restore service if your organization experiences a failure or outage, and also identifies the data and components used by Lync Server that you need to back up separately.</span></span>

<div>

## <a name="settings-and-configuration-requirements"></a><span data-ttu-id="e0160-106">设置和配置要求</span><span class="sxs-lookup"><span data-stu-id="e0160-106">Settings and Configuration Requirements</span></span>

<span data-ttu-id="e0160-107">本主题包括备份和还原 Lync Server 服务恢复所需的设置和配置信息的过程。</span><span class="sxs-lookup"><span data-stu-id="e0160-107">This topic includes procedures for backing up and restoring the settings and configuration information that is required for recovery of Lync Server service.</span></span> <span data-ttu-id="e0160-108">配置信息位于中央管理存储或其他后端数据库或 Standard Edition 服务器上。</span><span class="sxs-lookup"><span data-stu-id="e0160-108">The configuration information is located in the Central Management store or on another back-end database or on Standard Edition server.</span></span>

<span data-ttu-id="e0160-109">下表列出了备份和还原所需的设置和配置信息。</span><span class="sxs-lookup"><span data-stu-id="e0160-109">The following table identifies the settings and configuration information that you need to back up and restore.</span></span>

### <a name="settings-and-configuration-data"></a><span data-ttu-id="e0160-110">设置和配置数据</span><span class="sxs-lookup"><span data-stu-id="e0160-110">Settings and Configuration Data</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e0160-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="e0160-111">Type of data</span></span></th>
<th><span data-ttu-id="e0160-112">存储位置</span><span class="sxs-lookup"><span data-stu-id="e0160-112">Where stored</span></span></th>
<th><span data-ttu-id="e0160-113">Description/何时备份</span><span class="sxs-lookup"><span data-stu-id="e0160-113">Description / When to back up</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e0160-114">拓扑配置信息</span><span class="sxs-lookup"><span data-stu-id="e0160-114">Topology configuration information</span></span></p></td>
<td><p><span data-ttu-id="e0160-115">中央管理存储 (数据库： Xds) </span><span class="sxs-lookup"><span data-stu-id="e0160-115">Central Management store (database: Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="e0160-116">拓扑、策略和配置设置。</span><span class="sxs-lookup"><span data-stu-id="e0160-116">Topology, policy, and configuration settings.</span></span></p>
<p><span data-ttu-id="e0160-117">备份常规备份，并在使用 Lync Server 控制面板或 cmdlet 修改配置或策略之后。</span><span class="sxs-lookup"><span data-stu-id="e0160-117">Back up with your regular backups and after you use Lync Server Control Panel or cmdlets to modify your configuration or policies.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0160-118">位置信息</span><span class="sxs-lookup"><span data-stu-id="e0160-118">Location information</span></span></p></td>
<td><p><span data-ttu-id="e0160-119">中央管理存储 (数据库： .Lis) </span><span class="sxs-lookup"><span data-stu-id="e0160-119">Central Management store (database: Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="e0160-120">企业语音增强型 9-1-1 (E9-1-1) 配置信息。</span><span class="sxs-lookup"><span data-stu-id="e0160-120">Enterprise Voice Enhanced 9-1-1 (E9-1-1) configuration information.</span></span> <span data-ttu-id="e0160-121">此信息通常是静态的。</span><span class="sxs-lookup"><span data-stu-id="e0160-121">This information is generally static.</span></span></p>
<p><span data-ttu-id="e0160-122">使用常规备份进行备份。</span><span class="sxs-lookup"><span data-stu-id="e0160-122">Back up with your regular backups.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0160-123">响应组配置信息</span><span class="sxs-lookup"><span data-stu-id="e0160-123">Response Group configuration information</span></span></p></td>
<td><p><span data-ttu-id="e0160-124">后端服务器或 Standard Edition Server (数据库： RgsConfig) </span><span class="sxs-lookup"><span data-stu-id="e0160-124">Back End Server or Standard Edition server (database: RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="e0160-125">响应组代理组、队列和工作流。</span><span class="sxs-lookup"><span data-stu-id="e0160-125">Response Group agent groups, queues, and workflows.</span></span></p>
<p><span data-ttu-id="e0160-126">备份常规备份以及添加或更改代理组、队列或工作流之后。</span><span class="sxs-lookup"><span data-stu-id="e0160-126">Back up with your regular backups and after you add or change agent groups, queues, or workflows.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="data-requirements"></a><span data-ttu-id="e0160-127">数据要求</span><span class="sxs-lookup"><span data-stu-id="e0160-127">Data Requirements</span></span>

<span data-ttu-id="e0160-128">下面列出了需要备份的 Lync Server 数据，以便在发生故障时可以还原 Lync Server 服务。</span><span class="sxs-lookup"><span data-stu-id="e0160-128">Here is a list of the Lync Server data that you need to back up so that you can restore Lync Server service in the event of a failure.</span></span>

<span data-ttu-id="e0160-129">请注意，恢复时不需要某些类型的数据。</span><span class="sxs-lookup"><span data-stu-id="e0160-129">Note that some types of data are not required for recovery.</span></span> <span data-ttu-id="e0160-130">本主题不包含用于备份这些类型数据的过程，其中包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="e0160-130">This topic does not contain procedures for backing up these types of data, which include the following:</span></span>

  - <span data-ttu-id="e0160-131">临时用户数据，例如终结点和订阅、活动会议服务器和临时会议状态 (数据库： RtcDyn) </span><span class="sxs-lookup"><span data-stu-id="e0160-131">Transient user data, such as endpoints and subscriptions, active conferencing servers, and transient conferencing states (database: RtcDyn.mdf)</span></span>

  - <span data-ttu-id="e0160-132">通讯簿数据 (数据库： Rtcab 和 Rtcab1) 。</span><span class="sxs-lookup"><span data-stu-id="e0160-132">Address Book data (databases: Rtcab.mdf and Rtcab1.mdf).</span></span> <span data-ttu-id="e0160-133">通讯簿数据库将自动从 Active Directory 域服务中重新生成。</span><span class="sxs-lookup"><span data-stu-id="e0160-133">The Address Book database is regenerated automatically from Active Directory Domain Services.</span></span>

  - <span data-ttu-id="e0160-134"> (数据库： CpsDyn) 的呼叫寄存应用程序的动态信息</span><span class="sxs-lookup"><span data-stu-id="e0160-134">Dynamic information for the Call Park application (database: CpsDyn.mdf)</span></span>

  - <span data-ttu-id="e0160-135">临时响应组数据，如代理登录状态和呼叫等待信息 (数据库： RgsDyn) </span><span class="sxs-lookup"><span data-stu-id="e0160-135">Transient Response Group data, such as agent sign-in state and call waiting information (database: RgsDyn.mdf)</span></span>

  - <span data-ttu-id="e0160-136">持久聊天 (数据库： MgcComp) 的合规性数据库。</span><span class="sxs-lookup"><span data-stu-id="e0160-136">The compliance database for Persistent Chat (database: MgcComp.mdf).</span></span> <span data-ttu-id="e0160-137">如果启用了持久聊天合规性，则在将适配器配置为从数据库读取信息并将其转换为备用格式后，持久聊天合规性数据库中的信息将是瞬态的。</span><span class="sxs-lookup"><span data-stu-id="e0160-137">If you have Persistent Chat compliance enabled, the information in the Persistent Chat Compliance database is transient as long as you have an adapter configured to read information from the database and convert it to an alternate format.</span></span> <span data-ttu-id="e0160-138">因此，持久聊天的合规性数据库被认为是暂时性的。</span><span class="sxs-lookup"><span data-stu-id="e0160-138">Hence the compliance database for Persistent Chat is considered transient.</span></span>
    
    <span data-ttu-id="e0160-139">Lync Server 2013 持久聊天服务器附带有一个 XML 适配器。</span><span class="sxs-lookup"><span data-stu-id="e0160-139">Lync Server 2013 Persistent Chat Server ships with an XML adapter.</span></span> <span data-ttu-id="e0160-140">您还可以安装接受此数据的自定义适配器并将其移动到其他源，如 Exchange 托管的存档。</span><span class="sxs-lookup"><span data-stu-id="e0160-140">You can also install custom adapters that take this data and move it to other sources, such as Exchange Hosted Archives.</span></span>

<span data-ttu-id="e0160-141">下表标识了需要备份和还原的数据。</span><span class="sxs-lookup"><span data-stu-id="e0160-141">The following table identifies the data that you need to back up and restore.</span></span>

### <a name="data-stored-in-databases"></a><span data-ttu-id="e0160-142">存储在数据库中的数据</span><span class="sxs-lookup"><span data-stu-id="e0160-142">Data Stored in Databases</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e0160-143">数据类型</span><span class="sxs-lookup"><span data-stu-id="e0160-143">Type of data</span></span></th>
<th><span data-ttu-id="e0160-144">存储位置</span><span class="sxs-lookup"><span data-stu-id="e0160-144">Where stored</span></span></th>
<th><span data-ttu-id="e0160-145">Description/何时备份</span><span class="sxs-lookup"><span data-stu-id="e0160-145">Description / When to back up</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e0160-146">持久性用户数据</span><span class="sxs-lookup"><span data-stu-id="e0160-146">Persistent user data</span></span></p></td>
<td><p><span data-ttu-id="e0160-147">后端服务器或 Standard Edition Server (数据库： RTCXDS) </span><span class="sxs-lookup"><span data-stu-id="e0160-147">Back End Server or Standard Edition server (database: RTCXDS.mdf)</span></span></p></td>
<td><p><span data-ttu-id="e0160-148">用户权限、用户联系人列表、服务器或池数据、安排的会议等等。</span><span class="sxs-lookup"><span data-stu-id="e0160-148">User rights, user Contacts lists, server or pool data, scheduled conferences, and so on.</span></span> <span data-ttu-id="e0160-149">此用户数据不包括上载到会议的内容。</span><span class="sxs-lookup"><span data-stu-id="e0160-149">This user data does not include content uploaded to a conference.</span></span></p>
<p><span data-ttu-id="e0160-150">使用常规备份进行备份。</span><span class="sxs-lookup"><span data-stu-id="e0160-150">Back up with your regular backups.</span></span> <span data-ttu-id="e0160-151">此信息是动态的，但是，如果需要还原到上一次常规备份，则更新丢失不会严重到 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="e0160-151">This information is dynamic, but the loss of updates is not catastrophic to Lync Server if you need to restore to your last regular backup.</span></span> <span data-ttu-id="e0160-152">如果 "联系人" 列表对您的组织至关重要，您可以更频繁地备份此数据。</span><span class="sxs-lookup"><span data-stu-id="e0160-152">If Contacts lists are critical to your organization, you can back up this data more frequently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0160-153">存档数据</span><span class="sxs-lookup"><span data-stu-id="e0160-153">Archiving data</span></span></p></td>
<td><p><span data-ttu-id="e0160-154"> (数据库的存档数据库： LcsLog) </span><span class="sxs-lookup"><span data-stu-id="e0160-154">Archiving database (database: LcsLog.mdf)</span></span></p>
<p><span data-ttu-id="e0160-155">如果已启用 Microsoft Exchange 集成选项，则此数据可能存储在 Exchange 2013 上。</span><span class="sxs-lookup"><span data-stu-id="e0160-155">This data may be stored on Exchange 2013, if you have enabled the Microsoft Exchange integration option.</span></span> <span data-ttu-id="e0160-156">否则，此数据将保留在 Lync Server 存档数据库中，该数据库可能与另一个 Lync Server 数据库并置，也可能独立于单独的数据库服务器。</span><span class="sxs-lookup"><span data-stu-id="e0160-156">Otherwise, this data is kept in a Lync Server Archiving database, which may be collocated with another Lync Server database, or stand-alone on a separate database server.</span></span></p></td>
<td><p><span data-ttu-id="e0160-157">即时消息 (IM) 和会议内容。</span><span class="sxs-lookup"><span data-stu-id="e0160-157">Instant messaging (IM) and meeting content.</span></span></p>
<p><span data-ttu-id="e0160-158">此数据对 Lync Server 来说并不重要，但对您的组织而言可能是管理法规的关键。</span><span class="sxs-lookup"><span data-stu-id="e0160-158">This data is not critical to Lync Server, but it may be critical to your organization for regulatory purposes.</span></span> <span data-ttu-id="e0160-159">相应地确定备份计划。</span><span class="sxs-lookup"><span data-stu-id="e0160-159">Determine your back up schedule accordingly.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e0160-160">监视数据</span><span class="sxs-lookup"><span data-stu-id="e0160-160">Monitoring data</span></span></p></td>
<td><p><span data-ttu-id="e0160-161">监视数据库 (LcsCDR 和 QoeMetrics) </span><span class="sxs-lookup"><span data-stu-id="e0160-161">Monitoring databases (LcsCDR.mdf and QoeMetrics.mdf)</span></span></p>
<p><span data-ttu-id="e0160-162">这些数据库可以与其他 Lync Server 数据库并置，也可以独立在单独的数据库服务器上。</span><span class="sxs-lookup"><span data-stu-id="e0160-162">These databases may be collocated with another Lync Server database, or stand-alone on a separate database server.</span></span></p></td>
<td><p><span data-ttu-id="e0160-163"> (LcsCDR) 和经验质量 (QoE) 指标 (QoeMetrics) 中的呼叫详细记录。</span><span class="sxs-lookup"><span data-stu-id="e0160-163">Call detail records (LcsCDR.mdf) and Quality of Experience (QoE) metrics (QoeMetrics.mdf).</span></span></p>
<p><span data-ttu-id="e0160-164">呼叫详细信息记录是动态的，可能对您的业务至关重要。</span><span class="sxs-lookup"><span data-stu-id="e0160-164">Call detail records are dynamic and may be critical to your business.</span></span> <span data-ttu-id="e0160-165">通过考虑是否出于合规性原因需要这些记录来确定备份计划。</span><span class="sxs-lookup"><span data-stu-id="e0160-165">Determine your back up schedule by considering whether you need these records for regulatory reasons.</span></span></p>
<p><span data-ttu-id="e0160-166">体验质量信息是动态的。</span><span class="sxs-lookup"><span data-stu-id="e0160-166">Quality of experience information is dynamic.</span></span> <span data-ttu-id="e0160-167">QoE 数据丢失对 Lync Server 的操作并不重要，但对你的业务来说可能至关重要。</span><span class="sxs-lookup"><span data-stu-id="e0160-167">Loss of QoE data is not critical for the operation of Lync Server, but it may be critical to your business.</span></span> <span data-ttu-id="e0160-168">根据此信息对组织的重要性确定备份日程安排。</span><span class="sxs-lookup"><span data-stu-id="e0160-168">Determine your back up schedule based on how critical this information is to your organization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e0160-169">持久聊天数据</span><span class="sxs-lookup"><span data-stu-id="e0160-169">Persistent Chat data</span></span></p></td>
<td><p><span data-ttu-id="e0160-170">持久聊天数据库 (托管) 。</span><span class="sxs-lookup"><span data-stu-id="e0160-170">Persistent Chat database (mgd.mdf).</span></span></p>
<p><span data-ttu-id="e0160-171">此数据库可以与其他 Lync Server 数据库并置，也可以独立在单独的数据库服务器上。</span><span class="sxs-lookup"><span data-stu-id="e0160-171">This database may be collocated with another Lync Server database, or stand-alone on a separate database server.</span></span></p></td>
<td><p><span data-ttu-id="e0160-172">持久聊天数据是在聊天室中发布的实际聊天内容。</span><span class="sxs-lookup"><span data-stu-id="e0160-172">Persistent Chat Data is actual chat content being posted in chat rooms.</span></span> <span data-ttu-id="e0160-173">此数据通常是关键业务。</span><span class="sxs-lookup"><span data-stu-id="e0160-173">This data is often business critical.</span></span></p>
<p><span data-ttu-id="e0160-174">您可以选择使用 SQL Server 备份，也可以使用 Lync Server 中提供的 <strong>export-cspersistentchatdata</strong> cmdlet 导出数据库。</span><span class="sxs-lookup"><span data-stu-id="e0160-174">You can choose to use SQL Server backup, or export the database by using the <strong>Export-CsPersistentChatData</strong> cmdlet that is provided in Lync Server.</span></span> <span data-ttu-id="e0160-175">若要恢复数据，可以导入数据库并将其还原到上次完整备份的点，这意味着无法将数据库还原到故障点。</span><span class="sxs-lookup"><span data-stu-id="e0160-175">For recovery of the data, you can import and restore the database to the point of the last full backup, which means you cannot restore the database to the point of failure.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="file-store-data-requirements"></a><span data-ttu-id="e0160-176">文件存储数据要求</span><span class="sxs-lookup"><span data-stu-id="e0160-176">File Store Data Requirements</span></span>

<span data-ttu-id="e0160-177">在企业版部署中，Lync Server 文件存储通常位于文件服务器上。</span><span class="sxs-lookup"><span data-stu-id="e0160-177">In an Enterprise Edition deployment, the Lync Server file store is typically located on a file server.</span></span> <span data-ttu-id="e0160-178">在标准版部署中，默认情况下，Lync Server 文件存储位于 Standard Edition 服务器上。</span><span class="sxs-lookup"><span data-stu-id="e0160-178">In a Standard Edition deployment, the Lync Server file store is located by default on the Standard Edition server.</span></span> <span data-ttu-id="e0160-179">通常情况下，为一个站点共享一个 Lync Server 文件存储。</span><span class="sxs-lookup"><span data-stu-id="e0160-179">Typically, there is one Lync Server file store that is shared for a site.</span></span> <span data-ttu-id="e0160-180">持久聊天文件存储使用与 Lync Server 文件存储相同的文件共享。</span><span class="sxs-lookup"><span data-stu-id="e0160-180">The Persistent Chat file store uses the same file share as the Lync Server file store.</span></span>

<span data-ttu-id="e0160-181">文件存储位置标识为 \\ \\ 服务器 \\ 共享名称。</span><span class="sxs-lookup"><span data-stu-id="e0160-181">File store locations are identified as \\\\server\\share name.</span></span> <span data-ttu-id="e0160-182">若要查找文件存储区的特定位置，请打开拓扑生成器并查看 " **文件存储** " 节点。</span><span class="sxs-lookup"><span data-stu-id="e0160-182">To find the specific locations of your file stores, open Topology Builder and look in the **File stores** node.</span></span>

<span data-ttu-id="e0160-183">下表标识了需要备份和还原的文件存储区。</span><span class="sxs-lookup"><span data-stu-id="e0160-183">The following table identifies the file stores you need to back up and restore.</span></span>

### <a name="file-stores"></a><span data-ttu-id="e0160-184">文件存储</span><span class="sxs-lookup"><span data-stu-id="e0160-184">File Stores</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e0160-185">数据类型</span><span class="sxs-lookup"><span data-stu-id="e0160-185">Type of data</span></span></th>
<th><span data-ttu-id="e0160-186">存储位置</span><span class="sxs-lookup"><span data-stu-id="e0160-186">Where stored</span></span></th>
<th><span data-ttu-id="e0160-187">Description/何时备份</span><span class="sxs-lookup"><span data-stu-id="e0160-187">Description / when to back up</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e0160-188">Lync Server 文件存储</span><span class="sxs-lookup"><span data-stu-id="e0160-188">Lync Server file store</span></span></p></td>
<td><p><span data-ttu-id="e0160-189">通常在文件服务器、文件群集或 Standard Edition 服务器上</span><span class="sxs-lookup"><span data-stu-id="e0160-189">Typically on a file server, file cluster, or a Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="e0160-190">会议内容、会议内容元数据、会议合规性日志、应用程序数据文件、设备更新的更新文件、响应组的音频文件、呼叫寄存以及通知应用程序，以及发布到持久聊天室中的文件。</span><span class="sxs-lookup"><span data-stu-id="e0160-190">Meeting content, meeting content metadata, meeting compliance logs, application data files, update files for device updates, audio files for Response Group, Call Park, and Announcement applications, and files posted into Persistent Chat rooms.</span></span></p>
<p><span data-ttu-id="e0160-191">使用常规备份进行备份。</span><span class="sxs-lookup"><span data-stu-id="e0160-191">Back up with your regular backups.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="additional-backup-requirements"></a><span data-ttu-id="e0160-192">其他备份要求</span><span class="sxs-lookup"><span data-stu-id="e0160-192">Additional Backup Requirements</span></span>

<span data-ttu-id="e0160-193">为了帮助确保在发生故障时还原 Lync Server 服务的能力，您必须备份某些不属于 Lync Server 本身的必要组件。</span><span class="sxs-lookup"><span data-stu-id="e0160-193">To help ensure your ability to restore Lync Server services in the event of a failure, you must back up some necessary components that are not part of Lync Server itself.</span></span> <span data-ttu-id="e0160-194">以下组件不会作为本文档中所述的 Lync Server 备份和还原过程的一部分进行备份或还原：</span><span class="sxs-lookup"><span data-stu-id="e0160-194">The following components are not backed up or restored as part of the Lync Server backup and restoration process described in this document:</span></span>

  - <span data-ttu-id="e0160-195">**Active Directory 域服务**    您需要在备份 Lync Server 时使用 Active Directory 工具备份 AD DS。</span><span class="sxs-lookup"><span data-stu-id="e0160-195">**Active Directory Domain Services**   You need to back up AD DS by using Active Directory tools at the same time that you back up Lync Server.</span></span> <span data-ttu-id="e0160-196">务必将 AD DS 与 Lync Server 保持同步，以避免在 Lync Server 预期与 AD DS 中的联系人对象不匹配时可能出现的问题。</span><span class="sxs-lookup"><span data-stu-id="e0160-196">It is important to keep AD DS synchronized with Lync Server, to avoid problems that can occur when Lync Server expects contact objects that do not match those in AD DS.</span></span> <span data-ttu-id="e0160-197">AD DS 存储 Lync Server 使用的以下设置：</span><span class="sxs-lookup"><span data-stu-id="e0160-197">AD DS stores the following settings which are used by Lync Server:</span></span>
    
      - <span data-ttu-id="e0160-198">用户 SIP URI 和其他用户设置。</span><span class="sxs-lookup"><span data-stu-id="e0160-198">User SIP URI and other user settings.</span></span>
    
      - <span data-ttu-id="e0160-199">响应组和会议助理等应用程序的 Contact 对象。</span><span class="sxs-lookup"><span data-stu-id="e0160-199">Contact objects for applications such as Response Group and Conferencing Attendant.</span></span>
    
      - <span data-ttu-id="e0160-200">指向中央管理存储的指针。</span><span class="sxs-lookup"><span data-stu-id="e0160-200">A pointer to the Central Management Store.</span></span>
    
      - <span data-ttu-id="e0160-201">Kerberos 身份验证帐户 (可选的 computer 对象) 和 Lync Server 安全组。</span><span class="sxs-lookup"><span data-stu-id="e0160-201">Kerberos Authentication Account (an optional computer object) and Lync Server security groups.</span></span>
    
    <span data-ttu-id="e0160-202">有关在 Windows Server 2008 中备份和还原 AD DS 的详细信息，请参阅 "AD DS 备份和恢复分步指南"，网址为 [https://go.microsoft.com/fwlink/p/?linkId=209105](https://go.microsoft.com/fwlink/p/?linkid=209105) 。</span><span class="sxs-lookup"><span data-stu-id="e0160-202">For details about backing up and restoring AD DS in Windows Server 2008, see "AD DS Backup and Recovery Step-by-Step Guide" at [https://go.microsoft.com/fwlink/p/?linkId=209105](https://go.microsoft.com/fwlink/p/?linkid=209105).</span></span>

  - <span data-ttu-id="e0160-203">**证书颁发机构和证书**    使用您的组织的策略来备份证书颁发机构 (CA) 和证书。</span><span class="sxs-lookup"><span data-stu-id="e0160-203">**Certification authority and certificates**   Use your organization's policy for backing up your certification authority (CA) and certificates.</span></span> <span data-ttu-id="e0160-204">如果使用可导出私钥，则可以备份证书和私钥，如果使用本文档中的过程还原 Lync Server，则可以对其进行导出。</span><span class="sxs-lookup"><span data-stu-id="e0160-204">If you use exportable private keys, you can back up the certificate and the private key, and then export them if you use the procedures in this document to restore Lync Server.</span></span> <span data-ttu-id="e0160-205">如果您使用内部 CA，如果需要还原 Lync Server，则可以重新注册。</span><span class="sxs-lookup"><span data-stu-id="e0160-205">If you use an internal CA, you can re-enroll if you need to restore Lync Server.</span></span> <span data-ttu-id="e0160-206">在计算机出现故障时将私钥保存在安全位置，这一点很重要。</span><span class="sxs-lookup"><span data-stu-id="e0160-206">It is important that you retain the private key in a secure location where it will be available if a computer fails.</span></span>

  - <span data-ttu-id="e0160-207">**System Center Operations Manager**    如果使用 Microsoft System Center Operations Manager (以前的 Microsoft Operations Manager) 监视 Lync Server 部署，则可以选择在监视 Lync Server 时备份所创建的数据。</span><span class="sxs-lookup"><span data-stu-id="e0160-207">**System Center Operations Manager**   If you use Microsoft System Center Operations Manager (formerly Microsoft Operations Manager) to monitor your Lync Server deployment, you can optionally back up the data it creates while it is monitoring Lync Server.</span></span> <span data-ttu-id="e0160-208">使用您的标准 SQL Server 备份过程来备份 System Center Operations Manager 文件。</span><span class="sxs-lookup"><span data-stu-id="e0160-208">Use your standard SQL Server backup process to back up System Center Operations Manager files.</span></span> <span data-ttu-id="e0160-209">恢复过程中不会还原这些文件。</span><span class="sxs-lookup"><span data-stu-id="e0160-209">These files are not restored during recovery.</span></span>

  - <span data-ttu-id="e0160-210">**公开交换电话网络 (PSTN) 网关配置**    如果使用企业语音或 Survivable 分支设备，则需要备份 PSTN 网关配置。</span><span class="sxs-lookup"><span data-stu-id="e0160-210">**Public switched telephone network (PSTN) gateway configuration**   If you use Enterprise Voice or Survivable Branch Appliances, you need to back up the PSTN gateway configuration.</span></span> <span data-ttu-id="e0160-211">有关备份和还原 PSTN 网关配置的详细信息，请参阅你的供应商。</span><span class="sxs-lookup"><span data-stu-id="e0160-211">See your vendor for details about backing up and restoring PSTN gateway configurations.</span></span>

  - <span data-ttu-id="e0160-212">**Lync server 或 Office 通信服务器**     的版本共存如果您的 Lync Server 2013 部署 coexists 使用 Lync Server 2010 或早期版本的 Office 通信服务器，则不能使用本文档中的过程来备份或还原早期版本。</span><span class="sxs-lookup"><span data-stu-id="e0160-212">**Coexisting versions of Lync Server or Office Communications Server**   If your Lync Server 2013 deployment coexists with Lync Server 2010 or an earlier version of Office Communications Server, you can’t use the procedures in this document for backing up or restoring the earlier version.</span></span> <span data-ttu-id="e0160-213">相反，您必须使用专为早期版本记录的备份和还原过程。</span><span class="sxs-lookup"><span data-stu-id="e0160-213">Instead, you must use the backup and restoration procedures documented specifically for your earlier version.</span></span> <span data-ttu-id="e0160-214">有关备份和还原 Lync Server 2010 的详细信息，请参阅 [https://go.microsoft.com/fwlink/p/?linkId=265417](https://go.microsoft.com/fwlink/p/?linkid=265417) 。</span><span class="sxs-lookup"><span data-stu-id="e0160-214">For details about backing up and restoring Lync Server 2010, see [https://go.microsoft.com/fwlink/p/?linkId=265417](https://go.microsoft.com/fwlink/p/?linkid=265417) .</span></span> <span data-ttu-id="e0160-215">有关备份和还原 Microsoft Office 通信服务器 2007 R2 的详细信息，请参阅 [https://go.microsoft.com/fwlink/p/?linkId=168162](https://go.microsoft.com/fwlink/p/?linkid=168162) 。</span><span class="sxs-lookup"><span data-stu-id="e0160-215">For details about backing up and restoring Microsoft Office Communications Server 2007 R2, see [https://go.microsoft.com/fwlink/p/?linkId=168162](https://go.microsoft.com/fwlink/p/?linkid=168162).</span></span>

  - <span data-ttu-id="e0160-216">**基础结构信息**    您需要备份有关您的基础结构的信息，例如防火墙配置、负载平衡配置、Internet 信息服务 (IIS) 配置、域名系统 (DNS) 记录和 IP 地址，以及动态主机配置协议 (DHCP) 配置。</span><span class="sxs-lookup"><span data-stu-id="e0160-216">**Infrastructure information**   You need to back up information about your infrastructure, such as your firewall configuration, load balancing configuration, Internet Information Services (IIS) configuration, Domain Name System (DNS) records and IP addresses, and Dynamic Host Configuration Protocol (DHCP) configuration.</span></span> <span data-ttu-id="e0160-217">有关备份这些组件的详细信息，请咨询其各自的供应商。</span><span class="sxs-lookup"><span data-stu-id="e0160-217">For details about backing up these components, check with their respective vendors.</span></span>

  - <span data-ttu-id="e0160-218">\*\*Microsoft exchange 和 Exchange 统一消息 (UM) \*\*    备份和还原 Microsoft Exchange 和 Exchange UM，如 Microsoft Exchange 文档中所述。</span><span class="sxs-lookup"><span data-stu-id="e0160-218">**Microsoft Exchange and Exchange Unified Messaging (UM)**   Backup and restore Microsoft Exchange and Exchange UM as described in the Microsoft Exchange documentation.</span></span> <span data-ttu-id="e0160-219">有关备份和还原 Exchange Server 2013 的详细信息，请参阅 [https://go.microsoft.com/fwlink/?LinkId=285384](https://go.microsoft.com/fwlink/?linkid=285384) 。</span><span class="sxs-lookup"><span data-stu-id="e0160-219">For details about backing up and restoring Exchange Server 2013, see [https://go.microsoft.com/fwlink/?LinkId=285384](https://go.microsoft.com/fwlink/?linkid=285384).</span></span> <span data-ttu-id="e0160-220">有关备份和还原 Exchange Server 2010 的详细信息，请参阅 [https://go.microsoft.com/fwlink/p/?linkId=209179](https://go.microsoft.com/fwlink/p/?linkid=209179) 。</span><span class="sxs-lookup"><span data-stu-id="e0160-220">For details about backing up and restoring Exchange Server 2010, see [https://go.microsoft.com/fwlink/p/?linkId=209179](https://go.microsoft.com/fwlink/p/?linkid=209179).</span></span>
    
    <span data-ttu-id="e0160-221">请注意，Lync Server 2013 引入了将用户联系人列表、高清晰度用户照片和存档数据存储在 Exchange 2013 中的功能。</span><span class="sxs-lookup"><span data-stu-id="e0160-221">Note that Lync Server 2013 introduces the ability to have user contact lists, high definition user photos, and archiving data stored in Exchange 2013.</span></span> <span data-ttu-id="e0160-222">若要了解如何备份这些类型的数据，请参阅下面的列表：</span><span class="sxs-lookup"><span data-stu-id="e0160-222">See the following list to see how to back up these types of data:</span></span>
    
      - <span data-ttu-id="e0160-223">将**高清晰度照片**作为 Exchange Server 备份的一部分进行备份。</span><span class="sxs-lookup"><span data-stu-id="e0160-223">**High definition photos** are backed up as part of the Exchange Server backup.</span></span>
    
      - <span data-ttu-id="e0160-224">Lync Server 2013 中引入了**统一的联系人存储库**。</span><span class="sxs-lookup"><span data-stu-id="e0160-224">**Unified contact store** is introduced in Lync Server 2013.</span></span> <span data-ttu-id="e0160-225">统一联系人存储使用户能够将其所有联系人信息保留在 Exchange 2013 中。</span><span class="sxs-lookup"><span data-stu-id="e0160-225">Unified contact store enables users to keep all their contact information in Exchange 2013.</span></span>
        
        <span data-ttu-id="e0160-226">您应确保在用户的联系人存储在统一的联系人存储区中或在 Lync 后端服务器上，备份是最新的。</span><span class="sxs-lookup"><span data-stu-id="e0160-226">You should make sure that backups are up-to-date for users in terms of whether their user contacts are stored in the unified contact store or on the Lync Back End Server.</span></span> <span data-ttu-id="e0160-227">以下方案说明将用户联系人迁移到统一联系人存储区的位置可能会导致备份和还原过程中出现问题。</span><span class="sxs-lookup"><span data-stu-id="e0160-227">The following scenarios illustrate where migrating user contacts to the unified contact store can cause issues for the backup and restore process.</span></span>
        
        <span data-ttu-id="e0160-228">**方案1：** 用户联系人将迁移到统一的联系人存储库，并从迁移用户联系人之前执行的 Lync Server 备份中执行还原。</span><span class="sxs-lookup"><span data-stu-id="e0160-228">**Scenario 1:** User contacts are migrated to the unified contact store, and a restore is performed from a Lync Server backup taken prior to the migration of user contacts.</span></span> <span data-ttu-id="e0160-229">在这种情况下，用户将有一个过期的联系人状态为一天，直到 Lync Server 迁移任务开始将用户联系人迁移到 Exchange。</span><span class="sxs-lookup"><span data-stu-id="e0160-229">In this scenario, the user will have a state of outdated contacts for up to one day until Lync Server Migration Task begins migrating user contacts to Exchange.</span></span> <span data-ttu-id="e0160-230"> (请注意，由于之前的用户联系人已迁移到统一联系人存储，因此将使用) 的 Exchange 联系人信息。</span><span class="sxs-lookup"><span data-stu-id="e0160-230">(Note that because the user contacts were previously migrated to the unified contact store, the Exchange contact information will be used).</span></span> <span data-ttu-id="e0160-231">此方案中不需要管理员干预。</span><span class="sxs-lookup"><span data-stu-id="e0160-231">No administrator intervention is needed in this scenario.</span></span>
        
        <span data-ttu-id="e0160-232">**方案2：** 用户联系人以前存储在统一的联系人存储区中，但随后会回退。</span><span class="sxs-lookup"><span data-stu-id="e0160-232">**Scenario 2:** User contacts were previously stored in the unified contact store, but then rolled back.</span></span> <span data-ttu-id="e0160-233">当用户联系人存储在统一的联系人存储库中时，将从执行的 Lync Server 备份执行还原。</span><span class="sxs-lookup"><span data-stu-id="e0160-233">A restore is performed from a Lync Server backup taken when the user contacts were stored in the unified contact store.</span></span> <span data-ttu-id="e0160-234">在这种情况下， `Error: Incorrect Exchange Version` 在客户端或 Lyss 服务器日志中的一条错误消息可能表明这是一个问题。</span><span class="sxs-lookup"><span data-stu-id="e0160-234">In this scenario, an error message of `Error: Incorrect Exchange Version` in the client or Lyss server logs may indicate this as an issue.</span></span> <span data-ttu-id="e0160-235">用户将能够直接从 Exchange 访问 Lync 2013 中的联系人列表，但客户端的状态将与 Lync Server 的状态不匹配。</span><span class="sxs-lookup"><span data-stu-id="e0160-235">The user will be able to access their contact list in Lync 2013 directly from Exchange, but client’s state will not match the Lync Server state.</span></span> <span data-ttu-id="e0160-236">若要解决此问题，管理员需要对受影响的用户运行 **invoke-csucsrollback** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e0160-236">To fix this, an administrator will need to run the **Invoke-CsUCSRollback** cmdlets for the affected users.</span></span>
    
      - <span data-ttu-id="e0160-237">**存档数据** 可以存储在 Exchange 2013 中。</span><span class="sxs-lookup"><span data-stu-id="e0160-237">**Archiving Data** can be stored in Exchange 2013.</span></span> <span data-ttu-id="e0160-238">此数据对 Lync Server 来说并不重要，但对您的组织而言可能是管理法规的关键。</span><span class="sxs-lookup"><span data-stu-id="e0160-238">This data is not critical to Lync Server, but it may be critical to your organization for regulatory purposes.</span></span> <span data-ttu-id="e0160-239">如果存档数据存储在 Exchange 中并且对您的组织至关重要，请遵循 Exchange 备份和还原过程。</span><span class="sxs-lookup"><span data-stu-id="e0160-239">If archiving data is stored in Exchange and is critical to your organization, then follow Exchange backup and restore procedures.</span></span> <span data-ttu-id="e0160-240">请注意，存储在 Exchange 中的存档数据不能移回到 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="e0160-240">Note that archiving data stored in Exchange cannot be moved back to Lync Server.</span></span> <span data-ttu-id="e0160-241">此外，无法将已存储在 Lync 存档数据库中的数据移动到 Exchange。</span><span class="sxs-lookup"><span data-stu-id="e0160-241">Additionally, there is no way to move data already stored in the Lync archiving database to Exchange.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

