---
title: Skype 会议室系统的可管理性和工具
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
ms.assetid: c336ee9a-1ed8-4f64-9f7f-89549ae24c40
description: 阅读本主题，了解 Skype 会议室系统的管理工具。
ms.openlocfilehash: 81adbb93c71abc201d9099d86e8414a524d85dff
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093546"
---
# <a name="skype-room-system-manageability-and-tools"></a><span data-ttu-id="d7dd5-103">Skype 会议室系统的可管理性和工具</span><span class="sxs-lookup"><span data-stu-id="d7dd5-103">Skype Room System manageability and tools</span></span>
 
<span data-ttu-id="d7dd5-104">阅读本主题，了解 Skype 会议室系统的管理工具。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-104">Read this topic to learn about management tools for Skype Room System.</span></span>
  
## <a name="administrative-portal"></a><span data-ttu-id="d7dd5-105">管理门户</span><span class="sxs-lookup"><span data-stu-id="d7dd5-105">Administrative Portal</span></span>

<span data-ttu-id="d7dd5-106">对于 Skype for Business Server 本地部署，可以使用 Skype 会议室系统管理门户在组织中主动管理和监视 Skype 会议室系统部署。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-106">For Skype for Business Server on-premises deployments, you can use the Skype Room System administrative portal to actively manage and monitor Skype Room System deployments within your organization.</span></span>
  
<span data-ttu-id="d7dd5-107">有关详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="d7dd5-107">See the following article for more details:</span></span>
  
- [<span data-ttu-id="d7dd5-108">在 Skype for Business Server 中部署 SRS v1 管理 Web 门户</span><span class="sxs-lookup"><span data-stu-id="d7dd5-108">Deploy SRS v1 Administrative Web Portal in Skype for Business Server</span></span>](../deploy-conferencing/room-system-v1-administrative-web-portal.md)
    
  
## <a name="exchange-checklist"></a><span data-ttu-id="d7dd5-109">Exchange 清单</span><span class="sxs-lookup"><span data-stu-id="d7dd5-109">Exchange Checklist</span></span>

- <span data-ttu-id="d7dd5-110">确认已设置自动发现，并且内部 DNS A/CNAME 记录可用于 autodiscover.domain.com。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-110">Confirm Autodiscover is set up and an internal DNS A/CNAME RECORD is available for autodiscover.domain.com.</span></span>
    
