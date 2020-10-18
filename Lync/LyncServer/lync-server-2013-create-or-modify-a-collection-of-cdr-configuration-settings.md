---
title: Lync Server 2013：创建或修改 CDR 配置设置的集合
description: Lync Server 2013：创建或修改 CDR 配置设置的集合。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of CDR configuration settings
ms:assetid: c830be5a-2a82-468d-9c46-d3fec0f79fd0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721878(v=OCS.15)
ms:contentKeyID: 49733812
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ba911607db55a7b7206645495e70a27ed453784
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578328"
---
# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="762a4-103">在 Lync Server 2013 中创建或修改 CDR 配置设置的集合</span><span class="sxs-lookup"><span data-stu-id="762a4-103">Create or modify a collection of CDR configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="762a4-104">_**上次修改的主题：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="762a4-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="762a4-105">Call (CDR) 的详细记录使您能够跟踪对等即时消息会话的使用情况，如对等即时消息会话、网络语音协议 (VoIP) 电话联络和会议呼叫等内容。</span><span class="sxs-lookup"><span data-stu-id="762a4-105">Call detail recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls.</span></span> <span data-ttu-id="762a4-106">此使用情况数据包含有关呼叫者、被叫方、呼叫时间及通话时长的信息。</span><span class="sxs-lookup"><span data-stu-id="762a4-106">This usage data includes information about who called whom, when they called, and how long they talked.</span></span>

<span data-ttu-id="762a4-107">安装 Microsoft Lync Server 2013 时，将为您创建一个 CDR 配置设置的全局集合。</span><span class="sxs-lookup"><span data-stu-id="762a4-107">When you install Microsoft Lync Server 2013 a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="762a4-108">管理员还可以选择在站点范围创建自定义设置。</span><span class="sxs-lookup"><span data-stu-id="762a4-108">Administrators also have the option of creating custom settings at the site scope.</span></span> <span data-ttu-id="762a4-109">无论何时使用这些站点范围的设置，它们都优先于全局设置。</span><span class="sxs-lookup"><span data-stu-id="762a4-109">Whenever these site-scoped settings are used, they take precedence over the global settings.</span></span> <span data-ttu-id="762a4-110">例如，如果您为 Redmond 站点创建了网站范围的设置，则这些设置 (而不是全局设置) 将用于管理 Redmond 中的 CDR。</span><span class="sxs-lookup"><span data-stu-id="762a4-110">For example, if you create site-scoped settings for the Redmond site then those settings (rather than the global settings) will be used to manage CDR in Redmond.</span></span>

