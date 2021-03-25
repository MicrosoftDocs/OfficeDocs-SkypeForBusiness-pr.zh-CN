---
title: 测试设备
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientDeviceTestMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: a1ea564c-f403-4f61-a36b-5a429708e7ca
ROBOTS: NOINDEX, NOFOLLOW
description: 可将测试设备添加到“测试设备”页，然后使用此设备验证新更新的功能，之后再将更新部署到生产设备。 可以在整个环境中或单个站点 (全局测试) 测试设备。 可通过测试设备的媒体访问控制 (MAC) 地址或序列号标识测试设备。 添加设备时，它将显示在 Skype for Business Server 控制面板的"测试设备"页上的列表中。
ms.openlocfilehash: a8f8183974556caf11873597425ebc156701ddbc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120261"
---
# <a name="test-device"></a><span data-ttu-id="af712-106">测试设备</span><span class="sxs-lookup"><span data-stu-id="af712-106">Test Device</span></span>

<span data-ttu-id="af712-107">可将测试设备添加到“测试设备”页，然后使用此设备验证新更新的功能，之后再将更新部署到生产设备。</span><span class="sxs-lookup"><span data-stu-id="af712-107">You can add a test device to the **Test Device** page and then use this device to verify the functionality of new updates before deploying the updates to production devices.</span></span> <span data-ttu-id="af712-108">可以在整个环境中或单个站点 (全局测试) 测试设备。</span><span class="sxs-lookup"><span data-stu-id="af712-108">You can test a device globally (throughout your entire environment) or within a single site.</span></span> <span data-ttu-id="af712-109">可通过测试设备的媒体访问控制 (MAC) 地址或序列号标识测试设备。</span><span class="sxs-lookup"><span data-stu-id="af712-109">You identify a test device by its Media Access Control (MAC) address or serial number.</span></span> <span data-ttu-id="af712-110">添加设备时，它将显示在 Skype for Business  Server 控制面板的"测试设备"页上的列表中。</span><span class="sxs-lookup"><span data-stu-id="af712-110">When you add a device, it appears in the list on the **Test Device** page of the Skype for Business Server Control Panel.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="af712-111">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="af712-111">Tasks you can perform</span></span>

<span data-ttu-id="af712-112">您可以在“测试设备”页上执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="af712-112">You can perform the following tasks on the **Test Device** page:</span></span>

- <span data-ttu-id="af712-113">在全局范围或为特定站点添加测试设备。</span><span class="sxs-lookup"><span data-stu-id="af712-113">Add a test device globally or for a particular site.</span></span>

- <span data-ttu-id="af712-114">修改现有测试设备的选项。</span><span class="sxs-lookup"><span data-stu-id="af712-114">Modify the options for an existing test device.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="af712-115">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="af712-115">UI Reference</span></span>

<span data-ttu-id="af712-116">下表介绍了该页上的菜单、命令、字段和属性。</span><span class="sxs-lookup"><span data-stu-id="af712-116">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="af712-117">**新建** 你可以添加具有以下作用域的新测试设备：</span><span class="sxs-lookup"><span data-stu-id="af712-117">**New** You can add a new test device with the following scope:</span></span>

  - <span data-ttu-id="af712-118">全局</span><span class="sxs-lookup"><span data-stu-id="af712-118">Global</span></span>

  - <span data-ttu-id="af712-119">Site</span><span class="sxs-lookup"><span data-stu-id="af712-119">Site</span></span>

- <span data-ttu-id="af712-120">**编辑** 你可以更改列表中的测试设备选项。</span><span class="sxs-lookup"><span data-stu-id="af712-120">**Edit** You can change the options of a test device in the list.</span></span> <span data-ttu-id="af712-121">使用此选项，可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="af712-121">Using this option, you can do the following:</span></span>

  - <span data-ttu-id="af712-122">**显示详细信息** 此选项将打开一个对话框，可在其中更改测试设备的选项。</span><span class="sxs-lookup"><span data-stu-id="af712-122">**Show details** This option opens a dialog box in which you can change the options for a test device.</span></span>

  - <span data-ttu-id="af712-123">**全选** 此选项选择列表中的所有测试设备。</span><span class="sxs-lookup"><span data-stu-id="af712-123">**Select All** This option selects all test devices in the list.</span></span>

  - <span data-ttu-id="af712-124">**删除** 此选项将删除所有选定的测试设备。</span><span class="sxs-lookup"><span data-stu-id="af712-124">**Delete** This option deletes all selected test devices.</span></span>

- <span data-ttu-id="af712-125">**刷新** 你可以刷新测试设备列表以验证所有测试设备的选项状态。</span><span class="sxs-lookup"><span data-stu-id="af712-125">**Refresh** You can refresh the test device list to verify the status of the options of all test devices.</span></span>

<span data-ttu-id="af712-126">有关测试设备的详细信息，请参阅操作文档中的[Add a Device to Test Update Functionality](/previous-versions/office/lync-server-2013/lync-server-2013-create-a-device-to-test-update-functionality)。</span><span class="sxs-lookup"><span data-stu-id="af712-126">For details about testing devices, see [Add a Device to Test Update Functionality](/previous-versions/office/lync-server-2013/lync-server-2013-create-a-device-to-test-update-functionality) in the Operations documentation.</span></span>
## <a name="see-also"></a><span data-ttu-id="af712-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="af712-127">See also</span></span>

[<span data-ttu-id="af712-128">测试设备：创建新的或编辑现有的</span><span class="sxs-lookup"><span data-stu-id="af712-128">Test Device: Create New or Edit Existing</span></span>](ms.lync.lscp.ClientDeviceTestEdit.md)

[<span data-ttu-id="af712-129">New-CsTestDevice</span><span class="sxs-lookup"><span data-stu-id="af712-129">New-CsTestDevice</span></span>](/powershell/module/skype/new-cstestdevice?view=skype-ps)

[<span data-ttu-id="af712-130">Set-CsTestDevice</span><span class="sxs-lookup"><span data-stu-id="af712-130">Set-CsTestDevice</span></span>](/powershell/module/skype/set-cstestdevice?view=skype-ps)

[<span data-ttu-id="af712-131">查看组织中设备的软件更新</span><span class="sxs-lookup"><span data-stu-id="af712-131">View Software Updates for Devices in Your Organization</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-view-software-updates-for-devices-in-your-organization)