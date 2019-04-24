---
title: 管理业务服务器中 Skype 的存档数据的清除
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14c2b4fd-f612-4909-808d-09c655fc9f8a
description: 摘要： 了解如何管理的 Skype 业务服务器的存档数据清除。
ms.openlocfilehash: 5483871d69932239f5d6e654c95edf1feac7b9d9
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32211030"
---
# <a name="manage-purging-of-archived-data-in-skype-for-business-server"></a><span data-ttu-id="f8526-103">管理业务服务器中 Skype 的存档数据的清除</span><span class="sxs-lookup"><span data-stu-id="f8526-103">Manage purging of archived data in Skype for Business Server</span></span>

<span data-ttu-id="f8526-104">**摘要：** 了解如何管理的 Skype 业务服务器的存档数据清除。</span><span class="sxs-lookup"><span data-stu-id="f8526-104">**Summary:** Learn how to manage purging of archived data for Skype for Business Server.</span></span>
  
<span data-ttu-id="f8526-105">存档数据库不是以进行长期保留和 Skype 业务服务器不提供电子发现 （搜索） 解决方案的存档数据，因此需要移动到其他存储的数据。</span><span class="sxs-lookup"><span data-stu-id="f8526-105">The Archiving database is not intended for long-term retention, and Skype for Business Server does not provide an e-discovery (search) solution for archived data, so data needs to be moved to other storage.</span></span> <span data-ttu-id="f8526-106">Skype 业务服务器提供了可用于将存档的数据导出到可搜索脚本会话导出工具。</span><span class="sxs-lookup"><span data-stu-id="f8526-106">Skype for Business Server provides a session export tool that you can use to export archived data into searchable transcripts.</span></span> <span data-ttu-id="f8526-107">您需要定义何时清除已存档和已导出的数据。</span><span class="sxs-lookup"><span data-stu-id="f8526-107">You need to define when to purge archived and exported data.</span></span> 
  
<span data-ttu-id="f8526-108">有关使用**Export-csarchivingdata** cmdlet 导出数据的详细信息，请参阅[导出 Skype 业务服务器中的存档的数据](export-archived-data.md)。</span><span class="sxs-lookup"><span data-stu-id="f8526-108">For more information about exporting data by using the **Export-CsArchivingData** cmdlet, see [Export archived data in Skype for Business Server](export-archived-data.md).</span></span>
  
## <a name="manage-purging-of-data-by-using-the-control-panel"></a><span data-ttu-id="f8526-109">使用控制面板管理数据的清除</span><span class="sxs-lookup"><span data-stu-id="f8526-109">Manage purging of data by using the Control Panel</span></span>

<span data-ttu-id="f8526-110">要使用控制面板管理存档数据的清除：</span><span class="sxs-lookup"><span data-stu-id="f8526-110">To manage purging of archived data by using the Control Panel:</span></span>
  
1. <span data-ttu-id="f8526-111">使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="f8526-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="f8526-112">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="f8526-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="f8526-113">在左侧导航栏中，单击“监控和存档”\*\*\*\*，然后单击“存档配置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f8526-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="f8526-114">单击存档配置列表中相应的全局、站点或池配置的名称，单击“**编辑**”，再单击“**显示详细信息**”，然后执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f8526-114">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
   - <span data-ttu-id="f8526-115">要启用清除，请选中“**启用清除存档数据功能**”复选框，然后执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="f8526-115">To enable purging, select the **Enable purging of archiving data** check box and then do one of the following:</span></span>
    
     - <span data-ttu-id="f8526-116">要清除所有记录，请单击“**清除超过以下最长持续时间（天）的已导出存档数据和已存储存档数据**”，然后指定天数。</span><span class="sxs-lookup"><span data-stu-id="f8526-116">To purge all records, click the **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
     - <span data-ttu-id="f8526-117">要仅清除已导出的数据，请单击“**仅清除已导出的存档数据**”。</span><span class="sxs-lookup"><span data-stu-id="f8526-117">To purge only the data that has been exported, click **Purge exported archiving data only**.</span></span>
    
   - <span data-ttu-id="f8526-118">要禁用清除，请清除“**启用清除存档数据功能**”复选框。</span><span class="sxs-lookup"><span data-stu-id="f8526-118">To disable purging, clear the **Enable purging of archiving data** check box.</span></span>
    
5. <span data-ttu-id="f8526-119">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="f8526-119">Click **Commit**.</span></span>
    
