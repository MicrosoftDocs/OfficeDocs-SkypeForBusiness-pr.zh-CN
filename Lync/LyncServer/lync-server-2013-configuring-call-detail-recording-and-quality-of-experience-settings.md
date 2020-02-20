---
title: 配置呼叫详细信息记录和体验质量设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring call detail recording and Quality of Experience settings
ms:assetid: 009a0499-4f8c-450d-9c72-a565a08e9f7a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204621(v=OCS.15)
ms:contentKeyID: 48183223
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b0a7d6eb309c8afd13e671a12c98623c486b220d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150781"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-call-detail-recording-and-quality-of-experience-settings-in-lync-server-2013"></a><span data-ttu-id="180cb-102">在 Lync Server 2013 中配置呼叫详细信息记录和体验质量设置</span><span class="sxs-lookup"><span data-stu-id="180cb-102">Configuring call detail recording and Quality of Experience settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="180cb-103">_**上次修改的主题：** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="180cb-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="180cb-104">将监控存储与前端池关联之后，将其设置为监控存储，然后安装并配置 SQL Server Reporting Services 和监控报告，以管理呼叫详细信息记录（CDR）和体验质量（QoE）使用 Lync Server 命令行管理程序进行监控。</span><span class="sxs-lookup"><span data-stu-id="180cb-104">After you have associated a monitoring store with a Front End pool, set up the monitoring store, and then installed and configured SQL Server Reporting Services and Monitoring Reports you can manage Call Detail Recording (CDR) and Quality of Experience (QoE) monitoring by using Lync Server Management Shell.</span></span> <span data-ttu-id="180cb-105">Lync Server 命令行管理程序 cmdlet 允许您为特定站点或整个 Lync Server 部署启用和禁用 CDR 和/或 QoE 监控;为此，可以使用如下所示的命令来完成：</span><span class="sxs-lookup"><span data-stu-id="180cb-105">Lync Server Management Shell cmdlets allow you to enable and disable CDR and/or QoE monitoring for a particular site or for your entire Lync Server deployment; that can be done with a command as simple as this:</span></span>

    Set-CsQoEConfiguration -Identity "global" -EnableQoE $False

