---
title: 设备配置创建新的或编辑现有的
ms.reviewer: ''
ms.author: SerdarS
author: SerdarSoysal
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientPhoneCfgEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aac152bf-80e9-408a-9dbb-60d0843484ab
ROBOTS: NOINDEX, NOFOLLOW
description: 在新的设备配置或编辑设备配置页上，您可以创建或修改用于管理业务 Phone edition 的 Skype 的设置的集合。 通过这些设置，您可以配置以下内容：所需的安全性模式、设备日志记录级别、语音服务质量 (QoS) 设置以及在指定的非活动时间后电话是否应自动锁住。
ms.openlocfilehash: 3dd7c9f782160b0f8a58d15e749276b4b2ee6adf
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32215813"
---
# <a name="device-configuration-create-new-or-edit-existing"></a><span data-ttu-id="fb49b-104">设备配置：创建新的或编辑现有的</span><span class="sxs-lookup"><span data-stu-id="fb49b-104">Device Configuration: Create New or Edit Existing</span></span>
 
<span data-ttu-id="fb49b-105">在**新的设备配置**或**编辑设备配置**页上，您可以创建或修改用于管理业务 Phone edition 的 Skype 的设置的集合。</span><span class="sxs-lookup"><span data-stu-id="fb49b-105">On the **New Device Configuration** or **Edit Device Configuration** page, you can create or modify a collection of settings used to manage Skype for Business Phone Edition.</span></span> <span data-ttu-id="fb49b-106">通过这些设置，您可以配置以下内容：所需的安全性模式、设备日志记录级别、语音服务质量 (QoS) 设置以及在指定的非活动时间后电话是否应自动锁住。</span><span class="sxs-lookup"><span data-stu-id="fb49b-106">These settings enable you to configure such things as the required security mode, device logging level, Voice Quality of Service (QoS) settings, and whether or not phones should automatically lock after a specified period of inactivity.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="fb49b-107">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="fb49b-107">Tasks you can perform</span></span>

<span data-ttu-id="fb49b-108">您可以在“**新建设备配置**”或“**编辑设备配置**”页上执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="fb49b-108">You can perform the following tasks on the **New Device Configuration** or **Edit Device Configuration** page:</span></span>
  
- <span data-ttu-id="fb49b-109">添加新的设备配置。</span><span class="sxs-lookup"><span data-stu-id="fb49b-109">Add a new device configuration.</span></span>
    
- <span data-ttu-id="fb49b-110">修改现有设备配置的属性。</span><span class="sxs-lookup"><span data-stu-id="fb49b-110">Modify the properties of an existing device configuration.</span></span>
    
## <a name="ui-reference"></a><span data-ttu-id="fb49b-111">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="fb49b-111">UI Reference</span></span>

<span data-ttu-id="fb49b-112">下表介绍了该页上的菜单、命令、字段和属性。</span><span class="sxs-lookup"><span data-stu-id="fb49b-112">The following lists describe the menus, commands, fields, and properties on the page.</span></span>
  
- <span data-ttu-id="fb49b-113">**范围**标识设备配置的范围 （全局或站点）。</span><span class="sxs-lookup"><span data-stu-id="fb49b-113">**Scope** Identifies the scope (Global or Site) of the device configuration.</span></span>
    
- <span data-ttu-id="fb49b-114">**名称**您可以添加或修改设备配置的名称。</span><span class="sxs-lookup"><span data-stu-id="fb49b-114">**Name** You can add or modify the name of the device configuration.</span></span>
    
- <span data-ttu-id="fb49b-115">**SIP 安全**您可以配置传输和身份验证要求 Skype 业务 Phone Edition 设备。</span><span class="sxs-lookup"><span data-stu-id="fb49b-115">**SIP security** You can configure transport and authentication requirements for Skype for Business Phone Edition devices.</span></span> <span data-ttu-id="fb49b-116">您可以从以下选项中进行选择：</span><span class="sxs-lookup"><span data-stu-id="fb49b-116">You can select from the following options:</span></span>
    
  - <span data-ttu-id="fb49b-117">**低**允许任意类型的授权或传输。</span><span class="sxs-lookup"><span data-stu-id="fb49b-117">**Low** Allow any type of authorization or transport.</span></span>
    
  - <span data-ttu-id="fb49b-118">**中等**NTLM 或 Kerberos 才能进行用户身份验证。</span><span class="sxs-lookup"><span data-stu-id="fb49b-118">**Medium** NTLM or Kerberos is required for user authentication.</span></span>
    
  - <span data-ttu-id="fb49b-119">**高**NTLM 或 Kerberos 才能进行用户身份验证，并且需要 TLS 才能进行 SIP 连接。</span><span class="sxs-lookup"><span data-stu-id="fb49b-119">**High** NTLM or Kerberos is required for user authentication and TLS is required for SIP connections.</span></span>
    
