---
title: Lync Server 2013：创建体验配置设置的质量
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
ms.openlocfilehash: 0f651da026dcf73253eaccada14332a7f2f5c1f8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734242"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-quality-of-experience-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="19a92-102">在 Lync Server 2013 中创建体验配置设置的质量</span><span class="sxs-lookup"><span data-stu-id="19a92-102">Create Quality of Experience configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="19a92-103">_**主题上次修改时间：** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="19a92-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="19a92-p101">用户体验质量 (QoE) 指标跟踪组织中发出的语音和视频呼叫的质量，包括网络数据包丢失数目、背景噪音、"抖动"量（数据包延迟的差异）等。这些指标与其他数据（如呼叫详细信息记录）分开存储在一个数据库中，这样您就可以独立于其他数据记录启用和禁用 QoE。</span><span class="sxs-lookup"><span data-stu-id="19a92-p101">Quality of Experience (QoE) metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay). These metrics are stored in a database apart from other data (such as call detail records), which allows you to enable and disable QoE independent of other data recording.</span></span>

<span data-ttu-id="19a92-106">安装 Microsoft Lync Server 2013 时，将为你创建一个 QoE 配置设置的单个全局集合。</span><span class="sxs-lookup"><span data-stu-id="19a92-106">When you install Microsoft Lync Server 2013, a single, global collection of QoE configuration settings is created for you.</span></span> <span data-ttu-id="19a92-107">管理员还具有创建站点作用域的自定义设置的选项。</span><span class="sxs-lookup"><span data-stu-id="19a92-107">Administrators also have the option of creating custom settings at the site scope.</span></span> <span data-ttu-id="19a92-108">使用这些站点作用域设置时，它们将优先于全局设置。</span><span class="sxs-lookup"><span data-stu-id="19a92-108">Whenever these site-scoped settings are used, they take precedence over the global settings.</span></span> <span data-ttu-id="19a92-109">例如，如果您为 Redmond 站点创建了站点作用域设置，则这些设置（而不是全局设置）将用于管理 Redmond 内的 QoE。</span><span class="sxs-lookup"><span data-stu-id="19a92-109">For example, if you create site-scoped settings for the Redmond site then those settings (rather than the global settings) will be used to manage QoE in Redmond.</span></span>

