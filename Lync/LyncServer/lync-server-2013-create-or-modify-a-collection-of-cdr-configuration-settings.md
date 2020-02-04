---
title: Lync Server 2013：创建或修改 CDR 配置设置的集合
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
ms.openlocfilehash: 37ed8be52827f56b14c52f1bddd950ab39883cdf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763354"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="31761-102">在 Lync Server 2013 中创建或修改 CDR 配置设置的集合</span><span class="sxs-lookup"><span data-stu-id="31761-102">Create or modify a collection of CDR configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="31761-103">_**主题上次修改时间：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="31761-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="31761-p101">利用呼叫详细信息记录 (CDR)，可以跟踪对等即时消息会话、IP 语音 (VoIP) 电话呼叫和会议呼叫等的使用情况。此使用情况数据包含有关呼叫者、被叫方、呼叫时间及通话时长的信息。</span><span class="sxs-lookup"><span data-stu-id="31761-p101">Call detail recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls. This usage data includes information about who called whom, when they called, and how long they talked.</span></span>

<span data-ttu-id="31761-106">安装 Microsoft Lync Server 2013 时，将为你创建单个的 CDR 配置设置的全局集合。</span><span class="sxs-lookup"><span data-stu-id="31761-106">When you install Microsoft Lync Server 2013 a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="31761-107">管理员还具有创建站点作用域的自定义设置的选项。</span><span class="sxs-lookup"><span data-stu-id="31761-107">Administrators also have the option of creating custom settings at the site scope.</span></span> <span data-ttu-id="31761-108">使用这些站点作用域设置时，它们将优先于全局设置。</span><span class="sxs-lookup"><span data-stu-id="31761-108">Whenever these site-scoped settings are used, they take precedence over the global settings.</span></span> <span data-ttu-id="31761-109">例如，如果您为 Redmond 站点创建了站点作用域设置，则这些设置（而不是全局设置）将用于管理 Redmond 内的 CDR。</span><span class="sxs-lookup"><span data-stu-id="31761-109">For example, if you create site-scoped settings for the Redmond site then those settings (rather than the global settings) will be used to manage CDR in Redmond.</span></span>