- <span data-ttu-id="fb49b-120">**日志记录级别**您可以启用 UC 设备上的日志记录。</span><span class="sxs-lookup"><span data-stu-id="fb49b-120">**Logging level** You can enable logging on the UC device.</span></span> <span data-ttu-id="fb49b-121">有效值为： 关闭;低;中等;和高。</span><span class="sxs-lookup"><span data-stu-id="fb49b-121">Valid values are: Off; Low; Medium; and High.</span></span> <span data-ttu-id="fb49b-122">默认值已关闭。</span><span class="sxs-lookup"><span data-stu-id="fb49b-122">The default value is Off.</span></span>
    
- <span data-ttu-id="fb49b-123">**语音服务质量 (QoS)** 您可以指定分配给产生 Skype 业务 Phone Edition 设备的语音流量的 DSCP 值。</span><span class="sxs-lookup"><span data-stu-id="fb49b-123">**Voice Quality of Service (QoS)** You can specify the DSCP value assigned to voice traffic emanating from a Skype for Business Phone Edition device.</span></span> <span data-ttu-id="fb49b-124">默认值为 40。</span><span class="sxs-lookup"><span data-stu-id="fb49b-124">The default is 40.</span></span> <span data-ttu-id="fb49b-125">但是，40 不是通常用于音频流量; 的值而是音频流量始终标记替换为 DSCP 代码 46。</span><span class="sxs-lookup"><span data-stu-id="fb49b-125">However, 40 is not the value typically used for audio traffic; instead, audio traffic is almost always marked with the DSCP code 46.</span></span> <span data-ttu-id="fb49b-126">为了保持一致性整个网络，您可能想要将此值更改为 46。</span><span class="sxs-lookup"><span data-stu-id="fb49b-126">In order to maintain consistency throughout your network, you might want to change this value to 46.</span></span>
    
- <span data-ttu-id="fb49b-127">**电话锁定**您可以指定 UC 电话将自己在后自动锁定停止活动一段。</span><span class="sxs-lookup"><span data-stu-id="fb49b-127">**Phone lock** You can specify whether or not UC phones will automatically lock themselves after a specified period of inactivity.</span></span> <span data-ttu-id="fb49b-128">您可以配置的设置如下：</span><span class="sxs-lookup"><span data-stu-id="fb49b-128">The following are the settings you can configure:</span></span>
    
  - <span data-ttu-id="fb49b-129">**强制设备锁定**您可以强制设备锁定选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="fb49b-129">**Enforce device locking** You can enforce device locking by selecting this check box.</span></span>
    
  - <span data-ttu-id="fb49b-130">**最小 PIN 长度**您可以指定用于解锁电话的个人识别号 (PIN) 的最小长度。</span><span class="sxs-lookup"><span data-stu-id="fb49b-130">**Minimum PIN length** You can specify the minimum length for the personal identification number (PIN) that is used to unlock the phone.</span></span> <span data-ttu-id="fb49b-131">PIN 长度的范围是 4 到 15 位数字。</span><span class="sxs-lookup"><span data-stu-id="fb49b-131">The range for the PIN length is four to 15 digits.</span></span> <span data-ttu-id="fb49b-132">默认长度为 6 个数字。</span><span class="sxs-lookup"><span data-stu-id="fb49b-132">The default length is six digits.</span></span>
    
  - <span data-ttu-id="fb49b-133">**电话锁定超时**您可以指定电话锁定之前的时间的最小长度，本身。</span><span class="sxs-lookup"><span data-stu-id="fb49b-133">**Phone lock time-out** You can specify the minimum length of time before the phone locks itself.</span></span> <span data-ttu-id="fb49b-134">超时的范围是 0 到 60 分钟;默认值为 10 分钟。</span><span class="sxs-lookup"><span data-stu-id="fb49b-134">The range for the time-out is 0 to 60 minutes; the default value is 10 minutes.</span></span> <span data-ttu-id="fb49b-135">Mm: ss 的格式输入该值。</span><span class="sxs-lookup"><span data-stu-id="fb49b-135">Enter the value in the format HH:MM:SS.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="fb49b-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fb49b-136">See also</span></span>

[<span data-ttu-id="fb49b-137">设备配置</span><span class="sxs-lookup"><span data-stu-id="fb49b-137">Device Configuration</span></span>](ms.lync.lscp.ClientDeviceCfgMain.md)

[<span data-ttu-id="fb49b-138">Set-csucphoneconfiguration</span><span class="sxs-lookup"><span data-stu-id="fb49b-138">Set-CsUCPhoneConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps)