<span data-ttu-id="762a4-111">您可以使用 Lync Server 控制面板或 [set-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) CMDLET 创建 CDR 配置设置。</span><span class="sxs-lookup"><span data-stu-id="762a4-111">You can create CDR configuration settings by using either Lync Server Control Panel or the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) cmdlet.</span></span> <span data-ttu-id="762a4-112">您可以使用 Lync Server 控制面板或 [set-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet 修改现有设置。</span><span class="sxs-lookup"><span data-stu-id="762a4-112">You can use Lync Server Control Panel or the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet to modify existing settings.</span></span> <span data-ttu-id="762a4-113">如果您使用 Lync Server 控制面板创建或修改设置，将对您可用以下选项：</span><span class="sxs-lookup"><span data-stu-id="762a4-113">If you are using Lync Server Control Panel to create or modify settings, the following options will be available to you:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="762a4-114">UI 设置</span><span class="sxs-lookup"><span data-stu-id="762a4-114">UI Setting</span></span></th>
<th><span data-ttu-id="762a4-115">PowerShell 参数</span><span class="sxs-lookup"><span data-stu-id="762a4-115">PowerShell Parameter</span></span></th>
<th><span data-ttu-id="762a4-116">说明</span><span class="sxs-lookup"><span data-stu-id="762a4-116">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="762a4-117">Name</span><span class="sxs-lookup"><span data-stu-id="762a4-117">Name</span></span></p></td>
<td><p><span data-ttu-id="762a4-118">标识</span><span class="sxs-lookup"><span data-stu-id="762a4-118">Identity</span></span></p></td>
<td><p><span data-ttu-id="762a4-119">正在创建的 CDR 配置设置的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="762a4-119">Unique identifier for the CDR configuration settings being created.</span></span> <span data-ttu-id="762a4-120">这些设置只能在站点范围创建。</span><span class="sxs-lookup"><span data-stu-id="762a4-120">These settings can only be created at the site scope.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="762a4-121">启用对 Cdr 的监视</span><span class="sxs-lookup"><span data-stu-id="762a4-121">Enable monitoring of CDRs</span></span></p></td>
<td><p><span data-ttu-id="762a4-122">EnableCDR</span><span class="sxs-lookup"><span data-stu-id="762a4-122">EnableCDR</span></span></p></td>
<td><p><span data-ttu-id="762a4-123">指示是否启用 CDR。</span><span class="sxs-lookup"><span data-stu-id="762a4-123">Indicates whether or not CDR is enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="762a4-124">启用清除 Cdr</span><span class="sxs-lookup"><span data-stu-id="762a4-124">Enable purging of CDRs</span></span></p></td>
<td><p><span data-ttu-id="762a4-125">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="762a4-125">EnablePurging</span></span></p></td>
<td><p><span data-ttu-id="762a4-126">指示是否将定期从 CDR 数据库中删除 CDR 记录。</span><span class="sxs-lookup"><span data-stu-id="762a4-126">Indicates whether or not CDR records will periodically be deleted from the CDR database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="762a4-127">将 Cdr 保留最长持续 (天) </span><span class="sxs-lookup"><span data-stu-id="762a4-127">Keep CDRs for maximum duration (days)</span></span></p></td>
<td><p><span data-ttu-id="762a4-128">KeepCallDetailForDays</span><span class="sxs-lookup"><span data-stu-id="762a4-128">KeepCallDetailForDays</span></span></p></td>
<td><p><span data-ttu-id="762a4-129">指示 CDR 记录将保留在 CDR 数据库中的天数。</span><span class="sxs-lookup"><span data-stu-id="762a4-129">Indicates the number of days that CDR records will be kept in the CDR database.</span></span> <span data-ttu-id="762a4-130">早于指定天数的任何记录将自动删除。</span><span class="sxs-lookup"><span data-stu-id="762a4-130">Any records older than the specified number of days will automatically be deleted.</span></span> <span data-ttu-id="762a4-131"> (请注意，仅在启用了清除功能时才会进行清除。 ) </span><span class="sxs-lookup"><span data-stu-id="762a4-131">(Note that purging will take only place if purging has been enabled.)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="762a4-132">将错误报告数据的最长持续时间 (天) </span><span class="sxs-lookup"><span data-stu-id="762a4-132">Keep error report data for maximum duration (days)</span></span></p></td>
<td><p><span data-ttu-id="762a4-133">KeepErrorReportForDays</span><span class="sxs-lookup"><span data-stu-id="762a4-133">KeepErrorReportForDays</span></span></p></td>
<td><p><span data-ttu-id="762a4-134">指示保留了 CDR 错误报告的天数。</span><span class="sxs-lookup"><span data-stu-id="762a4-134">Indicates the number of days that CDR error reports are kept.</span></span> <span data-ttu-id="762a4-135">将自动删除早于指定天数的任何报告。</span><span class="sxs-lookup"><span data-stu-id="762a4-135">Any reports older than the specified number of days will automatically be deleted.</span></span> <span data-ttu-id="762a4-136">CDR 错误报告是由客户端应用程序上传的诊断报告。</span><span class="sxs-lookup"><span data-stu-id="762a4-136">CDR error reports are diagnostic reports uploaded by client applications.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="762a4-137">New-CsCdrConfiguration 和 Set-CsCdrConfiguration cmdlet 包括 Lync Server 控制面板中不可用的其他选项。</span><span class="sxs-lookup"><span data-stu-id="762a4-137">The New-CsCdrConfiguration and Set-CsCdrConfiguration cmdlets include additional options not available in Lync Server Control Panel.</span></span> <span data-ttu-id="762a4-138">有关详细信息，请参阅 <A href="https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration">set-cscdrconfiguration</A> 和 <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration">set-cscdrconfiguration</A> 帮助主题。</span><span class="sxs-lookup"><span data-stu-id="762a4-138">See the <A href="https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration">New-CsCdrConfiguration</A> and the <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration">Set-CsCdrConfiguration</A> help topics for more information.</span></span>



</div>

<div>

## <a name="to-create-cdr-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="762a4-139">使用 Lync Server 控制面板创建 CDR 配置设置</span><span class="sxs-lookup"><span data-stu-id="762a4-139">To create CDR configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="762a4-140">在 Lync Server 控制面板中，单击 " **监控和存档**"。</span><span class="sxs-lookup"><span data-stu-id="762a4-140">In Lync Server Control Panel click **Monitoring and Archiving**.</span></span>

2.  <span data-ttu-id="762a4-141">在 " **呼叫详细信息记录** " 选项卡上，单击 " **新建**"。</span><span class="sxs-lookup"><span data-stu-id="762a4-141">On the **Call Detail Recording** tab, click **New**.</span></span>

3.  <span data-ttu-id="762a4-142">在 " **选择站点** " 对话框中，选择要在其中创建新配置设置的站点。</span><span class="sxs-lookup"><span data-stu-id="762a4-142">In the **Select a Site** dialog box, select the site where the new configuration settings are to be created.</span></span> <span data-ttu-id="762a4-143">如果对话框为空，则表示已为您的所有网站分配 CDR 配置设置的集合。</span><span class="sxs-lookup"><span data-stu-id="762a4-143">If the dialog box is empty, that means all of your sites have already been assigned a collection of CDR configuration settings.</span></span> <span data-ttu-id="762a4-144">每个网站仅限于单个此类集合。</span><span class="sxs-lookup"><span data-stu-id="762a4-144">Each site is limited to a single such collection.</span></span> <span data-ttu-id="762a4-145">在这种情况下，您可以删除并重新创建设置，也可以只修改现有设置。</span><span class="sxs-lookup"><span data-stu-id="762a4-145">In that case you can either delete and then re-create the settings, or simply modify the existing settings.</span></span>

4.  <span data-ttu-id="762a4-146">在 " **新呼叫详细信息记录" (CDR) 设置** "对话框中，执行所需的选择，然后单击" **提交**"。</span><span class="sxs-lookup"><span data-stu-id="762a4-146">In the **New Call Detail Recording (CDR) Setting** dialog, make the desired selections and then click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-existing-cdr-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="762a4-147">使用 Lync Server 控制面板修改现有 CDR 配置设置的具体方法</span><span class="sxs-lookup"><span data-stu-id="762a4-147">To modify existing CDR configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="762a4-148">在 Lync Server 控制面板中，单击 " **监控和存档**"。</span><span class="sxs-lookup"><span data-stu-id="762a4-148">In Lync Server Control Panel click **Monitoring and Archiving**.</span></span>

2.  <span data-ttu-id="762a4-149">双击要修改的设置集合，或选择该集合，单击 " **编辑**"，然后单击 " **显示详细信息**"。</span><span class="sxs-lookup"><span data-stu-id="762a4-149">Double-click the collection of settings to be modified, or select the collection, click **Edit**, and then click **Show Details**.</span></span> <span data-ttu-id="762a4-150">请注意，一次只能修改一个集合。</span><span class="sxs-lookup"><span data-stu-id="762a4-150">Note that you can only modify a single collection at a time.</span></span> <span data-ttu-id="762a4-151">若要对多个集合进行相同的更改，请改用 Lync Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="762a4-151">To make the same changes to multiple collections, use the Lync Server Management Shell instead.</span></span>

3.  <span data-ttu-id="762a4-152">在 " **编辑呼叫详细信息记录" (CDR) 设置** "对话框中，执行所需的选择，然后单击" **提交**"。</span><span class="sxs-lookup"><span data-stu-id="762a4-152">In the **Edit Call Detail Recording (CDR) Setting** dialog, make the desired selections and then click **Commit**.</span></span>

</div>

<div>

## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="762a4-153">使用 Windows PowerShell Cmdlet 创建 CDR 配置设置</span><span class="sxs-lookup"><span data-stu-id="762a4-153">Creating CDR Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="762a4-154">您可以创建 CDR 配置设置，也可以使用 Windows PowerShell 和 **set-cscdrconfiguration** cmdlet 创建。</span><span class="sxs-lookup"><span data-stu-id="762a4-154">You can create CDR configuration settings can also be created by using Windows PowerShell and the **New-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="762a4-155">您可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="762a4-155">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="762a4-156">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上的 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="762a4-156">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a><span data-ttu-id="762a4-157">创建新的 CDR 配置设置集合</span><span class="sxs-lookup"><span data-stu-id="762a4-157">To create a new collection of CDR configuration settings</span></span>

  - <span data-ttu-id="762a4-158">此命令将创建应用于 Redmond 站点的 CDR 配置设置的新集合：</span><span class="sxs-lookup"><span data-stu-id="762a4-158">This command creates a new collection of CDR configuration settings applied to the Redmond site:</span></span>
    
        New-CsCdrConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a><span data-ttu-id="762a4-159">创建禁用呼叫详细信息记录的 CDR 配置设置的集合</span><span class="sxs-lookup"><span data-stu-id="762a4-159">To create a collection of CDR configuration settings that disable call detail recording</span></span>

  - <span data-ttu-id="762a4-160">由于在上述命令中未指定参数（不包括必需的 Identity 参数），新的配置设置集合的所有属性都将使用默认值。</span><span class="sxs-lookup"><span data-stu-id="762a4-160">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span> <span data-ttu-id="762a4-161">要创建使用不同属性值的设置，只需包含相应的参数和参数值。</span><span class="sxs-lookup"><span data-stu-id="762a4-161">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="762a4-162">例如，若要创建呼叫详细信息配置设置的集合，默认情况下允许禁用呼叫详细信息记录，请使用类似如下的命令：</span><span class="sxs-lookup"><span data-stu-id="762a4-162">For example, to create a collection of Call Detail configuration settings that, by default, allow disable Call Detail recording use a command like this:</span></span>
    
        New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a><span data-ttu-id="762a4-163">在创建新的 CDR 配置设置集合时指定多个属性值</span><span class="sxs-lookup"><span data-stu-id="762a4-163">To specify multiple property values when creating a new collection of CDR configuration settings</span></span>

  - <span data-ttu-id="762a4-164">您可以通过包含多个参数来修改多个属性值。</span><span class="sxs-lookup"><span data-stu-id="762a4-164">You can modify multiple property values by including multiple parameters.</span></span> <span data-ttu-id="762a4-165">例如，以下命令将新设置配置为将呼叫详细信息记录保留30天，错误报告为90天：</span><span class="sxs-lookup"><span data-stu-id="762a4-165">For example, this command configures the new settings to keep Call Detail records for 30 days and error reports for 90 days:</span></span>
    
        New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90

</div>

<span data-ttu-id="762a4-166">有关详细信息，请参阅 [set-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="762a4-166">For more information, see the help topic for the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

