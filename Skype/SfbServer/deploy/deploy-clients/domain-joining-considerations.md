---
title: Skype 会议室系统域加入注意事项
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
description: 阅读本主题，了解如何将 Skype 会议室系统电脑加入你的域。
ms.openlocfilehash: cf98f98a7294ead0920b3d6b07b00879cbfe15f3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093566"
---
# <a name="skype-room-system-domain-joining-considerations"></a><span data-ttu-id="9238b-103">Skype 会议室系统域加入注意事项</span><span class="sxs-lookup"><span data-stu-id="9238b-103">Skype Room System domain joining considerations</span></span>
 
<span data-ttu-id="9238b-104">阅读本主题，了解如何将 Skype 会议室系统电脑加入你的域。</span><span class="sxs-lookup"><span data-stu-id="9238b-104">Read this topic to learn how to join a Skype Room System appliance PC to your domain.</span></span>
  
## <a name="domain-joining-considerations"></a><span data-ttu-id="9238b-105">域加入注意事项</span><span class="sxs-lookup"><span data-stu-id="9238b-105">Domain joining considerations</span></span>

<span data-ttu-id="9238b-106">你可以将 Skype 会议室系统电脑加入 Active Directory 域或将电脑留在工作组中。</span><span class="sxs-lookup"><span data-stu-id="9238b-106">You can join the Skype Room System appliance PC to the Active Directory domain or leave it in a Workgroup.</span></span> <span data-ttu-id="9238b-107">做出此决定之前，请考虑以下几点：</span><span class="sxs-lookup"><span data-stu-id="9238b-107">Consider the following points before making this decision:</span></span>
  
- <span data-ttu-id="9238b-108">域加入 Skype 会议室系统电脑有助于自动导入组织的专用根证书链。</span><span class="sxs-lookup"><span data-stu-id="9238b-108">Domain-joining the Skype Room System appliance PC helps in importing your organization's private root certificate chain automatically.</span></span>
    
- <span data-ttu-id="9238b-109">通过加入 Skype 会议室系统电脑的域，可以授予域用户和组管理权限。</span><span class="sxs-lookup"><span data-stu-id="9238b-109">Domain-joining the Skype Room System appliance PC enables you to grant domain users and groups administrative rights.</span></span> <span data-ttu-id="9238b-110">这样，就不需要记住本地计算机级别的管理员帐户密码。</span><span class="sxs-lookup"><span data-stu-id="9238b-110">By doing so, you will not have to remember the local machine level administrator account password.</span></span>
    
- <span data-ttu-id="9238b-111">将 Skype 会议室系统电脑加入域时，需要创建单独的组织单位 (OU) ，以便你可以向所有 Skype 会议室系统计算机对象所在的 OU 提供组策略对象 (GPO) 排除项。</span><span class="sxs-lookup"><span data-stu-id="9238b-111">When you join an Skype Room System appliance PC to the domain, it is required that you create a separate Organizational Unit (OU), so that you can provide Group Policy Object (GPO) exclusions to the OU where all the Skype Room System machine objects reside.</span></span> <span data-ttu-id="9238b-112">当你这样做时，在 OU 中创建计算机对象，然后再将 Skype 会议室系统电脑加入域。</span><span class="sxs-lookup"><span data-stu-id="9238b-112">When you do this, create machine objects in the OU before joining the Skype Room System appliance PC to the domain.</span></span>
    
- <span data-ttu-id="9238b-113">许多组织具有以下 GPO，这会影响 Skype 会议室系统设备电脑的功能。</span><span class="sxs-lookup"><span data-stu-id="9238b-113">Many organizations have the following GPOs, which affect Skype Room System appliance PC functions.</span></span> <span data-ttu-id="9238b-114">确保覆盖或阻止 Skype 会议室系统 OU 中这些 GPO 的继承：</span><span class="sxs-lookup"><span data-stu-id="9238b-114">Ensure that you override or block the inheritance of these GPOs in the Skype Room System OU:</span></span> 
    
  - <span data-ttu-id="9238b-115">登录会话超时 (自动锁定) </span><span class="sxs-lookup"><span data-stu-id="9238b-115">Timeout of logon sessions (auto lockout)</span></span>
    
  - <span data-ttu-id="9238b-116">与电源管理相关的策略</span><span class="sxs-lookup"><span data-stu-id="9238b-116">Power management related policies</span></span>
    
  - <span data-ttu-id="9238b-117">需要其他身份验证步骤</span><span class="sxs-lookup"><span data-stu-id="9238b-117">Requiring additional authentication steps</span></span>
    
  - <span data-ttu-id="9238b-118">拒绝访问本地驱动器</span><span class="sxs-lookup"><span data-stu-id="9238b-118">Denying access to local drives</span></span>
    
  - <span data-ttu-id="9238b-119">提示用户网络连接缓慢</span><span class="sxs-lookup"><span data-stu-id="9238b-119">Prompting users for slow network connections</span></span>
    
  - <span data-ttu-id="9238b-120">登录时启动特定程序</span><span class="sxs-lookup"><span data-stu-id="9238b-120">Start a certain program at logon</span></span>
    
  - <span data-ttu-id="9238b-121">在所有加入域的计算机上创建另一个域用户帐户。</span><span class="sxs-lookup"><span data-stu-id="9238b-121">Create another domain user account on all domain-joined machines.</span></span>
    
  - <span data-ttu-id="9238b-122">将 Windows 更新推送到 Skype 会议室系统</span><span class="sxs-lookup"><span data-stu-id="9238b-122">Push Windows Update to Skype Room System</span></span>
    
