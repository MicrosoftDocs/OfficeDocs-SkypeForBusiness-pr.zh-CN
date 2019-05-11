---
title: Skype 会议室系统可管理性和工具
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c336ee9a-1ed8-4f64-9f7f-89549ae24c40
description: 阅读本主题，了解适用于 Skype 会议室系统的管理工具。
ms.openlocfilehash: 8a1d9f3e3d1c569a0473ca92cda6761ce63f0096
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33895031"
---
# <a name="skype-room-system-manageability-and-tools"></a><span data-ttu-id="9cda7-103">Skype 会议室系统可管理性和工具</span><span class="sxs-lookup"><span data-stu-id="9cda7-103">Skype Room System manageability and tools</span></span>
 
<span data-ttu-id="9cda7-104">阅读本主题，了解适用于 Skype 会议室系统的管理工具。</span><span class="sxs-lookup"><span data-stu-id="9cda7-104">Read this topic to learn about management tools for Skype Room System.</span></span>
  
## <a name="administrative-portal"></a><span data-ttu-id="9cda7-105">管理门户</span><span class="sxs-lookup"><span data-stu-id="9cda7-105">Administrative Portal</span></span>

<span data-ttu-id="9cda7-106">对于业务服务器的本地部署的 Skype，您可以使用 Skype 会议室系统管理门户主动管理和监视组织内的 Skype 会议室系统部署。</span><span class="sxs-lookup"><span data-stu-id="9cda7-106">For Skype for Business Server on-premises deployments, you can use the Skype Room System administrative portal to actively manage and monitor Skype Room System deployments within your organization.</span></span>
  
<span data-ttu-id="9cda7-107">请参阅以下文章，获取更多详细信息：</span><span class="sxs-lookup"><span data-stu-id="9cda7-107">See the following article for more details:</span></span>
  
- [<span data-ttu-id="9cda7-108">为业务服务器部署中 Skype SR v1 管理 Web 门户</span><span class="sxs-lookup"><span data-stu-id="9cda7-108">Deploy SRS v1 Administrative Web Portal in Skype for Business Server</span></span>](../deploy-conferencing/room-system-v1-administrative-web-portal.md)
    
## <a name="system-center-operations-manager"></a><span data-ttu-id="9cda7-109">System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="9cda7-109">System Center Operations Manager</span></span>

