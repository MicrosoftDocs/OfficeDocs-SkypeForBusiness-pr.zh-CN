---
title: 设备更新
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientDeviceUpdateMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6f6b7f73-f8f5-41dc-9e2a-727baaaa828b
description: Microsoft 会定期发布 Skype for Business Phone Edition 的新设备固件更新集，你可以将其导入服务器并分发给用户。 可以通过访问 Microsoft 网站的"帮助和支持"页并搜索Phone Edition 来获取一组最新的设备更新规则。下载最新的更新程序包，将文件解压缩到要上载更新的计算机上的文件夹。 解压缩文件后，可以使用 Import-CsDeviceUpdate cmdlet 导入解压缩后的 .CAB 文件（其名称为 UCUpdates.cab）中包含的设备更新规则。 有关详细信息，请参阅 Import-CsDeviceUpdate。
ms.openlocfilehash: e98d414c66c6d4400d1bf2de88158859e57b93a9
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51115270"
---
# <a name="device-update"></a><span data-ttu-id="6d991-106">设备更新</span><span class="sxs-lookup"><span data-stu-id="6d991-106">Device Update</span></span>

<span data-ttu-id="6d991-107">Microsoft 会定期发布 Skype for Business Phone Edition 的新设备固件更新集，你可以将其导入服务器并分发给用户。</span><span class="sxs-lookup"><span data-stu-id="6d991-107">Microsoft periodically releases a new set of device firmware updates for Skype for Business Phone Edition, which you can import to your servers and distribute to users.</span></span> <span data-ttu-id="6d991-108">可通过转至 Microsoft 网站上的帮助和支持页并搜索“Phone Edition”来获取一组最新的设备更新规则。</span><span class="sxs-lookup"><span data-stu-id="6d991-108">You can obtain the latest set of device update rules by going to the Help and Support page on the Microsoft website and searching for "Phone Edition."</span></span> <span data-ttu-id="6d991-109">下载最新的更新包，并将文件解压缩到计算机上要从中上载更新的文件夹。</span><span class="sxs-lookup"><span data-stu-id="6d991-109">Download the latest update package and extract the files to a folder on the computer where the updates are to be uploaded.</span></span> <span data-ttu-id="6d991-110">解压缩文件后，可以使用 **Import-CsDeviceUpdate** cmdlet 导入解压缩后的 .CAB 文件（其名称为 UCUpdates.cab）中包含的设备更新规则。</span><span class="sxs-lookup"><span data-stu-id="6d991-110">After the files have been extracted, you can then use the **Import-CsDeviceUpdate** cmdlet to import the device update rules found in the extracted .CAB file (which will have the name UCUpdates.cab).</span></span> <span data-ttu-id="6d991-111">有关详细信息，请参阅 [Import-CsDeviceUpdate](/powershell/module/skype/import-csdeviceupdate?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="6d991-111">For details, see [Import-CsDeviceUpdate](/powershell/module/skype/import-csdeviceupdate?view=skype-ps).</span></span>

<span data-ttu-id="6d991-112">导入设备更新规则后，可以使用"设备更新"页查看和管理组织的设备的这些规则。</span><span class="sxs-lookup"><span data-stu-id="6d991-112">After the device update rules have been imported, you can use the **Device Update** page to view and manage these rules for your organization's devices.</span></span>

> [!TIP]
> <span data-ttu-id="6d991-113">您可以测试固件更新，然后将更新提供给组织中使用的所有相关设备（假定测试成功）。</span><span class="sxs-lookup"><span data-stu-id="6d991-113">You can test the firmware updates and then, assuming the tests succeed, make the updates available to all the relevant devices used in the organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="6d991-114">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="6d991-114">Tasks you can perform</span></span>

<span data-ttu-id="6d991-115">您可以在“设备更新”页上执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="6d991-115">You can perform the following tasks on the **Device Update** page:</span></span>

- <span data-ttu-id="6d991-116">批准列表中的设备更新。</span><span class="sxs-lookup"><span data-stu-id="6d991-116">Approve device updates in the list.</span></span>

- <span data-ttu-id="6d991-117">取消或恢复挂起的设备更新。</span><span class="sxs-lookup"><span data-stu-id="6d991-117">Cancel or restore pending device updates.</span></span>

- <span data-ttu-id="6d991-118">从列表删除设备更新。</span><span class="sxs-lookup"><span data-stu-id="6d991-118">Delete device updates from the list.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="6d991-119">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="6d991-119">UI Reference</span></span>

<span data-ttu-id="6d991-120">下表介绍了该页上的菜单、命令、字段和属性。</span><span class="sxs-lookup"><span data-stu-id="6d991-120">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="6d991-121">**编辑** 可以使用此选项执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6d991-121">**Edit** You can use this option to do the following:</span></span>

  - <span data-ttu-id="6d991-122">**全选** 此选项选择列表中的所有设备更新。</span><span class="sxs-lookup"><span data-stu-id="6d991-122">**Select All** This option selects all device updates in the list.</span></span>

  - <span data-ttu-id="6d991-123">**删除** 此选项将删除所有选定的设备更新。</span><span class="sxs-lookup"><span data-stu-id="6d991-123">**Delete** This option deletes all selected device updates.</span></span>

- <span data-ttu-id="6d991-124">**操作** 可以选择列表中的一个或多个更新，并执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6d991-124">**Action** You can select one or more updates in the list and take the following actions:</span></span>

  - <span data-ttu-id="6d991-125">**取消挂起的更新** 此选项可阻止将所选更新部署到组织的设备。</span><span class="sxs-lookup"><span data-stu-id="6d991-125">**Cancel pending updates** This option prevents the selected update from being deployed to your organization's devices.</span></span>

  - <span data-ttu-id="6d991-126">**批准** 此选项允许将所选更新部署到组织的设备。</span><span class="sxs-lookup"><span data-stu-id="6d991-126">**Approve** This option allows the selected update to be deployed to your organization's devices.</span></span>

  - <span data-ttu-id="6d991-127">**还原** 此选项允许将以前批准的更新部署到组织的设备</span><span class="sxs-lookup"><span data-stu-id="6d991-127">**Restore** This option allows a previously approved update to be deployed to your organization's devices</span></span>

- <span data-ttu-id="6d991-128">**刷新** 你可以刷新列表以验证所有设备更新的状态。</span><span class="sxs-lookup"><span data-stu-id="6d991-128">**Refresh** You can refresh the list to verify the status of all device updates.</span></span>

<span data-ttu-id="6d991-129">有关设备更新 Web 服务的详细信息，请参阅规划文档中的[View Software Updates for Devices in Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-view-software-updates-for-devices-in-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="6d991-129">For details about Device Update Web service, see [View Software Updates for Devices in Your Organization](/previous-versions/office/lync-server-2013/lync-server-2013-view-software-updates-for-devices-in-your-organization) in the Planning documentation.</span></span>
## <a name="see-also"></a><span data-ttu-id="6d991-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6d991-130">See also</span></span>

[<span data-ttu-id="6d991-131">Import-CsDeviceUpdate</span><span class="sxs-lookup"><span data-stu-id="6d991-131">Import-CsDeviceUpdate</span></span>](/powershell/module/skype/import-csdeviceupdate?view=skype-ps)