<span data-ttu-id="31761-110">你可以使用 Lync Server 控制面板或[CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) CMDLET 创建 CDR 配置设置。</span><span class="sxs-lookup"><span data-stu-id="31761-110">You can create CDR configuration settings by using either Lync Server Control Panel or the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) cmdlet.</span></span> <span data-ttu-id="31761-111">你可以使用 Lync Server 控制面板或[CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet 修改现有设置。</span><span class="sxs-lookup"><span data-stu-id="31761-111">You can use Lync Server Control Panel or the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet to modify existing settings.</span></span> <span data-ttu-id="31761-112">如果您使用的是 Lync Server 控制面板来创建或修改设置，您将可以使用以下选项：</span><span class="sxs-lookup"><span data-stu-id="31761-112">If you are using Lync Server Control Panel to create or modify settings, the following options will be available to you:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="31761-113">UI 设置</span><span class="sxs-lookup"><span data-stu-id="31761-113">UI Setting</span></span></th>
<th><span data-ttu-id="31761-114">PowerShell 参数</span><span class="sxs-lookup"><span data-stu-id="31761-114">PowerShell Parameter</span></span></th>
<th><span data-ttu-id="31761-115">描述</span><span class="sxs-lookup"><span data-stu-id="31761-115">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="31761-116">名称</span><span class="sxs-lookup"><span data-stu-id="31761-116">Name</span></span></p></td>
<td><p><span data-ttu-id="31761-117">Identity</span><span class="sxs-lookup"><span data-stu-id="31761-117">Identity</span></span></p></td>
<td><p><span data-ttu-id="31761-p104">所创建的 CDR 配置设置的唯一标识符。这些设置只能在站点作用域内创建。</span><span class="sxs-lookup"><span data-stu-id="31761-p104">Unique identifier for the CDR configuration settings being created. These settings can only be created at the site scope.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31761-120">启用 CDR 监控</span><span class="sxs-lookup"><span data-stu-id="31761-120">Enable monitoring of CDRs</span></span></p></td>
<td><p><span data-ttu-id="31761-121">EnableCDR</span><span class="sxs-lookup"><span data-stu-id="31761-121">EnableCDR</span></span></p></td>
<td><p><span data-ttu-id="31761-122">指示是否启用 CDR。</span><span class="sxs-lookup"><span data-stu-id="31761-122">Indicates whether or not CDR is enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="31761-123">启用 CDR 清除</span><span class="sxs-lookup"><span data-stu-id="31761-123">Enable purging of CDRs</span></span></p></td>
<td><p><span data-ttu-id="31761-124">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="31761-124">EnablePurging</span></span></p></td>
<td><p><span data-ttu-id="31761-125">指示是否将定期从 CDR 数据库中删除 CDR 记录。</span><span class="sxs-lookup"><span data-stu-id="31761-125">Indicates whether or not CDR records will periodically be deleted from the CDR database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="31761-126">CDR 最长保留期限（天）</span><span class="sxs-lookup"><span data-stu-id="31761-126">Keep CDRs for maximum duration (days)</span></span></p></td>
<td><p><span data-ttu-id="31761-127">KeepCallDetailForDays</span><span class="sxs-lookup"><span data-stu-id="31761-127">KeepCallDetailForDays</span></span></p></td>
<td><p><span data-ttu-id="31761-p105">指示 CDR 记录在 CDR 数据库中保留的天数。任何早于指定天数的记录都将被自动删除。（请注意，仅当启用清除后，才会执行清除操作。）</span><span class="sxs-lookup"><span data-stu-id="31761-p105">Indicates the number of days that CDR records will be kept in the CDR database. Any records older than the specified number of days will automatically be deleted. (Note that purging will take only place if purging has been enabled.)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="31761-131">错误报告数据最长保留期限（天）</span><span class="sxs-lookup"><span data-stu-id="31761-131">Keep error report data for maximum duration (days)</span></span></p></td>
<td><p><span data-ttu-id="31761-132">KeepErrorReportForDays</span><span class="sxs-lookup"><span data-stu-id="31761-132">KeepErrorReportForDays</span></span></p></td>
<td><p><span data-ttu-id="31761-p106">指示 CDR 错误报告的保留天数。任何早于指定天数的记录都将被自动删除。CDR 错误报告是客户端应用程序上传的诊断报告。</span><span class="sxs-lookup"><span data-stu-id="31761-p106">Indicates the number of days that CDR error reports are kept. Any reports older than the specified number of days will automatically be deleted. CDR error reports are diagnostic reports uploaded by client applications.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="31761-136">CsCdrConfiguration 和 CsCdrConfiguration cmdlet 包括 "Lync Server 控制面板" 中不可用的其他选项。</span><span class="sxs-lookup"><span data-stu-id="31761-136">The New-CsCdrConfiguration and Set-CsCdrConfiguration cmdlets include additional options not available in Lync Server Control Panel.</span></span> <span data-ttu-id="31761-137">有关详细信息，请参阅<A href="https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration">新的 CsCdrConfiguration</A>和<A href="https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration">CsCdrConfiguration</A>的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="31761-137">See the <A href="https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration">New-CsCdrConfiguration</A> and the <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration">Set-CsCdrConfiguration</A> help topics for more information.</span></span>



</div>

<div>

## <a name="to-create-cdr-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="31761-138">使用 Lync Server "控制面板" 创建 CDR 配置设置</span><span class="sxs-lookup"><span data-stu-id="31761-138">To create CDR configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="31761-139">在 Lync Server 控制面板中，单击 "**监视和存档**"。</span><span class="sxs-lookup"><span data-stu-id="31761-139">In Lync Server Control Panel click **Monitoring and Archiving**.</span></span>

2.  <span data-ttu-id="31761-140">在 "**呼叫详细记录**" 选项卡上，单击 "**新建**"。</span><span class="sxs-lookup"><span data-stu-id="31761-140">On the **Call Detail Recording** tab, click **New**.</span></span>

3.  <span data-ttu-id="31761-p108">在“**选择站点**”对话框中，选择要在其中创建新配置设置的站点。如果该对话框为空，则表示所有站点均已被分配 CDR 配置设置集合。每个站点均限制为只有一个此类集合。在这种情况下，您可以删除设置然后重新创建，也可以只修改现有设置。</span><span class="sxs-lookup"><span data-stu-id="31761-p108">In the **Select a Site** dialog box, select the site where the new configuration settings are to be created. If the dialog box is empty, that means all of your sites have already been assigned a collection of CDR configuration settings. Each site is limited to a single such collection. In that case you can either delete and then re-create the settings, or simply modify the existing settings.</span></span>

4.  <span data-ttu-id="31761-145">在“**新建呼叫详细信息记录 (CDR) 设置**”  对话框中进行所需选择，然后单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="31761-145">In the **New Call Detail Recording (CDR) Setting** dialog, make the desired selections and then click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-existing-cdr-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="31761-146">使用 Lync Server "控制面板" 修改现有 CDR 配置设置</span><span class="sxs-lookup"><span data-stu-id="31761-146">To modify existing CDR configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="31761-147">在 Lync Server 控制面板中，单击 "**监视和存档**"。</span><span class="sxs-lookup"><span data-stu-id="31761-147">In Lync Server Control Panel click **Monitoring and Archiving**.</span></span>

2.  <span data-ttu-id="31761-148">双击要修改的设置集合，或选择集合后单击“**编辑**”，然后单击“**显示详细信息**”。</span><span class="sxs-lookup"><span data-stu-id="31761-148">Double-click the collection of settings to be modified, or select the collection, click **Edit**, and then click **Show Details**.</span></span> <span data-ttu-id="31761-149">请注意，一次只能修改一个集合。</span><span class="sxs-lookup"><span data-stu-id="31761-149">Note that you can only modify a single collection at a time.</span></span> <span data-ttu-id="31761-150">若要对多个集合进行相同的更改，请改用 Lync Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="31761-150">To make the same changes to multiple collections, use the Lync Server Management Shell instead.</span></span>

3.  <span data-ttu-id="31761-151">在“**编辑呼叫详细信息记录 (CDR) 设置**”对话框中进行所需选择，然后单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="31761-151">In the **Edit Call Detail Recording (CDR) Setting** dialog, make the desired selections and then click **Commit**.</span></span>

</div>

<div>

## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="31761-152">使用 Windows PowerShell Cmdlet 创建 CDR 配置设置</span><span class="sxs-lookup"><span data-stu-id="31761-152">Creating CDR Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="31761-153">你可以创建 CDR 配置设置，也可以使用 Windows PowerShell 和**CsCdrConfiguration** cmdlet 创建 CDR 配置设置。</span><span class="sxs-lookup"><span data-stu-id="31761-153">You can create CDR configuration settings can also be created by using Windows PowerShell and the **New-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="31761-154">你可以从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="31761-154">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="31761-155">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="31761-155">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a><span data-ttu-id="31761-156">创建新的 CDR 配置设置集合</span><span class="sxs-lookup"><span data-stu-id="31761-156">To create a new collection of CDR configuration settings</span></span>

  - <span data-ttu-id="31761-157">以下命令将创建新的应用于 Redmond 站点的 CDR 配置设置集合：</span><span class="sxs-lookup"><span data-stu-id="31761-157">This command creates a new collection of CDR configuration settings applied to the Redmond site:</span></span>
    
        New-CsCdrConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a><span data-ttu-id="31761-158">创建可禁用呼叫详细信息记录的 CDR 配置设置集合</span><span class="sxs-lookup"><span data-stu-id="31761-158">To create a collection of CDR configuration settings that disable call detail recording</span></span>

  - <span data-ttu-id="31761-p111">由于上述命令中未指定参数（不包括必需的 Identity 参数），新的配置设置集合的所有属性都将使用默认值。要创建使用不同属性值的设置，只需包含相应的参数和参数值。例如，要创建默认情况下允许禁用呼叫详细信息记录的呼叫详细信息配置设置集合，请使用如下命令：</span><span class="sxs-lookup"><span data-stu-id="31761-p111">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties. To create settings that use different property values, simply include the appropriate parameter and parameter value. For example, to create a collection of Call Detail configuration settings that, by default, allow disable Call Detail recording use a command like this:</span></span>
    
        New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a><span data-ttu-id="31761-162">在创建新的 CDR 配置设置集合时指定多个属性值</span><span class="sxs-lookup"><span data-stu-id="31761-162">To specify multiple property values when creating a new collection of CDR configuration settings</span></span>

  - <span data-ttu-id="31761-p112">您可以通过包含多个参数来修改多个属性值。例如，以下命令将新设置配置为将呼叫详细信息记录保留 30 天，而将错误报告保留 90 天：</span><span class="sxs-lookup"><span data-stu-id="31761-p112">You can modify multiple property values by including multiple parameters. For example, this command configures the new settings to keep Call Detail records for 30 days and error reports for 90 days:</span></span>
    
        New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90

</div>

<span data-ttu-id="31761-165">有关详细信息，请参阅[CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="31761-165">For more information, see the help topic for the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