- <span data-ttu-id="9238b-123">或者，你可能决定将电脑留在工作组中。</span><span class="sxs-lookup"><span data-stu-id="9238b-123">Alternatively, you might decide to leave the appliance PC in the workgroup.</span></span> <span data-ttu-id="9238b-124">与桌面 Skype for Business 客户端一样，这需要你在 Skype 会议室系统电脑中手动导入根证书链。</span><span class="sxs-lookup"><span data-stu-id="9238b-124">As with the desktop Skype for Business client, this requires you to manually import the root certificate chain on the Skype Room System appliance PC.</span></span> <span data-ttu-id="9238b-125">如果你的 Skype for Business 部署使用公共证书 (例如，Entrust、VeriSign 等，则不需要导入根证书链) 。</span><span class="sxs-lookup"><span data-stu-id="9238b-125">You're not required to import the root certificate chain if your Skype for Business deployment is using a public certificate (for example, Entrust, VeriSign, and so on).</span></span> 
    
<span data-ttu-id="9238b-126">如果计划将 Skype 会议室系统计算机加入域，为避免无意中将 Skype 会议室系统计算机加入非预期 OU（可能无法从 GPO 中释放）请确保加入正确的 OU。</span><span class="sxs-lookup"><span data-stu-id="9238b-126">If you plan to join Skype Room System machines to the domain, to avoid joining Skype Room System machine inadvertently to an unintended OU, which may not be free from GPOs, please ensure you join the correct OU.</span></span> <span data-ttu-id="9238b-127">可以使用 Skype 会议室系统计算机中的以下 cmdlet 加入正确的 OU，并且不会接收可能会阻止 LRS 功能的 GPO。</span><span class="sxs-lookup"><span data-stu-id="9238b-127">You can use the following cmdlet from the Skype Room System machine to join in the correct OU and does not receive GPOs that might block LRS functionality.</span></span> <span data-ttu-id="9238b-128">请与系统管理员或 OEM 合作伙伴联系以运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="9238b-128">Contact your system administrator or OEM partner to run these cmdlet:</span></span>
  
```powershell
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

<span data-ttu-id="9238b-129">即使您创建单独的 OU 并阻止继承，某些策略也会导致更高级别的问题。</span><span class="sxs-lookup"><span data-stu-id="9238b-129">Even if you create a separate OU and block inheritance, there are some policies which could cause issues at a higher level.</span></span> <span data-ttu-id="9238b-130">具有"无替代"设置的组策略会超过具有阻止策略继承设置的 OU。</span><span class="sxs-lookup"><span data-stu-id="9238b-130">A Group Policy with No Override setting beats an OU with a Block Policy Inheritance setting.</span></span> <span data-ttu-id="9238b-131">有关详细信息，请参阅组策略文档中的文章 No [Override as Compared to Block Policy Inheritance。](/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="9238b-131">For more information, see the article [No Override as Compared to Block Policy Inheritance](/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) in the Group Policy documentation.</span></span>
  
<span data-ttu-id="9238b-132">你可能有多种方法来解决这些问题。</span><span class="sxs-lookup"><span data-stu-id="9238b-132">You may have multiple approaches to solving these problems.</span></span> <span data-ttu-id="9238b-133">我们建议您咨询 Active Directory 专家，以确保为您提供具有相应 GPO 设置的 OU，或至少为您提供了不存在上述策略的 OU。</span><span class="sxs-lookup"><span data-stu-id="9238b-133">We advise you to consult with your Active Directory experts to ensure you are provided with an OU that has appropriate GPO settings, or at least an OU in which the previously described policies do not exist.</span></span> <span data-ttu-id="9238b-134">建议为 Skype 会议室系统设备 (QoS) 服务质量。</span><span class="sxs-lookup"><span data-stu-id="9238b-134">It is advised to enable Quality of Service (QoS) for Skype Room System devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="9238b-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9238b-135">See also</span></span>
  
[<span data-ttu-id="9238b-136">设备配置：创建新的或编辑现有的</span><span class="sxs-lookup"><span data-stu-id="9238b-136">Device Configuration: Create New or Edit Existing</span></span>](../../help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[<span data-ttu-id="9238b-137">管理服务质量</span><span class="sxs-lookup"><span data-stu-id="9238b-137">Managing Quality of Service</span></span>](../../plan-your-deployment/network-requirements/network-requirements.md#managing-quality-of-service)