<span data-ttu-id="180cb-106">安装 Microsoft Lync Server 2013 时，还将为 CDR 和 QoE 安装全局配置设置的预定义集合。</span><span class="sxs-lookup"><span data-stu-id="180cb-106">When you install Microsoft Lync Server 2013, you will also install a predefined collection of global configuration settings for both CDR and QoE.</span></span> <span data-ttu-id="180cb-107">下表显示了呼叫详细记录使用的一些较常用设置的默认值：</span><span class="sxs-lookup"><span data-stu-id="180cb-107">Default values for some of the more commonly-used settings used by Call Detail Recording are shown in the following table:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="180cb-108">属性</span><span class="sxs-lookup"><span data-stu-id="180cb-108">Property</span></span></th>
<th><span data-ttu-id="180cb-109">说明</span><span class="sxs-lookup"><span data-stu-id="180cb-109">Description</span></span></th>
<th><span data-ttu-id="180cb-110">默认值</span><span class="sxs-lookup"><span data-stu-id="180cb-110">Default Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="180cb-111">EnableCDR</span><span class="sxs-lookup"><span data-stu-id="180cb-111">EnableCDR</span></span></p></td>
<td><p><span data-ttu-id="180cb-p103">指示是否启用 CDR。如果为 True，将收集所有 CDR 记录并写入监控数据库。</span><span class="sxs-lookup"><span data-stu-id="180cb-p103">Indicates whether or not CDR is enabled. If True, all CDR records will be collected and written to the monitoring database.</span></span></p></td>
<td><p><span data-ttu-id="180cb-114">True</span><span class="sxs-lookup"><span data-stu-id="180cb-114">True</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="180cb-115">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="180cb-115">EnablePurging</span></span></p></td>
<td><p><span data-ttu-id="180cb-p104">指示是否定期从数据库中删除 CDR 记录。如果为 True，则将在属性 KeepCallDetailForDays（对于 CDR 记录）和 KeepErrorReportForDays（对于 CDR 错误）指定的时间段后删除记录。如果为 False，则将无限期保留 CDR 记录。</span><span class="sxs-lookup"><span data-stu-id="180cb-p104">Indicates whether or not CDR records will periodically be deleted from the database. If True, records will be deleted after the time period specified by the properties KeepCallDetailForDays (for CDR records) and KeepErrorReportForDays (for CDR errors). If False, CDR records will be maintained indefinitely.</span></span></p></td>
<td><p><span data-ttu-id="180cb-119">True</span><span class="sxs-lookup"><span data-stu-id="180cb-119">True</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="180cb-120">KeepCallDetailForDays</span><span class="sxs-lookup"><span data-stu-id="180cb-120">KeepCallDetailForDays</span></span></p></td>
<td><p><span data-ttu-id="180cb-p105">指示 CDR 记录在数据库中保留的天数；超过指定天数的任何记录将自动删除。但是，只有在启用了清除时才会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="180cb-p105">Indicates the number of days that CDR records will be kept in the database; any records older than the specified number of days will automatically be deleted. However, this will occur only if purging has been enabled.</span></span></p>
<p><span data-ttu-id="180cb-123">KeepCallDetailForDays 可以设置为 1 到 2562 天（大约 7 年）之间的任意整数值。</span><span class="sxs-lookup"><span data-stu-id="180cb-123">KeepCallDetailForDays can be set to any integer value between 1 and 2562 days (approximately 7 years).</span></span></p></td>
<td><p><span data-ttu-id="180cb-124">60 天</span><span class="sxs-lookup"><span data-stu-id="180cb-124">60 days</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="180cb-125">KeepErrorReportForDays</span><span class="sxs-lookup"><span data-stu-id="180cb-125">KeepErrorReportForDays</span></span></p></td>
<td><p><span data-ttu-id="180cb-126">指示保留 CDR 错误报告的天数；超过指定天数的任何报告将自动删除。</span><span class="sxs-lookup"><span data-stu-id="180cb-126">Indicates the number of days that CDR error reports are kept; any reports older than the specified number of days will automatically be deleted.</span></span> <span data-ttu-id="180cb-127">CDR 错误报告是由客户端应用程序（如 Microsoft Lync 2013）上传的诊断报告。</span><span class="sxs-lookup"><span data-stu-id="180cb-127">CDR error reports are diagnostic reports uploaded by client applications such as Microsoft Lync 2013.</span></span></p>
<p><span data-ttu-id="180cb-128">您可以将此属性设置为 1 到 2562 天之间的任意整数值。</span><span class="sxs-lookup"><span data-stu-id="180cb-128">You can set this property to any integer value between 1 and 2562 days.</span></span></p></td>
<td><p><span data-ttu-id="180cb-129">60 天</span><span class="sxs-lookup"><span data-stu-id="180cb-129">60 days</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="180cb-130">类似地，此表中也显示了选定 QoE 设置的默认值：</span><span class="sxs-lookup"><span data-stu-id="180cb-130">Similarly, default values for selected QoE settings are shown in this table:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="180cb-131">属性</span><span class="sxs-lookup"><span data-stu-id="180cb-131">Property</span></span></th>
<th><span data-ttu-id="180cb-132">说明</span><span class="sxs-lookup"><span data-stu-id="180cb-132">Description</span></span></th>
<th><span data-ttu-id="180cb-133">默认值</span><span class="sxs-lookup"><span data-stu-id="180cb-133">Default Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="180cb-134">EnableQoE</span><span class="sxs-lookup"><span data-stu-id="180cb-134">EnableQoE</span></span></p></td>
<td><p><span data-ttu-id="180cb-p107">指示是否启用 QoE 监控。如果为 True，将收集所有 QoE 记录并写入监控数据库。</span><span class="sxs-lookup"><span data-stu-id="180cb-p107">Indicates whether or not QoE monitoring is enabled. If True, all QoE records will be collected and written to the monitoring database.</span></span></p></td>
<td><p><span data-ttu-id="180cb-137">True</span><span class="sxs-lookup"><span data-stu-id="180cb-137">True</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="180cb-138">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="180cb-138">EnablePurging</span></span></p></td>
<td><p><span data-ttu-id="180cb-p108">指示是否定期从数据库中删除 QoE 记录。如果为 True，则将在属性 KeepQoEDataForDays 指定的时间段后删除记录。如果为 False，则将无限期保留 QoE 记录。</span><span class="sxs-lookup"><span data-stu-id="180cb-p108">Indicates whether or not QoE records will periodically be deleted from the database. If True, records will be deleted after the time period specified by the KeepQoEDataForDays property. If False, QoE records will be maintained indefinitely.</span></span></p></td>
<td><p><span data-ttu-id="180cb-142">True</span><span class="sxs-lookup"><span data-stu-id="180cb-142">True</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="180cb-143">KeepQoEDataForDays</span><span class="sxs-lookup"><span data-stu-id="180cb-143">KeepQoEDataForDays</span></span></p></td>
<td><p><span data-ttu-id="180cb-p109">指示 QoE 记录在数据库中保留的天数；超过指定天数的任何记录将自动删除。但是，只有在启用了清除时才会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="180cb-p109">Indicates the number of days that QoE records will be kept in the database; any records older than the specified number of days will automatically be deleted. However, this will occur only if purging has been enabled.</span></span></p>
<p><span data-ttu-id="180cb-146">可将 KeepCallDetailForDays 设置为 1 到 2562 天之间的任意整数值。</span><span class="sxs-lookup"><span data-stu-id="180cb-146">KeepCallDetailForDays can be set to any integer value between 1 and 2562 days.</span></span></p></td>
<td><p><span data-ttu-id="180cb-147">60 天</span><span class="sxs-lookup"><span data-stu-id="180cb-147">60 days</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="180cb-p110">如果您需要修改这些全局设置，可以使用 Set-CsCdrConfiguration 和 Set-CsQoEConfiguration cmdlet 来完成。例如，以下命令（从 Lync Server 命令行管理程序运行）在全局范围内禁用 CDR 监控；这是通过将 EnableCDR 属性设置为 False ($False) 来实现的：</span><span class="sxs-lookup"><span data-stu-id="180cb-p110">If you need to modify these global settings you can do so by using the Set-CsCdrConfiguration and the Set-CsQoEConfiguration cmdlets. For example, this command (run from within the Lync Server Management Shell) disables CDR monitoring at the global scope; that's done by setting the EnableCDR property to False ($False):</span></span>

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $False

