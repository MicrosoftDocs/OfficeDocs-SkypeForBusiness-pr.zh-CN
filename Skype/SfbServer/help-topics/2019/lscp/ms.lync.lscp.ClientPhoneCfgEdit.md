---
title: 设备配置 创建新的或编辑现有的
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.ClientPhoneCfgEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: aac152bf-80e9-408a-9dbb-60d0843484ab
ROBOTS: NOINDEX, NOFOLLOW
description: 在"新建设备配置"或"编辑设备配置"页上，可以创建或修改用于管理 Skype for Business Phone Edition 的设置集合。 通过这些设置，您可以配置以下内容：所需的安全性模式、设备日志记录级别、语音服务质量 (QoS) 设置以及在指定的非活动时间后电话是否应自动锁住。
ms.openlocfilehash: 47805db474169631b722cbd8e2af95ec42bc8fa6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100558"
---
# <a name="device-configuration-create-new-or-edit-existing"></a><span data-ttu-id="f9271-104">设备配置：创建新的或编辑现有的</span><span class="sxs-lookup"><span data-stu-id="f9271-104">Device Configuration: Create New or Edit Existing</span></span>
 
<span data-ttu-id="f9271-105">在" **新建设备配置** " **或** "编辑设备配置"页上，可以创建或修改用于管理 Skype for Business Phone Edition 的设置集合。</span><span class="sxs-lookup"><span data-stu-id="f9271-105">On the **New Device Configuration** or **Edit Device Configuration** page, you can create or modify a collection of settings used to manage Skype for Business Phone Edition.</span></span> <span data-ttu-id="f9271-106">通过这些设置，您可以配置以下内容：所需的安全性模式、设备日志记录级别、语音服务质量 (QoS) 设置以及在指定的非活动时间后电话是否应自动锁住。</span><span class="sxs-lookup"><span data-stu-id="f9271-106">These settings enable you to configure such things as the required security mode, device logging level, Voice Quality of Service (QoS) settings, and whether or not phones should automatically lock after a specified period of inactivity.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="f9271-107">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="f9271-107">Tasks you can perform</span></span>

<span data-ttu-id="f9271-108">您可以在“新建设备配置”或“编辑设备配置”页上执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="f9271-108">You can perform the following tasks on the **New Device Configuration** or **Edit Device Configuration** page:</span></span>
  
- <span data-ttu-id="f9271-109">添加新的设备配置。</span><span class="sxs-lookup"><span data-stu-id="f9271-109">Add a new device configuration.</span></span>
    
- <span data-ttu-id="f9271-110">修改现有设备配置的属性。</span><span class="sxs-lookup"><span data-stu-id="f9271-110">Modify the properties of an existing device configuration.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="f9271-111">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="f9271-111">UI Reference</span></span>

<span data-ttu-id="f9271-112">下表介绍了该页上的菜单、命令、字段和属性。</span><span class="sxs-lookup"><span data-stu-id="f9271-112">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="f9271-113">**范围** 标识设备 (全局) 站点范围。</span><span class="sxs-lookup"><span data-stu-id="f9271-113">**Scope** Identifies the scope (Global or Site) of the device configuration.</span></span>
    
- <span data-ttu-id="f9271-114">**名称** 你可以添加或修改设备配置的名称。</span><span class="sxs-lookup"><span data-stu-id="f9271-114">**Name** You can add or modify the name of the device configuration.</span></span>
    
- <span data-ttu-id="f9271-115">**SIP 安全性** 你可以为 Skype for Business Phone Edition 设备配置传输和身份验证要求。</span><span class="sxs-lookup"><span data-stu-id="f9271-115">**SIP security** You can configure transport and authentication requirements for Skype for Business Phone Edition devices.</span></span> <span data-ttu-id="f9271-116">可以从以下选项中进行选择：</span><span class="sxs-lookup"><span data-stu-id="f9271-116">You can select from the following options:</span></span>
    
  - <span data-ttu-id="f9271-117">**低** 允许任何类型的授权或传输。</span><span class="sxs-lookup"><span data-stu-id="f9271-117">**Low** Allow any type of authorization or transport.</span></span>
    
  - <span data-ttu-id="f9271-118">**中** 用户身份验证需要 NTLM 或 Kerberos。</span><span class="sxs-lookup"><span data-stu-id="f9271-118">**Medium** NTLM or Kerberos is required for user authentication.</span></span>
    
  - <span data-ttu-id="f9271-119">**高** 用户身份验证需要 NTLM 或 Kerberos，SIP 连接需要 TLS。</span><span class="sxs-lookup"><span data-stu-id="f9271-119">**High** NTLM or Kerberos is required for user authentication and TLS is required for SIP connections.</span></span>
    
