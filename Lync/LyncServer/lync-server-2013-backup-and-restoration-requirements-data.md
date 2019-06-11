---
title: 'Lync Server 2013: 备份和还原要求: 数据'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: 'Backup and restoration requirements: data'
ms:assetid: ecfb8e4d-cb4f-476d-9772-4486bd683c04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202194(v=OCS.15)
ms:contentKeyID: 51541526
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54814295343b99cb51e5827791df160dbeff2638
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837886"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-requirements-in-lync-server-2013-data"></a><span data-ttu-id="51a82-102">Lync Server 2013 中的备份和还原要求: 数据</span><span class="sxs-lookup"><span data-stu-id="51a82-102">Backup and restoration requirements in Lync Server 2013: data</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="51a82-103">_**主题上次修改时间:** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="51a82-103">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="51a82-104">Lync 服务器使用存储在数据库中的设置和配置信息, 以及存储在数据库和文件存储中的数据。</span><span class="sxs-lookup"><span data-stu-id="51a82-104">Lync Server uses settings and configuration information that are stored in databases, and data that is stored in databases and file stores.</span></span> <span data-ttu-id="51a82-105">本主题介绍了需要备份才能还原服务的数据 (如果你的组织遇到故障或中断), 并且还标识 Lync Server 用于你需要单独备份的数据和组件。</span><span class="sxs-lookup"><span data-stu-id="51a82-105">This topic describes the data that you need to back up to be able to restore service if your organization experiences a failure or outage, and also identifies the data and components used by Lync Server that you need to back up separately.</span></span>

<div>

## <a name="settings-and-configuration-requirements"></a><span data-ttu-id="51a82-106">设置和配置要求</span><span class="sxs-lookup"><span data-stu-id="51a82-106">Settings and Configuration Requirements</span></span>

<span data-ttu-id="51a82-107">本主题包括备份和还原 Lync Server 服务恢复所需的设置和配置信息的过程。</span><span class="sxs-lookup"><span data-stu-id="51a82-107">This topic includes procedures for backing up and restoring the settings and configuration information that is required for recovery of Lync Server service.</span></span> <span data-ttu-id="51a82-108">配置信息位于中央管理存储或其他后端数据库或标准版服务器上。</span><span class="sxs-lookup"><span data-stu-id="51a82-108">The configuration information is located in the Central Management store or on another back-end database or on Standard Edition server.</span></span>

<span data-ttu-id="51a82-109">下表标识了备份和还原所需的设置和配置信息。</span><span class="sxs-lookup"><span data-stu-id="51a82-109">The following table identifies the settings and configuration information that you need to back up and restore.</span></span>

### <a name="settings-and-configuration-data"></a><span data-ttu-id="51a82-110">设置和配置数据</span><span class="sxs-lookup"><span data-stu-id="51a82-110">Settings and Configuration Data</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="51a82-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="51a82-111">Type of data</span></span></th>
<th><span data-ttu-id="51a82-112">存储位置</span><span class="sxs-lookup"><span data-stu-id="51a82-112">Where stored</span></span></th>
<th><span data-ttu-id="51a82-113">说明/要备份的时间</span><span class="sxs-lookup"><span data-stu-id="51a82-113">Description / When to back up</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="51a82-114">拓扑配置信息</span><span class="sxs-lookup"><span data-stu-id="51a82-114">Topology configuration information</span></span></p></td>
<td><p><span data-ttu-id="51a82-115">中央管理存储 (数据库: Xds)</span><span class="sxs-lookup"><span data-stu-id="51a82-115">Central Management store (database: Xds.mdf)</span></span></p></td>
<td><p><span data-ttu-id="51a82-116">拓扑、策略和配置设置。</span><span class="sxs-lookup"><span data-stu-id="51a82-116">Topology, policy, and configuration settings.</span></span></p>
<p><span data-ttu-id="51a82-117">使用您的常规备份和使用 Lync Server 控制面板或 cmdlet 修改配置或策略后, 进行备份。</span><span class="sxs-lookup"><span data-stu-id="51a82-117">Back up with your regular backups and after you use Lync Server Control Panel or cmdlets to modify your configuration or policies.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51a82-118">位置信息</span><span class="sxs-lookup"><span data-stu-id="51a82-118">Location information</span></span></p></td>
<td><p><span data-ttu-id="51a82-119">中央管理存储 (数据库: .Lis)</span><span class="sxs-lookup"><span data-stu-id="51a82-119">Central Management store (database: Lis.mdf)</span></span></p></td>
<td><p><span data-ttu-id="51a82-120">企业语音增强 9-1-1 (E9-1) 配置信息。</span><span class="sxs-lookup"><span data-stu-id="51a82-120">Enterprise Voice Enhanced 9-1-1 (E9-1-1) configuration information.</span></span> <span data-ttu-id="51a82-121">此信息通常是静态的。</span><span class="sxs-lookup"><span data-stu-id="51a82-121">This information is generally static.</span></span></p>
<p><span data-ttu-id="51a82-122">备份您的常规备份。</span><span class="sxs-lookup"><span data-stu-id="51a82-122">Back up with your regular backups.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51a82-123">响应组配置信息</span><span class="sxs-lookup"><span data-stu-id="51a82-123">Response Group configuration information</span></span></p></td>
<td><p><span data-ttu-id="51a82-124">后端服务器或标准版服务器 (数据库: RgsConfig)</span><span class="sxs-lookup"><span data-stu-id="51a82-124">Back End Server or Standard Edition server (database: RgsConfig.mdf)</span></span></p></td>
<td><p><span data-ttu-id="51a82-125">响应组代理组、队列和工作流。</span><span class="sxs-lookup"><span data-stu-id="51a82-125">Response Group agent groups, queues, and workflows.</span></span></p>
<p><span data-ttu-id="51a82-126">备份您的常规备份以及添加或更改代理组、队列或工作流后。</span><span class="sxs-lookup"><span data-stu-id="51a82-126">Back up with your regular backups and after you add or change agent groups, queues, or workflows.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="data-requirements"></a><span data-ttu-id="51a82-127">数据要求</span><span class="sxs-lookup"><span data-stu-id="51a82-127">Data Requirements</span></span>

