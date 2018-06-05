---
title: Skype 会议室系统域加入注意事项
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/4/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3034fdcb-7c89-42c4-9c5e-13400e82d88f
description: 阅读本主题，了解如何将 Skype 会议室系统家用电脑加入你的域。
ms.openlocfilehash: ffc55984df3b42b06f4db8faa6a286ea41e99480
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568659"
---
# <a name="skype-room-system-domain-joining-considerations"></a><span data-ttu-id="bc86a-103">Skype 会议室系统域加入注意事项</span><span class="sxs-lookup"><span data-stu-id="bc86a-103">Skype Room System domain joining considerations</span></span>
 
<span data-ttu-id="bc86a-104">阅读本主题，了解如何将 Skype 会议室系统家用电脑加入你的域。</span><span class="sxs-lookup"><span data-stu-id="bc86a-104">Read this topic to learn how to join a Skype Room System appliance PC to your domain.</span></span>
  
## <a name="domain-joining-considerations"></a><span data-ttu-id="bc86a-105">域加入注意事项</span><span class="sxs-lookup"><span data-stu-id="bc86a-105">Domain joining considerations</span></span>

<span data-ttu-id="bc86a-106">可以将 Skype 会议室系统装置 PC 加入到 Active Directory 域或将其保留在工作组。</span><span class="sxs-lookup"><span data-stu-id="bc86a-106">You can join the Skype Room System appliance PC to the Active Directory domain or leave it in a Workgroup.</span></span> <span data-ttu-id="bc86a-107">做此决定之前请考虑以下事项：</span><span class="sxs-lookup"><span data-stu-id="bc86a-107">Consider the following points before making this decision:</span></span>
  
- <span data-ttu-id="bc86a-108">域加入 Skype 会议室系统装置 PC 帮助自动导入您的组织的私有根证书链。</span><span class="sxs-lookup"><span data-stu-id="bc86a-108">Domain-joining the Skype Room System appliance PC helps in importing your organization's private root certificate chain automatically.</span></span>
    
- <span data-ttu-id="bc86a-109">域加入 Skype 会议室系统装置 PC 使您能够授予域用户和组管理权限。</span><span class="sxs-lookup"><span data-stu-id="bc86a-109">Domain-joining the Skype Room System appliance PC enables you to grant domain users and groups administrative rights.</span></span> <span data-ttu-id="bc86a-110">这样做，你不必记住本地计算机级别的管理员帐户密码。</span><span class="sxs-lookup"><span data-stu-id="bc86a-110">By doing so, you will not have to remember the local machine level administrator account password.</span></span>
    
- <span data-ttu-id="bc86a-111">Skype 会议室系统装置 PC 加入域，时，需要您创建单独组织单位 (OU)，以便您可以为所有的 Skype 会议室系统计算机对象所在的 OU 提供组策略对象 (GPO) 排除。</span><span class="sxs-lookup"><span data-stu-id="bc86a-111">When you join an Skype Room System appliance PC to the domain, it is required that you create a separate Organizational Unit (OU), so that you can provide Group Policy Object (GPO) exclusions to the OU where all the Skype Room System machine objects reside.</span></span> <span data-ttu-id="bc86a-112">当执行此操作时，创建的 OU 中计算机对象 Skype 会议室系统装置 PC 加入域之前。</span><span class="sxs-lookup"><span data-stu-id="bc86a-112">When you do this, create machine objects in the OU before joining the Skype Room System appliance PC to the domain.</span></span>
    
- <span data-ttu-id="bc86a-113">许多组织的以下 Gpo，这会影响 Skype 会议室系统装置 PC 函数。</span><span class="sxs-lookup"><span data-stu-id="bc86a-113">Many organizations have the following GPOs, which affect Skype Room System appliance PC functions.</span></span> <span data-ttu-id="bc86a-114">确保您重写或阻止的 Skype 会议室系统 OU 中的这些 Gpo 的继承：</span><span class="sxs-lookup"><span data-stu-id="bc86a-114">Ensure that you override or block the inheritance of these GPOs in the Skype Room System OU:</span></span> 
    
  - <span data-ttu-id="bc86a-115">登录会话的超时（自动锁定）</span><span class="sxs-lookup"><span data-stu-id="bc86a-115">Timeout of logon sessions (auto lockout)</span></span>
    
  - <span data-ttu-id="bc86a-116">电源管理相关的策略</span><span class="sxs-lookup"><span data-stu-id="bc86a-116">Power management related policies</span></span>
    
  - <span data-ttu-id="bc86a-117">需要附加身份验证步骤</span><span class="sxs-lookup"><span data-stu-id="bc86a-117">Requiring additional authentication steps</span></span>
    
  - <span data-ttu-id="bc86a-118">拒绝访问本地驱动器</span><span class="sxs-lookup"><span data-stu-id="bc86a-118">Denying access to local drives</span></span>
    
  - <span data-ttu-id="bc86a-119">提示用户网络连接较慢</span><span class="sxs-lookup"><span data-stu-id="bc86a-119">Prompting users for slow network connections</span></span>
    
  - <span data-ttu-id="bc86a-120">登录时启动特定程序</span><span class="sxs-lookup"><span data-stu-id="bc86a-120">Start a certain program at logon</span></span>
    
  - <span data-ttu-id="bc86a-121">在所有加入域的计算机上创建另一个域用户帐户。</span><span class="sxs-lookup"><span data-stu-id="bc86a-121">Create another domain user account on all domain-joined machines.</span></span>
    
  - <span data-ttu-id="bc86a-122">推送到 Skype 会议室系统的 Windows 更新</span><span class="sxs-lookup"><span data-stu-id="bc86a-122">Push Windows Update to Skype Room System</span></span>
    
- <span data-ttu-id="bc86a-123">或者，你可能决定将家用电脑留在工作组中。</span><span class="sxs-lookup"><span data-stu-id="bc86a-123">Alternatively, you might decide to leave the appliance PC in the workgroup.</span></span> <span data-ttu-id="bc86a-124">与桌面 Skype 业务客户端，这也需要您手动导入根证书链 Skype 会议室系统装置 PC 上。</span><span class="sxs-lookup"><span data-stu-id="bc86a-124">As with the desktop Skype for Business client, this requires you to manually import the root certificate chain on the Skype Room System appliance PC.</span></span> <span data-ttu-id="bc86a-125">您不需要导入根证书链，如果您的业务部署 Skype 正在使用的公共证书 （例如，Entrust、 VeriSign、 等）。</span><span class="sxs-lookup"><span data-stu-id="bc86a-125">You're not required to import the root certificate chain if your Skype for Business deployment is using a public certificate (for example, Entrust, VeriSign, and so on).</span></span> 
    
<span data-ttu-id="bc86a-126">如果您打算将 Skype 会议室系统计算机加入到域，以避免无意中将 Skype 会议室系统计算机联接意外的 OU，这可能不是从 Gpo 免费，请确保您加入正确的 OU。</span><span class="sxs-lookup"><span data-stu-id="bc86a-126">If you plan to join Skype Room System machines to the domain, to avoid joining Skype Room System machine inadvertently to an unintended OU, which may not be free from GPOs, please ensure you join the correct OU.</span></span> <span data-ttu-id="bc86a-127">您可以使用以下 cmdlet 从 Skype 会议室系统机的正确的 OU 中加入并不会收到可能阻止 LRS 功能的 Gpo。</span><span class="sxs-lookup"><span data-stu-id="bc86a-127">You can use the following cmdlet from the Skype Room System machine to join in the correct OU and does not receive GPOs that might block LRS functionality.</span></span> <span data-ttu-id="bc86a-128">请联系你的系统管理员或 OEM 合作伙伴以运行这些 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="bc86a-128">Contact your system administrator or OEM partner to run these cmdlet:</span></span>
  
```
$username = "contso.local\LRS01"
$password = ConvertTo-SecureString "password123" -AsPlainText -Force
$myCred = New-Object System.Management.Automation.PSCredential $username, $password
Add-Computer -DomainName contoso.local -Credential $mycred -OUPath "OU=LyncRoomSystem,OU=Resources,DC=CONTOSO,DC=LOCAL"
```

<span data-ttu-id="bc86a-129">即使你创建单独的 OU 并阻止集成，但是有些策略可能会在较高级别引起问题。</span><span class="sxs-lookup"><span data-stu-id="bc86a-129">Even if you create a separate OU and block inheritance, there are some policies which could cause issues at a higher level.</span></span> <span data-ttu-id="bc86a-130">具有“禁止替代”设置的组策略会打败具有“阻止策略继承”设置的 OU。</span><span class="sxs-lookup"><span data-stu-id="bc86a-130">A Group Policy with No Override setting beats an OU with a Block Policy Inheritance setting.</span></span> <span data-ttu-id="bc86a-131">详细信息，请参阅文章"无重写 as 相比收件人阻止策略继承"中的组策略文档http://technet.microsoft.com/en-us/library/cc978255.aspx。</span><span class="sxs-lookup"><span data-stu-id="bc86a-131">For more information, see the article "No Override as Compared to Block Policy Inheritance" in the Group Policy documentation at http://technet.microsoft.com/en-us/library/cc978255.aspx.</span></span>
  
<span data-ttu-id="bc86a-132">你可能有多种方法来解决这些问题。</span><span class="sxs-lookup"><span data-stu-id="bc86a-132">You may have multiple approaches to solving these problems.</span></span> <span data-ttu-id="bc86a-133">我们建议你咨询 Active Directory 专家来确保为你提供的 OU 具有合适的 GPO 设置或者至少其中不存在上面所述的策略。</span><span class="sxs-lookup"><span data-stu-id="bc86a-133">We advise you to consult with your Active Directory experts to ensure you are provided with an OU that has appropriate GPO settings, or at least an OU in which the previously described policies do not exist.</span></span> <span data-ttu-id="bc86a-134">建议为 Skype 会议室系统设备启用服务质量 (QoS)。</span><span class="sxs-lookup"><span data-stu-id="bc86a-134">It is advised to enable Quality of Service (QoS) for Skype Room System devices.</span></span>

## <a name="see-also"></a><span data-ttu-id="bc86a-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bc86a-135">See also</span></span>
  
[<span data-ttu-id="bc86a-136">设备配置： 创建新的或编辑现有的</span><span class="sxs-lookup"><span data-stu-id="bc86a-136">Device Configuration: Create New or Edit Existing</span></span>](../../help-topics/help-lscp/device-configuration-create-new-or-edit-existing.md)

[<span data-ttu-id="bc86a-137">管理服务质量</span><span class="sxs-lookup"><span data-stu-id="bc86a-137">Managing Quality of Service</span></span>](../../plan-your-deployment/network-requirements/network-requirements.md#managing-quality-of-service)
