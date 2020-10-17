---
title: Lync Server 2013：创建体验质量配置设置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create Quality of Experience configuration settings
ms:assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521006(v=OCS.15)
ms:contentKeyID: 48184357
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a94b7183be9927267796d3e2adaed12b3b71eaf6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501629"
---
# <a name="create-quality-of-experience-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="0b6c8-102">在 Lync Server 2013 中创建体验质量配置设置</span><span class="sxs-lookup"><span data-stu-id="0b6c8-102">Create Quality of Experience configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b6c8-103">_**上次修改的主题：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="0b6c8-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="0b6c8-p101">用户体验质量 (QoE) 指标跟踪组织中发出的语音和视频呼叫的质量，包括网络数据包丢失数目、背景噪音、“抖动”量（数据包延迟的差异）等。这些指标与其他数据（如呼叫详细信息记录）分开存储在一个数据库中，这样您就可以独立于其他数据记录启用和禁用 QoE。</span><span class="sxs-lookup"><span data-stu-id="0b6c8-p101">Quality of Experience (QoE) metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay). These metrics are stored in a database apart from other data (such as call detail records), which allows you to enable and disable QoE independent of other data recording.</span></span>

<span data-ttu-id="0b6c8-106">安装 Microsoft Lync Server 2013 时，将为您创建一个 QoE 配置设置的单一全局集合。</span><span class="sxs-lookup"><span data-stu-id="0b6c8-106">When you install Microsoft Lync Server 2013, a single, global collection of QoE configuration settings is created for you.</span></span> <span data-ttu-id="0b6c8-107">管理员还可以选择在站点范围创建自定义设置。</span><span class="sxs-lookup"><span data-stu-id="0b6c8-107">Administrators also have the option of creating custom settings at the site scope.</span></span> <span data-ttu-id="0b6c8-108">无论何时使用这些站点范围的设置，它们都优先于全局设置。</span><span class="sxs-lookup"><span data-stu-id="0b6c8-108">Whenever these site-scoped settings are used, they take precedence over the global settings.</span></span> <span data-ttu-id="0b6c8-109">例如，如果您为 Redmond 站点创建了站点作用域设置，则这些设置 (而不是全局设置) 将用于管理 Redmond 中的 QoE。</span><span class="sxs-lookup"><span data-stu-id="0b6c8-109">For example, if you create site-scoped settings for the Redmond site then those settings (rather than the global settings) will be used to manage QoE in Redmond.</span></span>

