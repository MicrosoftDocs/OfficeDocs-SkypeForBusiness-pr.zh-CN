---
title: 在 Skype for Business Server 中管理存档数据的清除
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 14c2b4fd-f612-4909-808d-09c655fc9f8a
description: 摘要：了解如何管理清除 Skype for Business Server 的存档数据。
ms.openlocfilehash: aecc78f84b3cd4b745a96e534535c98c1739c156
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828532"
---
# <a name="manage-purging-of-archived-data-in-skype-for-business-server"></a><span data-ttu-id="dafa0-103">在 Skype for Business Server 中管理存档数据的清除</span><span class="sxs-lookup"><span data-stu-id="dafa0-103">Manage purging of archived data in Skype for Business Server</span></span>

<span data-ttu-id="dafa0-104">**摘要：** 了解如何管理清除 Skype for Business Server 的存档数据。</span><span class="sxs-lookup"><span data-stu-id="dafa0-104">**Summary:** Learn how to manage purging of archived data for Skype for Business Server.</span></span>
  
<span data-ttu-id="dafa0-105">存档数据库不用于长期保留，Skype for Business Server 不提供存档数据的电子发现 (搜索) 解决方案，因此需要将数据移动到其他存储。</span><span class="sxs-lookup"><span data-stu-id="dafa0-105">The Archiving database is not intended for long-term retention, and Skype for Business Server does not provide an e-discovery (search) solution for archived data, so data needs to be moved to other storage.</span></span> <span data-ttu-id="dafa0-106">Skype for Business Server 提供了一个会话导出工具，可用于将存档数据导出到可搜索的脚本中。</span><span class="sxs-lookup"><span data-stu-id="dafa0-106">Skype for Business Server provides a session export tool that you can use to export archived data into searchable transcripts.</span></span> <span data-ttu-id="dafa0-107">您需要定义何时清除存档和导出的数据。</span><span class="sxs-lookup"><span data-stu-id="dafa0-107">You need to define when to purge archived and exported data.</span></span> 
  
<span data-ttu-id="dafa0-108">有关使用 **Export-CsArchivingData** cmdlet 导出数据详细信息，请参阅"导出 Skype for Business Server 中的存档 [数据"。](export-archived-data.md)</span><span class="sxs-lookup"><span data-stu-id="dafa0-108">For more information about exporting data by using the **Export-CsArchivingData** cmdlet, see [Export archived data in Skype for Business Server](export-archived-data.md).</span></span>
  
## <a name="manage-purging-of-data-by-using-the-control-panel"></a><span data-ttu-id="dafa0-109">使用控制面板管理数据的清除</span><span class="sxs-lookup"><span data-stu-id="dafa0-109">Manage purging of data by using the Control Panel</span></span>

<span data-ttu-id="dafa0-110">若要使用控制面板管理存档数据的清除，</span><span class="sxs-lookup"><span data-stu-id="dafa0-110">To manage purging of archived data by using the Control Panel:</span></span>
  
1. <span data-ttu-id="dafa0-111">使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="dafa0-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="dafa0-112">打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="dafa0-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="dafa0-113">在左侧导航栏中，单击 **“监控和存档”**，然后单击 **“存档配置”**。</span><span class="sxs-lookup"><span data-stu-id="dafa0-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="dafa0-114">在存档配置列表中单击相应的全局、站点或池配置的名称，然后依次单击“编辑”、“显示详细信息”，然后执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="dafa0-114">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
   - <span data-ttu-id="dafa0-115">要启用清除，请选中“启用清除存档数据功能”复选框，然后执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="dafa0-115">To enable purging, select the **Enable purging of archiving data** check box and then do one of the following:</span></span>
    
     - <span data-ttu-id="dafa0-116">要清除所有记录，请单击“清除超过以下最长持续时间(天)的已导出存档数据和已存储存档数据”，然后指定天数。</span><span class="sxs-lookup"><span data-stu-id="dafa0-116">To purge all records, click the **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
     - <span data-ttu-id="dafa0-117">要仅清除已导出的数据，请单击“仅清除已导出的存档数据”。</span><span class="sxs-lookup"><span data-stu-id="dafa0-117">To purge only the data that has been exported, click **Purge exported archiving data only**.</span></span>
    
   - <span data-ttu-id="dafa0-118">要禁用清除，请清除“启用清除存档数据功能”复选框。</span><span class="sxs-lookup"><span data-stu-id="dafa0-118">To disable purging, clear the **Enable purging of archiving data** check box.</span></span>
    
