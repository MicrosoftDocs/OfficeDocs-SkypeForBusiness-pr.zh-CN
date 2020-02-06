---
title: 设备配置新建或编辑现有
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 在 "新建设备配置" 或 "编辑设备配置" 页面上，您可以创建或修改用于管理 Skype for Business Phone Edition 的设置集合。 通过这些设置，您可以配置以下内容：所需的安全性模式、设备日志记录级别、语音服务质量 (QoS) 设置以及在指定的非活动时间后电话是否应自动锁住。
ms.openlocfilehash: 772463b5816c4ce40b70be8cb38af2fee8daa0bf
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794481"
---
# <a name="device-configuration-create-new-or-edit-existing"></a><span data-ttu-id="804d6-104">设备配置：创建新的或编辑现有的</span><span class="sxs-lookup"><span data-stu-id="804d6-104">Device Configuration: Create New or Edit Existing</span></span>
 
<span data-ttu-id="804d6-105">在 "**新建设备配置**" 或 "**编辑设备配置**" 页面上，您可以创建或修改用于管理 Skype for business Phone Edition 的设置集合。</span><span class="sxs-lookup"><span data-stu-id="804d6-105">On the **New Device Configuration** or **Edit Device Configuration** page, you can create or modify a collection of settings used to manage Skype for Business Phone Edition.</span></span> <span data-ttu-id="804d6-106">通过这些设置，您可以配置以下内容：所需的安全性模式、设备日志记录级别、语音服务质量 (QoS) 设置以及在指定的非活动时间后电话是否应自动锁住。</span><span class="sxs-lookup"><span data-stu-id="804d6-106">These settings enable you to configure such things as the required security mode, device logging level, Voice Quality of Service (QoS) settings, and whether or not phones should automatically lock after a specified period of inactivity.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="804d6-107">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="804d6-107">Tasks you can perform</span></span>

<span data-ttu-id="804d6-108">您可以在“**新建设备配置**”或“**编辑设备配置**”页上执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="804d6-108">You can perform the following tasks on the **New Device Configuration** or **Edit Device Configuration** page:</span></span>
  
- <span data-ttu-id="804d6-109">添加新的设备配置。</span><span class="sxs-lookup"><span data-stu-id="804d6-109">Add a new device configuration.</span></span>
    
- <span data-ttu-id="804d6-110">修改现有设备配置的属性。</span><span class="sxs-lookup"><span data-stu-id="804d6-110">Modify the properties of an existing device configuration.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="804d6-111">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="804d6-111">UI Reference</span></span>

<span data-ttu-id="804d6-112">下表介绍了该页上的菜单、命令、字段和属性。</span><span class="sxs-lookup"><span data-stu-id="804d6-112">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="804d6-113">**范围**标识设备配置的作用域（全局或网站）。</span><span class="sxs-lookup"><span data-stu-id="804d6-113">**Scope** Identifies the scope (Global or Site) of the device configuration.</span></span>
    
- <span data-ttu-id="804d6-114">**名称**你可以添加或修改设备配置的名称。</span><span class="sxs-lookup"><span data-stu-id="804d6-114">**Name** You can add or modify the name of the device configuration.</span></span>
    
- <span data-ttu-id="804d6-115">**SIP 安全性**你可以配置 Skype for business Phone Edition 设备的传输和身份验证要求。</span><span class="sxs-lookup"><span data-stu-id="804d6-115">**SIP security** You can configure transport and authentication requirements for Skype for Business Phone Edition devices.</span></span> <span data-ttu-id="804d6-116">可以从以下选项中进行选择：</span><span class="sxs-lookup"><span data-stu-id="804d6-116">You can select from the following options:</span></span>
    
  - <span data-ttu-id="804d6-117">**低**允许任何类型的授权或传输。</span><span class="sxs-lookup"><span data-stu-id="804d6-117">**Low** Allow any type of authorization or transport.</span></span>
    
  - <span data-ttu-id="804d6-118">**中等**需要使用 NTLM 或 Kerberos 进行用户身份验证。</span><span class="sxs-lookup"><span data-stu-id="804d6-118">**Medium** NTLM or Kerberos is required for user authentication.</span></span>
    
  - <span data-ttu-id="804d6-119">**高**需要使用 NTLM 或 Kerberos 进行用户身份验证，并且需要使用 TLS 进行 SIP 连接。</span><span class="sxs-lookup"><span data-stu-id="804d6-119">**High** NTLM or Kerberos is required for user authentication and TLS is required for SIP connections.</span></span>
    