<span data-ttu-id="0b6c8-110">可以使用 Lync Server 控制面板或 [new-csqoeconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) Cmdlet 创建 QoE 配置设置。</span><span class="sxs-lookup"><span data-stu-id="0b6c8-110">QoE configuration settings can be created by using either Lync Server Control Panel or the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) cmdlet.</span></span> <span data-ttu-id="0b6c8-111">如果您使用 Lync Server 控制面板创建新设置，以下选项将对您可用：</span><span class="sxs-lookup"><span data-stu-id="0b6c8-111">If you are using Lync Server Control Panel to create new settings the following options will be available to you:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0b6c8-112">UI 设置</span><span class="sxs-lookup"><span data-stu-id="0b6c8-112">UI Setting</span></span></th>
<th><span data-ttu-id="0b6c8-113">PowerShell 参数</span><span class="sxs-lookup"><span data-stu-id="0b6c8-113">PowerShell Parameter</span></span></th>
<th><span data-ttu-id="0b6c8-114">说明</span><span class="sxs-lookup"><span data-stu-id="0b6c8-114">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0b6c8-115">Name</span><span class="sxs-lookup"><span data-stu-id="0b6c8-115">Name</span></span></p></td>
<td><p><span data-ttu-id="0b6c8-116">标识</span><span class="sxs-lookup"><span data-stu-id="0b6c8-116">Identity</span></span></p></td>
<td><p><span data-ttu-id="0b6c8-117">要创建的设置的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="0b6c8-117">Unique identifier for the settings to be created.</span></span> <span data-ttu-id="0b6c8-118">QoE 配置设置只能在网站范围内创建。</span><span class="sxs-lookup"><span data-stu-id="0b6c8-118">QoE configuration settings can only be created at the site scope.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b6c8-119">启用对 QoE 数据的监视</span><span class="sxs-lookup"><span data-stu-id="0b6c8-119">Enable monitoring of QoE data</span></span></p></td>
<td><p><span data-ttu-id="0b6c8-120">EnableQoE</span><span class="sxs-lookup"><span data-stu-id="0b6c8-120">EnableQoE</span></span></p></td>
<td><p><span data-ttu-id="0b6c8-121">指定是否收集 QoE 记录并将其保存到监控数据库。</span><span class="sxs-lookup"><span data-stu-id="0b6c8-121">Specifies whether QoE records will be collected and saved to the monitoring database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b6c8-122">启用清除 QoE 数据</span><span class="sxs-lookup"><span data-stu-id="0b6c8-122">Enable purging of QoE data</span></span></p></td>
<td><p><span data-ttu-id="0b6c8-123">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="0b6c8-123">EnablePurging</span></span></p></td>
<td><p><span data-ttu-id="0b6c8-124">指定在 "保持 QoE 数据" 中定义的持续时间 <strong> (天) </strong> 属性已过，是否将清除记录。</span><span class="sxs-lookup"><span data-stu-id="0b6c8-124">Specifies whether records will be purged after the duration defined in the <strong>Keep QoE data for a maximum duration (days)</strong> property has elapsed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b6c8-125">保留 QoE 数据的最长持续时间 (天) </span><span class="sxs-lookup"><span data-stu-id="0b6c8-125">Keep QoE data for maximum duration (days)</span></span></p></td>
<td><p><span data-ttu-id="0b6c8-126">KeepQoEDataForDays</span><span class="sxs-lookup"><span data-stu-id="0b6c8-126">KeepQoEDataForDays</span></span></p></td>
<td><p><span data-ttu-id="0b6c8-127">QoE 数据在从数据库中清除之前将存储的天数。</span><span class="sxs-lookup"><span data-stu-id="0b6c8-127">Number of days QoE data will be stored before being purged from the database.</span></span> <span data-ttu-id="0b6c8-128">如果禁用清除，则忽略此值。</span><span class="sxs-lookup"><span data-stu-id="0b6c8-128">This value is ignored if purging is disabled.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="0b6c8-129">New-CsQoEConfiguration cmdlet 包括 Lync Server 控制面板中不可用的其他选项。</span><span class="sxs-lookup"><span data-stu-id="0b6c8-129">The New-CsQoEConfiguration cmdlet includes additional options not available in Lync Server Control Panel.</span></span> <span data-ttu-id="0b6c8-130">有关详细信息，请参阅 <A href="https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration">new-csqoeconfiguration</A> 帮助主题。</span><span class="sxs-lookup"><span data-stu-id="0b6c8-130">For more information, see the <A href="https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration">New-CsQoEConfiguration</A> help topic.</span></span>



</div>

<div>

## <a name="to-create-qoe-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="0b6c8-131">使用 Lync Server 控制面板创建 QoE 配置设置</span><span class="sxs-lookup"><span data-stu-id="0b6c8-131">To create QoE configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="0b6c8-132">以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="0b6c8-132">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="0b6c8-133">有关详细信息，请参阅 [Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="0b6c8-133">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="0b6c8-134">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="0b6c8-134">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="0b6c8-135">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="0b6c8-135">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0b6c8-136">在左侧导航栏中，单击“监控和存档”\*\*\*\*，然后单击“用户体验质量数据”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0b6c8-136">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="0b6c8-137">在 " **体验质量数据** " 页上，单击 " **新建**"。</span><span class="sxs-lookup"><span data-stu-id="0b6c8-137">On the **Quality of Experience Data** page, click **New**.</span></span>

5.  <span data-ttu-id="0b6c8-138">在 " **选择站点**" 中，单击要应用该策略的站点，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="0b6c8-138">In **Select a Site**, click the site to which the policy is to be applied, and click **OK**.</span></span>