<span data-ttu-id="51a82-128">下面是您需要备份的 Lync 服务器数据的列表, 以便您可以在出现故障时还原 Lync Server 服务。</span><span class="sxs-lookup"><span data-stu-id="51a82-128">Here is a list of the Lync Server data that you need to back up so that you can restore Lync Server service in the event of a failure.</span></span>

<span data-ttu-id="51a82-129">请注意, 恢复时不需要某些类型的数据。</span><span class="sxs-lookup"><span data-stu-id="51a82-129">Note that some types of data are not required for recovery.</span></span> <span data-ttu-id="51a82-130">本主题不包含备份这些类型的数据的过程, 包括以下内容:</span><span class="sxs-lookup"><span data-stu-id="51a82-130">This topic does not contain procedures for backing up these types of data, which include the following:</span></span>

  - <span data-ttu-id="51a82-131">临时用户数据, 如终结点和订阅、活动会议服务器和暂时性的会议状态 (数据库: RtcDyn)</span><span class="sxs-lookup"><span data-stu-id="51a82-131">Transient user data, such as endpoints and subscriptions, active conferencing servers, and transient conferencing states (database: RtcDyn.mdf)</span></span>

  - <span data-ttu-id="51a82-132">通讯簿数据 (数据库: Rtcab 和 Rtcab1)。</span><span class="sxs-lookup"><span data-stu-id="51a82-132">Address Book data (databases: Rtcab.mdf and Rtcab1.mdf).</span></span> <span data-ttu-id="51a82-133">通讯簿数据库将从 Active Directory 域服务自动重新生成。</span><span class="sxs-lookup"><span data-stu-id="51a82-133">The Address Book database is regenerated automatically from Active Directory Domain Services.</span></span>

  - <span data-ttu-id="51a82-134">呼叫驻留应用程序的动态信息 (数据库: CpsDyn)</span><span class="sxs-lookup"><span data-stu-id="51a82-134">Dynamic information for the Call Park application (database: CpsDyn.mdf)</span></span>

  - <span data-ttu-id="51a82-135">暂时性的响应组数据, 例如代理登录状态和呼叫等待信息 (数据库: RgsDyn)</span><span class="sxs-lookup"><span data-stu-id="51a82-135">Transient Response Group data, such as agent sign-in state and call waiting information (database: RgsDyn.mdf)</span></span>

  - <span data-ttu-id="51a82-136">适用于持久聊天的合规性数据库 (数据库: MgcComp)。</span><span class="sxs-lookup"><span data-stu-id="51a82-136">The compliance database for Persistent Chat (database: MgcComp.mdf).</span></span> <span data-ttu-id="51a82-137">如果你启用了持久的聊天合规性, 则只要你拥有配置为从数据库读取信息并将其转换为备用格式的适配器, 持久聊天合规性数据库中的信息就会暂时性。</span><span class="sxs-lookup"><span data-stu-id="51a82-137">If you have Persistent Chat compliance enabled, the information in the Persistent Chat Compliance database is transient as long as you have an adapter configured to read information from the database and convert it to an alternate format.</span></span> <span data-ttu-id="51a82-138">因此, 持久聊天的合规性数据库被认为是暂时性的。</span><span class="sxs-lookup"><span data-stu-id="51a82-138">Hence the compliance database for Persistent Chat is considered transient.</span></span>
    
    <span data-ttu-id="51a82-139">Lync Server 2013 持久聊天服务器随附有一个 XML 适配器。</span><span class="sxs-lookup"><span data-stu-id="51a82-139">Lync Server 2013 Persistent Chat Server ships with an XML adapter.</span></span> <span data-ttu-id="51a82-140">你还可以安装接受此数据并将其移动到其他源 (如 Exchange 托管的存档) 的自定义适配器。</span><span class="sxs-lookup"><span data-stu-id="51a82-140">You can also install custom adapters that take this data and move it to other sources, such as Exchange Hosted Archives.</span></span>

