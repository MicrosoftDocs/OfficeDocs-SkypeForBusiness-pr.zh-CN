---
title: Skype 会议室系统域加入注意事项
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
ms.collection:
- M365-collaboration
description: 管理员可以了解如何将会议室Skype电脑加入 Active Directory 域，以及执行此操作的注意事项。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c322819fb765e05cead793c95b5e3b6af2d2a180
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117550"
---
<!-- This asset missed in the rebrand, and honestly not sure if it's worth keeping.   -->

# <a name="skype-room-system-domain-joining-considerations"></a><span data-ttu-id="518ef-103">Skype 会议室系统域加入注意事项</span><span class="sxs-lookup"><span data-stu-id="518ef-103">Skype Room System domain joining considerations</span></span>
 
<span data-ttu-id="518ef-104">阅读本主题，了解如何将 Skype 会议室系统家用电脑加入你的域。</span><span class="sxs-lookup"><span data-stu-id="518ef-104">Read this topic to learn how to join a Skype Room System appliance PC to your domain.</span></span>
  
## <a name="domain-joining-considerations"></a><span data-ttu-id="518ef-105">域加入注意事项</span><span class="sxs-lookup"><span data-stu-id="518ef-105">Domain joining considerations</span></span>

<span data-ttu-id="518ef-106">可以将会议室Skype设备电脑加入 Active Directory 域，或将该设备留在"工作组"中。</span><span class="sxs-lookup"><span data-stu-id="518ef-106">You can join the Skype Room System appliance PC to the Active Directory domain or leave it in a Workgroup.</span></span> <span data-ttu-id="518ef-107">做此决定之前请考虑以下事项：</span><span class="sxs-lookup"><span data-stu-id="518ef-107">Consider the following points before making this decision:</span></span>
  
- <span data-ttu-id="518ef-108">将会议室系统Skype电脑加入域有助于自动导入组织的专用根证书链。</span><span class="sxs-lookup"><span data-stu-id="518ef-108">Domain-joining the Skype Room System appliance PC helps in importing your organization's private root certificate chain automatically.</span></span>
- <span data-ttu-id="518ef-109">使用会议室系统Skype电脑加入域可授予域用户和组管理权限。</span><span class="sxs-lookup"><span data-stu-id="518ef-109">Domain-joining the Skype Room System appliance PC enables you to grant domain users and groups administrative rights.</span></span> <span data-ttu-id="518ef-110">这样做，你不必记住本地计算机级别的管理员帐户密码。</span><span class="sxs-lookup"><span data-stu-id="518ef-110">By doing so, you will not have to remember the local machine level administrator account password.</span></span>
- <span data-ttu-id="518ef-111">将 Skype 会议室系统设备电脑加入域时，需要创建单独的组织单位 (OU) ，以便可以将组策略对象 (GPO) 排除项提供到所有 Skype 会议室系统计算机对象所在的 OU。</span><span class="sxs-lookup"><span data-stu-id="518ef-111">When you join a Skype Room System appliance PC to the domain, it is required that you create a separate Organizational Unit (OU), so that you can provide Group Policy Object (GPO) exclusions to the OU where all the Skype Room System machine objects reside.</span></span> <span data-ttu-id="518ef-112">执行此操作时，在 OU 中创建计算机对象，Skype会议室系统设备电脑加入域。</span><span class="sxs-lookup"><span data-stu-id="518ef-112">When you do this, create machine objects in the OU before joining the Skype Room System appliance PC to the domain.</span></span>
- <span data-ttu-id="518ef-113">许多组织具有以下 GPO，这Skype会议室系统设备电脑功能。</span><span class="sxs-lookup"><span data-stu-id="518ef-113">Many organizations have the following GPOs, which affect Skype Room System appliance PC functions.</span></span> <span data-ttu-id="518ef-114">确保在会议室系统 OU 中重写或阻止Skype GPO：</span><span class="sxs-lookup"><span data-stu-id="518ef-114">Ensure that you override or block the inheritance of these GPOs in the Skype Room System OU:</span></span>

  - <span data-ttu-id="518ef-115">登录会话的超时（自动锁定）</span><span class="sxs-lookup"><span data-stu-id="518ef-115">Timeout of logon sessions (auto lockout)</span></span>
  - <span data-ttu-id="518ef-116">与电源管理相关的策略</span><span class="sxs-lookup"><span data-stu-id="518ef-116">Policies related to power management</span></span>
  - <span data-ttu-id="518ef-117">需要附加身份验证步骤</span><span class="sxs-lookup"><span data-stu-id="518ef-117">Requiring additional authentication steps</span></span>
  - <span data-ttu-id="518ef-118">拒绝访问本地驱动器</span><span class="sxs-lookup"><span data-stu-id="518ef-118">Denying access to local drives</span></span>
  - <span data-ttu-id="518ef-119">提示用户网络连接较慢</span><span class="sxs-lookup"><span data-stu-id="518ef-119">Prompting users for slow network connections</span></span>
  - <span data-ttu-id="518ef-120">登录时启动特定程序</span><span class="sxs-lookup"><span data-stu-id="518ef-120">Start a certain program at logon</span></span>
  - <span data-ttu-id="518ef-121">在所有加入域的计算机上创建另一个域用户帐户。</span><span class="sxs-lookup"><span data-stu-id="518ef-121">Create another domain user account on all domain-joined machines.</span></span>
  - <span data-ttu-id="518ef-122">将Windows更新推送Skype会议室系统</span><span class="sxs-lookup"><span data-stu-id="518ef-122">Push Windows Update to Skype Room System</span></span>
    