<span data-ttu-id="180cb-150">请注意，禁用监控不会从前端池解除监控存储关联，也不卸载或以其他方式影响后端监控数据库。</span><span class="sxs-lookup"><span data-stu-id="180cb-150">Note that disabling monitoring does not dissociate the monitoring store from the Front End pool, nor does it uninstall or otherwise affect the backend monitoring database.</span></span> <span data-ttu-id="180cb-151">当您使用 Lync Server 命令行管理程序禁用 CDR 或 QoE 监视时，您确实会暂时停止 Lync Server 收集和存档监控数据。</span><span class="sxs-lookup"><span data-stu-id="180cb-151">When you use Lync Server Management Shell to disable either CDR or QoE monitoring all you really do is temporarily stop Lync Server from collecting and archiving monitoring data.</span></span> <span data-ttu-id="180cb-152">如果要恢复收集和存档 CDR 数据，只需要将 EnableCDR 属性重新设置为 True ($True) 即可：</span><span class="sxs-lookup"><span data-stu-id="180cb-152">If you want to resume, in this case, the collection and archiving of CDR data, all you need to do is set the EnableCDR property back to True ($True):</span></span>

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $True

<span data-ttu-id="180cb-153">类似地，以下命令在全局范围内禁止清除 QoE 记录：</span><span class="sxs-lookup"><span data-stu-id="180cb-153">Similarly, this command disables the purging of QoE records at the global scope:</span></span>

    Set-CsQoEConfiguration -Identity "global" -EnablePurging $False

<span data-ttu-id="180cb-p112">除了全局设置，也可将 CDR 和 QoE 配置设置分配给站点范围。这样，在实施监控时可提供更大的管理灵活性；例如，管理员可以对 Redmond 站点启用 CDR 监控，而对 Dublin 站点禁用 CDR 监控。要在站点范围创建新的 CDR 配置设置，请使用类似如下的命令：</span><span class="sxs-lookup"><span data-stu-id="180cb-p112">In addition to the global settings, CDR and QoE configurations settings can be assigned to the site scope. This provides additional management flexibility when it comes to monitoring; for example, an administrator can enable CDR monitoring for the Redmond site but disable CDR monitoring for the Dublin site. To create new CDR configuration settings at the site scope, use a command similar to this:</span></span>

    New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

<span data-ttu-id="180cb-p113">请记住，在站点范围配置的设置优先于在全局范围配置的设置。例如，假设在全局范围启用了 CDR 监控，但在站点范围（对于 Redmond 站点）禁用了 CDR 监控。这意味着将不为 Redmond 站点中的用户存档呼叫详细记录信息。但是，其他站点中的用户（即，由全局设置而非 Redmond 站点设置管理的用户）的呼叫详细记录仍将存档。</span><span class="sxs-lookup"><span data-stu-id="180cb-p113">Keep in mind that settings configured at the site scope take precedence over settings configured at the global scope. For example, suppose CDR monitoring is enabled at the global scope, but disabled at the site scope (for the Redmond site). That means that call detail recording information will not be archived for users in the Redmond site. However, users in other sites (that is, users managed by the global settings instead of the Redmond site settings) will have their call detail recording information archived.</span></span>

<span data-ttu-id="180cb-161">可以使用类似如下的命令在站点范围创建新的 QoE 配置设置：</span><span class="sxs-lookup"><span data-stu-id="180cb-161">New QoE configuration settings can be created at the site scope by using a command like this one:</span></span>

    New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 15

<span data-ttu-id="180cb-162">有关详细信息，请在 Lync Server 命令行管理程序中键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="180cb-162">For more information, type the following commands from within the Lync Server Management Shell:</span></span>

    Get-Help New-CsCdrConfiguration | more
    Get-Help Set-CsCdrConfiguration | more
    Get-Help New-CsQoEConfiguration | more
    Get-Help Set-CsQoEConfiguration | more

</div>

<span> </span>

</div>

</div>

</div>