<span data-ttu-id="51a82-141">下表标识了备份和还原所需的数据。</span><span class="sxs-lookup"><span data-stu-id="51a82-141">The following table identifies the data that you need to back up and restore.</span></span>

### <a name="data-stored-in-databases"></a><span data-ttu-id="51a82-142">数据库中存储的数据</span><span class="sxs-lookup"><span data-stu-id="51a82-142">Data Stored in Databases</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="51a82-143">数据类型</span><span class="sxs-lookup"><span data-stu-id="51a82-143">Type of data</span></span></th>
<th><span data-ttu-id="51a82-144">存储位置</span><span class="sxs-lookup"><span data-stu-id="51a82-144">Where stored</span></span></th>
<th><span data-ttu-id="51a82-145">说明/要备份的时间</span><span class="sxs-lookup"><span data-stu-id="51a82-145">Description / When to back up</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="51a82-146">永久性用户数据</span><span class="sxs-lookup"><span data-stu-id="51a82-146">Persistent user data</span></span></p></td>
<td><p><span data-ttu-id="51a82-147">后端服务器或标准版服务器 (数据库: RTCXDS)</span><span class="sxs-lookup"><span data-stu-id="51a82-147">Back End Server or Standard Edition server (database: RTCXDS.mdf)</span></span></p></td>
<td><p><span data-ttu-id="51a82-148">用户权限、用户联系人列表、服务器或池数据、计划的会议等。</span><span class="sxs-lookup"><span data-stu-id="51a82-148">User rights, user Contacts lists, server or pool data, scheduled conferences, and so on.</span></span> <span data-ttu-id="51a82-149">此用户数据不包括上载到会议的内容。</span><span class="sxs-lookup"><span data-stu-id="51a82-149">This user data does not include content uploaded to a conference.</span></span></p>
<p><span data-ttu-id="51a82-150">备份您的常规备份。</span><span class="sxs-lookup"><span data-stu-id="51a82-150">Back up with your regular backups.</span></span> <span data-ttu-id="51a82-151">此信息是动态的, 但更新丢失对于 Lync 服务器来说不是严重的, 前提是您需要还原到上一次常规备份。</span><span class="sxs-lookup"><span data-stu-id="51a82-151">This information is dynamic, but the loss of updates is not catastrophic to Lync Server if you need to restore to your last regular backup.</span></span> <span data-ttu-id="51a82-152">如果联系人列表对您的组织非常重要, 则您可以更频繁地备份此数据。</span><span class="sxs-lookup"><span data-stu-id="51a82-152">If Contacts lists are critical to your organization, you can back up this data more frequently.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51a82-153">存档数据</span><span class="sxs-lookup"><span data-stu-id="51a82-153">Archiving data</span></span></p></td>
<td><p><span data-ttu-id="51a82-154">存档数据库 (数据库: LcsLog)</span><span class="sxs-lookup"><span data-stu-id="51a82-154">Archiving database (database: LcsLog.mdf)</span></span></p>
<p><span data-ttu-id="51a82-155">如果已启用 "Microsoft Exchange 集成" 选项, 则此数据可能存储在 Exchange 2013 上。</span><span class="sxs-lookup"><span data-stu-id="51a82-155">This data may be stored on Exchange 2013, if you have enabled the Microsoft Exchange integration option.</span></span> <span data-ttu-id="51a82-156">否则, 此数据将保留在 Lync Server 存档数据库中, 该数据库可能与另一个 Lync Server 数据库 collocated, 或者在单独的数据库服务器上独立。</span><span class="sxs-lookup"><span data-stu-id="51a82-156">Otherwise, this data is kept in a Lync Server Archiving database, which may be collocated with another Lync Server database, or stand-alone on a separate database server.</span></span></p></td>
<td><p><span data-ttu-id="51a82-157">即时消息 (IM) 和会议内容。</span><span class="sxs-lookup"><span data-stu-id="51a82-157">Instant messaging (IM) and meeting content.</span></span></p>
<p><span data-ttu-id="51a82-158">对于 Lync Server 而言, 此数据并不重要, 但对您的组织而言可能至关重要。</span><span class="sxs-lookup"><span data-stu-id="51a82-158">This data is not critical to Lync Server, but it may be critical to your organization for regulatory purposes.</span></span> <span data-ttu-id="51a82-159">请相应地确定您的备份计划。</span><span class="sxs-lookup"><span data-stu-id="51a82-159">Determine your back up schedule accordingly.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51a82-160">监视数据</span><span class="sxs-lookup"><span data-stu-id="51a82-160">Monitoring data</span></span></p></td>
<td><p><span data-ttu-id="51a82-161">监视数据库 (LcsCDR 和 QoeMetrics)</span><span class="sxs-lookup"><span data-stu-id="51a82-161">Monitoring databases (LcsCDR.mdf and QoeMetrics.mdf)</span></span></p>
<p><span data-ttu-id="51a82-162">这些数据库可能与另一个 Lync Server 数据库 collocated, 也可能独立于单独的数据库服务器。</span><span class="sxs-lookup"><span data-stu-id="51a82-162">These databases may be collocated with another Lync Server database, or stand-alone on a separate database server.</span></span></p></td>
<td><p><span data-ttu-id="51a82-163">呼叫详细记录 (LcsCDR) 和体验质量 (QoE) 指标 (QoeMetrics)。</span><span class="sxs-lookup"><span data-stu-id="51a82-163">Call detail records (LcsCDR.mdf) and Quality of Experience (QoE) metrics (QoeMetrics.mdf).</span></span></p>
<p><span data-ttu-id="51a82-164">通话详细记录是动态的, 可能对您的企业至关重要。</span><span class="sxs-lookup"><span data-stu-id="51a82-164">Call detail records are dynamic and may be critical to your business.</span></span> <span data-ttu-id="51a82-165">通过考虑是否需要这些记录来确定备份计划, 以确定其合规性。</span><span class="sxs-lookup"><span data-stu-id="51a82-165">Determine your back up schedule by considering whether you need these records for regulatory reasons.</span></span></p>
<p><span data-ttu-id="51a82-166">体验信息的质量是动态的。</span><span class="sxs-lookup"><span data-stu-id="51a82-166">Quality of experience information is dynamic.</span></span> <span data-ttu-id="51a82-167">QoE 数据的损失对于 Lync Server 的操作并不重要, 但对您的业务来说可能至关重要。</span><span class="sxs-lookup"><span data-stu-id="51a82-167">Loss of QoE data is not critical for the operation of Lync Server, but it may be critical to your business.</span></span> <span data-ttu-id="51a82-168">根据你的组织的这些信息的重要程度确定你的备份计划。</span><span class="sxs-lookup"><span data-stu-id="51a82-168">Determine your back up schedule based on how critical this information is to your organization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51a82-169">持久聊天数据</span><span class="sxs-lookup"><span data-stu-id="51a82-169">Persistent Chat data</span></span></p></td>
<td><p><span data-ttu-id="51a82-170">持久聊天数据库 (mgd)。</span><span class="sxs-lookup"><span data-stu-id="51a82-170">Persistent Chat database (mgd.mdf).</span></span></p>
<p><span data-ttu-id="51a82-171">此数据库可以与另一个 Lync Server 数据库 collocated, 也可以独立于单独的数据库服务器。</span><span class="sxs-lookup"><span data-stu-id="51a82-171">This database may be collocated with another Lync Server database, or stand-alone on a separate database server.</span></span></p></td>
<td><p><span data-ttu-id="51a82-172">持久聊天数据是在聊天室中发布的实际聊天内容。</span><span class="sxs-lookup"><span data-stu-id="51a82-172">Persistent Chat Data is actual chat content being posted in chat rooms.</span></span> <span data-ttu-id="51a82-173">此数据通常是业务关键型的。</span><span class="sxs-lookup"><span data-stu-id="51a82-173">This data is often business critical.</span></span></p>
<p><span data-ttu-id="51a82-174">你可以选择使用 SQL Server 备份, 或使用 Lync Server 中提供的<strong>CsPersistentChatData</strong> cmdlet 导出数据库。</span><span class="sxs-lookup"><span data-stu-id="51a82-174">You can choose to use SQL Server backup, or export the database by using the <strong>Export-CsPersistentChatData</strong> cmdlet that is provided in Lync Server.</span></span> <span data-ttu-id="51a82-175">若要恢复数据, 可以将数据库导入和还原到上次完全备份的位置, 这意味着无法将数据库还原到故障点。</span><span class="sxs-lookup"><span data-stu-id="51a82-175">For recovery of the data, you can import and restore the database to the point of the last full backup, which means you cannot restore the database to the point of failure.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="file-store-data-requirements"></a><span data-ttu-id="51a82-176">文件存储数据要求</span><span class="sxs-lookup"><span data-stu-id="51a82-176">File Store Data Requirements</span></span>

