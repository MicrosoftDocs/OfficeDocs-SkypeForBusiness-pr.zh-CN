---
title: 设备更新
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceUpdateMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6f6b7f73-f8f5-41dc-9e2a-727baaaa828b
description: Microsoft 定期为 Skype for business Phone Edition 发布一组新的设备固件更新, 您可以将其导入到服务器并分发给用户。 通过转到 Microsoft 网站上的 "帮助和支持" 页面并搜索 forPhone 版本, 你可以获取最新的设备更新规则集。下载最新的更新程序包, 并将文件解压缩到要上载更新的计算机上的某个文件夹中。 解压缩文件后，可以使用 Import-CsDeviceUpdate cmdlet 导入解压缩后的 .CAB 文件（其名称为 UCUpdates.cab）中包含的设备更新规则。 有关详细信息, 请参阅导入-CsDeviceUpdate。
ms.openlocfilehash: b387a24d88ab0b65c3df43a8ca5dd25d582a4827
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34285923"
---
# <a name="device-update"></a><span data-ttu-id="28aab-106">设备更新</span><span class="sxs-lookup"><span data-stu-id="28aab-106">Device Update</span></span>

<span data-ttu-id="28aab-107">Microsoft 定期为 Skype for business Phone Edition 发布一组新的设备固件更新, 您可以将其导入到服务器并分发给用户。</span><span class="sxs-lookup"><span data-stu-id="28aab-107">Microsoft periodically releases a new set of device firmware updates for Skype for Business Phone Edition, which you can import to your servers and distribute to users.</span></span> <span data-ttu-id="28aab-108">可通过转至 Microsoft 网站上的帮助和支持页并搜索“Phone Edition”来获取一组最新的设备更新规则。</span><span class="sxs-lookup"><span data-stu-id="28aab-108">You can obtain the latest set of device update rules by going to the Help and Support page on the Microsoft website and searching for "Phone Edition."</span></span> <span data-ttu-id="28aab-109">下载最新的更新包，并将文件解压缩到计算机上要从中上载更新的文件夹。</span><span class="sxs-lookup"><span data-stu-id="28aab-109">Download the latest update package and extract the files to a folder on the computer where the updates are to be uploaded.</span></span> <span data-ttu-id="28aab-110">解压缩文件后，可以使用 **Import-CsDeviceUpdate** cmdlet 导入解压缩后的 .CAB 文件（其名称为 UCUpdates.cab）中包含的设备更新规则。</span><span class="sxs-lookup"><span data-stu-id="28aab-110">After the files have been extracted, you can then use the **Import-CsDeviceUpdate** cmdlet to import the device update rules found in the extracted .CAB file (which will have the name UCUpdates.cab).</span></span> <span data-ttu-id="28aab-111">有关详细信息, 请参阅[导入-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="28aab-111">For details, see [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps).</span></span>

<span data-ttu-id="28aab-112">导入设备更新规则后, 您可以使用 "**设备更新**" 页面查看和管理组织设备的这些规则。</span><span class="sxs-lookup"><span data-stu-id="28aab-112">After the device update rules have been imported, you can use the **Device Update** page to view and manage these rules for your organization's devices.</span></span>

> [!TIP]
> <span data-ttu-id="28aab-113">您可以测试固件更新，然后将更新提供给组织中使用的所有相关设备（假定测试成功）。</span><span class="sxs-lookup"><span data-stu-id="28aab-113">You can test the firmware updates and then, assuming the tests succeed, make the updates available to all the relevant devices used in the organization.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="28aab-114">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="28aab-114">Tasks you can perform</span></span>

<span data-ttu-id="28aab-115">您可以在“**设备更新**”页上执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="28aab-115">You can perform the following tasks on the **Device Update** page:</span></span>

- <span data-ttu-id="28aab-116">批准列表中的设备更新。</span><span class="sxs-lookup"><span data-stu-id="28aab-116">Approve device updates in the list.</span></span>

- <span data-ttu-id="28aab-117">取消或恢复挂起的设备更新。</span><span class="sxs-lookup"><span data-stu-id="28aab-117">Cancel or restore pending device updates.</span></span>

- <span data-ttu-id="28aab-118">从列表删除设备更新。</span><span class="sxs-lookup"><span data-stu-id="28aab-118">Delete device updates from the list.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="28aab-119">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="28aab-119">UI Reference</span></span>

<span data-ttu-id="28aab-120">下表介绍了该页上的菜单、命令、字段和属性。</span><span class="sxs-lookup"><span data-stu-id="28aab-120">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="28aab-121">**编辑**可使用此选项执行下列操作:</span><span class="sxs-lookup"><span data-stu-id="28aab-121">**Edit** You can use this option to do the following:</span></span>

  - <span data-ttu-id="28aab-122">**全选**此选项将选择列表中的所有设备更新。</span><span class="sxs-lookup"><span data-stu-id="28aab-122">**Select All** This option selects all device updates in the list.</span></span>

  - <span data-ttu-id="28aab-123">**Delete**此选项将删除所有选定的设备更新。</span><span class="sxs-lookup"><span data-stu-id="28aab-123">**Delete** This option deletes all selected device updates.</span></span>

- <span data-ttu-id="28aab-124">**操作**可以在列表中选择一个或多个更新, 并执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="28aab-124">**Action** You can select one or more updates in the list and take the following actions:</span></span>

  - <span data-ttu-id="28aab-125">**取消挂起的更新**此选项可防止将所选更新部署到你的组织的设备。</span><span class="sxs-lookup"><span data-stu-id="28aab-125">**Cancel pending updates** This option prevents the selected update from being deployed to your organization's devices.</span></span>

  - <span data-ttu-id="28aab-126">**批准**此选项允许将所选更新部署到你的组织的设备。</span><span class="sxs-lookup"><span data-stu-id="28aab-126">**Approve** This option allows the selected update to be deployed to your organization's devices.</span></span>

  - <span data-ttu-id="28aab-127">**还原**此选项允许将以前批准的更新部署到你的组织的设备</span><span class="sxs-lookup"><span data-stu-id="28aab-127">**Restore** This option allows a previously approved update to be deployed to your organization's devices</span></span>

- <span data-ttu-id="28aab-128">**刷新**你可以刷新列表以验证所有设备更新的状态。</span><span class="sxs-lookup"><span data-stu-id="28aab-128">**Refresh** You can refresh the list to verify the status of all device updates.</span></span>

<span data-ttu-id="28aab-129">有关设备更新 Web 服务的详细信息，请参阅规划文档中的[View Software Updates for Devices in Your Organization](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx)。</span><span class="sxs-lookup"><span data-stu-id="28aab-129">For details about Device Update Web service, see [View Software Updates for Devices in Your Organization](https://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx) in the Planning documentation.</span></span>
## <a name="see-also"></a><span data-ttu-id="28aab-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="28aab-130">See also</span></span>

[<span data-ttu-id="28aab-131">Import-CsDeviceUpdate</span><span class="sxs-lookup"><span data-stu-id="28aab-131">Import-CsDeviceUpdate</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps)