- <span data-ttu-id="f9271-120">**日志记录级别** 可以在 UC 设备上启用日志记录。</span><span class="sxs-lookup"><span data-stu-id="f9271-120">**Logging level** You can enable logging on the UC device.</span></span> <span data-ttu-id="f9271-121">有效值为：Off;低;中;高。</span><span class="sxs-lookup"><span data-stu-id="f9271-121">Valid values are: Off; Low; Medium; and High.</span></span> <span data-ttu-id="f9271-122">默认值为 Off。</span><span class="sxs-lookup"><span data-stu-id="f9271-122">The default value is Off.</span></span>
    
- <span data-ttu-id="f9271-123">**QoS (语音服务质量)** 你可以指定分配给来自 Skype for Business Phone Edition 设备的语音流量的 DSCP 值。</span><span class="sxs-lookup"><span data-stu-id="f9271-123">**Voice Quality of Service (QoS)** You can specify the DSCP value assigned to voice traffic emanating from a Skype for Business Phone Edition device.</span></span> <span data-ttu-id="f9271-124">默认值为 40。</span><span class="sxs-lookup"><span data-stu-id="f9271-124">The default is 40.</span></span> <span data-ttu-id="f9271-125">但是，40 并不是通常用于音频流量的值；音频流量几乎始终用 DSCP 代码 46 进行标记。</span><span class="sxs-lookup"><span data-stu-id="f9271-125">However, 40 is not the value typically used for audio traffic; instead, audio traffic is almost always marked with the DSCP code 46.</span></span> <span data-ttu-id="f9271-126">为了在整个网络中保持一致性，您可能需要将此值更改为 46。</span><span class="sxs-lookup"><span data-stu-id="f9271-126">In order to maintain consistency throughout your network, you might want to change this value to 46.</span></span>
    
- <span data-ttu-id="f9271-127">**电话锁定** 可以指定 UC 电话是否将在指定的非活动时间后自动锁定自身。</span><span class="sxs-lookup"><span data-stu-id="f9271-127">**Phone lock** You can specify whether or not UC phones will automatically lock themselves after a specified period of inactivity.</span></span> <span data-ttu-id="f9271-128">以下是可以配置的设置：</span><span class="sxs-lookup"><span data-stu-id="f9271-128">The following are the settings you can configure:</span></span>
    
  - <span data-ttu-id="f9271-129">**强制设备锁定** 可以通过选中此复选框来强制设备锁定。</span><span class="sxs-lookup"><span data-stu-id="f9271-129">**Enforce device locking** You can enforce device locking by selecting this check box.</span></span>
    
  - <span data-ttu-id="f9271-130">**最小 PIN 长度** 你可以指定用于解锁电话的个人标识 (PIN) 的最小长度。</span><span class="sxs-lookup"><span data-stu-id="f9271-130">**Minimum PIN length** You can specify the minimum length for the personal identification number (PIN) that is used to unlock the phone.</span></span> <span data-ttu-id="f9271-131">PIN 长度的范围为 4 到 15 位数字。</span><span class="sxs-lookup"><span data-stu-id="f9271-131">The range for the PIN length is four to 15 digits.</span></span> <span data-ttu-id="f9271-132">默认长度为六位数字。</span><span class="sxs-lookup"><span data-stu-id="f9271-132">The default length is six digits.</span></span>
    
  - <span data-ttu-id="f9271-133">**电话锁定的退出** 你可以指定电话自行锁定之前的最小时间长度。</span><span class="sxs-lookup"><span data-stu-id="f9271-133">**Phone lock time-out** You can specify the minimum length of time before the phone locks itself.</span></span> <span data-ttu-id="f9271-134">该退出的范围是 0 到 60 分钟;默认值为 10 分钟。</span><span class="sxs-lookup"><span data-stu-id="f9271-134">The range for the time-out is 0 to 60 minutes; the default value is 10 minutes.</span></span> <span data-ttu-id="f9271-135">输入 HH：MM：SS 格式的值。</span><span class="sxs-lookup"><span data-stu-id="f9271-135">Enter the value in the format HH:MM:SS.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="f9271-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f9271-136">See also</span></span>

[<span data-ttu-id="f9271-137">设备配置</span><span class="sxs-lookup"><span data-stu-id="f9271-137">Device Configuration</span></span>](ms.lync.lscp.ClientDeviceCfgMain.md)

[<span data-ttu-id="f9271-138">Set-CsUCPhoneConfiguration</span><span class="sxs-lookup"><span data-stu-id="f9271-138">Set-CsUCPhoneConfiguration</span></span>](/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps)