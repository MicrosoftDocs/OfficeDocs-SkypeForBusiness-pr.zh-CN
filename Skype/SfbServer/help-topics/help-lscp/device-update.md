---
title: 设备更新
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceUpdateMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6f6b7f73-f8f5-41dc-9e2a-727baaaa828b
description: Microsoft 会定期会的 Skype 的一组新的设备固件更新业务 Phone edition，您可以导入到您的服务器，并将分发给用户发布。 您可以通过 Microsoft 网站上转到帮助和支持页上，并搜索 forPhone Edition.Download 的最新的更新程序包获取最新的设备更新规则集，并将文件提取到的文件夹的计算机上，更新要上载。 解压缩文件后，可以使用 Import-CsDeviceUpdate cmdlet 导入解压缩后的 .CAB 文件（其名称为 UCUpdates.cab）中包含的设备更新规则。 有关详细信息，请参阅 Import-csdeviceupdate。
ms.openlocfilehash: 9e3d553357131c2e0f9e0b0bcef1329f5d2a4104
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33902816"
---
# <a name="device-update"></a><span data-ttu-id="d1131-106">设备更新</span><span class="sxs-lookup"><span data-stu-id="d1131-106">Device Update</span></span>

<span data-ttu-id="d1131-107">Microsoft 会定期会的 Skype 的一组新的设备固件更新业务 Phone edition，您可以导入到您的服务器，并将分发给用户发布。</span><span class="sxs-lookup"><span data-stu-id="d1131-107">Microsoft periodically releases a new set of device firmware updates for Skype for Business Phone Edition, which you can import to your servers and distribute to users.</span></span> <span data-ttu-id="d1131-108">可通过转至 Microsoft 网站上的帮助和支持页并搜索“Phone Edition”来获取一组最新的设备更新规则。</span><span class="sxs-lookup"><span data-stu-id="d1131-108">You can obtain the latest set of device update rules by going to the Help and Support page on the Microsoft website and searching for "Phone Edition."</span></span> <span data-ttu-id="d1131-109">下载最新的更新包，并将文件解压缩到计算机上要从中上载更新的文件夹。</span><span class="sxs-lookup"><span data-stu-id="d1131-109">Download the latest update package and extract the files to a folder on the computer where the updates are to be uploaded.</span></span> <span data-ttu-id="d1131-110">解压缩文件后，可以使用 **Import-CsDeviceUpdate** cmdlet 导入解压缩后的 .CAB 文件（其名称为 UCUpdates.cab）中包含的设备更新规则。</span><span class="sxs-lookup"><span data-stu-id="d1131-110">After the files have been extracted, you can then use the **Import-CsDeviceUpdate** cmdlet to import the device update rules found in the extracted .CAB file (which will have the name UCUpdates.cab).</span></span> <span data-ttu-id="d1131-111">有关详细信息，请参阅[Import-csdeviceupdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="d1131-111">For details, see [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps).</span></span>

<span data-ttu-id="d1131-112">已导入设备更新规则之后，您可以使用**设备更新**页上查看和管理组织的设备的各个规则。</span><span class="sxs-lookup"><span data-stu-id="d1131-112">After the device update rules have been imported, you can use the **Device Update** page to view and manage these rules for your organization's devices.</span></span>

> [!TIP]
> <span data-ttu-id="d1131-113">您可以测试固件更新，然后将更新提供给组织中使用的所有相关设备（假定测试成功）。</span><span class="sxs-lookup"><span data-stu-id="d1131-113">You can test the firmware updates and then, assuming the tests succeed, make the updates available to all the relevant devices used in the organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="d1131-114">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="d1131-114">Tasks you can perform</span></span>

<span data-ttu-id="d1131-115">您可以在“**设备更新**”页上执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="d1131-115">You can perform the following tasks on the **Device Update** page:</span></span>

- <span data-ttu-id="d1131-116">批准列表中的设备更新。</span><span class="sxs-lookup"><span data-stu-id="d1131-116">Approve device updates in the list.</span></span>

- <span data-ttu-id="d1131-117">取消或恢复挂起的设备更新。</span><span class="sxs-lookup"><span data-stu-id="d1131-117">Cancel or restore pending device updates.</span></span>

- <span data-ttu-id="d1131-118">从列表删除设备更新。</span><span class="sxs-lookup"><span data-stu-id="d1131-118">Delete device updates from the list.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="d1131-119">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="d1131-119">UI Reference</span></span>

<span data-ttu-id="d1131-120">下表介绍了该页上的菜单、命令、字段和属性。</span><span class="sxs-lookup"><span data-stu-id="d1131-120">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="d1131-121">**编辑**您可以使用此选项可执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="d1131-121">**Edit** You can use this option to do the following:</span></span>

  - <span data-ttu-id="d1131-122">**选择全部**此选项可选择列表中所有设备更新。</span><span class="sxs-lookup"><span data-stu-id="d1131-122">**Select All** This option selects all device updates in the list.</span></span>

  - <span data-ttu-id="d1131-123">**删除**此选项可删除所有选定的设备更新。</span><span class="sxs-lookup"><span data-stu-id="d1131-123">**Delete** This option deletes all selected device updates.</span></span>

- <span data-ttu-id="d1131-124">**操作**您可以在列表中选择一个或多个更新并执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d1131-124">**Action** You can select one or more updates in the list and take the following actions:</span></span>

  - <span data-ttu-id="d1131-125">**取消挂起更新**此选项阻止向组织设备部署所选的更新。</span><span class="sxs-lookup"><span data-stu-id="d1131-125">**Cancel pending updates** This option prevents the selected update from being deployed to your organization's devices.</span></span>

  - <span data-ttu-id="d1131-126">**批准**此选项允许向组织设备部署所选的更新。</span><span class="sxs-lookup"><span data-stu-id="d1131-126">**Approve** This option allows the selected update to be deployed to your organization's devices.</span></span>

  - <span data-ttu-id="d1131-127">**还原**此选项允许向组织设备部署之前批准的更新</span><span class="sxs-lookup"><span data-stu-id="d1131-127">**Restore** This option allows a previously approved update to be deployed to your organization's devices</span></span>

- <span data-ttu-id="d1131-128">**刷新**您可以刷新列表以验证所有设备更新的状态。</span><span class="sxs-lookup"><span data-stu-id="d1131-128">**Refresh** You can refresh the list to verify the status of all device updates.</span></span>

<span data-ttu-id="d1131-129">有关设备更新 Web 服务的详细信息，请参阅规划文档中的[View Software Updates for Devices in Your Organization](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx)。</span><span class="sxs-lookup"><span data-stu-id="d1131-129">For details about Device Update Web service, see [View Software Updates for Devices in Your Organization](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx) in the Planning documentation.</span></span>
## <a name="see-also"></a><span data-ttu-id="d1131-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d1131-130">See also</span></span>

[<span data-ttu-id="d1131-131">Import-csdeviceupdate</span><span class="sxs-lookup"><span data-stu-id="d1131-131">Import-CsDeviceUpdate</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps)