<span data-ttu-id="9cda7-110">Skype 会议室系统可以监控通过 System Center Operations Manager (SCOM) 通过下载[Skype 会议室系统管理包](https://www.microsoft.com/download/details.aspx?id=42320)和 SCOM 服务器上安装它。</span><span class="sxs-lookup"><span data-stu-id="9cda7-110">Skype Room System can be monitored through the System Center Operations Manager (SCOM) by downloading the [Skype Room System Management Pack](https://www.microsoft.com/download/details.aspx?id=42320) and installing it on your SCOM server.</span></span> <span data-ttu-id="9cda7-111">您可以使用 SCOM 设置通知、 监视 Skype 会议室系统的运行状况、 生成正常运行时间报告以及更多。</span><span class="sxs-lookup"><span data-stu-id="9cda7-111">You can use SCOM to set alerts, monitor the health of Skype Room System, generate uptime reports, and much more.</span></span> <span data-ttu-id="9cda7-112">Skype 会议室系统附带的可配置为指向 SCOM 服务器的预安装监控代理。</span><span class="sxs-lookup"><span data-stu-id="9cda7-112">Skype Room System comes with a pre-installed monitoring agent that can be configured to point to SCOM server.</span></span> <span data-ttu-id="9cda7-113">请参阅 Skype 会议室系统制造商提供的安装指南了解如何配置 Skype 会议室系统上的监控代理。</span><span class="sxs-lookup"><span data-stu-id="9cda7-113">Refer to the installation guide provided by your Skype Room System manufacturer to know how to configure the monitoring agent on Skype Room System.</span></span>
  
## <a name="exchange-checklist"></a><span data-ttu-id="9cda7-114">Exchange 清单</span><span class="sxs-lookup"><span data-stu-id="9cda7-114">Exchange Checklist</span></span>

- <span data-ttu-id="9cda7-115">确认已设置自动发现并且内部 DNS A/CNAME 记录可用于 autodiscover.domain.com。</span><span class="sxs-lookup"><span data-stu-id="9cda7-115">Confirm Autodiscover is set up and an internal DNS A/CNAME RECORD is available for autodiscover.domain.com.</span></span>
    
- <span data-ttu-id="9cda7-116">Ping 自动发现（例如，Ping Autodiscover.contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="9cda7-116">Ping autodiscover (e.g., Ping Autodiscover.contoso.com).</span></span>
    
- <span data-ttu-id="9cda7-117">使用 Microsoft Connectivity Analyzer 工具测试你的自动发现服务。</span><span class="sxs-lookup"><span data-stu-id="9cda7-117">Test your Autodiscover service with the Microsoft Connectivity Analyzer Tool.</span></span> <span data-ttu-id="9cda7-118">选择第一个测试，"我不能登录与 Office Outlook。"</span><span class="sxs-lookup"><span data-stu-id="9cda7-118">Choose the first test, "I can't log on with Office Outlook."</span></span>
    
- <span data-ttu-id="9cda7-119">如果已资源邮箱会议室，扩展此帐户的 Skype 会议室系统 （页面底部的示例脚本）。</span><span class="sxs-lookup"><span data-stu-id="9cda7-119">If the meeting room already has a resource mailbox, extend this account for the Skype Room System (example script at the bottom of the page).</span></span>
    
## <a name="skype-for-business-checklist"></a><span data-ttu-id="9cda7-120">Skype 的业务清单</span><span class="sxs-lookup"><span data-stu-id="9cda7-120">Skype for Business Checklist</span></span>

- <span data-ttu-id="9cda7-121">运行以下工具：</span><span class="sxs-lookup"><span data-stu-id="9cda7-121">Run the following tools:</span></span>
    
  - <span data-ttu-id="9cda7-122">业务最佳做法分析器的 Skype</span><span class="sxs-lookup"><span data-stu-id="9cda7-122">Skype for Business Best Practices Analyzer</span></span>     
  - <span data-ttu-id="9cda7-123">Skype 业务运行状况分析工具 (Excel)</span><span class="sxs-lookup"><span data-stu-id="9cda7-123">Skype for Business Health Analysis Tool (Excel)</span></span>    
  - <span data-ttu-id="9cda7-124">Skype 用于 Business Connectivity Analyzer 32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="9cda7-124">Skype for Business Connectivity Analyzer 32-Bit or 64-Bit</span></span>
    
- <span data-ttu-id="9cda7-125">查看[有用的新疑难解答和分析工具，用于 Office 365](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/)。</span><span class="sxs-lookup"><span data-stu-id="9cda7-125">Review [Useful new troubleshooting and analysis tools for Office 365](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/).</span></span> <span data-ttu-id="9cda7-126">确认您具有业务池和 Office Web Apps server Skype 并可以共享 PowerPoint 系列时使用 for Business 客户端的 Skype。</span><span class="sxs-lookup"><span data-stu-id="9cda7-126">Confirm you have a Skype for Business pool and an Office Web Apps server and can share a PowerPoint deck using the Skype for Business client.</span></span>
    
- <span data-ttu-id="9cda7-127">如果已资源邮箱会议室，启用它 for Business 的 Skype。</span><span class="sxs-lookup"><span data-stu-id="9cda7-127">If the meeting room already has a resource mailbox, enable it for Skype for Business.</span></span>
    
- <span data-ttu-id="9cda7-128">如果需要，请为会议室系统请求 DID（电话号码）并在 Active Directory 工具中更新“常规电话”字段。</span><span class="sxs-lookup"><span data-stu-id="9cda7-128">If required, request a DID (phone number) for the Meeting Room System, and update the General Telephone field in the Active Directory tool.</span></span>
    
## <a name="network"></a><span data-ttu-id="9cda7-129">网络</span><span class="sxs-lookup"><span data-stu-id="9cda7-129">Network</span></span>

- <span data-ttu-id="9cda7-130">请确保 Skype 会议室系统具有有线的网络连接。</span><span class="sxs-lookup"><span data-stu-id="9cda7-130">Make sure you have a wired network connection for the Skype Room System.</span></span>
    
- <span data-ttu-id="9cda7-131">阅读 for Business 的规划指南 Skype 网络。</span><span class="sxs-lookup"><span data-stu-id="9cda7-131">Read the Network Planning Guide for Skype for Business.</span></span>
    
- <span data-ttu-id="9cda7-132">从业务合作伙伴 Skype 请求业务网络评估 Skype。</span><span class="sxs-lookup"><span data-stu-id="9cda7-132">Request a Skype for Business network assessment from a Skype for Business partner.</span></span>
    
- <span data-ttu-id="9cda7-133">通读 Skype 中捕获的业务运行状况分析工具 (Excel) 的性能数据。</span><span class="sxs-lookup"><span data-stu-id="9cda7-133">Read through the performance data captured in the Skype for Business Health Analysis Tool (Excel).</span></span>
    
- <span data-ttu-id="9cda7-134">运行网络分析工具。</span><span class="sxs-lookup"><span data-stu-id="9cda7-134">Run the Network Analysis Tool.</span></span>
    
- <span data-ttu-id="9cda7-135">运行预呼叫诊断工具。</span><span class="sxs-lookup"><span data-stu-id="9cda7-135">Run the Pre-Call Diagnostics Tool.</span></span>
    
## <a name="skype-room-system-security"></a><span data-ttu-id="9cda7-136">Skype 会议室 System 安全</span><span class="sxs-lookup"><span data-stu-id="9cda7-136">Skype Room System Security</span></span>

<span data-ttu-id="9cda7-137">Skype 会议室系统是嵌入的系统，可以完全集成在 Windows 部署中，使用 Skype 业务安全模型、 权限管理和管理工具，如 SCOM。</span><span class="sxs-lookup"><span data-stu-id="9cda7-137">Skype Room System is an embedded system that can be fully integrated in a Windows deployment, using the Skype for Business security model, rights management, and management tools such as SCOM.</span></span> <span data-ttu-id="9cda7-138">功能包括：</span><span class="sxs-lookup"><span data-stu-id="9cda7-138">Features include:</span></span>
  
- <span data-ttu-id="9cda7-139">写入筛选器，可防止磁盘在用户模式下写入</span><span class="sxs-lookup"><span data-stu-id="9cda7-139">A Write Filter to prevent disk writes in user mode</span></span> 
    
- <span data-ttu-id="9cda7-p105">应用锁定器，可防止未经授权的应用运行。在用户模式下，所有 USB 端口都被禁用。</span><span class="sxs-lookup"><span data-stu-id="9cda7-p105">App Locker to prevent unauthorized apps from running. All USB ports are disabled in user mode.</span></span>
    
  - <span data-ttu-id="9cda7-142">没有标准的应用程序或查看者驻留在 Skype 会议室系统硬件上。</span><span class="sxs-lookup"><span data-stu-id="9cda7-142">No standard apps or viewers reside on the Skype Room System hardware.</span></span> <span data-ttu-id="9cda7-143">所有内容都是通过 HTTP 或 RDP 协议呈现的。</span><span class="sxs-lookup"><span data-stu-id="9cda7-143">All content is rendered via HTTP or RDP protocols.</span></span>
    
  - <span data-ttu-id="9cda7-p107">家用电脑运行 Windows Embedded Standard 7 操作系统。所有硬件（包括设备）都由 OEM 合作伙伴提供。</span><span class="sxs-lookup"><span data-stu-id="9cda7-p107">The appliance PC runs the Windows Embedded Standard 7 operating system. All hardware, including devices, is provided by OEM partners.</span></span>
    
  - <span data-ttu-id="9cda7-146">选择性地将域加入到 Active Directory 域服务 (AD DS)，实现本地安全帐户管理和控制。</span><span class="sxs-lookup"><span data-stu-id="9cda7-146">Optional Domain Join to Active Directory Domain Services (AD DS), enabling local security account management and control.</span></span>
    
- <span data-ttu-id="9cda7-147">您还可以管理业务管理中心的使用 Skype 的本地管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="9cda7-147">You can also manage the local admin account using the Skype for Business admin center.</span></span>
    
- <span data-ttu-id="9cda7-148">Skype 会议室系统是通过标准 Microsoft 更新过程进行了更新。</span><span class="sxs-lookup"><span data-stu-id="9cda7-148">Skype Room System is updated through standard Microsoft Update processes.</span></span>
    
- <span data-ttu-id="9cda7-149">Skype 会议室系统连接和 Skype 的业务。</span><span class="sxs-lookup"><span data-stu-id="9cda7-149">Skype Room System connects with Skype for Business.</span></span>
    
  - <span data-ttu-id="9cda7-150">Skype for Business 用于所有通信模式的端到端加密和授权</span><span class="sxs-lookup"><span data-stu-id="9cda7-150">Skype for Business uses end-to-end encryption and authorization for all modes of communication</span></span>
    
  - <span data-ttu-id="9cda7-151">Skype 会议室系统支持业务安全性和遵从性标准 Skype。</span><span class="sxs-lookup"><span data-stu-id="9cda7-151">Skype Room System supports Skype for Business security and compliance standards.</span></span> <span data-ttu-id="9cda7-152">有关详细信息，请参阅[规划 Skype 的业务 Server 中的安全性](../../plan-your-deployment/security/security.md)。</span><span class="sxs-lookup"><span data-stu-id="9cda7-152">See [Plan for security in Skype For Business Server](../../plan-your-deployment/security/security.md) for more information.</span></span>
    
## <a name="license"></a><span data-ttu-id="9cda7-153">许可证</span><span class="sxs-lookup"><span data-stu-id="9cda7-153">License</span></span>

<span data-ttu-id="9cda7-154">验证你是否可以使用 KMS 激活软件。</span><span class="sxs-lookup"><span data-stu-id="9cda7-154">Verify that you use a KMS for activating software.</span></span> <span data-ttu-id="9cda7-155">如果是这样，您可能需要检查或向其添加业务客户端 KMS 密钥 Skype。</span><span class="sxs-lookup"><span data-stu-id="9cda7-155">If so, you might need to check or add the Skype for Business client KMS key to it.</span></span> <span data-ttu-id="9cda7-156">如果您不使用 KMS，则请求批量许可密钥的业务客户端 MAK Skype。</span><span class="sxs-lookup"><span data-stu-id="9cda7-156">If you aren't using KMS, then request the volume licensing key for the Skype for Business client MAK.</span></span>
  
## <a name="license-keys"></a><span data-ttu-id="9cda7-157">许可证密钥</span><span class="sxs-lookup"><span data-stu-id="9cda7-157">License keys</span></span>

<span data-ttu-id="9cda7-158">Skype 会议室系统在后台运行业务桌面客户端 Skype。</span><span class="sxs-lookup"><span data-stu-id="9cda7-158">Skype Room System runs the Skype for Business desktop client in the background.</span></span> <span data-ttu-id="9cda7-159">如果 Skype 会议室系统是域成员，它将发现您的 KMS。</span><span class="sxs-lookup"><span data-stu-id="9cda7-159">If Skype Room System is a domain member, it will discover your KMS.</span></span> <span data-ttu-id="9cda7-160">（和批量授权 KMS 密钥，如果将自动激活）。</span><span class="sxs-lookup"><span data-stu-id="9cda7-160">(and if it has the Volume Licensing KMS Key it will activate automatically).</span></span> <span data-ttu-id="9cda7-161">）批量许可也提供 MAK，当你输入时，它将显示 xxxxx-xxxxx-xxxxx-xxxxx。</span><span class="sxs-lookup"><span data-stu-id="9cda7-161">Volume Licensing also provides a MAK, which you enter as it displays xxxxx-xxxxx-xxxxx-xxxxx.</span></span> <span data-ttu-id="9cda7-162">（你需要 Internet 访问才能使用 MAK 而不是 KMS 激活。</span><span class="sxs-lookup"><span data-stu-id="9cda7-162">(You need Internet access to activate using MAK but not KMS).</span></span> <span data-ttu-id="9cda7-163">）有关详细信息，请参阅“Office 2013 的批量激活”。</span><span class="sxs-lookup"><span data-stu-id="9cda7-163">For more information, see Volume activation of Office 2013.</span></span>
  
- <span data-ttu-id="9cda7-164">若要输入 MAK 密钥，请转到 OEM 设置\>SR 许可工具。</span><span class="sxs-lookup"><span data-stu-id="9cda7-164">To enter the MAK key, go to OEM Settings \> SRS Licensing Tool.</span></span> <span data-ttu-id="9cda7-165">单击“检查状态”。</span><span class="sxs-lookup"><span data-stu-id="9cda7-165">Click Check Status.</span></span> <span data-ttu-id="9cda7-166">当该状态将显示"产品未激活"时，输入密钥。</span><span class="sxs-lookup"><span data-stu-id="9cda7-166">When the status says "product isn't activated," enter the key.</span></span>
    
- <span data-ttu-id="9cda7-167">如果在激活过程中出现一条错误消息，"软件许可服务报告的产品密钥无效，"然后验证：</span><span class="sxs-lookup"><span data-stu-id="9cda7-167">If during activation you get an error that says, "'The Software Licensing Service reported that the product key is invalid," then verify that:</span></span>
    
  - <span data-ttu-id="9cda7-168">正确输入密钥。</span><span class="sxs-lookup"><span data-stu-id="9cda7-168">The key was entered correctly.</span></span>
    
  - <span data-ttu-id="9cda7-169">您输入 Skype 业务 MAK 密钥和不另一个键。</span><span class="sxs-lookup"><span data-stu-id="9cda7-169">You entered the Skype for Business MAK key and not another key.</span></span>
    
  - <span data-ttu-id="9cda7-170">系统具有 Internet 访问。</span><span class="sxs-lookup"><span data-stu-id="9cda7-170">The system has Internet access.</span></span>
    
- <span data-ttu-id="9cda7-171">你可以通过电话激活，但是必须首先已尝试使用 SRS 许可工具激活。</span><span class="sxs-lookup"><span data-stu-id="9cda7-171">You can activate via telephone but must have attempted to activate using the SRS Licensing Tool first.</span></span> <span data-ttu-id="9cda7-172">要通过电话激活，请启动测试会议（而不是测试呼叫，因为测试呼叫时间太短）。</span><span class="sxs-lookup"><span data-stu-id="9cda7-172">To activate via telephone, start a test meeting (not a test call as that is too short).</span></span> <span data-ttu-id="9cda7-173">在 Office 激活向导中，选择电话激活、 呼叫 Microsoft、 键入长的数字，和输入响应。</span><span class="sxs-lookup"><span data-stu-id="9cda7-173">In the Office Activation Wizard, select Telephone Activation, call Microsoft, type the long number, and enter a response.</span></span>
    
## <a name="certificate-authority"></a><span data-ttu-id="9cda7-174">证书颁发机构</span><span class="sxs-lookup"><span data-stu-id="9cda7-174">Certificate Authority</span></span>

<span data-ttu-id="9cda7-175">确认用于颁发 Office Web Apps Server 2013 证书的证书颁发机构在证书吊销列表中包括 HTTP 路径。</span><span class="sxs-lookup"><span data-stu-id="9cda7-175">Confirm the Certificate Authority used to issue the Office Web Apps Server 2013 certificate has an HTTP path included in the Certificate Revocation List property.</span></span>
  
<span data-ttu-id="9cda7-176">如果对业务服务器使用 Skype 到 Skype 会议室系统导入证书文件 (.crt)。</span><span class="sxs-lookup"><span data-stu-id="9cda7-176">Import the Certificate file (.crt) to the Skype Room System if using Skype for Business Server.</span></span> <span data-ttu-id="9cda7-177">可轻松地从 CA 服务器的 CertEnroll 共享中或者在任何加入域的电脑的“受信任的根”文件夹中获得。</span><span class="sxs-lookup"><span data-stu-id="9cda7-177">It's easily obtained from the CertEnroll share of the CA server, or in the Trusted Root folder of any domain joined PC.</span></span>
  
## <a name="certificates"></a><span data-ttu-id="9cda7-178">证书</span><span class="sxs-lookup"><span data-stu-id="9cda7-178">Certificates</span></span>

<span data-ttu-id="9cda7-p114">验证你的证书颁发机构是否具有证书吊销列表的 http 路径。如果没有，请更新你的 CA 以包括该路径。</span><span class="sxs-lookup"><span data-stu-id="9cda7-p114">Verify your Certificate Authority has an http path for the Certificate Revocation List. If not, update your CA to include one.</span></span>
  
<span data-ttu-id="9cda7-181">在系统设置下的 Skype 会议室系统管理员安装中安装证书\>证书管理器。</span><span class="sxs-lookup"><span data-stu-id="9cda7-181">Install certificates in the admin setup of the Skype Room System under System Settings \> Certificate Manager.</span></span> <span data-ttu-id="9cda7-182">你需要你的内部证书的企业根 CA。</span><span class="sxs-lookup"><span data-stu-id="9cda7-182">You need the Enterprise Root CA for your internal certificate.</span></span>
  
<span data-ttu-id="9cda7-183">获取所需证书的一种方法是发现颁发你的证书的 CA。</span><span class="sxs-lookup"><span data-stu-id="9cda7-183">One way to obtain the certificates you need is to discover the CA that issued your certificates.</span></span> <span data-ttu-id="9cda7-184">单击设置的企业服务器，在 Skype for Business，PC 上的 Skype\>工具\>电话拨入式会议设置。</span><span class="sxs-lookup"><span data-stu-id="9cda7-184">For Skype for Business Server, on a PC in Skype for Business, click Settings \> Tools \> Dial-in Conference Settings.</span></span> <span data-ttu-id="9cda7-185">这将打开网页保护颁发内部证书的 CA。</span><span class="sxs-lookup"><span data-stu-id="9cda7-185">This opens a web page secured by the CA that issued the internal certificates.</span></span> <span data-ttu-id="9cda7-186">单击浏览器地址栏上的锁图标以显示安全报告。</span><span class="sxs-lookup"><span data-stu-id="9cda7-186">Click the Lock icon on the browser address bar to display a security report.</span></span> <span data-ttu-id="9cda7-187">单击“查看证书”并检查“CRL 分布点”属性。</span><span class="sxs-lookup"><span data-stu-id="9cda7-187">Click View Certificates and examine the CRL Distribution Point property.</span></span> <span data-ttu-id="9cda7-188">第二个 CN 参数应为 CA 的服务器名称。</span><span class="sxs-lookup"><span data-stu-id="9cda7-188">The second CN parameter should be the server name of the CA.</span></span> <span data-ttu-id="9cda7-189">现在该地址打开 Windows 资源管理器\\ \< CA 服务器名\>\CertEnroll。</span><span class="sxs-lookup"><span data-stu-id="9cda7-189">Now open Windows Explorer for that address \\\< CA Server Name \>\CertEnroll.</span></span> <span data-ttu-id="9cda7-190">请将两个 .crl 文件和 .crt 文件复制到 U 盘，并将其放在智能白板的左侧。</span><span class="sxs-lookup"><span data-stu-id="9cda7-190">Copy the two .crl files and the .crt file to a flash drive and put it in the left hand side of the SMART board.</span></span>
  
<span data-ttu-id="9cda7-191">导入受信任的会议室证书颁发机构文件夹下 Skype 会议室系统.crt 文件。</span><span class="sxs-lookup"><span data-stu-id="9cda7-191">Import the .crt file to the Skype Room System under Trusted Room Certification Authority folder.</span></span>
  
<span data-ttu-id="9cda7-192">导入中间证书颁发机构文件夹下 Skype 会议室系统上的.crl 文件。</span><span class="sxs-lookup"><span data-stu-id="9cda7-192">Import the .crl files on the Skype Room System under the Intermediate Certificate Authorities folder.</span></span> <span data-ttu-id="9cda7-193">（您需要将证书管理器中的文件扩展名筛选器更改为.crl 以查看文件）。</span><span class="sxs-lookup"><span data-stu-id="9cda7-193">(You need to change the file extension filter in Certificate Manager to .crl to see the files).</span></span>
  
<span data-ttu-id="9cda7-194">注意： Office Web Apps 2013 服务器可以共享同一个 CA 为 for Business 的 Skype。</span><span class="sxs-lookup"><span data-stu-id="9cda7-194">Note: The Office Web Apps 2013 server may share the same CA as Skype for Business.</span></span> <span data-ttu-id="9cda7-195">如果不是，那么你将无法在会议中共享 PowerPoint 演示文稿。</span><span class="sxs-lookup"><span data-stu-id="9cda7-195">If it doesn't you won't be able to share PowerPoint in a meeting.</span></span> <span data-ttu-id="9cda7-196">请与 IT 核实，并按上面所述从 CA 网络共享 CertEnroll 获取 CRT 和 CRL 文件。</span><span class="sxs-lookup"><span data-stu-id="9cda7-196">Check with IT and obtain the CRT and CRL files off the CA network share CertEnroll as explained above.</span></span> 
  
<span data-ttu-id="9cda7-197">域成员身份可以简化的事情，因为视为 Windows 系统 Skype 会议室系统，它可以依赖 Active Directory 的一些方面证书。</span><span class="sxs-lookup"><span data-stu-id="9cda7-197">Domain membership can simplify some things because you can treat the Skype Room System as a Windows system and it can rely on Active Directory for some of the certificate aspects.</span></span> <span data-ttu-id="9cda7-198">但是，最好是手动管理它。</span><span class="sxs-lookup"><span data-stu-id="9cda7-198">However, it's best to manually manage this.</span></span>
  

