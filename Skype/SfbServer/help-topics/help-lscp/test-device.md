---
title: 测试设备
ms.author: laurawi
author: LauraWi
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceTestMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a1ea564c-f403-4f61-a36b-5a429708e7ca
description: 可以测试设备添加到测试设备页面，并将此设备来验证之前将更新部署到生产设备进行更新的功能。 可以在全局范围（在整个环境中）或在单个站点中测试设备。 可通过测试设备的媒体访问控制 (MAC) 地址或序列号标识测试设备。 当您添加一个设备时，似乎 Skype 的测试设备页上的列表中的业务服务器的控制面板。
ms.openlocfilehash: de08a562695af309e795b0ded98c66ea738d0183
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="test-device"></a><span data-ttu-id="f3233-106">测试设备</span><span class="sxs-lookup"><span data-stu-id="f3233-106">Test Device</span></span>
 
<span data-ttu-id="f3233-107">可将测试设备添加到“**测试设备**”页，然后使用此设备验证新更新的功能，之后再将更新部署到生产设备。</span><span class="sxs-lookup"><span data-stu-id="f3233-107">You can add a test device to the **Test Device** page and then use this device to verify the functionality of new updates before deploying the updates to production devices.</span></span> <span data-ttu-id="f3233-108">可以在全局范围（在整个环境中）或在单个站点中测试设备。</span><span class="sxs-lookup"><span data-stu-id="f3233-108">You can test a device globally (throughout your entire environment) or within a single site.</span></span> <span data-ttu-id="f3233-109">可通过测试设备的媒体访问控制 (MAC) 地址或序列号标识测试设备。</span><span class="sxs-lookup"><span data-stu-id="f3233-109">You identify a test device by its Media Access Control (MAC) address or serial number.</span></span> <span data-ttu-id="f3233-110">当您添加一个设备时，似乎 Skype 的**测试设备**页上的列表中的业务服务器的控制面板。</span><span class="sxs-lookup"><span data-stu-id="f3233-110">When you add a device, it appears in the list on the **Test Device** page of the Skype for Business Server Control Panel.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="f3233-111">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="f3233-111">Tasks you can perform</span></span>

<span data-ttu-id="f3233-112">在**测试设备**页，可以执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="f3233-112">You can perform the following tasks on the **Test Device** page:</span></span>
  
- <span data-ttu-id="f3233-113">在全局范围内或针对某一特定站点添加测试设备。</span><span class="sxs-lookup"><span data-stu-id="f3233-113">Add a test device globally or for a particular site.</span></span>
    
- <span data-ttu-id="f3233-114">修改现有的测试设备的选项。</span><span class="sxs-lookup"><span data-stu-id="f3233-114">Modify the options for an existing test device.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="f3233-115">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="f3233-115">UI Reference</span></span>

<span data-ttu-id="f3233-116">下表介绍了该页上的菜单、命令、字段和属性。</span><span class="sxs-lookup"><span data-stu-id="f3233-116">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="f3233-117">**新**您可以添加新的测试设备具有下列作用：</span><span class="sxs-lookup"><span data-stu-id="f3233-117">**New** You can add a new test device with the following scope:</span></span>
    
  - <span data-ttu-id="f3233-118">全局</span><span class="sxs-lookup"><span data-stu-id="f3233-118">Global</span></span>
    
  - <span data-ttu-id="f3233-119">站点</span><span class="sxs-lookup"><span data-stu-id="f3233-119">Site</span></span>
    
- <span data-ttu-id="f3233-120">**编辑**您可以更改列表中的测试设备的选项。</span><span class="sxs-lookup"><span data-stu-id="f3233-120">**Edit** You can change the options of a test device in the list.</span></span> <span data-ttu-id="f3233-121">使用此选项，可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f3233-121">Using this option, you can do the following:</span></span>
    
  - <span data-ttu-id="f3233-122">**显示详细信息**此选项将打开一个对话框，您可以在其中更改测试设备的选项。</span><span class="sxs-lookup"><span data-stu-id="f3233-122">**Show details** This option opens a dialog box in which you can change the options for a test device.</span></span>
    
  - <span data-ttu-id="f3233-123">**选择全部**此选项在列表中选择所有的测试设备。</span><span class="sxs-lookup"><span data-stu-id="f3233-123">**Select All** This option selects all test devices in the list.</span></span>
    
  - <span data-ttu-id="f3233-124">**删除**此选项将删除所有选定的测试设备。</span><span class="sxs-lookup"><span data-stu-id="f3233-124">**Delete** This option deletes all selected test devices.</span></span>
    
- <span data-ttu-id="f3233-125">**刷新**您可以刷新测试设备列表来验证所有的测试设备的选项的状态。</span><span class="sxs-lookup"><span data-stu-id="f3233-125">**Refresh** You can refresh the test device list to verify the status of the options of all test devices.</span></span>
    
<span data-ttu-id="f3233-126">测试设备的详细信息，请参阅操作文档中[将设备添加到测试更新功能](http://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx)。</span><span class="sxs-lookup"><span data-stu-id="f3233-126">For details about testing devices, see [Add a Device to Test Update Functionality](http://technet.microsoft.com/library/ce509fd1-17b3-4b78-b269-fe5d06fe2e1d.aspx) in the Operations documentation.</span></span>
## <a name="see-also"></a><span data-ttu-id="f3233-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f3233-127">See also</span></span>

#### 

[<span data-ttu-id="f3233-128">创建新模板或编辑现有的测试设备：</span><span class="sxs-lookup"><span data-stu-id="f3233-128">Test Device: Create New or Edit Existing</span></span>](test-device-create-new-or-edit-existing.md)
#### 

[<span data-ttu-id="f3233-129">新 CsTestDevice</span><span class="sxs-lookup"><span data-stu-id="f3233-129">New-CsTestDevice</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cstestdevice?view=skype-ps)
  
[<span data-ttu-id="f3233-130">一组 CsTestDevice</span><span class="sxs-lookup"><span data-stu-id="f3233-130">Set-CsTestDevice</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cstestdevice?view=skype-ps)
  
[<span data-ttu-id="f3233-131">查看软件更新为您的组织中的设备的</span><span class="sxs-lookup"><span data-stu-id="f3233-131">View Software Updates for Devices in Your Organization</span></span>](http://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx)

