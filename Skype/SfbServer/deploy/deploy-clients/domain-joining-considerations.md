---
title: Skype 会议室系统域加入注意事项
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
description: 阅读本主题，了解如何将 Skype 会议室系统家用电脑加入你的域。
ms.openlocfilehash: 49e8c89ed9ddbbd579e7ed30fec6b98a933e3a3f
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768925"
---
# <a name="skype-room-system-domain-joining-considerations"></a><span data-ttu-id="c3fae-103">Skype 会议室系统域加入注意事项</span><span class="sxs-lookup"><span data-stu-id="c3fae-103">Skype Room System domain joining considerations</span></span>
 
<span data-ttu-id="c3fae-104">阅读本主题，了解如何将 Skype 会议室系统家用电脑加入你的域。</span><span class="sxs-lookup"><span data-stu-id="c3fae-104">Read this topic to learn how to join a Skype Room System appliance PC to your domain.</span></span>
  
## <a name="domain-joining-considerations"></a><span data-ttu-id="c3fae-105">域加入注意事项</span><span class="sxs-lookup"><span data-stu-id="c3fae-105">Domain joining considerations</span></span>

<span data-ttu-id="c3fae-106">您可以将 Skype 会议室系统设备电脑加入到 Active Directory 域或将其留在工作组中。</span><span class="sxs-lookup"><span data-stu-id="c3fae-106">You can join the Skype Room System appliance PC to the Active Directory domain or leave it in a Workgroup.</span></span> <span data-ttu-id="c3fae-107">做此决定之前请考虑以下事项：</span><span class="sxs-lookup"><span data-stu-id="c3fae-107">Consider the following points before making this decision:</span></span>
  
- <span data-ttu-id="c3fae-108">域-加入 Skype 会议室系统设备电脑有助于自动导入组织的专用根证书链。</span><span class="sxs-lookup"><span data-stu-id="c3fae-108">Domain-joining the Skype Room System appliance PC helps in importing your organization's private root certificate chain automatically.</span></span>
    
- <span data-ttu-id="c3fae-109">域-加入 Skype 会议室系统设备电脑使您能够授予域用户和组管理权限。</span><span class="sxs-lookup"><span data-stu-id="c3fae-109">Domain-joining the Skype Room System appliance PC enables you to grant domain users and groups administrative rights.</span></span> <span data-ttu-id="c3fae-110">这样做，你不必记住本地计算机级别的管理员帐户密码。</span><span class="sxs-lookup"><span data-stu-id="c3fae-110">By doing so, you will not have to remember the local machine level administrator account password.</span></span>
    
- <span data-ttu-id="c3fae-111">当你将 Skype 会议室系统设备电脑加入域时，需要创建单独的组织单元（OU），以便你可以为所有 Skype 会议室系统计算机对象所在的 OU 提供组策略对象（GPO）排除项。</span><span class="sxs-lookup"><span data-stu-id="c3fae-111">When you join an Skype Room System appliance PC to the domain, it is required that you create a separate Organizational Unit (OU), so that you can provide Group Policy Object (GPO) exclusions to the OU where all the Skype Room System machine objects reside.</span></span> <span data-ttu-id="c3fae-112">执行此操作时，先在 OU 中创建计算机对象，然后再将 Skype 会议室系统设备电脑加入域。</span><span class="sxs-lookup"><span data-stu-id="c3fae-112">When you do this, create machine objects in the OU before joining the Skype Room System appliance PC to the domain.</span></span>
    
- <span data-ttu-id="c3fae-113">许多组织拥有以下 Gpo，这些 Gpo 会影响 Skype 会议室系统设备电脑功能。</span><span class="sxs-lookup"><span data-stu-id="c3fae-113">Many organizations have the following GPOs, which affect Skype Room System appliance PC functions.</span></span> <span data-ttu-id="c3fae-114">确保在 Skype 会议室系统 OU 中覆盖或阻止这些 Gpo 的继承：</span><span class="sxs-lookup"><span data-stu-id="c3fae-114">Ensure that you override or block the inheritance of these GPOs in the Skype Room System OU:</span></span> 
    
  - <span data-ttu-id="c3fae-115">登录会话的超时（自动锁定）</span><span class="sxs-lookup"><span data-stu-id="c3fae-115">Timeout of logon sessions (auto lockout)</span></span>
    
  - <span data-ttu-id="c3fae-116">电源管理相关的策略</span><span class="sxs-lookup"><span data-stu-id="c3fae-116">Power management related policies</span></span>
    
  - <span data-ttu-id="c3fae-117">需要附加身份验证步骤</span><span class="sxs-lookup"><span data-stu-id="c3fae-117">Requiring additional authentication steps</span></span>
    
  - <span data-ttu-id="c3fae-118">拒绝访问本地驱动器</span><span class="sxs-lookup"><span data-stu-id="c3fae-118">Denying access to local drives</span></span>
    
  - <span data-ttu-id="c3fae-119">提示用户网络连接较慢</span><span class="sxs-lookup"><span data-stu-id="c3fae-119">Prompting users for slow network connections</span></span>
    
  - <span data-ttu-id="c3fae-120">登录时启动特定程序</span><span class="sxs-lookup"><span data-stu-id="c3fae-120">Start a certain program at logon</span></span>
    
  - <span data-ttu-id="c3fae-121">在所有加入域的计算机上创建另一个域用户帐户。</span><span class="sxs-lookup"><span data-stu-id="c3fae-121">Create another domain user account on all domain-joined machines.</span></span>
    
  - <span data-ttu-id="c3fae-122">将 Windows 更新推送到 Skype 会议室系统</span><span class="sxs-lookup"><span data-stu-id="c3fae-122">Push Windows Update to Skype Room System</span></span>
    
- <span data-ttu-id="c3fae-123">或者，你可能决定将家用电脑留在工作组中。</span><span class="sxs-lookup"><span data-stu-id="c3fae-123">Alternatively, you might decide to leave the appliance PC in the workgroup.</span></span> <span data-ttu-id="c3fae-124">与桌面版 Skype for Business 客户端一样，这要求你手动导入 Skype 会议室 System 设备电脑上的根证书链。</span><span class="sxs-lookup"><span data-stu-id="c3fae-124">As with the desktop Skype for Business client, this requires you to manually import the root certificate chain on the Skype Room System appliance PC.</span></span> <span data-ttu-id="c3fae-125">如果您的 Skype for Business 部署使用公共证书（例如，Entrust、VeriSign 等），则无需导入根证书链。</span><span class="sxs-lookup"><span data-stu-id="c3fae-125">You're not required to import the root certificate chain if your Skype for Business deployment is using a public certificate (for example, Entrust, VeriSign, and so on).</span></span> 
    
<span data-ttu-id="c3fae-126">如果你计划将 Skype 会议室系统计算机加入到域，以避免将 Skype 会议室系统计算机从无意中加入非有意的 OU （这可能并非来自 Gpo），请确保加入正确的 OU。</span><span class="sxs-lookup"><span data-stu-id="c3fae-126">If you plan to join Skype Room System machines to the domain, to avoid joining Skype Room System machine inadvertently to an unintended OU, which may not be free from GPOs, please ensure you join the correct OU.</span></span> <span data-ttu-id="c3fae-127">你可以使用 Skype 会议室系统计算机中的以下 cmdlet 加入正确的 OU，并且不会收到可能会阻止 LRS 功能的 Gpo。</span><span class="sxs-lookup"><span data-stu-id="c3fae-127">You can use the following cmdlet from the Skype Room System machine to join in the correct OU and does not receive GPOs that might block LRS functionality.</span></span> <span data-ttu-id="c3fae-128">请联系你的系统管理员或 OEM 合作伙伴以运行这些 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="c3fae-128">Contact your system administrator or OEM partner to run these cmdlet:</span></span>
  
```powershell
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

<span data-ttu-id="c3fae-129">即使你创建单独的 OU 并阻止集成，但是有些策略可能会在较高级别引起问题。</span><span class="sxs-lookup"><span data-stu-id="c3fae-129">Even if you create a separate OU and block inheritance, there are some policies which could cause issues at a higher level.</span></span> <span data-ttu-id="c3fae-130">具有“禁止替代”设置的组策略会打败具有“阻止策略继承”设置的 OU。</span><span class="sxs-lookup"><span data-stu-id="c3fae-130">A Group Policy with No Override setting beats an OU with a Block Policy Inheritance setting.</span></span> <span data-ttu-id="c3fae-131">有关详细信息，请参阅有关组策略文档中的 "[阻止策略继承](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10))" 的文章没有替代。</span><span class="sxs-lookup"><span data-stu-id="c3fae-131">For more information, see the article [No Override as Compared to Block Policy Inheritance](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc978255(v=technet.10)) in the Group Policy documentation.</span></span>
  
<span data-ttu-id="c3fae-132">你可能有多种方法来解决这些问题。</span><span class="sxs-lookup"><span data-stu-id="c3fae-132">You may have multiple approaches to solving these problems.</span></span> <span data-ttu-id="c3fae-133">我们建议你咨询 Active Directory 专家来确保为你提供的 OU 具有合适的 GPO 设置或者至少其中不存在上面所述的策略。</span><span class="sxs-lookup"><span data-stu-id="c3fae-133">We advise you to consult with your Active Directory experts to ensure you are provided with an OU that has appropriate GPO settings, or at least an OU in which the previously described policies do not exist.</span></span> <span data-ttu-id="c3fae-134">建议为 Skype 会议室系统设备启用服务质量（QoS）。</span><span class="sxs-lookup"><span data-stu-id="c3fae-134">It is advised to enable Quality of Service (QoS) for Skype Room System devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="c3fae-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c3fae-135">See also</span></span>
  
[<span data-ttu-id="c3fae-136">设备配置：创建新的或编辑现有的</span><span class="sxs-lookup"><span data-stu-id="c3fae-136">Device Configuration: Create New or Edit Existing</span></span>](../../help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[<span data-ttu-id="c3fae-137">管理服务质量</span><span class="sxs-lookup"><span data-stu-id="c3fae-137">Managing Quality of Service</span></span>](../../plan-your-deployment/network-requirements/network-requirements.md#managing-quality-of-service)