<span data-ttu-id="51a82-177">在企业版部署中, Lync Server 文件存储通常位于文件服务器上。</span><span class="sxs-lookup"><span data-stu-id="51a82-177">In an Enterprise Edition deployment, the Lync Server file store is typically located on a file server.</span></span> <span data-ttu-id="51a82-178">在标准版部署中, Lync Server 文件存储在默认情况下位于标准版服务器上。</span><span class="sxs-lookup"><span data-stu-id="51a82-178">In a Standard Edition deployment, the Lync Server file store is located by default on the Standard Edition server.</span></span> <span data-ttu-id="51a82-179">通常情况下, 网站会共享一个 Lync Server 文件存储。</span><span class="sxs-lookup"><span data-stu-id="51a82-179">Typically, there is one Lync Server file store that is shared for a site.</span></span> <span data-ttu-id="51a82-180">持久聊天文件存储使用与 Lync Server 文件存储相同的文件共享。</span><span class="sxs-lookup"><span data-stu-id="51a82-180">The Persistent Chat file store uses the same file share as the Lync Server file store.</span></span>

<span data-ttu-id="51a82-181">文件存储位置标识为\\ \\服务器\\共享名称。</span><span class="sxs-lookup"><span data-stu-id="51a82-181">File store locations are identified as \\\\server\\share name.</span></span> <span data-ttu-id="51a82-182">若要查找文件存储的特定位置, 请打开拓扑生成器并查看 "**文件存储**" 节点。</span><span class="sxs-lookup"><span data-stu-id="51a82-182">To find the specific locations of your file stores, open Topology Builder and look in the **File stores** node.</span></span>