6.  <span data-ttu-id="0b6c8-139">在 " **新体验质量设置**" 中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0b6c8-139">In **New Quality of Experience Setting**, do the following:</span></span>
    
      - <span data-ttu-id="0b6c8-140">选择 " **启用对 QoE 数据的监视** " 以启用监控。</span><span class="sxs-lookup"><span data-stu-id="0b6c8-140">Select **Enable monitoring of QoE data** to turn on monitoring.</span></span>
    
      - <span data-ttu-id="0b6c8-141">选择 " **启用对 QoE 数据的清除** " 以启用清除。</span><span class="sxs-lookup"><span data-stu-id="0b6c8-141">Select **Enable purging of QoE data** to turn on purging.</span></span>
    
      - <span data-ttu-id="0b6c8-142">在 " \*\*保持 QoE 的最长持续时间 (天) \*\*中，选择应保留 QoE 记录的最大天数。</span><span class="sxs-lookup"><span data-stu-id="0b6c8-142">In **Keep QoE for maximum duration (days)**, select the maximum number of days that QoE records should be retained.</span></span>

7.  <span data-ttu-id="0b6c8-143">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="0b6c8-143">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="0b6c8-144">使用 Windows PowerShell Cmdlet 创建 QoE 配置设置</span><span class="sxs-lookup"><span data-stu-id="0b6c8-144">Creating QoE Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="0b6c8-145">您可以使用 Windows PowerShell 和 New-CsQoEConfiguration cmdlet 创建 QoE 配置设置。</span><span class="sxs-lookup"><span data-stu-id="0b6c8-145">You can create QoE configuration settings by using Windows PowerShell and the New-CsQoEConfiguration cmdlet.</span></span> <span data-ttu-id="0b6c8-146">您可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0b6c8-146">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="0b6c8-147">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上的 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。</span><span class="sxs-lookup"><span data-stu-id="0b6c8-147">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-collection-of-qoe-configuration-settings"></a><span data-ttu-id="0b6c8-148">创建新的 QoE 配置设置集合</span><span class="sxs-lookup"><span data-stu-id="0b6c8-148">To create a new collection of QoE configuration settings</span></span>

  - <span data-ttu-id="0b6c8-149">此命令将创建应用于 Redmond 站点的 QoE 配置设置的新集合：</span><span class="sxs-lookup"><span data-stu-id="0b6c8-149">This command creates a new collection of QoE configuration settings applied to the Redmond site:</span></span>
    
        New-CsQoEConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-collection-of-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a><span data-ttu-id="0b6c8-150">创建新的 QoE 配置设置集合，其中禁用了 QoE 监视</span><span class="sxs-lookup"><span data-stu-id="0b6c8-150">To create a new collection of QoE configuration settings where QoE monitoring is disabled</span></span>

  - <span data-ttu-id="0b6c8-151">由于在上述命令中未指定参数（不包括必需的 Identity 参数），新的配置设置集合的所有属性都将使用默认值。</span><span class="sxs-lookup"><span data-stu-id="0b6c8-151">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span> <span data-ttu-id="0b6c8-152">要创建使用不同属性值的设置，只需包含相应的参数和参数值。</span><span class="sxs-lookup"><span data-stu-id="0b6c8-152">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="0b6c8-153">例如，若要创建 "体验质量" 配置设置的集合，默认情况下，允许禁用 QoE 录制时，请使用如下所示的命令：</span><span class="sxs-lookup"><span data-stu-id="0b6c8-153">For example, to create a collection of Quality of Experience configuration settings that, by default, allow disable QoE recording use a command like this:</span></span>
    
        New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-qoe-configuration-settings"></a><span data-ttu-id="0b6c8-154">在创建新的 QoE 配置设置集合时指定多个属性值</span><span class="sxs-lookup"><span data-stu-id="0b6c8-154">To specify multiple property values when creating a new collection of QoE configuration settings</span></span>

  - <span data-ttu-id="0b6c8-155">您可以通过包含多个参数来使用多个属性值。</span><span class="sxs-lookup"><span data-stu-id="0b6c8-155">You can multiple property values by including multiple parameters.</span></span> <span data-ttu-id="0b6c8-156">例如，以下命令将新设置配置为将 QoE 数据保留30天，并在 3:00 AM 处清除旧数据：</span><span class="sxs-lookup"><span data-stu-id="0b6c8-156">For example, this command configures the new settings to keep QoE data for 30 days and to purge old data at 3:00 AM:</span></span>
    
        New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3

</div>

<span data-ttu-id="0b6c8-157">有关详细信息，请参阅 [new-csqoeconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="0b6c8-157">For more information, see the help topic for the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

