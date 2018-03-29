---
title: 为业务服务器 2015年配置在 Skype 呼叫详细记录和体验质量设置
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 009a0499-4f8c-450d-9c72-a565a08e9f7a
description: 摘要： 了解如何配置 CDR 和 QoE 在 Skype 业务服务器 2015年。
ms.openlocfilehash: 0b72aa4ca58de934d2d09c599e6e7686e70f8822
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-call-detail-recording-and-quality-of-experience-settings-in-skype-for-business-server-2015"></a><span data-ttu-id="7bc44-103">为业务服务器 2015年配置在 Skype 呼叫详细记录和体验质量设置</span><span class="sxs-lookup"><span data-stu-id="7bc44-103">Configure call detail recording and Quality of Experience settings in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="7bc44-104">**摘要：**了解如何配置 CDR 和 QoE 在 Skype 业务服务器 2015年。</span><span class="sxs-lookup"><span data-stu-id="7bc44-104">**Summary:** Learn how to configure CDR and QoE in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="7bc44-105">配置 CDR 和 QoE 监控业务服务器 2015年的 Skype 使用 SQL Server 报表服务报告。</span><span class="sxs-lookup"><span data-stu-id="7bc44-105">Configure CDR and QoE monitoring using SQL Server Reporting Services reports for Skype for Business Server 2015.</span></span>
  
## <a name="configure-cdr-and-qoe"></a><span data-ttu-id="7bc44-106">配置 CDR 和 QoE</span><span class="sxs-lookup"><span data-stu-id="7bc44-106">Configure CDR and QoE</span></span>

<span data-ttu-id="7bc44-107">监视存储相关联的前端池，设置监视存储区，然后再安装和配置 SQL Server Reporting Services 和监视报告后您可以管理呼叫详细记录 (CDR) 和体验质量 (QoE)监视使用 Skype 业务服务器管理程序。</span><span class="sxs-lookup"><span data-stu-id="7bc44-107">After you have associated a monitoring store with a Front End pool, set up the monitoring store, and then installed and configured SQL Server Reporting Services and Monitoring Reports you can manage Call Detail Recording (CDR) and Quality of Experience (QoE) monitoring by using Skype for Business Server Management Shell.</span></span> <span data-ttu-id="7bc44-108">企业服务器管理外壳 cmdlet 的 Skype 允许您启用和禁用 CDR 和/或 QoE 监控为特定网站或您整个 Skype 业务服务器部署;它可以简单，如下的命令：</span><span class="sxs-lookup"><span data-stu-id="7bc44-108">Skype for Business Server Management Shell cmdlets allow you to enable and disable CDR and/or QoE monitoring for a particular site or for your entire Skype for Business Server deployment; that can be done with a command as simple as this:</span></span>
  
```
Set-CsQoEConfiguration -Identity "global" -EnableQoE $False
```

<span data-ttu-id="7bc44-109">业务服务器 2015年安装 Skype 时，还将安装一组预定的 CDR 和 QoE 全局配置设置。</span><span class="sxs-lookup"><span data-stu-id="7bc44-109">When you install Skype for Business Server 2015, you will also install a predefined collection of global configuration settings for both CDR and QoE.</span></span> <span data-ttu-id="7bc44-110">下表显示了呼叫详细记录使用的一些较常用设置的默认值：</span><span class="sxs-lookup"><span data-stu-id="7bc44-110">Default values for some of the more commonly-used settings used by Call Detail Recording are shown in the following table:</span></span>
  