<span data-ttu-id="51a82-183">下表标识了需要备份和还原的文件存储。</span><span class="sxs-lookup"><span data-stu-id="51a82-183">The following table identifies the file stores you need to back up and restore.</span></span>

### <a name="file-stores"></a><span data-ttu-id="51a82-184">文件存储</span><span class="sxs-lookup"><span data-stu-id="51a82-184">File Stores</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="51a82-185">数据类型</span><span class="sxs-lookup"><span data-stu-id="51a82-185">Type of data</span></span></th>
<th><span data-ttu-id="51a82-186">存储位置</span><span class="sxs-lookup"><span data-stu-id="51a82-186">Where stored</span></span></th>
<th><span data-ttu-id="51a82-187">说明/要备份的时间</span><span class="sxs-lookup"><span data-stu-id="51a82-187">Description / when to back up</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="51a82-188">Lync Server 文件存储</span><span class="sxs-lookup"><span data-stu-id="51a82-188">Lync Server file store</span></span></p></td>
<td><p><span data-ttu-id="51a82-189">通常在文件服务器、文件群集或标准版服务器上</span><span class="sxs-lookup"><span data-stu-id="51a82-189">Typically on a file server, file cluster, or a Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="51a82-190">会议内容、会议内容元数据、会议合规性日志、应用程序数据文件、为设备更新更新文件、响应组的音频文件、呼叫寄存和发布应用程序, 以及发布到持久聊天室的文件。</span><span class="sxs-lookup"><span data-stu-id="51a82-190">Meeting content, meeting content metadata, meeting compliance logs, application data files, update files for device updates, audio files for Response Group, Call Park, and Announcement applications, and files posted into Persistent Chat rooms.</span></span></p>
<p><span data-ttu-id="51a82-191">备份您的常规备份。</span><span class="sxs-lookup"><span data-stu-id="51a82-191">Back up with your regular backups.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="additional-backup-requirements"></a><span data-ttu-id="51a82-192">其他备份要求</span><span class="sxs-lookup"><span data-stu-id="51a82-192">Additional Backup Requirements</span></span>