<span data-ttu-id="19a92-110">QoE 配置设置可使用 Lync Server 控制面板或[CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) cmdlet 创建。</span><span class="sxs-lookup"><span data-stu-id="19a92-110">QoE configuration settings can be created by using either Lync Server Control Panel or the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) cmdlet.</span></span> <span data-ttu-id="19a92-111">如果您使用的是 Lync Server 控制面板来创建新设置，您将可以使用以下选项：</span><span class="sxs-lookup"><span data-stu-id="19a92-111">If you are using Lync Server Control Panel to create new settings the following options will be available to you:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="19a92-112">UI 设置</span><span class="sxs-lookup"><span data-stu-id="19a92-112">UI Setting</span></span></th>
<th><span data-ttu-id="19a92-113">PowerShell 参数</span><span class="sxs-lookup"><span data-stu-id="19a92-113">PowerShell Parameter</span></span></th>
<th><span data-ttu-id="19a92-114">描述</span><span class="sxs-lookup"><span data-stu-id="19a92-114">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="19a92-115">名称</span><span class="sxs-lookup"><span data-stu-id="19a92-115">Name</span></span></p></td>
<td><p><span data-ttu-id="19a92-116">Identity</span><span class="sxs-lookup"><span data-stu-id="19a92-116">Identity</span></span></p></td>
<td><p><span data-ttu-id="19a92-p104">要创建的设置的唯一标识符。只能创建站点作用域的 QoE 配置设置。</span><span class="sxs-lookup"><span data-stu-id="19a92-p104">Unique identifier for the settings to be created. QoE configuration settings can only be created at the site scope.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19a92-119">启用对 QoE 数据的监视</span><span class="sxs-lookup"><span data-stu-id="19a92-119">Enable monitoring of QoE data</span></span></p></td>
<td><p><span data-ttu-id="19a92-120">EnableQoE</span><span class="sxs-lookup"><span data-stu-id="19a92-120">EnableQoE</span></span></p></td>
<td><p><span data-ttu-id="19a92-121">指定是否收集 QoE 记录并将其保存到监控数据库。</span><span class="sxs-lookup"><span data-stu-id="19a92-121">Specifies whether QoE records will be collected and saved to the monitoring database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="19a92-122">启用清除 QoE 数据功能</span><span class="sxs-lookup"><span data-stu-id="19a92-122">Enable purging of QoE data</span></span></p></td>
<td><p><span data-ttu-id="19a92-123">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="19a92-123">EnablePurging</span></span></p></td>
<td><p><span data-ttu-id="19a92-124">指定经过在“<strong>QoE 数据最长保留期限（天）</strong>”中定义的持续时间后是否清除记录。</span><span class="sxs-lookup"><span data-stu-id="19a92-124">Specifies whether records will be purged after the duration defined in the <strong>Keep QoE data for a maximum duration (days)</strong> property has elapsed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="19a92-125">QoE 数据最长保留期限(天)</span><span class="sxs-lookup"><span data-stu-id="19a92-125">Keep QoE data for maximum duration (days)</span></span></p></td>
<td><p><span data-ttu-id="19a92-126">KeepQoEDataForDays</span><span class="sxs-lookup"><span data-stu-id="19a92-126">KeepQoEDataForDays</span></span></p></td>
<td><p><span data-ttu-id="19a92-p105">从数据库清除 QoE 数据之前存储的天数。如果禁用清除，则忽略此值。</span><span class="sxs-lookup"><span data-stu-id="19a92-p105">Number of days QoE data will be stored before being purged from the database. This value is ignored if purging is disabled.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="19a92-129">CsQoEConfiguration cmdlet 包括 Lync Server 控制面板中不可用的其他选项。</span><span class="sxs-lookup"><span data-stu-id="19a92-129">The New-CsQoEConfiguration cmdlet includes additional options not available in Lync Server Control Panel.</span></span> <span data-ttu-id="19a92-130">有关详细信息，请参阅<A href="https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration">CsQoEConfiguration</A>帮助主题。</span><span class="sxs-lookup"><span data-stu-id="19a92-130">For more information, see the <A href="https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration">New-CsQoEConfiguration</A> help topic.</span></span>



</div>

<div>

## <a name="to-create-qoe-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="19a92-131">使用 Lync Server "控制面板" 创建 QoE 配置设置</span><span class="sxs-lookup"><span data-stu-id="19a92-131">To create QoE configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="19a92-132">以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="19a92-132">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="19a92-133">有关详细信息，请参阅[在 Lync Server 2013 中委派设置权限](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="19a92-133">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="19a92-134">打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。</span><span class="sxs-lookup"><span data-stu-id="19a92-134">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="19a92-135">有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="19a92-135">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="19a92-136">在左侧导航栏中，单击“**监控和存档**”，然后单击“**用户体验质量数据**”。</span><span class="sxs-lookup"><span data-stu-id="19a92-136">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="19a92-137">在“**用户体验质量数据**”页上，单击“**新建**”。</span><span class="sxs-lookup"><span data-stu-id="19a92-137">On the **Quality of Experience Data** page, click **New**.</span></span>

5.  <span data-ttu-id="19a92-138">在“**选择站点**”中，单击要应用此策略的站点，然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="19a92-138">In **Select a Site**, click the site to which the policy is to be applied, and click **OK**.</span></span>

