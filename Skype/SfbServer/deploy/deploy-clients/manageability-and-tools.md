---
title: Skype 会议室系统可管理性和工具
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/4/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c336ee9a-1ed8-4f64-9f7f-89549ae24c40
description: 阅读本主题，了解适用于 Skype 会议室系统的管理工具。
ms.openlocfilehash: c18c8a1e8f4580551dc809d3a8cedbf6f6a3fbfa
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-system-manageability-and-tools"></a><span data-ttu-id="39f13-103">Skype 会议室系统可管理性和工具</span><span class="sxs-lookup"><span data-stu-id="39f13-103">Skype Room System manageability and tools</span></span>
 
<span data-ttu-id="39f13-104">阅读本主题，了解适用于 Skype 会议室系统的管理工具。</span><span class="sxs-lookup"><span data-stu-id="39f13-104">Read this topic to learn about management tools for Skype Room System.</span></span>
  
## <a name="administrative-portal"></a><span data-ttu-id="39f13-105">管理门户</span><span class="sxs-lookup"><span data-stu-id="39f13-105">Administrative Portal</span></span>

<span data-ttu-id="39f13-106">为 Skype 业务服务器内部部署，可以使用 Skype 的空间系统管理门户来主动管理和监视 Skype 的空间系统部署您的组织中。</span><span class="sxs-lookup"><span data-stu-id="39f13-106">For Skype for Business Server on-premises deployments, you can use the Skype Room System administrative portal to actively manage and monitor Skype Room System deployments within your organization.</span></span>
  
<span data-ttu-id="39f13-107">有关更多详细信息，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="39f13-107">See the following articles for more details:</span></span>
  