<span data-ttu-id="51a82-193">为了帮助确保在发生故障时还原 Lync Server 服务的能力, 您必须备份不属于 Lync Server 本身的一些必要组件。</span><span class="sxs-lookup"><span data-stu-id="51a82-193">To help ensure your ability to restore Lync Server services in the event of a failure, you must back up some necessary components that are not part of Lync Server itself.</span></span> <span data-ttu-id="51a82-194">以下组件不会作为本文档中所述 Lync Server 备份和还原过程的一部分进行备份或还原:</span><span class="sxs-lookup"><span data-stu-id="51a82-194">The following components are not backed up or restored as part of the Lync Server backup and restoration process described in this document:</span></span>

  - <span data-ttu-id="51a82-195">**Active directory 域服务**   您需要在备份 Lync Server 的同时使用 active directory 工具备份 AD DS。</span><span class="sxs-lookup"><span data-stu-id="51a82-195">**Active Directory Domain Services**   You need to back up AD DS by using Active Directory tools at the same time that you back up Lync Server.</span></span> <span data-ttu-id="51a82-196">将 AD DS 与 Lync Server 保持同步, 以避免当 Lync Server 预期与 AD DS 中的联系人对象不匹配时可能出现的问题是非常重要的。</span><span class="sxs-lookup"><span data-stu-id="51a82-196">It is important to keep AD DS synchronized with Lync Server, to avoid problems that can occur when Lync Server expects contact objects that do not match those in AD DS.</span></span> <span data-ttu-id="51a82-197">AD DS 存储由 Lync Server 使用的以下设置:</span><span class="sxs-lookup"><span data-stu-id="51a82-197">AD DS stores the following settings which are used by Lync Server:</span></span>
    
      - <span data-ttu-id="51a82-198">用户 SIP URI 和其他用户设置。</span><span class="sxs-lookup"><span data-stu-id="51a82-198">User SIP URI and other user settings.</span></span>
    
      - <span data-ttu-id="51a82-199">响应组和会议助理等应用程序的联系人对象。</span><span class="sxs-lookup"><span data-stu-id="51a82-199">Contact objects for applications such as Response Group and Conferencing Attendant.</span></span>
    
      - <span data-ttu-id="51a82-200">指向中央管理存储的指针。</span><span class="sxs-lookup"><span data-stu-id="51a82-200">A pointer to the Central Management Store.</span></span>
    
      - <span data-ttu-id="51a82-201">Kerberos 身份验证帐户 (可选的计算机对象) 和 Lync Server 安全组。</span><span class="sxs-lookup"><span data-stu-id="51a82-201">Kerberos Authentication Account (an optional computer object) and Lync Server security groups.</span></span>
    
    <span data-ttu-id="51a82-202">有关在 Windows Server 2008 中备份和还原 AD DS 的详细信息, 请参阅 "AD DS 备份和恢复分步指南" [http://go.microsoft.com/fwlink/p/?linkId=209105](http://go.microsoft.com/fwlink/p/?linkid=209105)。</span><span class="sxs-lookup"><span data-stu-id="51a82-202">For details about backing up and restoring AD DS in Windows Server 2008, see "AD DS Backup and Recovery Step-by-Step Guide" at [http://go.microsoft.com/fwlink/p/?linkId=209105](http://go.microsoft.com/fwlink/p/?linkid=209105).</span></span>

  - <span data-ttu-id="51a82-203">**证书颁发机构和证书**   使用您的组织的策略来备份您的证书颁发机构 (CA) 和证书。</span><span class="sxs-lookup"><span data-stu-id="51a82-203">**Certification authority and certificates**   Use your organization's policy for backing up your certification authority (CA) and certificates.</span></span> <span data-ttu-id="51a82-204">如果使用可导出私钥, 则可以备份证书和私钥, 如果使用本文档中的过程还原 Lync Server, 则可以将其导出。</span><span class="sxs-lookup"><span data-stu-id="51a82-204">If you use exportable private keys, you can back up the certificate and the private key, and then export them if you use the procedures in this document to restore Lync Server.</span></span> <span data-ttu-id="51a82-205">如果你使用内部 CA, 则可以重新注册 (如果你需要还原 Lync 服务器)。</span><span class="sxs-lookup"><span data-stu-id="51a82-205">If you use an internal CA, you can re-enroll if you need to restore Lync Server.</span></span> <span data-ttu-id="51a82-206">请务必将私钥保留在一个安全的位置, 以便在计算机出现故障时使用该私钥。</span><span class="sxs-lookup"><span data-stu-id="51a82-206">It is important that you retain the private key in a secure location where it will be available if a computer fails.</span></span>

  - <span data-ttu-id="51a82-207">**System Center operations manager**   如果你使用 microsoft System center operations manager (以前称为 Microsoft Operations manager) 监视 lync Server 部署, 你可以选择备份它在监视 lync 时创建的数据服务.</span><span class="sxs-lookup"><span data-stu-id="51a82-207">**System Center Operations Manager**   If you use Microsoft System Center Operations Manager (formerly Microsoft Operations Manager) to monitor your Lync Server deployment, you can optionally back up the data it creates while it is monitoring Lync Server.</span></span> <span data-ttu-id="51a82-208">使用您的标准 SQL Server 备份过程备份 System Center Operations Manager 文件。</span><span class="sxs-lookup"><span data-stu-id="51a82-208">Use your standard SQL Server backup process to back up System Center Operations Manager files.</span></span> <span data-ttu-id="51a82-209">这些文件在恢复期间不会还原。</span><span class="sxs-lookup"><span data-stu-id="51a82-209">These files are not restored during recovery.</span></span>

  - <span data-ttu-id="51a82-210">**公共交换式电话网络 (PSTN) 网关配置**   如果您使用企业语音或 Survivable 分支装置, 则需要备份 PSTN 网关配置。</span><span class="sxs-lookup"><span data-stu-id="51a82-210">**Public switched telephone network (PSTN) gateway configuration**   If you use Enterprise Voice or Survivable Branch Appliances, you need to back up the PSTN gateway configuration.</span></span> <span data-ttu-id="51a82-211">有关备份和还原 PSTN 网关配置的详细信息, 请参阅您的供应商。</span><span class="sxs-lookup"><span data-stu-id="51a82-211">See your vendor for details about backing up and restoring PSTN gateway configurations.</span></span>

  - <span data-ttu-id="51a82-212">**旧版 lync server 或 Office 通信服务器**   如果您的 lync server 2013 部署 coexists 使用 lync server 2010 或早期版本的 Office 通信服务器, 则不能使用本文档中的过程进行备份或还原早期版本。</span><span class="sxs-lookup"><span data-stu-id="51a82-212">**Coexisting versions of Lync Server or Office Communications Server**   If your Lync Server 2013 deployment coexists with Lync Server 2010 or an earlier version of Office Communications Server, you can’t use the procedures in this document for backing up or restoring the earlier version.</span></span> <span data-ttu-id="51a82-213">而是必须使用专为早期版本记录的备份和还原过程。</span><span class="sxs-lookup"><span data-stu-id="51a82-213">Instead, you must use the backup and restoration procedures documented specifically for your earlier version.</span></span> <span data-ttu-id="51a82-214">有关备份和还原 Lync Server 2010 的详细信息, 请[http://go.microsoft.com/fwlink/p/?linkId=265417](http://go.microsoft.com/fwlink/p/?linkid=265417)参阅。</span><span class="sxs-lookup"><span data-stu-id="51a82-214">For details about backing up and restoring Lync Server 2010, see [http://go.microsoft.com/fwlink/p/?linkId=265417](http://go.microsoft.com/fwlink/p/?linkid=265417) .</span></span> <span data-ttu-id="51a82-215">有关备份和还原 Microsoft Office 通信服务器 2007 R2 的详细信息, 请[http://go.microsoft.com/fwlink/p/?linkId=168162](http://go.microsoft.com/fwlink/p/?linkid=168162)参阅。</span><span class="sxs-lookup"><span data-stu-id="51a82-215">For details about backing up and restoring Microsoft Office Communications Server 2007 R2, see [http://go.microsoft.com/fwlink/p/?linkId=168162](http://go.microsoft.com/fwlink/p/?linkid=168162).</span></span>

  - <span data-ttu-id="51a82-216">**基础结构信息**   您需要备份有关您的基础结构的信息, 例如防火墙配置、负载平衡配置、Internet 信息服务 (IIS) 配置、域名系统 (DNS) 记录和IP 地址和动态主机配置协议 (DHCP) 配置。</span><span class="sxs-lookup"><span data-stu-id="51a82-216">**Infrastructure information**   You need to back up information about your infrastructure, such as your firewall configuration, load balancing configuration, Internet Information Services (IIS) configuration, Domain Name System (DNS) records and IP addresses, and Dynamic Host Configuration Protocol (DHCP) configuration.</span></span> <span data-ttu-id="51a82-217">有关备份这些组件的详细信息, 请咨询其各自的供应商。</span><span class="sxs-lookup"><span data-stu-id="51a82-217">For details about backing up these components, check with their respective vendors.</span></span>

  - <span data-ttu-id="51a82-218">**Microsoft exchange 和 exchange 统一消息 (UM)**   备份和还原 microsoft exchange 和 exchange UM, 如 microsoft exchange 文档中所述。</span><span class="sxs-lookup"><span data-stu-id="51a82-218">**Microsoft Exchange and Exchange Unified Messaging (UM)**   Backup and restore Microsoft Exchange and Exchange UM as described in the Microsoft Exchange documentation.</span></span> <span data-ttu-id="51a82-219">有关备份和还原 Exchange Server 2013 的详细信息, 请[http://go.microsoft.com/fwlink/?LinkId=285384](http://go.microsoft.com/fwlink/?linkid=285384)参阅。</span><span class="sxs-lookup"><span data-stu-id="51a82-219">For details about backing up and restoring Exchange Server 2013, see [http://go.microsoft.com/fwlink/?LinkId=285384](http://go.microsoft.com/fwlink/?linkid=285384).</span></span> <span data-ttu-id="51a82-220">有关备份和还原 Exchange Server 2010 的详细信息, 请[http://go.microsoft.com/fwlink/p/?linkId=209179](http://go.microsoft.com/fwlink/p/?linkid=209179)参阅。</span><span class="sxs-lookup"><span data-stu-id="51a82-220">For details about backing up and restoring Exchange Server 2010, see [http://go.microsoft.com/fwlink/p/?linkId=209179](http://go.microsoft.com/fwlink/p/?linkid=209179).</span></span>
    
    <span data-ttu-id="51a82-221">请注意, Lync Server 2013 引入了具有用户联系人列表、高清晰度用户照片和存档 Exchange 2013 中存储的数据的功能。</span><span class="sxs-lookup"><span data-stu-id="51a82-221">Note that Lync Server 2013 introduces the ability to have user contact lists, high definition user photos, and archiving data stored in Exchange 2013.</span></span> <span data-ttu-id="51a82-222">请参阅以下列表, 了解如何备份这些类型的数据:</span><span class="sxs-lookup"><span data-stu-id="51a82-222">See the following list to see how to back up these types of data:</span></span>
    
      - <span data-ttu-id="51a82-223">**高清晰度照片**作为 Exchange Server 备份的一部分进行备份。</span><span class="sxs-lookup"><span data-stu-id="51a82-223">**High definition photos** are backed up as part of the Exchange Server backup.</span></span>
    
      - <span data-ttu-id="51a82-224">在 Lync Server 2013 中引入了 "**统一联系人存储**"。</span><span class="sxs-lookup"><span data-stu-id="51a82-224">**Unified contact store** is introduced in Lync Server 2013.</span></span> <span data-ttu-id="51a82-225">"统一联系人存储" 使用户能够在 Exchange 2013 中保留其所有联系人信息。</span><span class="sxs-lookup"><span data-stu-id="51a82-225">Unified contact store enables users to keep all their contact information in Exchange 2013.</span></span>
        
        <span data-ttu-id="51a82-226">你应该确保对用户而言, 用户的联系人存储在 "统一联系人存储" 还是 "Lync 后端服务器" 中。</span><span class="sxs-lookup"><span data-stu-id="51a82-226">You should make sure that backups are up-to-date for users in terms of whether their user contacts are stored in the unified contact store or on the Lync Back End Server.</span></span> <span data-ttu-id="51a82-227">以下方案说明将用户联系人迁移到 "统一联系人存储" 的位置可能会导致备份和还原过程中出现问题。</span><span class="sxs-lookup"><span data-stu-id="51a82-227">The following scenarios illustrate where migrating user contacts to the unified contact store can cause issues for the backup and restore process.</span></span>
        
        <span data-ttu-id="51a82-228">**情形 1:** 用户联系人将迁移到 "统一联系人存储区", 从迁移用户联系人之前所执行的 Lync 服务器备份执行还原。</span><span class="sxs-lookup"><span data-stu-id="51a82-228">**Scenario 1:** User contacts are migrated to the unified contact store, and a restore is performed from a Lync Server backup taken prior to the migration of user contacts.</span></span> <span data-ttu-id="51a82-229">在此方案中, 用户将在最长一天内有过时的联系人状态, 直到 Lync Server 迁移任务开始将用户联系人迁移到 Exchange。</span><span class="sxs-lookup"><span data-stu-id="51a82-229">In this scenario, the user will have a state of outdated contacts for up to one day until Lync Server Migration Task begins migrating user contacts to Exchange.</span></span> <span data-ttu-id="51a82-230">(请注意, 由于用户联系人以前已迁移到 "统一联系人存储", 将使用 Exchange 联系人信息)。</span><span class="sxs-lookup"><span data-stu-id="51a82-230">(Note that because the user contacts were previously migrated to the unified contact store, the Exchange contact information will be used).</span></span> <span data-ttu-id="51a82-231">此方案中不需要管理员干预。</span><span class="sxs-lookup"><span data-stu-id="51a82-231">No administrator intervention is needed in this scenario.</span></span>
        
        <span data-ttu-id="51a82-232">**方案 2:** 用户联系人之前已存储在 "统一联系人存储" 中, 但随后会回退。</span><span class="sxs-lookup"><span data-stu-id="51a82-232">**Scenario 2:** User contacts were previously stored in the unified contact store, but then rolled back.</span></span> <span data-ttu-id="51a82-233">当用户联系人存储在 "统一联系人存储" 中时, 将从 Lync Server 备份执行还原。</span><span class="sxs-lookup"><span data-stu-id="51a82-233">A restore is performed from a Lync Server backup taken when the user contacts were stored in the unified contact store.</span></span> <span data-ttu-id="51a82-234">在这种情况下, 客户端`Error: Incorrect Exchange Version`或 Lyss 服务器日志中的一条错误消息可能会指示此问题。</span><span class="sxs-lookup"><span data-stu-id="51a82-234">In this scenario, an error message of `Error: Incorrect Exchange Version` in the client or Lyss server logs may indicate this as an issue.</span></span> <span data-ttu-id="51a82-235">用户将能够直接从 Exchange 访问 Lync 2013 中的联系人列表, 但客户端的状态将与 Lync Server 状态不匹配。</span><span class="sxs-lookup"><span data-stu-id="51a82-235">The user will be able to access their contact list in Lync 2013 directly from Exchange, but client’s state will not match the Lync Server state.</span></span> <span data-ttu-id="51a82-236">若要解决此问题, 管理员需要针对受影响的用户运行**CsUCSRollback** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="51a82-236">To fix this, an administrator will need to run the **Invoke-CsUCSRollback** cmdlets for the affected users.</span></span>
    
      - <span data-ttu-id="51a82-237">**存档数据**可以存储在 Exchange 2013 中。</span><span class="sxs-lookup"><span data-stu-id="51a82-237">**Archiving Data** can be stored in Exchange 2013.</span></span> <span data-ttu-id="51a82-238">对于 Lync Server 而言, 此数据并不重要, 但对您的组织而言可能至关重要。</span><span class="sxs-lookup"><span data-stu-id="51a82-238">This data is not critical to Lync Server, but it may be critical to your organization for regulatory purposes.</span></span> <span data-ttu-id="51a82-239">如果存档数据存储在 Exchange 中且对您的组织非常重要, 请按照 Exchange 备份和还原过程操作。</span><span class="sxs-lookup"><span data-stu-id="51a82-239">If archiving data is stored in Exchange and is critical to your organization, then follow Exchange backup and restore procedures.</span></span> <span data-ttu-id="51a82-240">请注意, 存储在 Exchange 中的存档数据不能移回 Lync 服务器。</span><span class="sxs-lookup"><span data-stu-id="51a82-240">Note that archiving data stored in Exchange cannot be moved back to Lync Server.</span></span> <span data-ttu-id="51a82-241">此外, 无法将已存储在 Lync 存档数据库中的数据移动到 Exchange。</span><span class="sxs-lookup"><span data-stu-id="51a82-241">Additionally, there is no way to move data already stored in the Lync archiving database to Exchange.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