5. <span data-ttu-id="dafa0-119">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="dafa0-119">Click **Commit**.</span></span>
    
## <a name="manage-purging-of-data-by-using-windows-powershell"></a><span data-ttu-id="dafa0-120">使用数据库管理数据清除Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="dafa0-120">Manage purging of data by using Windows PowerShell</span></span>

<span data-ttu-id="dafa0-121">您可以使用以下 cmdlet 管理存档数据的清除Windows PowerShell cmdlet：</span><span class="sxs-lookup"><span data-stu-id="dafa0-121">You can manage purging of archived data by using the following Windows PowerShell cmdlets:</span></span>
  
- <span data-ttu-id="dafa0-122">**Set-CsArchivingConfiguration** cmdlet 和 EnablePurging 参数允许您启用或禁用存档数据的清除。</span><span class="sxs-lookup"><span data-stu-id="dafa0-122">**Set-CsArchivingConfiguration** cmdlet with the EnablePurging parameter lets you enable or disable purging of archived data.</span></span>
    
- <span data-ttu-id="dafa0-123">**Invoke-CsArchivingDatabasePurge** 允许您手动清除存档数据库中的记录。</span><span class="sxs-lookup"><span data-stu-id="dafa0-123">**Invoke-CsArchivingDatabasePurge** lets you manually purge records from the Archiving database.</span></span>
    
<span data-ttu-id="dafa0-124">例如，以下命令允许清除所有存档数据。</span><span class="sxs-lookup"><span data-stu-id="dafa0-124">For example, the following command enables the purging of all archived data.</span></span> <span data-ttu-id="dafa0-125">运行此命令后，Skype for Business Server 将清除所有超过为 KeepArchivingDataForDays 参数指定的值的存档记录。</span><span class="sxs-lookup"><span data-stu-id="dafa0-125">After this command is run, Skype for Business Server will purge all archiving records older than the value specified for the KeepArchivingDataForDays parameter.</span></span> 
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
```

<span data-ttu-id="dafa0-126">以下命令将清除限制使用 **Export-CSArchivingData** cmdlet (导出到数据文件的存档) 。</span><span class="sxs-lookup"><span data-stu-id="dafa0-126">The following command limits purging to archived records that have been exported to a data file (by using the **Export-CSArchivingData** cmdlet).</span></span> <span data-ttu-id="dafa0-127">还必须将 PurgeExportedArchivesOnly 参数设置为 True ($True) ：</span><span class="sxs-lookup"><span data-stu-id="dafa0-127">You must also set the PurgeExportedArchivesOnly parameter to True ($True):</span></span>
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
```

<span data-ttu-id="dafa0-128">运行此命令后，Skype for Business Server 将仅清除满足两个条件的存档记录：1) 它们比 KeepArchivingDataForDays 参数指定的值旧;和 2) **Export-CsArchivingData** cmdlet 导出它们。</span><span class="sxs-lookup"><span data-stu-id="dafa0-128">After this command is run, Skype for Business Server will only purge archiving records that meet two criteria: 1) they are older than the value specified for the KeepArchivingDataForDays parameter; and, 2) they have been exported by using the **Export-CsArchivingData** cmdlet.</span></span>
  
<span data-ttu-id="dafa0-129">若要禁用自动清除存档记录，将 EnablePurging 参数设置为 False ($False) ：</span><span class="sxs-lookup"><span data-stu-id="dafa0-129">To disable the automated purging of archiving records, set the EnablePurging parameter to False ($False):</span></span>
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False
```

<span data-ttu-id="dafa0-130">以下示例使用 **Invoke-CsArchivingDatabasePurge** cmdlet 清除存档数据库中 24 小时之前的所有记录atl-sql-001.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="dafa0-130">The following example uses the **Invoke-CsArchivingDatabasePurge** cmdlet to purge all the records more than 24 hours old from the archiving database on atl-sql-001.contoso.com.</span></span> <span data-ttu-id="dafa0-131">为了确保删除所有记录（包括尚未导出的记录），PurgeExportedArchivesOnly 参数设置为 False ($False) ：</span><span class="sxs-lookup"><span data-stu-id="dafa0-131">To ensure that all the records are deleted, including records that have not been exported, the PurgeExportedArchivesOnly parameter is set to False ($False):</span></span>
  
```PowerShell
Invoke-CsArchivingDatabasePurge -Identity "service:ArchivingDatabase:atl-sql-001.contoso.com" -PurgeArchivingDataOlderThanHours 24 -PurgeExportedArchivesOnly $False
```