- <span data-ttu-id="d7dd5-111">Ping 自动发现 (例如 Ping Autodiscover.contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-111">Ping autodiscover (e.g., Ping Autodiscover.contoso.com).</span></span>
    
- <span data-ttu-id="d7dd5-112">使用 Microsoft Connectivity Analyzer 工具测试自动发现服务。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-112">Test your Autodiscover service with the Microsoft Connectivity Analyzer Tool.</span></span> <span data-ttu-id="d7dd5-113">选择第一个测试"I can't log on with Office Outlook"。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-113">Choose the first test, "I can't log on with Office Outlook."</span></span>
    
- <span data-ttu-id="d7dd5-114">如果会议室已有资源邮箱，请扩展 Skype 会议室系统帐户 (页面底部的示例脚本) 。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-114">If the meeting room already has a resource mailbox, extend this account for the Skype Room System (example script at the bottom of the page).</span></span>
    
## <a name="skype-for-business-checklist"></a><span data-ttu-id="d7dd5-115">Skype for Business 清单</span><span class="sxs-lookup"><span data-stu-id="d7dd5-115">Skype for Business Checklist</span></span>

- <span data-ttu-id="d7dd5-116">运行以下工具：</span><span class="sxs-lookup"><span data-stu-id="d7dd5-116">Run the following tools:</span></span>
    
  - <span data-ttu-id="d7dd5-117">Skype for Business 最佳做法分析器</span><span class="sxs-lookup"><span data-stu-id="d7dd5-117">Skype for Business Best Practices Analyzer</span></span>     
  - <span data-ttu-id="d7dd5-118">Excel (Skype for Business 运行状况分析工具) </span><span class="sxs-lookup"><span data-stu-id="d7dd5-118">Skype for Business Health Analysis Tool (Excel)</span></span>    
  - <span data-ttu-id="d7dd5-119">Skype for 业务连接 Analyzer 32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="d7dd5-119">Skype for Business Connectivity Analyzer 32-Bit or 64-Bit</span></span>
    
- <span data-ttu-id="d7dd5-120">Review [Useful new troubleshooting and analysis tools for Office 365](/archive/blogs/educloud/useful-new-troubleshooting-and-analysis-tools-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="d7dd5-120">Review [Useful new troubleshooting and analysis tools for Office 365](/archive/blogs/educloud/useful-new-troubleshooting-and-analysis-tools-for-office-365).</span></span> <span data-ttu-id="d7dd5-121">确认你有 Skype for Business 池和 Office Web Apps 服务器，并且可以使用 Skype for Business 客户端共享 PowerPoint 平台。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-121">Confirm you have a Skype for Business pool and an Office Web Apps server and can share a PowerPoint deck using the Skype for Business client.</span></span>
    
- <span data-ttu-id="d7dd5-122">如果会议室已有资源邮箱，请为 Skype for Business 启用该邮箱。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-122">If the meeting room already has a resource mailbox, enable it for Skype for Business.</span></span>
    
- <span data-ttu-id="d7dd5-123">如果需要，请求为会议室 (DID) 电话号码，并更新 Active Directory 工具中的"常规电话"字段。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-123">If required, request a DID (phone number) for the Meeting Room System, and update the General Telephone field in the Active Directory tool.</span></span>
    
## <a name="network"></a><span data-ttu-id="d7dd5-124">网络</span><span class="sxs-lookup"><span data-stu-id="d7dd5-124">Network</span></span>

- <span data-ttu-id="d7dd5-125">请确保 Skype 会议室系统具有有线网络连接。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-125">Make sure you have a wired network connection for the Skype Room System.</span></span>
    
- <span data-ttu-id="d7dd5-126">阅读 Skype for Business 网络规划指南。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-126">Read the Network Planning Guide for Skype for Business.</span></span>
    
- <span data-ttu-id="d7dd5-127">从 Skype for Business 合作伙伴请求 Skype for Business 网络评估。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-127">Request a Skype for Business network assessment from a Skype for Business partner.</span></span>
    
- <span data-ttu-id="d7dd5-128">阅读 Excel) 中的 Skype for Business 运行状况分析工具中捕获 (数据。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-128">Read through the performance data captured in the Skype for Business Health Analysis Tool (Excel).</span></span>
    
- <span data-ttu-id="d7dd5-129">运行网络分析工具。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-129">Run the Network Analysis Tool.</span></span>
    
- <span data-ttu-id="d7dd5-130">运行预调用诊断工具。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-130">Run the Pre-Call Diagnostics Tool.</span></span>
    
## <a name="skype-room-system-security"></a><span data-ttu-id="d7dd5-131">Skype 会议室系统安全性</span><span class="sxs-lookup"><span data-stu-id="d7dd5-131">Skype Room System Security</span></span>

<span data-ttu-id="d7dd5-132">Skype 会议室系统是一个嵌入系统，可以使用 Skype for Business 安全模型、权限管理和 SCOM 等管理工具完全集成在 Windows 部署中。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-132">Skype Room System is an embedded system that can be fully integrated in a Windows deployment, using the Skype for Business security model, rights management, and management tools such as SCOM.</span></span> <span data-ttu-id="d7dd5-133">这些功能包括： </span><span class="sxs-lookup"><span data-stu-id="d7dd5-133">Features include:</span></span>
  
- <span data-ttu-id="d7dd5-134">防止在用户模式下写入磁盘的写入筛选器</span><span class="sxs-lookup"><span data-stu-id="d7dd5-134">A Write Filter to prevent disk writes in user mode</span></span> 
    
- <span data-ttu-id="d7dd5-135">应用保险箱，可防止未经授权的应用运行。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-135">App Locker to prevent unauthorized apps from running.</span></span> <span data-ttu-id="d7dd5-136">在用户模式下禁用所有 USB 端口。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-136">All USB ports are disabled in user mode.</span></span>
    
  - <span data-ttu-id="d7dd5-137">Skype 会议室系统硬件上没有标准应用或查看器。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-137">No standard apps or viewers reside on the Skype Room System hardware.</span></span> <span data-ttu-id="d7dd5-138">所有内容都通过 HTTP 或 RDP 协议呈现。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-138">All content is rendered via HTTP or RDP protocols.</span></span>
    
  - <span data-ttu-id="d7dd5-139">电脑运行 Windows Embedded Standard 7 操作系统。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-139">The appliance PC runs the Windows Embedded Standard 7 operating system.</span></span> <span data-ttu-id="d7dd5-140">所有硬件（包括设备）都由 OEM 合作伙伴提供。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-140">All hardware, including devices, is provided by OEM partners.</span></span>
    
  - <span data-ttu-id="d7dd5-141">AD DS (Active Directory 域服务的可选域) ，从而实现本地安全帐户管理和控制。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-141">Optional Domain Join to Active Directory Domain Services (AD DS), enabling local security account management and control.</span></span>
    
- <span data-ttu-id="d7dd5-142">您还可以使用 Skype for Business 管理中心管理本地管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-142">You can also manage the local admin account using the Skype for Business admin center.</span></span>
    
- <span data-ttu-id="d7dd5-143">Skype 会议室系统通过标准 Microsoft 更新过程进行更新。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-143">Skype Room System is updated through standard Microsoft Update processes.</span></span>
    
- <span data-ttu-id="d7dd5-144">Skype 会议室系统与 Skype for Business 连接。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-144">Skype Room System connects with Skype for Business.</span></span>
    
  - <span data-ttu-id="d7dd5-145">Skype for Business 将端到端加密和授权用于所有通信模式</span><span class="sxs-lookup"><span data-stu-id="d7dd5-145">Skype for Business uses end-to-end encryption and authorization for all modes of communication</span></span>
    
  - <span data-ttu-id="d7dd5-146">Skype 会议室系统支持 Skype for Business 安全性和合规性标准。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-146">Skype Room System supports Skype for Business security and compliance standards.</span></span> <span data-ttu-id="d7dd5-147">有关详细信息[，请参阅 Plan for security in Skype For Business Server。](../../plan-your-deployment/security/security.md)</span><span class="sxs-lookup"><span data-stu-id="d7dd5-147">See [Plan for security in Skype For Business Server](../../plan-your-deployment/security/security.md) for more information.</span></span>
    
## <a name="license"></a><span data-ttu-id="d7dd5-148">许可证</span><span class="sxs-lookup"><span data-stu-id="d7dd5-148">License</span></span>

<span data-ttu-id="d7dd5-149">验证是否使用 KMS 激活软件。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-149">Verify that you use a KMS for activating software.</span></span> <span data-ttu-id="d7dd5-150">如果是这样，你可能需要检查或添加 Skype for Business 客户端 KMS 密钥。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-150">If so, you might need to check or add the Skype for Business client KMS key to it.</span></span> <span data-ttu-id="d7dd5-151">如果不使用 KMS，请为 Skype for Business 客户端 MAK 请求批量许可密钥。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-151">If you aren't using KMS, then request the volume licensing key for the Skype for Business client MAK.</span></span>
  
## <a name="license-keys"></a><span data-ttu-id="d7dd5-152">许可证密钥</span><span class="sxs-lookup"><span data-stu-id="d7dd5-152">License keys</span></span>

<span data-ttu-id="d7dd5-153">Skype 会议室系统在后台运行 Skype for Business 桌面客户端。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-153">Skype Room System runs the Skype for Business desktop client in the background.</span></span> <span data-ttu-id="d7dd5-154">如果 Skype 会议室系统是域成员，它将发现你的 KMS。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-154">If Skype Room System is a domain member, it will discover your KMS.</span></span> <span data-ttu-id="d7dd5-155"> (并且如果具有批量许可 KMS 密钥，它将在系统) 。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-155">(and if it has the Volume Licensing KMS Key it will activate automatically).</span></span> <span data-ttu-id="d7dd5-156">批量许可还提供 MAK，在显示 xxxxx-xxxxx-xxxxx-xxxxx 时输入此 MAK。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-156">Volume Licensing also provides a MAK, which you enter as it displays xxxxx-xxxxx-xxxxx-xxxxx.</span></span> <span data-ttu-id="d7dd5-157"> (需要 Internet 访问权限才能使用 MAK（而不是 KMS) ）。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-157">(You need Internet access to activate using MAK but not KMS).</span></span> <span data-ttu-id="d7dd5-158">有关详细信息，请参阅 Volume activation of Office 2013。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-158">For more information, see Volume activation of Office 2013.</span></span>
  
- <span data-ttu-id="d7dd5-159">若要输入 MAK 密钥，请转到 OEM 设置 \> SRS 许可工具。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-159">To enter the MAK key, go to OEM Settings \> SRS Licensing Tool.</span></span> <span data-ttu-id="d7dd5-160">单击“检查状态”。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-160">Click Check Status.</span></span> <span data-ttu-id="d7dd5-161">当状态显示"产品未激活"时，输入密钥。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-161">When the status says "product isn't activated," enter the key.</span></span>
    
- <span data-ttu-id="d7dd5-162">如果在激活期间收到一个错误，指出"软件许可服务报告产品密钥无效"，请验证：</span><span class="sxs-lookup"><span data-stu-id="d7dd5-162">If during activation you get an error that says, "'The Software Licensing Service reported that the product key is invalid," then verify that:</span></span>
    
  - <span data-ttu-id="d7dd5-163">键输入正确。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-163">The key was entered correctly.</span></span>
    
  - <span data-ttu-id="d7dd5-164">你输入了 Skype for Business MAK 密钥，而不是另一个密钥。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-164">You entered the Skype for Business MAK key and not another key.</span></span>
    
  - <span data-ttu-id="d7dd5-165">系统可以访问 Internet。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-165">The system has Internet access.</span></span>
    
- <span data-ttu-id="d7dd5-166">可以通过电话激活，但必须先尝试使用 SRS 许可工具激活。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-166">You can activate via telephone but must have attempted to activate using the SRS Licensing Tool first.</span></span> <span data-ttu-id="d7dd5-167">若要通过电话激活，请启动测试 (而不是测试呼叫，因为测试) 。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-167">To activate via telephone, start a test meeting (not a test call as that is too short).</span></span> <span data-ttu-id="d7dd5-168">在"Office 激活向导"中，选择"电话激活"，致电 Microsoft，键入长号，然后输入响应。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-168">In the Office Activation Wizard, select Telephone Activation, call Microsoft, type the long number, and enter a response.</span></span>
    
## <a name="certificate-authority"></a><span data-ttu-id="d7dd5-169">证书颁发机构</span><span class="sxs-lookup"><span data-stu-id="d7dd5-169">Certificate Authority</span></span>

<span data-ttu-id="d7dd5-170">确认用于颁发 Office Web Apps Server 2013 证书的证书颁发机构在证书吊销列表属性中包含 HTTP 路径。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-170">Confirm the Certificate Authority used to issue the Office Web Apps Server 2013 certificate has an HTTP path included in the Certificate Revocation List property.</span></span>
  
<span data-ttu-id="d7dd5-171">如果使用 Skype for Business Server， (.crt) 文件导入 Skype 会议室系统。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-171">Import the Certificate file (.crt) to the Skype Room System if using Skype for Business Server.</span></span> <span data-ttu-id="d7dd5-172">它很容易从 CA 服务器的 CertEnroll 共享，或在任何加入域的电脑的受信任的根文件夹中获取。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-172">It's easily obtained from the CertEnroll share of the CA server, or in the Trusted Root folder of any domain joined PC.</span></span>
  
## <a name="certificates"></a><span data-ttu-id="d7dd5-173">证书</span><span class="sxs-lookup"><span data-stu-id="d7dd5-173">Certificates</span></span>

<span data-ttu-id="d7dd5-174">验证证书颁发机构是否具有证书吊销列表的 http 路径。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-174">Verify your Certificate Authority has an http path for the Certificate Revocation List.</span></span> <span data-ttu-id="d7dd5-175">如果没有，请更新 CA 以包含一个 CA。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-175">If not, update your CA to include one.</span></span>
  
<span data-ttu-id="d7dd5-176">在"系统设置证书管理器"下的 Skype 会议室系统的管理员设置 \> 中安装证书。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-176">Install certificates in the admin setup of the Skype Room System under System Settings \> Certificate Manager.</span></span> <span data-ttu-id="d7dd5-177">内部证书需要企业根 CA。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-177">You need the Enterprise Root CA for your internal certificate.</span></span>
  
<span data-ttu-id="d7dd5-178">获取所需的证书的一种方式是发现颁发证书的 CA。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-178">One way to obtain the certificates you need is to discover the CA that issued your certificates.</span></span> <span data-ttu-id="d7dd5-179">对于 Skype for Business Server，在 Skype for Business 中的电脑上，单击"设置 \> ""工具 \> ""电话拨入式会议设置"。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-179">For Skype for Business Server, on a PC in Skype for Business, click Settings \> Tools \> Dial-in Conference Settings.</span></span> <span data-ttu-id="d7dd5-180">这将打开由颁发内部证书的 CA 保护的网页。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-180">This opens a web page secured by the CA that issued the internal certificates.</span></span> <span data-ttu-id="d7dd5-181">单击浏览器地址栏上的"锁定"图标以显示安全报告。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-181">Click the Lock icon on the browser address bar to display a security report.</span></span> <span data-ttu-id="d7dd5-182">单击"查看证书"并检查 CRL 分发点属性。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-182">Click View Certificates and examine the CRL Distribution Point property.</span></span> <span data-ttu-id="d7dd5-183">第二个 CN 参数应为 CA 的服务器名称。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-183">The second CN parameter should be the server name of the CA.</span></span> <span data-ttu-id="d7dd5-184">现在打开该地址 \\ \< CA Server Name \> \CertEnroll 的 Windows 资源管理器。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-184">Now open Windows Explorer for that address \\\< CA Server Name \>\CertEnroll.</span></span> <span data-ttu-id="d7dd5-185">将两个 .crl 文件和 .crt 文件复制到闪存驱动器，并放在 SMART 板的左侧。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-185">Copy the two .crl files and the .crt file to a flash drive and put it in the left hand side of the SMART board.</span></span>
  
<span data-ttu-id="d7dd5-186">将 .crt 文件导入到"受信任的会议室证书颁发机构"文件夹下的 Skype 会议室系统。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-186">Import the .crt file to the Skype Room System under Trusted Room Certification Authority folder.</span></span>
  
<span data-ttu-id="d7dd5-187">在 Skype 会议室系统中的中间证书颁发机构文件夹下导入 .crl 文件。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-187">Import the .crl files on the Skype Room System under the Intermediate Certificate Authorities folder.</span></span> <span data-ttu-id="d7dd5-188"> (你需要将证书管理器中的文件扩展名筛选器更改为 .crl，以查看) 。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-188">(You need to change the file extension filter in Certificate Manager to .crl to see the files).</span></span>
  
<span data-ttu-id="d7dd5-189">注意：Office Web Apps 2013 服务器可能与 Skype for Business 共享同一 CA。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-189">Note: The Office Web Apps 2013 server may share the same CA as Skype for Business.</span></span> <span data-ttu-id="d7dd5-190">如果没有，你将无法在会议中共享 PowerPoint。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-190">If it doesn't you won't be able to share PowerPoint in a meeting.</span></span> <span data-ttu-id="d7dd5-191">与 IT 核实，从 CA 网络共享 CertEnroll 获取 CRT 和 CRL 文件，如上所述。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-191">Check with IT and obtain the CRT and CRL files off the CA network share CertEnroll as explained above.</span></span> 
  
<span data-ttu-id="d7dd5-192">域成员身份可以简化一些操作，因为你可以将 Skype 会议室系统视为 Windows 系统，并且它可以依赖 Active Directory 来了解某些证书方面。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-192">Domain membership can simplify some things because you can treat the Skype Room System as a Windows system and it can rely on Active Directory for some of the certificate aspects.</span></span> <span data-ttu-id="d7dd5-193">但是，最好手动管理它。</span><span class="sxs-lookup"><span data-stu-id="d7dd5-193">However, it's best to manually manage this.</span></span>