|<span data-ttu-id="7bc44-111">**属性**</span><span class="sxs-lookup"><span data-stu-id="7bc44-111">**Property**</span></span>|<span data-ttu-id="7bc44-112">**说明**</span><span class="sxs-lookup"><span data-stu-id="7bc44-112">**Description**</span></span>|<span data-ttu-id="7bc44-113">**默认值**</span><span class="sxs-lookup"><span data-stu-id="7bc44-113">**Default Value**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7bc44-114">EnableCDR</span><span class="sxs-lookup"><span data-stu-id="7bc44-114">EnableCDR</span></span>  <br/> |<span data-ttu-id="7bc44-p103">指示是否启用 CDR。如果为 True，将收集所有 CDR 记录并写入监控数据库。</span><span class="sxs-lookup"><span data-stu-id="7bc44-p103">Indicates whether or not CDR is enabled. If True, all CDR records will be collected and written to the monitoring database.</span></span>  <br/> |<span data-ttu-id="7bc44-117">True</span><span class="sxs-lookup"><span data-stu-id="7bc44-117">True</span></span>  <br/> |
|<span data-ttu-id="7bc44-118">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="7bc44-118">EnablePurging</span></span>  <br/> |<span data-ttu-id="7bc44-p104">指示是否定期从数据库中删除 CDR 记录。如果为 True，则将在属性 KeepCallDetailForDays（对于 CDR 记录）和 KeepErrorReportForDays（对于 CDR 错误）指定的时间段后删除记录。如果为 False，则将无限期保留 CDR 记录。</span><span class="sxs-lookup"><span data-stu-id="7bc44-p104">Indicates whether or not CDR records will periodically be deleted from the database. If True, records will be deleted after the time period specified by the properties KeepCallDetailForDays (for CDR records) and KeepErrorReportForDays (for CDR errors). If False, CDR records will be maintained indefinitely.</span></span>  <br/> |<span data-ttu-id="7bc44-122">True</span><span class="sxs-lookup"><span data-stu-id="7bc44-122">True</span></span>  <br/> |
|<span data-ttu-id="7bc44-123">KeepCallDetailForDays</span><span class="sxs-lookup"><span data-stu-id="7bc44-123">KeepCallDetailForDays</span></span>  <br/> |<span data-ttu-id="7bc44-p105">指示 CDR 记录在数据库中保留的天数；超过指定天数的任何记录将自动删除。但是，只有在启用了清除时才会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="7bc44-p105">Indicates the number of days that CDR records will be kept in the database; any records older than the specified number of days will automatically be deleted. However, this will occur only if purging has been enabled.</span></span>  <br/> <span data-ttu-id="7bc44-126">KeepCallDetailForDays 可以设置为 1 到 2562 天（大约 7 年）之间的任意整数值。</span><span class="sxs-lookup"><span data-stu-id="7bc44-126">KeepCallDetailForDays can be set to any integer value between 1 and 2562 days (approximately 7 years).</span></span>  <br/> |<span data-ttu-id="7bc44-127">60 天</span><span class="sxs-lookup"><span data-stu-id="7bc44-127">60 days</span></span>  <br/> |
|<span data-ttu-id="7bc44-128">KeepErrorReportForDays</span><span class="sxs-lookup"><span data-stu-id="7bc44-128">KeepErrorReportForDays</span></span>  <br/> |<span data-ttu-id="7bc44-129">指示保留 CDR 错误报告的天数；超过指定天数的任何报告将自动删除。</span><span class="sxs-lookup"><span data-stu-id="7bc44-129">Indicates the number of days that CDR error reports are kept; any reports older than the specified number of days will automatically be deleted.</span></span> <span data-ttu-id="7bc44-130">CDR 的错误报告是由客户端应用程序，如 Skype 的业务服务器 2015年上载诊断报告。</span><span class="sxs-lookup"><span data-stu-id="7bc44-130">CDR error reports are diagnostic reports uploaded by client applications such as Skype for Business Server 2015.</span></span>  <br/> <span data-ttu-id="7bc44-131">您可以将此属性设置为 1 到 2562 天之间的任意整数值。</span><span class="sxs-lookup"><span data-stu-id="7bc44-131">You can set this property to any integer value between 1 and 2562 days.</span></span>  <br/> |<span data-ttu-id="7bc44-132">60 天</span><span class="sxs-lookup"><span data-stu-id="7bc44-132">60 days</span></span>  <br/> |
   
<span data-ttu-id="7bc44-133">类似地，此表中也显示了选定 QoE 设置的默认值：</span><span class="sxs-lookup"><span data-stu-id="7bc44-133">Similarly, default values for selected QoE settings are shown in this table:</span></span>
  