- <span data-ttu-id="518ef-123">或者，你可能决定将家用电脑留在工作组中。</span><span class="sxs-lookup"><span data-stu-id="518ef-123">Alternatively, you might decide to leave the appliance PC in the workgroup.</span></span> <span data-ttu-id="518ef-124">与桌面客户端Microsoft Teams Skype for Business一样，这要求在会议室系统设备电脑上Skype根证书链。</span><span class="sxs-lookup"><span data-stu-id="518ef-124">As with the desktop Microsoft Teams or Skype for Business client, this requires you to manually import the root certificate chain on the Skype Room System appliance PC.</span></span> <span data-ttu-id="518ef-125">如果部署使用的是公共证书链，则不需要导入根证书链 (例如，Entrust、VeriSign 等) 。</span><span class="sxs-lookup"><span data-stu-id="518ef-125">You're not required to import the root certificate chain if your deployment is using a public certificate (for example, Entrust, VeriSign, and so on).</span></span> 
    
<span data-ttu-id="518ef-126">如果计划将 Skype Room System 计算机加入域，为了避免无意中将 Skype 会议室系统计算机加入意外的 OU（可能无法从 GPO 中释放）中，请确保加入正确的 OU。</span><span class="sxs-lookup"><span data-stu-id="518ef-126">If you plan to join Skype Room System machines to the domain, to avoid joining Skype Room System machine inadvertently to an unintended OU, which may not be free from GPOs, please ensure you join the correct OU.</span></span> <span data-ttu-id="518ef-127">可以使用会议室系统计算机中的以下 cmdlet Skype加入正确的 OU，并且不会收到可能会阻止 LRS 功能的 GPO。</span><span class="sxs-lookup"><span data-stu-id="518ef-127">You can use the following cmdlet from the Skype Room System machine to join in the correct OU and does not receive GPOs that might block LRS functionality.</span></span> <span data-ttu-id="518ef-128">请联系系统管理员或 OEM 合作伙伴来运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="518ef-128">Contact your system administrator or OEM partner to run these cmdlets:</span></span>
  
```powershell
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

<span data-ttu-id="518ef-129">即使创建单独的 OU 和块继承，也有一些策略可能会导致更高级别的问题。</span><span class="sxs-lookup"><span data-stu-id="518ef-129">Even if you create a separate OU and block inheritance, there are some policies that could cause issues at a higher level.</span></span> <span data-ttu-id="518ef-130">具有“禁止替代”设置的组策略会打败具有“阻止策略继承”设置的 OU。</span><span class="sxs-lookup"><span data-stu-id="518ef-130">A Group Policy with No Override setting beats an OU with a Block Policy Inheritance setting.</span></span> <span data-ttu-id="518ef-131">有关详细信息，请参阅组 [策略文档中的"无替代"（](/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) 与阻止策略继承相比）。</span><span class="sxs-lookup"><span data-stu-id="518ef-131">For more information, see [No Override as Compared to Block Policy Inheritance](/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) in the Group Policy documentation.</span></span>
  
<span data-ttu-id="518ef-132">你可能有多种方法来解决这些问题。</span><span class="sxs-lookup"><span data-stu-id="518ef-132">You may have multiple approaches to solving these problems.</span></span> <span data-ttu-id="518ef-133">建议咨询 Active Directory 专家，确保获得具有适当 GPO 设置的 OU，或者至少提供不存在上述策略的 OU。</span><span class="sxs-lookup"><span data-stu-id="518ef-133">We advise you to consult with your Active Directory experts to ensure that you are provided with an OU that has appropriate GPO settings, or at least an OU in which the previously described policies do not exist.</span></span> <span data-ttu-id="518ef-134">我们建议为会议室系统设备 (QoS) Skype服务质量。</span><span class="sxs-lookup"><span data-stu-id="518ef-134">We advise to enabling Quality of Service (QoS) for Skype Room System devices.</span></span>

## <a name="related-topics"></a><span data-ttu-id="518ef-135">相关主题</span><span class="sxs-lookup"><span data-stu-id="518ef-135">Related topics</span></span>
  
[<span data-ttu-id="518ef-136">设备配置：创建新的或编辑现有的</span><span class="sxs-lookup"><span data-stu-id="518ef-136">Device Configuration: Create New or Edit Existing</span></span>](/skypeforbusiness/help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[<span data-ttu-id="518ef-137">管理服务质量</span><span class="sxs-lookup"><span data-stu-id="518ef-137">Managing Quality of Service</span></span>](/skypeforbusiness/plan-your-deployment/network-requirements/network-requirements#managing-quality-of-service)