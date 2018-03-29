---
title: 设备更新
ms.author: laurawi
author: LauraWi
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceUpdateMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6f6b7f73-f8f5-41dc-9e2a-727baaaa828b
description: Microsoft 会定期会对 Skype 的一套新的设备的固件更新业务电话版中，您可以导入到您的服务器并向用户分发发布。 可以通过在 Microsoft 网站上转到帮助和支持页面，搜索 forPhone Edition.Download 最新的更新软件包获得最新的一套设备更新规则，并将文件提取到一个文件夹在计算机上更新将要上载。 在提取文件后，可以使用导入 CsDeviceUpdate cmdlet 导入中所提取的设备更新规则。CAB 文件 （它们将具有 UCUpdates.cab 的名称）。 有关详细信息，请参阅导入 CsDeviceUpdate。
ms.openlocfilehash: 584c04e8169eec4621c91c469127b99388f4820a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="device-update"></a><span data-ttu-id="e0525-106">设备更新</span><span class="sxs-lookup"><span data-stu-id="e0525-106">Device Update</span></span>
 
<span data-ttu-id="e0525-107">Microsoft 会定期会对 Skype 的一套新的设备的固件更新业务电话版中，您可以导入到您的服务器并向用户分发发布。</span><span class="sxs-lookup"><span data-stu-id="e0525-107">Microsoft periodically releases a new set of device firmware updates for Skype for Business Phone Edition, which you can import to your servers and distribute to users.</span></span> <span data-ttu-id="e0525-108">可通过转至 Microsoft 网站上的帮助和支持页并搜索“Phone Edition”来获取一组最新的设备更新规则。</span><span class="sxs-lookup"><span data-stu-id="e0525-108">You can obtain the latest set of device update rules by going to the Help and Support page on the Microsoft website and searching for "Phone Edition."</span></span> <span data-ttu-id="e0525-109">下载最新的更新包，并将文件解压缩到计算机上要从中上载更新的文件夹。</span><span class="sxs-lookup"><span data-stu-id="e0525-109">Download the latest update package and extract the files to a folder on the computer where the updates are to be uploaded.</span></span> <span data-ttu-id="e0525-110">解压缩文件后，可以使用 **Import-CsDeviceUpdate** cmdlet 导入解压缩后的 .CAB 文件（其名称为 UCUpdates.cab）中包含的设备更新规则。</span><span class="sxs-lookup"><span data-stu-id="e0525-110">After the files have been extracted, you can then use the **Import-CsDeviceUpdate** cmdlet to import the device update rules found in the extracted .CAB file (which will have the name UCUpdates.cab).</span></span> <span data-ttu-id="e0525-111">有关详细信息，请参阅[导入 CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="e0525-111">For details, see [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps).</span></span>
  
<span data-ttu-id="e0525-112">已导入设备更新规则后，可以使用**设备更新**页可以查看和管理这些规则为您的组织的设备。</span><span class="sxs-lookup"><span data-stu-id="e0525-112">After the device update rules have been imported, you can use the **Device Update** page to view and manage these rules for your organization's devices.</span></span>
  
> [!TIP]
> <span data-ttu-id="e0525-113">您可以测试固件更新，然后将更新提供给组织中使用的所有相关设备（假定测试成功）。</span><span class="sxs-lookup"><span data-stu-id="e0525-113">You can test the firmware updates and then, assuming the tests succeed, make the updates available to all the relevant devices used in the organization.</span></span> 
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="e0525-114">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="e0525-114">Tasks you can perform</span></span>

<span data-ttu-id="e0525-115">您可以在“**设备更新**”页上执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="e0525-115">You can perform the following tasks on the **Device Update** page:</span></span>
  
- <span data-ttu-id="e0525-116">批准列表中的设备更新。</span><span class="sxs-lookup"><span data-stu-id="e0525-116">Approve device updates in the list.</span></span>
    
- <span data-ttu-id="e0525-117">取消或恢复挂起的设备更新。</span><span class="sxs-lookup"><span data-stu-id="e0525-117">Cancel or restore pending device updates.</span></span>
    
- <span data-ttu-id="e0525-118">从列表删除设备更新。</span><span class="sxs-lookup"><span data-stu-id="e0525-118">Delete device updates from the list.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="e0525-119">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="e0525-119">UI Reference</span></span>

<span data-ttu-id="e0525-120">下表介绍了该页上的菜单、命令、字段和属性。</span><span class="sxs-lookup"><span data-stu-id="e0525-120">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="e0525-121">**编辑**可以使用此选项，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="e0525-121">**Edit** You can use this option to do the following:</span></span>
    
  - <span data-ttu-id="e0525-122">**选择全部**此选项在列表中选择设备的所有更新。</span><span class="sxs-lookup"><span data-stu-id="e0525-122">**Select All** This option selects all device updates in the list.</span></span>
    
  - <span data-ttu-id="e0525-123">**删除**此选项将删除所有选定的设备更新。</span><span class="sxs-lookup"><span data-stu-id="e0525-123">**Delete** This option deletes all selected device updates.</span></span>
    
- <span data-ttu-id="e0525-124">**操作**您可以从列表中选择一个或多个更新并执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e0525-124">**Action** You can select one or more updates in the list and take the following actions:</span></span>
    
  - <span data-ttu-id="e0525-125">**取消挂起的更新**此选项可防止所选的更新部署到您的组织的设备。</span><span class="sxs-lookup"><span data-stu-id="e0525-125">**Cancel pending updates** This option prevents the selected update from being deployed to your organization's devices.</span></span>
    
  - <span data-ttu-id="e0525-126">**批准**此选项允许所选的更新部署到您的组织的设备。</span><span class="sxs-lookup"><span data-stu-id="e0525-126">**Approve** This option allows the selected update to be deployed to your organization's devices.</span></span>
    
  - <span data-ttu-id="e0525-127">**还原**此选项允许在将其部署到您的组织的设备以前批准的更新</span><span class="sxs-lookup"><span data-stu-id="e0525-127">**Restore** This option allows a previously approved update to be deployed to your organization's devices</span></span>
    
- <span data-ttu-id="e0525-128">**刷新**您可以刷新列表来验证所有设备更新的状态。</span><span class="sxs-lookup"><span data-stu-id="e0525-128">**Refresh** You can refresh the list to verify the status of all device updates.</span></span>
    
<span data-ttu-id="e0525-129">设备更新 Web 服务的详细信息，请参阅规划文档中[查看软件更新您组织中的设备](http://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx)。</span><span class="sxs-lookup"><span data-stu-id="e0525-129">For details about Device Update Web service, see [View Software Updates for Devices in Your Organization](http://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx) in the Planning documentation.</span></span>
## <a name="see-also"></a><span data-ttu-id="e0525-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e0525-130">See also</span></span>

#### 

[<span data-ttu-id="e0525-131">导入 CsDeviceUpdate</span><span class="sxs-lookup"><span data-stu-id="e0525-131">Import-CsDeviceUpdate</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps)