|<span data-ttu-id="7bc44-134">**属性**</span><span class="sxs-lookup"><span data-stu-id="7bc44-134">**Property**</span></span>|<span data-ttu-id="7bc44-135">**说明**</span><span class="sxs-lookup"><span data-stu-id="7bc44-135">**Description**</span></span>|<span data-ttu-id="7bc44-136">**默认值**</span><span class="sxs-lookup"><span data-stu-id="7bc44-136">**Default Value**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7bc44-137">EnableQoE</span><span class="sxs-lookup"><span data-stu-id="7bc44-137">EnableQoE</span></span>  <br/> |<span data-ttu-id="7bc44-p107">指示是否启用 QoE 监控。如果为 True，将收集所有 QoE 记录并写入监控数据库。</span><span class="sxs-lookup"><span data-stu-id="7bc44-p107">Indicates whether or not QoE monitoring is enabled. If True, all QoE records will be collected and written to the monitoring database.</span></span>  <br/> |<span data-ttu-id="7bc44-140">True</span><span class="sxs-lookup"><span data-stu-id="7bc44-140">True</span></span>  <br/> |
|<span data-ttu-id="7bc44-141">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="7bc44-141">EnablePurging</span></span>  <br/> |<span data-ttu-id="7bc44-p108">指示是否定期从数据库中删除 QoE 记录。如果为 True，则将在属性 KeepQoEDataForDays 指定的时间段后删除记录。如果为 False，则将无限期保留 QoE 记录。</span><span class="sxs-lookup"><span data-stu-id="7bc44-p108">Indicates whether or not QoE records will periodically be deleted from the database. If True, records will be deleted after the time period specified by the KeepQoEDataForDays property. If False, QoE records will be maintained indefinitely.</span></span>  <br/> |<span data-ttu-id="7bc44-145">True</span><span class="sxs-lookup"><span data-stu-id="7bc44-145">True</span></span>  <br/> |
|<span data-ttu-id="7bc44-146">KeepQoEDataForDays</span><span class="sxs-lookup"><span data-stu-id="7bc44-146">KeepQoEDataForDays</span></span>  <br/> |<span data-ttu-id="7bc44-p109">指示 QoE 记录在数据库中保留的天数；超过指定天数的任何记录将自动删除。但是，只有在启用了清除时才会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="7bc44-p109">Indicates the number of days that QoE records will be kept in the database; any records older than the specified number of days will automatically be deleted. However, this will occur only if purging has been enabled.</span></span>  <br/> <span data-ttu-id="7bc44-149">可将 KeepCallDetailForDays 设置为 1 到 2562 天之间的任意整数值。</span><span class="sxs-lookup"><span data-stu-id="7bc44-149">KeepCallDetailForDays can be set to any integer value between 1 and 2562 days.</span></span>  <br/> |<span data-ttu-id="7bc44-150">60 天</span><span class="sxs-lookup"><span data-stu-id="7bc44-150">60 days</span></span>  <br/> |
   
<span data-ttu-id="7bc44-151">如果您需要修改这些全局设置，可以使用 Set-CsCdrConfiguration 和 Set-CsQoEConfiguration cmdlet 来完成。</span><span class="sxs-lookup"><span data-stu-id="7bc44-151">If you need to modify these global settings you can do so by using the Set-CsCdrConfiguration and the Set-CsQoEConfiguration cmdlets.</span></span> <span data-ttu-id="7bc44-152">例如，（从内运行 Skype 的业务服务器管理外壳） 该命令将禁用 CDR 监视在全局范围内;它是通过将 EnableCDR 属性设置为 False ($False):</span><span class="sxs-lookup"><span data-stu-id="7bc44-152">For example, this command (run from within the Skype for Business Server Management Shell) disables CDR monitoring at the global scope; that's done by setting the EnableCDR property to False ($False):</span></span>
  
```
Set-CsCdrConfiguration -Identity "global" -EnableCDR $False
```