- [<span data-ttu-id="39f13-108">Lync Server 2013 的 Lync 室系统管理 Web 门户部署</span><span class="sxs-lookup"><span data-stu-id="39f13-108">Deploying the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>](http://technet.microsoft.com/library/ecba5b36-632e-40b9-9c2e-ab825baf7a46.aspx)
    
- [<span data-ttu-id="39f13-109">Lync 室系统管理 Web 门户的配置 Lync Server 2013 环境</span><span class="sxs-lookup"><span data-stu-id="39f13-109">Configuring your Lync Server 2013 environment for the Lync Room System Administrative Web Portal</span></span>](http://technet.microsoft.com/library/1bf3cc55-cfa8-46ee-a8bc-6dab3bff76b2.aspx)
    
- [<span data-ttu-id="39f13-110">在 Lync Server 2013 安装 Lync 室系统管理 Web 门户</span><span class="sxs-lookup"><span data-stu-id="39f13-110">Installing the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>](http://technet.microsoft.com/library/dd19e368-c338-4e21-a40d-6439d46a9748.aspx)
    
- [<span data-ttu-id="39f13-111">在 Lync Server 2013 使用 Lync 室系统管理 Web 门户</span><span class="sxs-lookup"><span data-stu-id="39f13-111">Using the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>](http://technet.microsoft.com/library/c387b2a3-3e42-4642-af72-88126ed2820f.aspx)
    
## <a name="system-center-operations-manager"></a><span data-ttu-id="39f13-112">System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="39f13-112">System Center Operations Manager</span></span>

<span data-ttu-id="39f13-113">Skype 的空间系统可以通过下载[Skype 的空间系统管理包](https://www.microsoft.com/en-us/download/details.aspx?id=42320)并将其安装在 SCOM 服务器上监视系统中心操作管理器 (SCOM) 通过。</span><span class="sxs-lookup"><span data-stu-id="39f13-113">Skype Room System can be monitored through the System Center Operations Manager (SCOM) by downloading the [Skype Room System Management Pack](https://www.microsoft.com/en-us/download/details.aspx?id=42320) and installing it on your SCOM server.</span></span> <span data-ttu-id="39f13-114">SCOM 可用于设置警报、 监控其运行状况的 Skype 的空间系统，生成正常运行时间报告，以及更多。</span><span class="sxs-lookup"><span data-stu-id="39f13-114">You can use SCOM to set alerts, monitor the health of Skype Room System, generate uptime reports, and much more.</span></span> <span data-ttu-id="39f13-115">Skype 的空间系统带有可配置为指向 SCOM 服务器预安装监视 agent。</span><span class="sxs-lookup"><span data-stu-id="39f13-115">Skype Room System comes with a pre-installed monitoring agent that can be configured to point to SCOM server.</span></span> <span data-ttu-id="39f13-116">请参阅 Skype 的空间系统制造商提供的安装指南了解如何配置上 Skype 的空间系统的监视代理。</span><span class="sxs-lookup"><span data-stu-id="39f13-116">Refer to the installation guide provided by your Skype Room System manufacturer to know how to configure the monitoring agent on Skype Room System.</span></span>
  
## <a name="exchange-checklist"></a><span data-ttu-id="39f13-117">Exchange 清单</span><span class="sxs-lookup"><span data-stu-id="39f13-117">Exchange Checklist</span></span>

- <span data-ttu-id="39f13-118">确认已设置自动发现并且内部 DNS A/CNAME 记录可用于 autodiscover.domain.com。</span><span class="sxs-lookup"><span data-stu-id="39f13-118">Confirm Autodiscover is set up and an internal DNS A/CNAME RECORD is available for autodiscover.domain.com.</span></span>
    
- <span data-ttu-id="39f13-119">Ping 自动发现（例如，Ping Autodiscover.contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="39f13-119">Ping autodiscover (e.g., Ping Autodiscover.contoso.com).</span></span>
    
- <span data-ttu-id="39f13-120">使用 Microsoft Connectivity Analyzer 工具测试你的自动发现服务。</span><span class="sxs-lookup"><span data-stu-id="39f13-120">Test your Autodiscover service with the Microsoft Connectivity Analyzer Tool.</span></span> <span data-ttu-id="39f13-121">选择第一个测试中，"我不能登录使用 Outlook"。</span><span class="sxs-lookup"><span data-stu-id="39f13-121">Choose the first test, "I can't log on with Office Outlook."</span></span>
    
- <span data-ttu-id="39f13-122">如果会议室已经对 Skype 的空间系统 （示例脚本在页面的底部） 扩展此帐户的资源邮箱。</span><span class="sxs-lookup"><span data-stu-id="39f13-122">If the meeting room already has a resource mailbox, extend this account for the Skype Room System (example script at the bottom of the page).</span></span>
    
## <a name="skype-for-business-checklist"></a><span data-ttu-id="39f13-123">Skype 业务检查表</span><span class="sxs-lookup"><span data-stu-id="39f13-123">Skype for Business Checklist</span></span>

- <span data-ttu-id="39f13-124">运行以下工具：</span><span class="sxs-lookup"><span data-stu-id="39f13-124">Run the following tools:</span></span>
    
  - <span data-ttu-id="39f13-125">Skype 的商业最佳实践分析工具</span><span class="sxs-lookup"><span data-stu-id="39f13-125">Skype for Business Best Practices Analyzer</span></span> 
    
  - <span data-ttu-id="39f13-126">Skype 业务运行状况分析工具 (Excel)</span><span class="sxs-lookup"><span data-stu-id="39f13-126">Skype for Business Health Analysis Tool (Excel)</span></span> 
    
  - <span data-ttu-id="39f13-127">Skype 业务连接分析器 32 位或 64 位</span><span class="sxs-lookup"><span data-stu-id="39f13-127">Skype for Business Connectivity Analyzer 32-Bit or 64-Bit</span></span>
    
- <span data-ttu-id="39f13-128">查看[有用新故障诊断和分析工具，用于 Office 365](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/)。</span><span class="sxs-lookup"><span data-stu-id="39f13-128">Review [Useful new troubleshooting and analysis tools for Office 365](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/).</span></span> <span data-ttu-id="39f13-129">确认有 Skype 业务池和 Office Web 应用程序服务器，并且可以共享的业务客户端使用 Skype PowerPoint 幻灯片。</span><span class="sxs-lookup"><span data-stu-id="39f13-129">Confirm you have a Skype for Business pool and an Office Web Apps server and can share a PowerPoint deck using the Skype for Business client.</span></span>
    
- <span data-ttu-id="39f13-130">会议室已有资源邮箱，如果 Skype 业务为启用。</span><span class="sxs-lookup"><span data-stu-id="39f13-130">If the meeting room already has a resource mailbox, enable it for Skype for Business.</span></span>
    
- <span data-ttu-id="39f13-131">如果需要，请为会议室系统请求 DID（电话号码）并在 Active Directory 工具中更新“常规电话”字段。</span><span class="sxs-lookup"><span data-stu-id="39f13-131">If required, request a DID (phone number) for the Meeting Room System, and update the General Telephone field in the Active Directory tool.</span></span>
    
## <a name="network"></a><span data-ttu-id="39f13-132">网络</span><span class="sxs-lookup"><span data-stu-id="39f13-132">Network</span></span>

- <span data-ttu-id="39f13-133">确保您具有有线的网络连接的 Skype 的空间系统。</span><span class="sxs-lookup"><span data-stu-id="39f13-133">Make sure you have a wired network connection for the Skype Room System.</span></span>
    
- <span data-ttu-id="39f13-134">阅读规划业务指南 Skype 的网络。</span><span class="sxs-lookup"><span data-stu-id="39f13-134">Read the Network Planning Guide for Skype for Business.</span></span>
    
- <span data-ttu-id="39f13-135">请求对商业伙伴 Skype 业务网络评估 Skype。</span><span class="sxs-lookup"><span data-stu-id="39f13-135">Request a Skype for Business network assessment from a Skype for Business partner.</span></span>
    
- <span data-ttu-id="39f13-136">读取性能数据捕获在 Skype 业务运行状况分析工具 (Excel)。</span><span class="sxs-lookup"><span data-stu-id="39f13-136">Read through the performance data captured in the Skype for Business Health Analysis Tool (Excel).</span></span>
    
- <span data-ttu-id="39f13-137">运行网络分析工具。</span><span class="sxs-lookup"><span data-stu-id="39f13-137">Run the Network Analysis Tool.</span></span>
    
- <span data-ttu-id="39f13-138">运行预呼叫诊断工具。</span><span class="sxs-lookup"><span data-stu-id="39f13-138">Run the Pre-Call Diagnostics Tool.</span></span>
    
## <a name="skype-room-system-security"></a><span data-ttu-id="39f13-139">Skype 的空间系统的安全性</span><span class="sxs-lookup"><span data-stu-id="39f13-139">Skype Room System Security</span></span>

<span data-ttu-id="39f13-140">Skype 的空间系统是嵌入式的系统可以完全集成在 Windows 部署中，使用 Skype 业务安全模型、 权限管理和管理工具，例如 SCOM。</span><span class="sxs-lookup"><span data-stu-id="39f13-140">Skype Room System is an embedded system that can be fully integrated in a Windows deployment, using the Skype for Business security model, rights management, and management tools such as SCOM.</span></span> <span data-ttu-id="39f13-141">功能包括：</span><span class="sxs-lookup"><span data-stu-id="39f13-141">Features include:</span></span>
  
- <span data-ttu-id="39f13-142">写入筛选器，可防止磁盘在用户模式下写入</span><span class="sxs-lookup"><span data-stu-id="39f13-142">A Write Filter to prevent disk writes in user mode</span></span> 
    
- <span data-ttu-id="39f13-p105">应用锁定器，可防止未经授权的应用运行。在用户模式下，所有 USB 端口都被禁用。</span><span class="sxs-lookup"><span data-stu-id="39f13-p105">App Locker to prevent unauthorized apps from running. All USB ports are disabled in user mode.</span></span>
    
  - <span data-ttu-id="39f13-145">没有标准的应用程序或查看器驻留在 Skype 的空间系统硬件上。</span><span class="sxs-lookup"><span data-stu-id="39f13-145">No standard apps or viewers reside on the Skype Room System hardware.</span></span> <span data-ttu-id="39f13-146">所有内容都是通过 HTTP 或 RDP 协议呈现的。</span><span class="sxs-lookup"><span data-stu-id="39f13-146">All content is rendered via HTTP or RDP protocols.</span></span>
    
  - <span data-ttu-id="39f13-p107">家用电脑运行 Windows Embedded Standard 7 操作系统。所有硬件（包括设备）都由 OEM 合作伙伴提供。</span><span class="sxs-lookup"><span data-stu-id="39f13-p107">The appliance PC runs the Windows Embedded Standard 7 operating system. All hardware, including devices, is provided by OEM partners.</span></span>
    
  - <span data-ttu-id="39f13-149">选择性地将域加入到 Active Directory 域服务 (AD DS)，实现本地安全帐户管理和控制。</span><span class="sxs-lookup"><span data-stu-id="39f13-149">Optional Domain Join to Active Directory Domain Services (AD DS), enabling local security account management and control.</span></span>
    
- <span data-ttu-id="39f13-150">您还可以管理业务管理中心使用 Skype 的本地管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="39f13-150">You can also manage the local admin account using the Skype for Business admin center.</span></span>
    
- <span data-ttu-id="39f13-151">Skype 的空间系统将更新通过标准的 Microsoft 更新过程。</span><span class="sxs-lookup"><span data-stu-id="39f13-151">Skype Room System is updated through standard Microsoft Update processes.</span></span>
    
- <span data-ttu-id="39f13-152">Skype 的空间系统用 Skype 业务连接。</span><span class="sxs-lookup"><span data-stu-id="39f13-152">Skype Room System connects with Skype for Business.</span></span>
    
  - <span data-ttu-id="39f13-153">Skype 业务为用于所有通信模式的端到端加密和授权</span><span class="sxs-lookup"><span data-stu-id="39f13-153">Skype for Business uses end-to-end encryption and authorization for all modes of communication</span></span>
    
  - <span data-ttu-id="39f13-154">Skype 的空间系统支持 Skype 业务安全和法规遵从性标准。</span><span class="sxs-lookup"><span data-stu-id="39f13-154">Skype Room System supports Skype for Business security and compliance standards.</span></span> <span data-ttu-id="39f13-155">有关详细信息，请参阅“规划 Lync Server 2013 的安全性”。</span><span class="sxs-lookup"><span data-stu-id="39f13-155">See Planning for security in Lync Server 2013 for more information.</span></span>
    
## <a name="license"></a><span data-ttu-id="39f13-156">许可证</span><span class="sxs-lookup"><span data-stu-id="39f13-156">License</span></span>

<span data-ttu-id="39f13-157">验证你是否可以使用 KMS 激活软件。</span><span class="sxs-lookup"><span data-stu-id="39f13-157">Verify that you use a KMS for activating software.</span></span> <span data-ttu-id="39f13-158">如果是这样，您可能需要检查或向其中添加业务客户端 KMS 密钥为 Skype。</span><span class="sxs-lookup"><span data-stu-id="39f13-158">If so, you might need to check or add the Skype for Business client KMS key to it.</span></span> <span data-ttu-id="39f13-159">如果您不使用 KMS，然后请求批量业务客户端 MAK 的 Skype 的许可密钥。</span><span class="sxs-lookup"><span data-stu-id="39f13-159">If you aren't using KMS, then request the volume licensing key for the Skype for Business client MAK.</span></span>
  
## <a name="license-keys"></a><span data-ttu-id="39f13-160">许可证密钥</span><span class="sxs-lookup"><span data-stu-id="39f13-160">License keys</span></span>

<span data-ttu-id="39f13-161">Skype 的空间系统运行在后台业务桌面客户端的 Skype。</span><span class="sxs-lookup"><span data-stu-id="39f13-161">Skype Room System runs the Skype for Business desktop client in the background.</span></span> <span data-ttu-id="39f13-162">如果 Skype 的空间系统是域成员，它将会发现您的 KMS。</span><span class="sxs-lookup"><span data-stu-id="39f13-162">If Skype Room System is a domain member, it will discover your KMS.</span></span> <span data-ttu-id="39f13-163">（并且，如果具有批量许可 KMS Lync 密钥，则将自动激活。</span><span class="sxs-lookup"><span data-stu-id="39f13-163">(and if it has the Volume Licensing KMS Lync Key it will activate automatically).</span></span> <span data-ttu-id="39f13-164">）批量许可也提供 MAK，当你输入时，它将显示 xxxxx-xxxxx-xxxxx-xxxxx。</span><span class="sxs-lookup"><span data-stu-id="39f13-164">Volume Licensing also provides a MAK, which you enter as it displays xxxxx-xxxxx-xxxxx-xxxxx.</span></span> <span data-ttu-id="39f13-165">（你需要 Internet 访问才能使用 MAK 而不是 KMS 激活。</span><span class="sxs-lookup"><span data-stu-id="39f13-165">(You need Internet access to activate using MAK but not KMS).</span></span> <span data-ttu-id="39f13-166">）有关详细信息，请参阅“Office 2013 的批量激活”。</span><span class="sxs-lookup"><span data-stu-id="39f13-166">For more information, see Volume activation of Office 2013.</span></span>
  
- <span data-ttu-id="39f13-167">要输入 MAK 密钥，请转到 OEM 设置\>SRS 授权工具。</span><span class="sxs-lookup"><span data-stu-id="39f13-167">To enter the MAK key, go to OEM Settings \> SRS Licensing Tool.</span></span> <span data-ttu-id="39f13-168">单击“检查状态”。</span><span class="sxs-lookup"><span data-stu-id="39f13-168">Click Check Status.</span></span> <span data-ttu-id="39f13-169">当该状态显示"产品未激活"时，请输入密钥。</span><span class="sxs-lookup"><span data-stu-id="39f13-169">When the status says "product isn't activated," enter the key.</span></span>
    
- <span data-ttu-id="39f13-170">如果在激活过程中收到错误，指出:"' 软件授权服务报告的产品密钥无效，"然后确认：</span><span class="sxs-lookup"><span data-stu-id="39f13-170">If during activation you get an error that says, "'The Software Licensing Service reported that the product key is invalid," then verify that:</span></span>
    
  - <span data-ttu-id="39f13-171">正确输入密钥。</span><span class="sxs-lookup"><span data-stu-id="39f13-171">The key was entered correctly.</span></span>
    
  - <span data-ttu-id="39f13-172">Skype 输入业务 MAK 密钥并不是另一个密钥。</span><span class="sxs-lookup"><span data-stu-id="39f13-172">You entered the Skype for Business MAK key and not another key.</span></span>
    
  - <span data-ttu-id="39f13-173">系统具有 Internet 访问。</span><span class="sxs-lookup"><span data-stu-id="39f13-173">The system has Internet access.</span></span>
    
- <span data-ttu-id="39f13-174">你可以通过电话激活，但是必须首先已尝试使用 SRS 许可工具激活。</span><span class="sxs-lookup"><span data-stu-id="39f13-174">You can activate via telephone but must have attempted to activate using the SRS Licensing Tool first.</span></span> <span data-ttu-id="39f13-175">要通过电话激活，请启动测试会议（而不是测试呼叫，因为测试呼叫时间太短）。</span><span class="sxs-lookup"><span data-stu-id="39f13-175">To activate via telephone, start a test meeting (not a test call as that is too short).</span></span> <span data-ttu-id="39f13-176">在 Office 激活向导中，选择电话激活致电 Microsoft、 键入的长号，输入的响应。</span><span class="sxs-lookup"><span data-stu-id="39f13-176">In the Office Activation Wizard, select Telephone Activation, call Microsoft, type the long number, and enter a response.</span></span>
    
## <a name="certificate-authority"></a><span data-ttu-id="39f13-177">证书颁发机构</span><span class="sxs-lookup"><span data-stu-id="39f13-177">Certificate Authority</span></span>

<span data-ttu-id="39f13-178">确认用于颁发 Office Web Apps Server 2013 证书的证书颁发机构在证书吊销列表中包括 HTTP 路径。</span><span class="sxs-lookup"><span data-stu-id="39f13-178">Confirm the Certificate Authority used to issue the Office Web Apps Server 2013 certificate has an HTTP path included in the Certificate Revocation List property.</span></span>
  
<span data-ttu-id="39f13-179">如果使用 Skype 业务服务器到 Skype 的空间系统导入证书文件 (.crt)。</span><span class="sxs-lookup"><span data-stu-id="39f13-179">Import the Certificate file (.crt) to the Skype Room System if using Skype for Business Server.</span></span> <span data-ttu-id="39f13-180">可轻松地从 CA 服务器的 CertEnroll 共享中或者在任何加入域的电脑的“受信任的根”文件夹中获得。</span><span class="sxs-lookup"><span data-stu-id="39f13-180">It's easily obtained from the CertEnroll share of the CA server, or in the Trusted Root folder of any domain joined PC.</span></span>
  
## <a name="certificates"></a><span data-ttu-id="39f13-181">证书</span><span class="sxs-lookup"><span data-stu-id="39f13-181">Certificates</span></span>

<span data-ttu-id="39f13-p114">验证你的证书颁发机构是否具有证书吊销列表的 http 路径。如果没有，请更新你的 CA 以包括该路径。</span><span class="sxs-lookup"><span data-stu-id="39f13-p114">Verify your Certificate Authority has an http path for the Certificate Revocation List. If not, update your CA to include one.</span></span>
  
<span data-ttu-id="39f13-184">在系统设置中的 Skype 的空间系统管理设置安装证书\>证书管理器。</span><span class="sxs-lookup"><span data-stu-id="39f13-184">Install certificates in the admin setup of the Skype Room System under System Settings \> Certificate Manager.</span></span> <span data-ttu-id="39f13-185">你需要你的内部证书的企业根 CA。</span><span class="sxs-lookup"><span data-stu-id="39f13-185">You need the Enterprise Root CA for your internal certificate.</span></span>
  
<span data-ttu-id="39f13-186">获取所需证书的一种方法是发现颁发你的证书的 CA。</span><span class="sxs-lookup"><span data-stu-id="39f13-186">One way to obtain the certificates you need is to discover the CA that issued your certificates.</span></span> <span data-ttu-id="39f13-187">单击设置为企业服务器，Skype 的业务，在电脑上的 Skype\>工具\>会议设置拨入。</span><span class="sxs-lookup"><span data-stu-id="39f13-187">For Skype for Business Server, on a PC in Skype for Business, click Settings \> Tools \> Dial-in Conference Settings.</span></span> <span data-ttu-id="39f13-188">此时将打开一个受颁发内部 Lync 证书的 CA 保护的网页。</span><span class="sxs-lookup"><span data-stu-id="39f13-188">This opens a web page secured by the CA that issued the internal Lync certificates.</span></span> <span data-ttu-id="39f13-189">单击浏览器地址栏上的锁图标以显示安全报告。</span><span class="sxs-lookup"><span data-stu-id="39f13-189">Click the Lock icon on the browser address bar to display a security report.</span></span> <span data-ttu-id="39f13-190">单击“查看证书”并检查“CRL 分布点”属性。</span><span class="sxs-lookup"><span data-stu-id="39f13-190">Click View Certificates and examine the CRL Distribution Point property.</span></span> <span data-ttu-id="39f13-191">第二个 CN 参数应为 CA 的服务器名称。</span><span class="sxs-lookup"><span data-stu-id="39f13-191">The second CN parameter should be the server name of the CA.</span></span> <span data-ttu-id="39f13-192">现在，Windows 资源管理器打开该地址\\\<的 CA 服务器名称\>\CertEnroll。</span><span class="sxs-lookup"><span data-stu-id="39f13-192">Now open Windows Explorer for that address \\\< CA Server Name \>\CertEnroll.</span></span> <span data-ttu-id="39f13-193">请将两个 .crl 文件和 .crt 文件复制到 U 盘，并将其放在智能白板的左侧。</span><span class="sxs-lookup"><span data-stu-id="39f13-193">Copy the two .crl files and the .crt file to a flash drive and put it in the left hand side of the SMART board.</span></span>
  
<span data-ttu-id="39f13-194">将.crt 文件导入到受信任房间证书颁发机构文件夹下 Skype 室系统。</span><span class="sxs-lookup"><span data-stu-id="39f13-194">Import the .crt file to the Skype Room System under Trusted Room Certification Authority folder.</span></span>
  
<span data-ttu-id="39f13-195">在中间证书颁发机构文件夹下，Skype 的空间系统为.crl 文件导入。</span><span class="sxs-lookup"><span data-stu-id="39f13-195">Import the .crl files on the Skype Room System under the Intermediate Certificate Authorities folder.</span></span> <span data-ttu-id="39f13-196">（您需要将证书管理器中的文件扩展名筛选器更改为.crl 查看这些文件）。</span><span class="sxs-lookup"><span data-stu-id="39f13-196">(You need to change the file extension filter in Certificate Manager to .crl to see the files).</span></span>
  
<span data-ttu-id="39f13-p118">注意：Office Web Apps 2013 服务器可能与 Lync 共用同一个 CA。如果不是，那么你将无法在会议中共享 PowerPoint 演示文稿。请与 IT 核实，并按上面所述从 CA 网络共享 CertEnroll 获取 CRT 和 CRL 文件。</span><span class="sxs-lookup"><span data-stu-id="39f13-p118">Note: The Office Web Apps 2013 server may share the same CA as Lync. If it doesn't you won't be able to share PowerPoint in a meeting. Check with IT and obtain the CRT and CRL files off the CA network share CertEnroll as explained above.</span></span> 
  
<span data-ttu-id="39f13-200">因为作为 Windows 系统，可以将 Skype 的空间系统，它可以依赖 Active Directory 证书方面的某些域成员身份可以简化一些。</span><span class="sxs-lookup"><span data-stu-id="39f13-200">Domain membership can simplify some things because you can treat the Skype Room System as a Windows system and it can rely on Active Directory for some of the certificate aspects.</span></span> <span data-ttu-id="39f13-201">但是，最好是手动管理它。</span><span class="sxs-lookup"><span data-stu-id="39f13-201">However, it's best to manually manage this.</span></span>
  