## <a name="manage-purging-of-data-by-using-windows-powershell"></a><span data-ttu-id="f8526-120">使用 Windows PowerShell 管理数据的清除</span><span class="sxs-lookup"><span data-stu-id="f8526-120">Manage purging of data by using Windows PowerShell</span></span>

<span data-ttu-id="f8526-121">您可以使用以下 Windows PowerShell cmdlet 管理存档数据的清除：</span><span class="sxs-lookup"><span data-stu-id="f8526-121">You can manage purging of archived data by using the following Windows PowerShell cmdlets:</span></span>
  
- <span data-ttu-id="f8526-122">**Set-CsArchivingConfiguration** cmdlet 和 EnablePurging 参数允许您启用或禁用存档数据的清除。</span><span class="sxs-lookup"><span data-stu-id="f8526-122">**Set-CsArchivingConfiguration** cmdlet with the EnablePurging parameter lets you enable or disable purging of archived data.</span></span>
    
- <span data-ttu-id="f8526-123">**Invoke-CsArchivingDatabasePurge** 可让您手动清除存档数据库中的记录。</span><span class="sxs-lookup"><span data-stu-id="f8526-123">**Invoke-CsArchivingDatabasePurge** lets you manually purge records from the Archiving database.</span></span>
    
<span data-ttu-id="f8526-124">例如，以下命令可启用所有存档数据的清除。</span><span class="sxs-lookup"><span data-stu-id="f8526-124">For example, the following command enables the purging of all archived data.</span></span> <span data-ttu-id="f8526-125">运行此命令后，Skype 业务服务器都会清除早于指定于为 KeepArchivingDataForDays 参数的值的所有存档记录。</span><span class="sxs-lookup"><span data-stu-id="f8526-125">After this command is run, Skype for Business Server will purge all archiving records older than the value specified for the KeepArchivingDataForDays parameter.</span></span> 
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
```

<span data-ttu-id="f8526-126">下面的命令限制清除已 （通过使用**Export-csarchivingdata** cmdlet） 为数据文件中导出的存档记录。</span><span class="sxs-lookup"><span data-stu-id="f8526-126">The following command limits purging to archived records that have been exported to a data file (by using the **Export-CSArchivingData** cmdlet).</span></span> <span data-ttu-id="f8526-127">您还必须设置为 True ($True) PurgeExportedArchivesOnly 参数：</span><span class="sxs-lookup"><span data-stu-id="f8526-127">You must also set the PurgeExportedArchivesOnly parameter to True ($True):</span></span>
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
```

<span data-ttu-id="f8526-128">Skype 业务服务器运行此命令后，将仅清除存档记录满足两个条件： 1) 在早于于为 KeepArchivingDataForDays 参数，则为指定的值以及 2） 已使用**Export-csarchivingdata** cmdlet 导出它们。</span><span class="sxs-lookup"><span data-stu-id="f8526-128">After this command is run, Skype for Business Server will only purge archiving records that meet two criteria: 1) they are older than the value specified for the KeepArchivingDataForDays parameter; and, 2) they have been exported by using the **Export-CsArchivingData** cmdlet.</span></span>
  
<span data-ttu-id="f8526-129">若要禁用自动清除存档记录功能，请将  EnablePurging 参数设置为 False ($False)。</span><span class="sxs-lookup"><span data-stu-id="f8526-129">To disable the automated purging of archiving records, set the EnablePurging parameter to False ($False):</span></span>
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False
```

<span data-ttu-id="f8526-130">下面的示例使用**Invoke-csarchivingdatabasepurge** cmdlet 从 atl-sql-001.contoso.com 上的存档数据库中清除所有记录超过 24 小时。</span><span class="sxs-lookup"><span data-stu-id="f8526-130">The following example uses the **Invoke-CsArchivingDatabasePurge** cmdlet to purge all the records more than 24 hours old from the archiving database on atl-sql-001.contoso.com.</span></span> <span data-ttu-id="f8526-131">为确保删除所有记录，包括尚未导出的记录，请将 PurgeExportedArchivesOnly 参数设置为 False ($False)。</span><span class="sxs-lookup"><span data-stu-id="f8526-131">To ensure that all the records are deleted, including records that have not been exported, the PurgeExportedArchivesOnly parameter is set to False ($False):</span></span>
  
```
Invoke-CsArchivingDatabasePurge -Identity "service:ArchivingDatabase:atl-sql-001.contoso.com" -PurgeArchivingDataOlderThanHours 24 -PurgeExportedArchivesOnly $False
```