<span data-ttu-id="7bc44-153">请注意，禁用监控不会从前端池解除监控存储关联，也不卸载或以其他方式影响后端监控数据库。</span><span class="sxs-lookup"><span data-stu-id="7bc44-153">Note that disabling monitoring does not dissociate the monitoring store from the Front End pool, nor does it uninstall or otherwise affect the backend monitoring database.</span></span> <span data-ttu-id="7bc44-154">当您使用 Skype 的业务服务器管理外壳程序禁用 CDR 或 QoE 监控真的做的一切是暂时停止从收集和存档监视数据业务服务器的 Skype。</span><span class="sxs-lookup"><span data-stu-id="7bc44-154">When you use Skype for Business Server Management Shell to disable either CDR or QoE monitoring all you really do is temporarily stop Skype for Business Server from collecting and archiving monitoring data.</span></span> <span data-ttu-id="7bc44-155">如果要恢复收集和存档 CDR 数据，只需要将 EnableCDR 属性重新设置为 True ($True) 即可：</span><span class="sxs-lookup"><span data-stu-id="7bc44-155">If you want to resume, in this case, the collection and archiving of CDR data, all you need to do is set the EnableCDR property back to True ($True):</span></span>
  
```
Set-CsCdrConfiguration -Identity "global" -EnableCDR $True
```

<span data-ttu-id="7bc44-156">类似地，以下命令在全局范围内禁止清除 QoE 记录：</span><span class="sxs-lookup"><span data-stu-id="7bc44-156">Similarly, this command disables the purging of QoE records at the global scope:</span></span>
  
```
Set-CsQoEConfiguration -Identity "global" -EnablePurging $False
```

<span data-ttu-id="7bc44-p112">除了全局设置，也可将 CDR 和 QoE 配置设置分配给站点范围。这样，在实施监控时可提供更大的管理灵活性；例如，管理员可以对 Redmond 站点启用 CDR 监控，而对 Dublin 站点禁用 CDR 监控。要在站点范围创建新的 CDR 配置设置，请使用类似如下的命令：</span><span class="sxs-lookup"><span data-stu-id="7bc44-p112">In addition to the global settings, CDR and QoE configurations settings can be assigned to the site scope. This provides additional management flexibility when it comes to monitoring; for example, an administrator can enable CDR monitoring for the Redmond site but disable CDR monitoring for the Dublin site. To create new CDR configuration settings at the site scope, use a command similar to this:</span></span>
  
```
New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False
```

<span data-ttu-id="7bc44-p113">请记住，在站点范围配置的设置优先于在全局范围配置的设置。例如，假设在全局范围启用了 CDR 监控，但在站点范围（对于 Redmond 站点）禁用了 CDR 监控。这意味着将不为 Redmond 站点中的用户存档呼叫详细记录信息。但是，其他站点中的用户（即，由全局设置而非 Redmond 站点设置管理的用户）的呼叫详细记录仍将存档。</span><span class="sxs-lookup"><span data-stu-id="7bc44-p113">Keep in mind that settings configured at the site scope take precedence over settings configured at the global scope. For example, suppose CDR monitoring is enabled at the global scope, but disabled at the site scope (for the Redmond site). That means that call detail recording information will not be archived for users in the Redmond site. However, users in other sites (that is, users managed by the global settings instead of the Redmond site settings) will have their call detail recording information archived.</span></span>
  
<span data-ttu-id="7bc44-164">可以使用类似如下的命令在站点范围创建新的 QoE 配置设置：</span><span class="sxs-lookup"><span data-stu-id="7bc44-164">New QoE configuration settings can be created at the site scope by using a command like this one:</span></span>
  
```
New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 15
```

<span data-ttu-id="7bc44-165">有关详细信息，键入下面的命令从 Skype 在业务服务器管理外壳程序：</span><span class="sxs-lookup"><span data-stu-id="7bc44-165">For more information, type the following commands from within the Skype for Business Server Management Shell:</span></span>
  
```
Get-Help New-CsCdrConfiguration | more
Get-Help Set-CsCdrConfiguration | more
Get-Help New-CsQoEConfiguration | more
Get-Help Set-CsQoEConfiguration | more
```