- <span data-ttu-id="804d6-120">**日志记录级别**可以在 UC 设备上启用日志记录。</span><span class="sxs-lookup"><span data-stu-id="804d6-120">**Logging level** You can enable logging on the UC device.</span></span> <span data-ttu-id="804d6-121">有效值为： Off;盘中期和高。</span><span class="sxs-lookup"><span data-stu-id="804d6-121">Valid values are: Off; Low; Medium; and High.</span></span> <span data-ttu-id="804d6-122">默认值为 Off。</span><span class="sxs-lookup"><span data-stu-id="804d6-122">The default value is Off.</span></span>
    
- <span data-ttu-id="804d6-123">**语音服务质量（QoS）** 你可以从 Skype for business Phone Edition 设备指定分配给语音流量 emanating 的 DSCP 值。</span><span class="sxs-lookup"><span data-stu-id="804d6-123">**Voice Quality of Service (QoS)** You can specify the DSCP value assigned to voice traffic emanating from a Skype for Business Phone Edition device.</span></span> <span data-ttu-id="804d6-124">默认值为40。</span><span class="sxs-lookup"><span data-stu-id="804d6-124">The default is 40.</span></span> <span data-ttu-id="804d6-125">但是，40不是通常用于音频流量的值;相反，音频流量几乎始终标有 DSCP 代码46。</span><span class="sxs-lookup"><span data-stu-id="804d6-125">However, 40 is not the value typically used for audio traffic; instead, audio traffic is almost always marked with the DSCP code 46.</span></span> <span data-ttu-id="804d6-126">为了保持整个网络的一致性，你可能希望将此值更改为46。</span><span class="sxs-lookup"><span data-stu-id="804d6-126">In order to maintain consistency throughout your network, you might want to change this value to 46.</span></span>
    
- <span data-ttu-id="804d6-127">**电话锁定**你可以指定 UC 电话是否会在指定的非活动期后自动锁定其自身。</span><span class="sxs-lookup"><span data-stu-id="804d6-127">**Phone lock** You can specify whether or not UC phones will automatically lock themselves after a specified period of inactivity.</span></span> <span data-ttu-id="804d6-128">以下是你可以配置的设置：</span><span class="sxs-lookup"><span data-stu-id="804d6-128">The following are the settings you can configure:</span></span>
    
  - <span data-ttu-id="804d6-129">**强制执行设备锁定**你可以通过选中此复选框来强制执行设备锁定。</span><span class="sxs-lookup"><span data-stu-id="804d6-129">**Enforce device locking** You can enforce device locking by selecting this check box.</span></span>
    
  - <span data-ttu-id="804d6-130">**最小 PIN 长度**你可以指定用于解锁手机的个人识别码（PIN）的最小长度。</span><span class="sxs-lookup"><span data-stu-id="804d6-130">**Minimum PIN length** You can specify the minimum length for the personal identification number (PIN) that is used to unlock the phone.</span></span> <span data-ttu-id="804d6-131">PIN 长度的范围是4到15个数字。</span><span class="sxs-lookup"><span data-stu-id="804d6-131">The range for the PIN length is four to 15 digits.</span></span> <span data-ttu-id="804d6-132">默认长度为6个数字。</span><span class="sxs-lookup"><span data-stu-id="804d6-132">The default length is six digits.</span></span>
    
  - <span data-ttu-id="804d6-133">**电话锁定超时**你可以指定电话锁定自身之前的最短时间长度。</span><span class="sxs-lookup"><span data-stu-id="804d6-133">**Phone lock time-out** You can specify the minimum length of time before the phone locks itself.</span></span> <span data-ttu-id="804d6-134">超时的范围是0到60分钟;默认值为10分钟。</span><span class="sxs-lookup"><span data-stu-id="804d6-134">The range for the time-out is 0 to 60 minutes; the default value is 10 minutes.</span></span> <span data-ttu-id="804d6-135">以 HH： MM： SS 格式输入值。</span><span class="sxs-lookup"><span data-stu-id="804d6-135">Enter the value in the format HH:MM:SS.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="804d6-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="804d6-136">See also</span></span>

[<span data-ttu-id="804d6-137">设备配置</span><span class="sxs-lookup"><span data-stu-id="804d6-137">Device Configuration</span></span>](ms.lync.lscp.ClientDeviceCfgMain.md)

[<span data-ttu-id="804d6-138">Set-CsUCPhoneConfiguration</span><span class="sxs-lookup"><span data-stu-id="804d6-138">Set-CsUCPhoneConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps)
