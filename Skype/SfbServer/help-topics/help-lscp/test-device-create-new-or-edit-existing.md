---
title: 测试设备创建新的或编辑现有的
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
- ms.lync.lscp.ClientDeviceTestEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f9125dd-04b3-4a6d-9f41-4f19ddaf7a2d
description: 测试设备功能与设备更新功能结合使用。 可将测试设备添加到“测试设备”页，然后使用此设备验证新更新的功能，之后再将更新部署到生产设备。 可以在整个环境中或单个站点 (全局测试) 测试设备。 可通过测试设备的媒体访问控制 (MAC) 地址或序列号标识测试设备。 添加设备时，它将显示在 Skype for Business Server 控制面板的"测试设备"页上的列表中。
ms.openlocfilehash: 6a472923040dbf1101044a28667cb1358399f808
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099368"
---
# <a name="test-device-create-new-or-edit-existing"></a><span data-ttu-id="d02bc-107">测试设备：创建新的或编辑现有的</span><span class="sxs-lookup"><span data-stu-id="d02bc-107">Test Device: Create New or Edit Existing</span></span>

<span data-ttu-id="d02bc-108">测试设备功能与设备更新功能结合使用。</span><span class="sxs-lookup"><span data-stu-id="d02bc-108">The Test Device feature works in conjunction with the Device Update feature.</span></span> <span data-ttu-id="d02bc-109">可将测试设备添加到“测试设备”页，然后使用此设备验证新更新的功能，之后再将更新部署到生产设备。</span><span class="sxs-lookup"><span data-stu-id="d02bc-109">You can add a test device to the **Test Device** page and then use this device to verify the functionality of new updates before deploying the updates to production devices.</span></span> <span data-ttu-id="d02bc-110">可以在整个环境中或单个站点 (全局测试) 测试设备。</span><span class="sxs-lookup"><span data-stu-id="d02bc-110">You can test a device globally (throughout your entire environment) or within a single site.</span></span> <span data-ttu-id="d02bc-111">可通过测试设备的媒体访问控制 (MAC) 地址或序列号标识测试设备。</span><span class="sxs-lookup"><span data-stu-id="d02bc-111">You identify a test device by its Media Access Control (MAC) address or serial number.</span></span> <span data-ttu-id="d02bc-112">添加设备时，它将显示在 Skype for Business  Server 控制面板的"测试设备"页上的列表中。</span><span class="sxs-lookup"><span data-stu-id="d02bc-112">When you add a device, it appears in the list on the **Test Device** page of the Skype for Business Server Control Panel.</span></span>

## <a name="tasks-you-can-perform"></a><span data-ttu-id="d02bc-113">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="d02bc-113">Tasks you can perform</span></span>

<span data-ttu-id="d02bc-114">您可以在“新建测试设备”或“编辑测试设备”页上执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="d02bc-114">You can perform the following tasks on the **New Test Device** or **Edit Test Device** page:</span></span>

- <span data-ttu-id="d02bc-115">添加新的测试设备。</span><span class="sxs-lookup"><span data-stu-id="d02bc-115">Add a new test device.</span></span>

- <span data-ttu-id="d02bc-116">修改现有测试设备的属性。</span><span class="sxs-lookup"><span data-stu-id="d02bc-116">Modify the properties of an existing test device.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="d02bc-117">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="d02bc-117">UI Reference</span></span>

<span data-ttu-id="d02bc-118">下表介绍了该页上的菜单、命令、字段和属性。</span><span class="sxs-lookup"><span data-stu-id="d02bc-118">The following lists describe the menus, commands, fields, and properties on the page.</span></span>

- <span data-ttu-id="d02bc-119">**范围** 标识测试 (全局) 站点范围。</span><span class="sxs-lookup"><span data-stu-id="d02bc-119">**Scope** Identifies the scope (Global or Site) of the test device.</span></span>

- <span data-ttu-id="d02bc-120">**名称** 你可以添加或修改测试设备的名称。</span><span class="sxs-lookup"><span data-stu-id="d02bc-120">**Name** You can add or modify the name of the test device.</span></span>

- <span data-ttu-id="d02bc-121">**设备名称** 你可以添加或修改测试设备的名称。</span><span class="sxs-lookup"><span data-stu-id="d02bc-121">**Device name** You can add or modify the name of the test device.</span></span>

- <span data-ttu-id="d02bc-122">**标识符类型** 通过选择下列选项之一，可以选择用于标识设备的方法：</span><span class="sxs-lookup"><span data-stu-id="d02bc-122">**Identifier type** You can select the method to use to identify the device by selecting one of the following:</span></span>

  - <span data-ttu-id="d02bc-123">**MAC 地址**</span><span class="sxs-lookup"><span data-stu-id="d02bc-123">**MAC address**</span></span>

  - <span data-ttu-id="d02bc-124">**序列号**</span><span class="sxs-lookup"><span data-stu-id="d02bc-124">**Serial number**</span></span>

- <span data-ttu-id="d02bc-125">**唯一标识符** 可以键入设备的 MAC 地址或序列号。</span><span class="sxs-lookup"><span data-stu-id="d02bc-125">**Unique identifier** You can type the MAC address or serial number of the device.</span></span>

<span data-ttu-id="d02bc-126">有关测试设备的详细信息，请参阅操作文档中的[Add a Device to Test Update Functionality](/previous-versions/office/lync-server-2013/lync-server-2013-create-a-device-to-test-update-functionality)。</span><span class="sxs-lookup"><span data-stu-id="d02bc-126">For details about testing devices, see [Add a Device to Test Update Functionality](/previous-versions/office/lync-server-2013/lync-server-2013-create-a-device-to-test-update-functionality) in the Operations documentation.</span></span>
## <a name="see-also"></a><span data-ttu-id="d02bc-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d02bc-127">See also</span></span>

[<span data-ttu-id="d02bc-128">测试设备</span><span class="sxs-lookup"><span data-stu-id="d02bc-128">Test Device</span></span>](test-device.md)

[<span data-ttu-id="d02bc-129">New-CsTestDevice</span><span class="sxs-lookup"><span data-stu-id="d02bc-129">New-CsTestDevice</span></span>](/powershell/module/skype/new-cstestdevice?view=skype-ps)

[<span data-ttu-id="d02bc-130">Set-CsTestDevice</span><span class="sxs-lookup"><span data-stu-id="d02bc-130">Set-CsTestDevice</span></span>](/powershell/module/skype/set-cstestdevice?view=skype-ps)

[<span data-ttu-id="d02bc-131">查看组织中设备的软件更新</span><span class="sxs-lookup"><span data-stu-id="d02bc-131">View Software Updates for Devices in Your Organization</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-view-software-updates-for-devices-in-your-organization)