6.  <span data-ttu-id="19a92-139">在“**新建用户体验质量设置**”中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="19a92-139">In **New Quality of Experience Setting**, do the following:</span></span>
    
      - <span data-ttu-id="19a92-140">选择“**启用对 QoE 数据的监视**”以启用监视。</span><span class="sxs-lookup"><span data-stu-id="19a92-140">Select **Enable monitoring of QoE data** to turn on monitoring.</span></span>
    
      - <span data-ttu-id="19a92-141">选择“**启用清除 QoE 数据功能**”以启用清除。</span><span class="sxs-lookup"><span data-stu-id="19a92-141">Select **Enable purging of QoE data** to turn on purging.</span></span>
    
      - <span data-ttu-id="19a92-142">在“**QoE 最长保留期限（天）**”中，选择应保留 QoE 记录的最长天数。</span><span class="sxs-lookup"><span data-stu-id="19a92-142">In **Keep QoE for maximum duration (days)**, select the maximum number of days that QoE records should be retained.</span></span>

7.  <span data-ttu-id="19a92-143">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="19a92-143">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="19a92-144">使用 Windows PowerShell Cmdlet 创建 QoE 配置设置</span><span class="sxs-lookup"><span data-stu-id="19a92-144">Creating QoE Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="19a92-145">你可以使用 Windows PowerShell 和 CsQoEConfiguration cmdlet 创建 QoE 配置设置。</span><span class="sxs-lookup"><span data-stu-id="19a92-145">You can create QoE configuration settings by using Windows PowerShell and the New-CsQoEConfiguration cmdlet.</span></span> <span data-ttu-id="19a92-146">你可以从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话运行此 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="19a92-146">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="19a92-147">有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。</span><span class="sxs-lookup"><span data-stu-id="19a92-147">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-collection-of-qoe-configuration-settings"></a><span data-ttu-id="19a92-148">创建新的 QoE 配置设置的集合</span><span class="sxs-lookup"><span data-stu-id="19a92-148">To create a new collection of QoE configuration settings</span></span>

  - <span data-ttu-id="19a92-149">以下命令将创建新的应用于 Redmond 站点的 QoE 配置设置的集合：</span><span class="sxs-lookup"><span data-stu-id="19a92-149">This command creates a new collection of QoE configuration settings applied to the Redmond site:</span></span>
    
        New-CsQoEConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-collection-of-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a><span data-ttu-id="19a92-150">创建其中禁用 QoE 监视的 QoE 配置设置的新集合</span><span class="sxs-lookup"><span data-stu-id="19a92-150">To create a new collection of QoE configuration settings where QoE monitoring is disabled</span></span>

  - <span data-ttu-id="19a92-p110">由于前面的命令中未指定参数（必需的 Identity 参数之外），因此新的配置设置集合将对其所有属性使用默认值。若要创建使用不同属性值的设置，只需包含相应的参数和参数值。例如，若要创建用户体验质量配置设置的集合，默认情况下，允许禁用 QoE 记录使用与以下命令类似的命令：</span><span class="sxs-lookup"><span data-stu-id="19a92-p110">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties. To create settings that use different property values, simply include the appropriate parameter and parameter value. For example, to create a collection of Quality of Experience configuration settings that, by default, allow disable QoE recording use a command like this:</span></span>
    
        New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-qoe-configuration-settings"></a><span data-ttu-id="19a92-154">创建新的 QoE 配置设置集合时指定多个属性值</span><span class="sxs-lookup"><span data-stu-id="19a92-154">To specify multiple property values when creating a new collection of QoE configuration settings</span></span>

  - <span data-ttu-id="19a92-p111">您可通过包含多个参数指定多个属性值。例如，此命令会将新设置配置为保留 QoE 数据 30 天并于上午 3:00 清除旧数据：</span><span class="sxs-lookup"><span data-stu-id="19a92-p111">You can multiple property values by including multiple parameters. For example, this command configures the new settings to keep QoE data for 30 days and to purge old data at 3:00 AM:</span></span>
    
        New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3

</div>

<span data-ttu-id="19a92-157">有关详细信息，请参阅[CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="19a92-157">For more information, see the help topic for the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

