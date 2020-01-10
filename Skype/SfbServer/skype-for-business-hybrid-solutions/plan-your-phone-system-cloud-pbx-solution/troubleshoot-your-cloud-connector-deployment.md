---
title: 云连接器部署故障排除
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/5/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e6cf58cc-dbd9-4f35-a51a-3e2fea71b5a5
description: 对云连接器版本部署进行故障排除。
ms.openlocfilehash: 3edc67d5887c21543e4cbb01a6057a0c657e95e3
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002072"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a><span data-ttu-id="e430e-103">云连接器部署故障排除</span><span class="sxs-lookup"><span data-stu-id="e430e-103">Troubleshoot your Cloud Connector deployment</span></span>
 
<span data-ttu-id="e430e-104">对云连接器版本部署进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="e430e-104">Troubleshoot your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="e430e-p101">本主题介绍云连接器版本部署常见问题的解决方案。如果你在通过公用电话交换网 (PSTN) 拨打和接听电话时遇到问题，可以按照本主题中介绍的解决方案进行调查。</span><span class="sxs-lookup"><span data-stu-id="e430e-p101">This topic describes solutions to common issues with Cloud Connector Edition deployments. If you are experiencing issues with calls to and from the Public Switched Telephone Network (PSTN), you can investigate by following the solutions described in this topic.</span></span>
  
<span data-ttu-id="e430e-107">云连接器提供了用于自动解决某些问题的内置机制。</span><span class="sxs-lookup"><span data-stu-id="e430e-107">Cloud Connector provides built-in mechanisms for automatically resolving some issues.</span></span> <span data-ttu-id="e430e-108">自动检测过程查找云连接器设备的潜在问题，如果可能，请采取纠正措施来解决这些问题，而无需管理员干预。</span><span class="sxs-lookup"><span data-stu-id="e430e-108">An automatic detection process looks for potential issues with the Cloud Connector appliances, and, if possible, takes corrective action to resolve those issues without the need for administrator intervention.</span></span> <span data-ttu-id="e430e-109">检测过程工作方式如下：</span><span class="sxs-lookup"><span data-stu-id="e430e-109">The detection process works as follows:</span></span>
  
- <span data-ttu-id="e430e-110">**检测序列：** 云连接器管理服务每隔60秒运行一次进程，用于检测装置是否已停机。</span><span class="sxs-lookup"><span data-stu-id="e430e-110">**Detection sequence:** The Cloud Connector Management service runs a process every 60 seconds for detecting whether an appliance is down.</span></span> <span data-ttu-id="e430e-111">在云连接器版本2.0 和更高版本中，检测过程使用 Skype for Business 的企业版企业版交换连接到云连接器计算机;对于2.0 之前的版本，检测过程使用云连接器管理开关。</span><span class="sxs-lookup"><span data-stu-id="e430e-111">In Cloud Connector version 2.0 and later, the detection process uses the Skype for Business Corpnet switch for making PowerShell connections to the Cloud Connector machines; for versions previous to 2.0, the detection process uses the Cloud Connector management switch.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e430e-112">若要自动恢复成功，主机和虚拟机之间必须具有通过主机网络交换机的网络连接。</span><span class="sxs-lookup"><span data-stu-id="e430e-112">For automatic recovery to succeed, there must be network connectivity between the host and virtual machines over the host network switch.</span></span> <span data-ttu-id="e430e-113">请确保检查网络连接，以确保自动检测和恢复能够成功。</span><span class="sxs-lookup"><span data-stu-id="e430e-113">Be sure to check network connectivity to ensure that automatic detection and recovery can succeed.</span></span> 
  
- <span data-ttu-id="e430e-114">**监视：** 在云连接器版本2.0 和更高版本中监视以下服务：</span><span class="sxs-lookup"><span data-stu-id="e430e-114">**Monitoring:** The following services are monitored in Cloud Connector version 2.0 and later:</span></span>
    
  - <span data-ttu-id="e430e-115">虚拟机未连接到云连接器企业或 Internet 虚拟交换机</span><span class="sxs-lookup"><span data-stu-id="e430e-115">Virtual Machines are not connected to the Cloud Connector Corporate or Internet virtual switches</span></span>
    
  - <span data-ttu-id="e430e-116">虚拟机处于已保存或已停止状态</span><span class="sxs-lookup"><span data-stu-id="e430e-116">Virtual Machines are in a saved or stopped status</span></span>
    
  - <span data-ttu-id="e430e-117">中央管理服务器服务：副本、主机</span><span class="sxs-lookup"><span data-stu-id="e430e-117">Central Management Server services: REPLICA, MASTER</span></span>
    
  - <span data-ttu-id="e430e-118">中介服务器服务：副本、RTCSRV 和 MEDSVC</span><span class="sxs-lookup"><span data-stu-id="e430e-118">Mediation Server services: REPLICA, RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="e430e-119">边缘服务器服务：副本、RTCSRV、RTCDATAPROXY、RTCMRAUTH、RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="e430e-119">Edge Server services: REPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY</span></span>
    
  - <span data-ttu-id="e430e-120">在 Edge 服务器上为 CS RTCSRV 禁用入站防火墙规则，在中介服务器上的 CS RTCMEDSRV</span><span class="sxs-lookup"><span data-stu-id="e430e-120">Inbound firewall rules are disabled for CS RTCSRV on Edge server, CS RTCMEDSRV on Mediation server</span></span>
    
    <span data-ttu-id="e430e-121">在云连接器版本1.4.2 中，仅监视以下服务：</span><span class="sxs-lookup"><span data-stu-id="e430e-121">In Cloud Connector version 1.4.2, only the following services are monitored:</span></span>
    
  - <span data-ttu-id="e430e-122">中介服务器服务： RTCSRV 和 MEDSVC</span><span class="sxs-lookup"><span data-stu-id="e430e-122">Mediation Server services: RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="e430e-123">Edge 服务器服务： RTCSRV</span><span class="sxs-lookup"><span data-stu-id="e430e-123">Edge Server service: RTCSRV</span></span>
    
- <span data-ttu-id="e430e-124">**恢复过程：** 如果任何监视的服务已关闭，则会将设备标记为已关闭，并且服务将停止并标记为手动，直到解决所有问题。</span><span class="sxs-lookup"><span data-stu-id="e430e-124">**Recovery process:** If any monitored services are down, an appliance is marked down, and services are stopped and marked manual until all issues can be resolved.</span></span> <span data-ttu-id="e430e-125">这将阻止呼叫路由到可能导致呼叫失败的装置。</span><span class="sxs-lookup"><span data-stu-id="e430e-125">This will prevent calls from routing to an appliance that may cause call failures.</span></span>
    
    <span data-ttu-id="e430e-126">云连接器管理服务将重试自动恢复，如下所示</span><span class="sxs-lookup"><span data-stu-id="e430e-126">The Cloud Connector Management service will retry automatic recovery as follows</span></span>
    
  - <span data-ttu-id="e430e-127">初始重试间隔是每隔十秒，最大间隔时间为一小时。</span><span class="sxs-lookup"><span data-stu-id="e430e-127">The initial retry interval is every ten seconds with a maximum interval time of one hour.</span></span>
    
  - <span data-ttu-id="e430e-128">对于前三次恢复尝试，间隔时间为10秒。</span><span class="sxs-lookup"><span data-stu-id="e430e-128">For the first three recovery attempts, the interval time is 10 seconds.</span></span> <span data-ttu-id="e430e-129">从第四个重试开始，间隔时间将增加上一个间隔时间的两倍。</span><span class="sxs-lookup"><span data-stu-id="e430e-129">Starting from the fourth retry, the interval time increases by two times the previous interval time.</span></span> <span data-ttu-id="e430e-130">例如，第四次重试将在20秒内发生，第五个在40秒中，依此类推。</span><span class="sxs-lookup"><span data-stu-id="e430e-130">For example, the fourth retry will occur in 20 seconds, the fifth in 40 seconds, and so on.</span></span> 
    
  - <span data-ttu-id="e430e-131">当达到一小时的最大间隔时间时，每小时的重试将继续。</span><span class="sxs-lookup"><span data-stu-id="e430e-131">When the maximum interval time of one hour is reached, retries will continue once per hour.</span></span>
    
  - <span data-ttu-id="e430e-132">恢复成功后，"间隔" 和 "重试次数" 将设置为初始值。</span><span class="sxs-lookup"><span data-stu-id="e430e-132">When recovery is successful, the interval and retry counts are set to their initial values.</span></span>
    
  - <span data-ttu-id="e430e-133">如果重新启动管理服务，则会将 "间隔" 和 "重试计数" 重置为其初始值。</span><span class="sxs-lookup"><span data-stu-id="e430e-133">If the Management service is restarted, the interval and retry counts are reset to their initial values.</span></span>
    
## <a name="troubleshooting"></a><span data-ttu-id="e430e-134">疑难解答</span><span class="sxs-lookup"><span data-stu-id="e430e-134">Troubleshooting</span></span>

<span data-ttu-id="e430e-135">以下是经常遇到的问题的解决方案：</span><span class="sxs-lookup"><span data-stu-id="e430e-135">Following are solutions to commonly encountered issues:</span></span>
  
- <span data-ttu-id="e430e-136">**问题：运行部署脚本时部署失败或停止响应。登录每个虚拟机后，管理/内部/外部 NIC 的 IP 地址缺失或不正确。**</span><span class="sxs-lookup"><span data-stu-id="e430e-136">**Issue: Deployment fails or stops responding when running the deployment scripts. After logging on to each VM, the IP address is missing or incorrect for the Management/Internal/External NIC.**</span></span>
    
    <span data-ttu-id="e430e-137">**解决方案：** 无法自动解决此问题。</span><span class="sxs-lookup"><span data-stu-id="e430e-137">**Resolution:** This issue cannot be resolved automatically.</span></span> <span data-ttu-id="e430e-138">Nic 在运行时不能添加到 Vm。</span><span class="sxs-lookup"><span data-stu-id="e430e-138">NICs cannot be added to VMs while they are running.</span></span> <span data-ttu-id="e430e-139">请在 hyper-v 管理器中关闭并删除这些 Vm，然后运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="e430e-139">Please shut down and remove these VMs in hyper-v manager, then run the following cmdlets:</span></span>
    
  ```powershell
  Uninstall-CcAppliance
  ```

  ```powershell
  Install-CcAppliance
  ```

- 
    
    <span data-ttu-id="e430e-140">**问题：安装 Active Directory 服务器和林后，CMS 服务器和/或中介服务器未正确加入域。**</span><span class="sxs-lookup"><span data-stu-id="e430e-140">**Issue: After the Active Directory Server and forest are installed, the CMS Server and/or Mediation Server did not join the domain correctly.**</span></span>
    
    <span data-ttu-id="e430e-141">**解决方法：** 要解决此问题，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="e430e-141">**Resolution:** To resolve this issue, take the following steps:</span></span>
    
  - <span data-ttu-id="e430e-142">登录 Active Directory 服务器并验证是否已正确创建域。</span><span class="sxs-lookup"><span data-stu-id="e430e-142">Log on to the Active Directory Server and verify that the domain was created correctly.</span></span>
    
  - <span data-ttu-id="e430e-143">登录 CMS/中介服务器，并验证公司网络 NIC 上是否分配了有效的 IP 地址，以及是否将有效的静态 IP 和 DNS 配置为 AD 服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="e430e-143">Log on to the CMS/Mediation Server and verify that on the corpnet NIC a valid IP address is assigned, and that valid static IP and DNS is configured as the AD server's IP address.</span></span>
    
  - <span data-ttu-id="e430e-144">登录到 CMS/中介服务器，然后打开命令提示符。</span><span class="sxs-lookup"><span data-stu-id="e430e-144">Log on to the CMS/Mediation Server, and open a command prompt.</span></span> <span data-ttu-id="e430e-145">确保可以 ping Active Directory 服务器的 FQDN 和 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="e430e-145">Make sure you can ping the FQDN and IP address of the Active Directory Server.</span></span> <span data-ttu-id="e430e-146">如果不可以，则可能存在 IP 地址冲突。</span><span class="sxs-lookup"><span data-stu-id="e430e-146">If you cannot, there may be an IP address conflict.</span></span> <span data-ttu-id="e430e-147">请尝试为 Active Directory 分配新 IP 并相应更新 CMS/中介服务器上的 DNS。</span><span class="sxs-lookup"><span data-stu-id="e430e-147">Please try to assign a new IP for Active Directory and update DNS on the CMS/Mediation server accordingly.</span></span>
    
- <span data-ttu-id="e430e-148">**问题：在删除虚拟以太网交换机时收到以下错误消息 "Remove-VMSwitch：" 失败。无法删除虚拟交换机 "云连接器管理开关"，因为它正被运行虚拟机或分配到子池。 "**</span><span class="sxs-lookup"><span data-stu-id="e430e-148">**Issue: You receive the following error message, "Remove-VMSwitch : Failed while removing virtual Ethernet switch. The virtual switch 'Cloud Connector Management Switch' cannot be deleted because it is being used by running virtual machines or assigned to child pools."**</span></span>
    
    <span data-ttu-id="e430e-149">**解决方案：** 部署后，"云连接器管理开关" 未被删除。</span><span class="sxs-lookup"><span data-stu-id="e430e-149">**Resolution:** The "Cloud Connector Management Switch" was not deleted after the deployment.</span></span> <span data-ttu-id="e430e-150">如果你遇到此错误，请转到 Hyper-v 管理器并验证是否仍有虚拟机仍连接到它。</span><span class="sxs-lookup"><span data-stu-id="e430e-150">If you hit this error, please go to Hyper-v manager and verify that there is not still a virtual machine still connected to it.</span></span> <span data-ttu-id="e430e-151">如果存在仍连接的虚拟机，请将其断开连接并删除管理交换机。</span><span class="sxs-lookup"><span data-stu-id="e430e-151">If there are virtual machines still connected, disconnect them and delete the management switch.</span></span> <span data-ttu-id="e430e-152">如果仍然无法删除管理开关，请重新启动主机服务器，然后重试。</span><span class="sxs-lookup"><span data-stu-id="e430e-152">If the management switch still cannot be deleted, restart the host server and try again.</span></span>
    
- <span data-ttu-id="e430e-153">**问题：收到以下错误消息： "服务 RTCMRAUTH 无法启动。检查以确保该服务未禁用。 "**</span><span class="sxs-lookup"><span data-stu-id="e430e-153">**Issue: You receive the following error message, "Service RTCMRAUTH failed to start. Check to make sure the service is not disabled."**</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e430e-154">此问题仅适用于1.4.2 以前的云连接器版本。</span><span class="sxs-lookup"><span data-stu-id="e430e-154">This issue only applies to Cloud Connector versions earlier than 1.4.2.</span></span> 
  
    <span data-ttu-id="e430e-p110">无法启动也可能是因为此前端服务器之前经过故障转移（使用计算机故障转移）。如果是这种情况，请调用故障回复（使用计算机故障回复）。</span><span class="sxs-lookup"><span data-stu-id="e430e-p110">The failure to start could also be because this Front End server was previously failed over (using computer fail over). If that's the case, please invoke fail back (using computer fail back).</span></span>
    
    <span data-ttu-id="e430e-p111">**解决方法：** 当边缘服务器不信任根 CA 证书或中间 CA 证书时，边缘服务器上会出现此问题。即使可以导入外部证书，但证书链已损坏。在这种情况下，RTCMRAUTH 和/或 RTCSRV 服务无法启动。</span><span class="sxs-lookup"><span data-stu-id="e430e-p111">**Resolution:** This issue happens on an Edge Server when the root CA certificate or intermediate CA certificate is not trusted by the Edge Server. Even if the external certificate can be imported but the certificate chain is broken. Under this condition, the RTCMRAUTH and/or RTCSRV service can not start.</span></span>
    
    <span data-ttu-id="e430e-p112">请手动将外部证书的根 CA 证书和所有中间 CA 证书导入到边缘服务器，然后重新启动边缘服务器。看到 RTCMRAUTH 和 RTCSRV 服务在边缘服务器上启动之后，返回到主机服务器，以管理员身份启动 PowerShell 控制台，并运行以下 cmdlet 以便切换到新部署：</span><span class="sxs-lookup"><span data-stu-id="e430e-p112">Please import the root CA certificate and all intermediate CA certificates of your external certificate manually into the Edge Server and then restart the Edge Server. After you see the RTCMRAUTH and RTCSRV services started on the Edge Server, go back to your host server, launch a PowerShell console as administrator, and run following cmdlet to switch to the new deployment:</span></span>
    
  ```powershell
  Switch-CcVersion
  ```

- 
    
    <span data-ttu-id="e430e-162">**问题：应用 Windows 更新时主机服务器重新启动，由此服务器支持的调用失败。**</span><span class="sxs-lookup"><span data-stu-id="e430e-162">**Issue: The host server was restarted when Windows updates were applied, and calls serviced by the server are failing.**</span></span>
    
    <span data-ttu-id="e430e-p113">**解决方法：** 如果你已部署高可用性环境，Microsoft 提供的 cmdlet 可以帮助你在手动检查和安装 Windows 更新时将一台主机（部署实例）移入或移出当前拓扑。要完成此操作，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="e430e-p113">**Resolution:** If you deployed a high availability environment, Microsoft provides a cmdlet to help move one host machine (deployment instance) into or out of the current topology when you check and install Windows update manually. Use the following steps to accomplish this:</span></span>
    
1. <span data-ttu-id="e430e-165">在主机服务器上，以管理员身份启动 PowerShell 控制台，然后运行：</span><span class="sxs-lookup"><span data-stu-id="e430e-165">On the host server, start a PowerShell console as administrator, then run:</span></span>
    
   ```powershell
   Enter-CcUpdate
   ```

2. <span data-ttu-id="e430e-166">检查更新并安装所有可用更新。</span><span class="sxs-lookup"><span data-stu-id="e430e-166">Check for updates and install any that are available.</span></span>
    
3. <span data-ttu-id="e430e-167">在 PowerShell 控制台中，运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="e430e-167">In the PowerShell console, run the following cmdlet:</span></span>
    
   ```powershell
   Exit-CcUpdate
   ```

- 
    
    <span data-ttu-id="e430e-168">**问题：使用 PSTN 号码从 Skype for Business 客户端进行呼叫时，无法通过邀请其他 PSTN 号码将该呼叫提升为会议。**</span><span class="sxs-lookup"><span data-stu-id="e430e-168">**Issue: When a call is made from a Skype for Business client using a PSTN number, the call cannot be escalated to a conference by inviting another PSTN number.**</span></span>
    
    <span data-ttu-id="e430e-169">**解决方案：** 若要解决此问题，请参阅[配置联机混合中介服务器设置](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer)。</span><span class="sxs-lookup"><span data-stu-id="e430e-169">**Resolution:** To resolve this issue, see [Configure online hybrid Mediation Server Settings](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).</span></span>
    
- <span data-ttu-id="e430e-170">**问题：安装 Active Directory 服务器时，显示关于 Windows 更新的警告消息 -“未启用 Windows 自动更新。为确保新安装的角色或功能将自动更新，请启用 Windows 更新。”**</span><span class="sxs-lookup"><span data-stu-id="e430e-170">**Issue: A warning message is displayed about Windows Update when you are installing Active Directory server - "Windows automatic updating is not enabled. To ensure that your newly-installed role or feature is automatically updated, turn on Windows Update."**</span></span>
    
    <span data-ttu-id="e430e-171">**解决方案：** 使用 Skype for Business 租户管理员凭据启动租户远程 PowerShell 会话，然后运行以下 cmdlet 检查网站的_EnableAutoUpdate_配置：</span><span class="sxs-lookup"><span data-stu-id="e430e-171">**Resolution:** Launch a Tenant Remote PowerShell session using Skype for Business tenant admin credentials, then run the following cmdlet to check the _EnableAutoUpdate_ configuration of your site:</span></span>
    
  ```powershell
  Get-CsHybridPSTNSite
  ```

    <span data-ttu-id="e430e-172">如果_EnableAutoUpdate_设置为**True**，则可以安全地忽略此警告消息，因为 CCEManagement 服务将为虚拟机和主机服务器处理下载和安装 Windows 更新。</span><span class="sxs-lookup"><span data-stu-id="e430e-172">If  _EnableAutoUpdate_ is set to **True**, you can safely ignore this warning message because the CCEManagement service will handle downloading and installing Windows updates for both virtual machines and the host server.</span></span> <span data-ttu-id="e430e-173">如果_EnableAutoUpdate_设置为**False**，请运行以下 cmdlet 以将其设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="e430e-173">If  _EnableAutoUpdate_ is set to **False**, run following cmdlet to set it to **True**.</span></span>
    
  ```powershell
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    <span data-ttu-id="e430e-174">此外，你还可以手动检查并安装更新。</span><span class="sxs-lookup"><span data-stu-id="e430e-174">Alternatively, you can manually check for and install updates.</span></span> <span data-ttu-id="e430e-175">请参阅下节内容。</span><span class="sxs-lookup"><span data-stu-id="e430e-175">See the next section.</span></span>
    
- <span data-ttu-id="e430e-176">**问题：收到一条错误消息：无法注册装置，因为当前输入/配置\<SiteName\>或\<ApplianceName\>或\<中介服务器 FQDN\>或\<中介服务器 IP 地址\>与现有装置相冲突。删除冲突装置或更新输入/配置信息，然后再次注册。' 当运行 Register-CcAppliance 将当前装置注册到联机时。**</span><span class="sxs-lookup"><span data-stu-id="e430e-176">**Issue: You receive an error message: Cannot register appliance because your current input/configuration \<SiteName\> or \<ApplianceName\> or \<Mediation Server FQDN\> or \<Mediation Server IP Address\> conflicts with existing appliance(s). Remove conflict appliance or update your input/configuration information then register again. ' when run Register-CcAppliance to register current appliance to online.**</span></span>
    
    <span data-ttu-id="e430e-177">**解决方案：**\<\>ApplianceName、 \<中介服务器\> FQDN 和\<中介服务器 IP 地址\>的值必须是唯一的，并且仅用于一个装置注册。</span><span class="sxs-lookup"><span data-stu-id="e430e-177">**Resolution:** Values for the \<ApplianceName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> must be unique and only used for one appliance registration.</span></span> <span data-ttu-id="e430e-178">默认情况下\<，\> ApplianceName 来自主机名。</span><span class="sxs-lookup"><span data-stu-id="e430e-178">By default, \<ApplianceName\> comes from the host name.</span></span> <span data-ttu-id="e430e-179">\<在配置 ini\>文件\<中定义的中介\>服务器 FQDN 和中介服务器 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="e430e-179">\<Mediation Server FQDN\> and \<Mediation Server IP Address\> defined in configuration ini file.</span></span>
    
    <span data-ttu-id="e430e-180">例如，使用 (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) 来注册 SiteName=MySite 时，如果存在已注册设备 (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10)，则会出现冲突。</span><span class="sxs-lookup"><span data-stu-id="e430e-180">For example, using (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) to register to SiteName=MySite, but if there is a registered appliance (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10), you will have the conflict.</span></span>
    
    <span data-ttu-id="e430e-181">首先，请检查 ApplianceRoot 目录部分中的 CloudConnector.ini 文件。</span><span class="sxs-lookup"><span data-stu-id="e430e-181">First, please check your CloudConnector.ini file in ApplianceRoot directory section.</span></span> <span data-ttu-id="e430e-182">你将获得\<文件\>中\<的 SiteName、\>中介\<服务器 FQDN 和中介\>服务器 IP 地址值。</span><span class="sxs-lookup"><span data-stu-id="e430e-182">You will get \<SiteName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> values in the file.</span></span> <span data-ttu-id="e430e-183">\<ApplianceName\>是你的主机服务器名称。</span><span class="sxs-lookup"><span data-stu-id="e430e-183">\<ApplianceName\> is your host server name.</span></span>
    
    <span data-ttu-id="e430e-184">其次，使用您的 Skype for Business 租户管理员凭据启动租户远程 PowerShell，然后运行以下 cmdlet 以检查已注册的装置。</span><span class="sxs-lookup"><span data-stu-id="e430e-184">Second, Launch Tenant Remote PowerShell using your Skype for Business tenant admin credentials, then run the following cmdlet to check the registered appliance(s).</span></span>
    
  ```powershell
  Get-CsHybridPSTNAppliance
  ```

    <span data-ttu-id="e430e-185">确定任何冲突后，可以使用与已注册设备匹配的信息更新 CloudConnector.ini 文件，或注销现有设备以解决冲突。</span><span class="sxs-lookup"><span data-stu-id="e430e-185">After identifying any conflicts, you can either update your CloudConnector.ini file with information that matches the registered appliance, or unregister the existing appliance to resolve the conflicts.</span></span>
    
  ```powershell
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- <span data-ttu-id="e430e-186">**问题：如果在主机上运行了已部署的装置，则 CcRunningVersion cmdlet 将返回空值。**</span><span class="sxs-lookup"><span data-stu-id="e430e-186">**Issue: The Get-CcRunningVersion cmdlet returns an empty value if there is a deployed appliance running on the host.**</span></span>
    
  <span data-ttu-id="e430e-187">**解决方案：** 从1.3.4 或1.3.8 升级到1.4.1 时，可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="e430e-187">**Resolution:** This can happen when you upgrade from 1.3.4 or 1.3.8 to 1.4.1.</span></span> <span data-ttu-id="e430e-188">在安装1.4.1 版本的版本后，必须在运行任何其他`Register-CcAppliance` cmdlet 之前运行。</span><span class="sxs-lookup"><span data-stu-id="e430e-188">After you install version 1.4.1 with the .msi, you must run `Register-CcAppliance` before you run any other cmdlet.</span></span> <span data-ttu-id="e430e-189">`Register-CcAppliance`会将%UserProfile%\CloudConnector 文件从迁移到%ProgramData%\CloudConnector。</span><span class="sxs-lookup"><span data-stu-id="e430e-189">`Register-CcAppliance` will migrate the module.ini file from %UserProfile%\CloudConnector to %ProgramData%\CloudConnector.</span></span> <span data-ttu-id="e430e-190">如果错过了它，将在%ProgramData%\CloudConnector 文件夹中创建新的 module .ini，并替换1.3.4 或1.3.8 的运行/备份版本信息。</span><span class="sxs-lookup"><span data-stu-id="e430e-190">If you missed it, a new module.ini will be created in %ProgramData%\CloudConnector folder and replace the running/backup version information for 1.3.4 or 1.3.8.</span></span>
    
  <span data-ttu-id="e430e-191">比较 %UserProfile%\CloudConnector 和 %ProgramData%\CloudConnector 文件夹中的 module.ini 文件。</span><span class="sxs-lookup"><span data-stu-id="e430e-191">Compare module.ini files in %UserProfile%\CloudConnector and %ProgramData%\CloudConnector folder.</span></span> <span data-ttu-id="e430e-192">如果存在差异，请在%ProgramData%\CloudConnector 中删除 module 文件，然后重新运行`Register-CcAppliance`。</span><span class="sxs-lookup"><span data-stu-id="e430e-192">If there are differences, delete the module.ini file in %ProgramData%\CloudConnector and rerun  `Register-CcAppliance`.</span></span> <span data-ttu-id="e430e-193">您也可以将文件手动修改为正确运行和备份的版本。</span><span class="sxs-lookup"><span data-stu-id="e430e-193">You could also modify the file manually to the correct running and backup version.</span></span>
    
- <span data-ttu-id="e430e-194">**问题：运行 CcVersion cmdlet 以切换到不同于当前脚本版本的旧版本时，此旧版本不提供任何高可用性支持。**</span><span class="sxs-lookup"><span data-stu-id="e430e-194">**Issue: After you run the Switch-CcVersion cmdlet to switch to an old version which is different from current script version, there is no High Availability support for this old version.**</span></span>
    
    <span data-ttu-id="e430e-195">**解决方案：** 例如，您已从1.4.1 升级到1.4.2。</span><span class="sxs-lookup"><span data-stu-id="e430e-195">**Resolution:** For example, you have upgraded from 1.4.1 to 1.4.2.</span></span> <span data-ttu-id="e430e-196">你的当前脚本版本（可以通过运行`Get-CcVersion`）和运行版本（这两个版本都`Get-CcRunningVersion`是1.4.2）确定。</span><span class="sxs-lookup"><span data-stu-id="e430e-196">Your current script version, which can be determined by running `Get-CcVersion`, and your running version, which can be determined by running  `Get-CcRunningVersion` are both 1.4.2.</span></span> <span data-ttu-id="e430e-197">此时，如果你运行`Switch-CcVersion`以将运行版本切换回1.4.1，则此旧版本不提供任何高可用性支持。</span><span class="sxs-lookup"><span data-stu-id="e430e-197">At this time, if you run `Switch-CcVersion` to switch the running version back to 1.4.1, then there will be no High Availability support for this old version.</span></span>
    
    <span data-ttu-id="e430e-p121">要获得完整的高可用性支持，请切换回 1.4.2，从而使运行版本和脚本版本相同。如果 1.4.2 部署出现问题，请尽快将其卸载并重新安装。</span><span class="sxs-lookup"><span data-stu-id="e430e-p121">To get full High Availability support, please switch back to 1.4.2, so the running version and script version are the same. If you are experiencing problems with your 1.4.2 deployment, please uninstall and reinstall it as soon as possible.</span></span>
    
- <span data-ttu-id="e430e-200">**问题：证书颁发机构证书或颁发给中央管理存储、中介服务器和边缘服务器的内部证书即将过期或已损坏。**</span><span class="sxs-lookup"><span data-stu-id="e430e-200">**Issue: Certificate authority certificates or internal certificates issued to Central Management Store, Mediation Server, and Edge Server are near expiration or are compromised.**</span></span>
    
    <span data-ttu-id="e430e-p122">**解决方法：** Skype for Business 证书颁发机构证书有效期为 5 年。颁发给中央管理存储、中介服务器和边缘服务器的内部证书有效期为 2 年。</span><span class="sxs-lookup"><span data-stu-id="e430e-p122">**Resolution:** Skype for Business certification authority certificates are valid for five years. Internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="e430e-203">在云连接器版本2.0 和更高版本中，CcServerCertificate cmdlet 已更改为更新-CcServerCertificate，续订 CcCACertificate cmdlet 已更改为 "更新-CcCACertificate"。</span><span class="sxs-lookup"><span data-stu-id="e430e-203">In Cloud Connector version 2.0 and later, the Renew-CcServerCertificate cmdlet has changed to Update-CcServerCertificate and the Renew-CcCACertificate cmdlet has changed to Update-CcCACertificate.</span></span> 
  
    <span data-ttu-id="e430e-204">如果向中央管理存储、中介服务器和边缘服务器颁发的内部证书即将到期或遭到破坏，请运行 CcServerCertificate 或 CcServerCertificate cmdlet 续订你的证书。</span><span class="sxs-lookup"><span data-stu-id="e430e-204">If internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are near expiration or compromised, run the Renew-CcServerCertificate or Update-CcServerCertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="e430e-205">如果证书颁发机构证书即将到期，请运行 CcCACertificate 或 CcCACertificate cmdlet 续订你的证书。</span><span class="sxs-lookup"><span data-stu-id="e430e-205">If certification authority certificates are near expiration, run the Renew-CcCACertificate or Update-CcCACertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="e430e-206">**如果证书颁发机构证书遭到破坏，并且站点中只有一个装置，请**执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="e430e-206">**If certification authority certificates are compromised and there is only one appliance in the site,** perform the following steps:</span></span>
    
1. <span data-ttu-id="e430e-207">运行 Enter-CcUpdate cmdlet 以排出服务并将该设备置于维护模式。</span><span class="sxs-lookup"><span data-stu-id="e430e-207">Run the Enter-CcUpdate cmdlet to drain services and put the appliance in maintenance mode.</span></span>
   
   ```powershell
   Enter-CcUpdate
   ```
   
2. <span data-ttu-id="e430e-208">运行以下 cmdlet 以重置证书颁发机构证书和所有内部服务器证书并创建相应的新证书：</span><span class="sxs-lookup"><span data-stu-id="e430e-208">Run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
    <span data-ttu-id="e430e-209">对于在2.0 之前的云连接器版本：</span><span class="sxs-lookup"><span data-stu-id="e430e-209">For Cloud Connector releases before 2.0:</span></span>
    
    ```powershell
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    <span data-ttu-id="e430e-210">或者对于云连接器版本2.0 和更高版本，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e430e-210">Or for Cloud Connector release 2.0 and later:</span></span>
    
    ```powershell
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```
    
3. <span data-ttu-id="e430e-211">如果在网关和中介服务器之间使用 TLS，请从设备运行 CcRootCertificate cmdlet，然后将导出的证书安装到 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="e430e-211">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from the appliance, and then install the exported certificate to your PSTN gateways.</span></span> <span data-ttu-id="e430e-212">您可能还需要重新签发您的网关的证书。</span><span class="sxs-lookup"><span data-stu-id="e430e-212">You may also be required to re-issue the certificate on your gateway.</span></span>

   ```powershell
   Export-CcRootCertificate
   ```

4. <span data-ttu-id="e430e-213">运行 CcUpdate cmdlet 以启动服务并退出维护模式。</span><span class="sxs-lookup"><span data-stu-id="e430e-213">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span>

   ```powershell
   Exit-CcUpdate
   ```


    <span data-ttu-id="e430e-214">**如果证书颁发机构证书遭到破坏，并且站点中有多个装置，请**在站点中的每个设备上执行以下顺序步骤。</span><span class="sxs-lookup"><span data-stu-id="e430e-214">**If certification authority certificates are compromised and there are multiple appliances in the site,** perform the following sequential steps on each appliance in the site.</span></span>
    
    <span data-ttu-id="e430e-215">Microsoft 建议你在非高峰使用时间内执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="e430e-215">Microsoft recommends that you perform these steps during non-peak usage times.</span></span>
    
1. <span data-ttu-id="e430e-216">在第一个设备上，运行 CcCertificationAuthorityFile cmdlet 以清理\<SiteRoot\>目录中的 CA 备份文件。</span><span class="sxs-lookup"><span data-stu-id="e430e-216">On the first appliance, run the Remove-CcCertificationAuthorityFile cmdlet to clean up the CA backup files in the \<SiteRoot\> directory.</span></span>

     ```powershell
     Remove-CcCertificationAuthorityFile
     ```
    
2. <span data-ttu-id="e430e-217">运行 CcUpdate cmdlet 以排出服务并将每台装置置于维护模式。</span><span class="sxs-lookup"><span data-stu-id="e430e-217">Run the Enter-CcUpdate cmdlet to drain services and put each appliance in maintenance mode.</span></span>

     ```powershell
     Enter-CcUpdate
     ```
    
3. <span data-ttu-id="e430e-218">在第一个设备上，运行以下 cmdlet 以重置和创建新的证书颁发机构证书和所有内部服务器证书：</span><span class="sxs-lookup"><span data-stu-id="e430e-218">On the first appliance, run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
     <span data-ttu-id="e430e-219">对于在2.0 之前的云连接器版本：</span><span class="sxs-lookup"><span data-stu-id="e430e-219">For Cloud Connector releases before 2.0:</span></span>
    
     ```powershell
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     <span data-ttu-id="e430e-220">或者对于云连接器版本2.0 和更高版本，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e430e-220">Or for Cloud Connector release 2.0 and later:</span></span>
    
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

4. <span data-ttu-id="e430e-221">在第一个设备上，运行以下 cmdlet 以将 CA 文件备份到\<SiteRoot\>文件夹。</span><span class="sxs-lookup"><span data-stu-id="e430e-221">On the first appliance, run the following cmdlet to back up the CA files to the \<SiteRoot\> folder.</span></span>
    
     ```powershell
     Backup-CcCertificationAuthority
     ```
   
5. <span data-ttu-id="e430e-222">在同一网站中的所有其他设备上，运行以下命令以使用 CA 备份文件，以便所有设备都使用相同的根证书，然后请求新的证书。</span><span class="sxs-lookup"><span data-stu-id="e430e-222">On all other appliance's in the same site, run the following commands to consume the CA backup files, so that the appliances all use the same root certificate, and then request new certificates.</span></span> 
   
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```
     
6. <span data-ttu-id="e430e-223">如果在网关和中介服务器之间使用 TLS，请从网站中的任何设备运行 Export-CcRootCertificate cmdlet，然后将导出的证书安装到 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="e430e-223">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from any appliance in the site, and then install the exported certificate to your PSTN gateways.</span></span> <span data-ttu-id="e430e-224">您可能还需要重新签发您的网关的证书。</span><span class="sxs-lookup"><span data-stu-id="e430e-224">You may also be required to re-issue the certificate on your gateway.</span></span>
  
     ```powershell
     Export-CcRootCertificate
     ```
     
7. <span data-ttu-id="e430e-225">运行 CcUpdate cmdlet 以启动服务并退出维护模式。</span><span class="sxs-lookup"><span data-stu-id="e430e-225">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span> 

     ```powershell
     Exit-CcUpdate
     ```
    
    
- <span data-ttu-id="e430e-226">**问题：在云连接器管理服务日志中收到以下错误消息： "C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log"： CceService 错误：0：将状态报告为 online 时出现意外异常：：为用户\<全局租户管理员\>登录失败。请创建一个新的凭据对象，确保您使用了正确的用户名和密码。---\>**</span><span class="sxs-lookup"><span data-stu-id="e430e-226">**Issue: You receive the following error message in the Cloud Connector Management Service Log, "C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": CceService Error: 0 : Unexpected exception when reporting status to online: System.Management.Automation.CmdletInvocationException: Logon failed for the user \<Global Tenant Admin\>. Please create a new credential object, making sure that you have used the correct user name and password. ---\>**</span></span>
    
    <span data-ttu-id="e430e-227">**解决方案：** Office 365 全局租户管理员凭据在注册云连接器设备后已更改。</span><span class="sxs-lookup"><span data-stu-id="e430e-227">**Resolution:** The Office 365 global tenant admin credentials have been changed since the Cloud Connector appliance was registered.</span></span> <span data-ttu-id="e430e-228">若要在云连接器装置上更新本地存储的凭据，请在主机设备上从管理员 PowerShell 中运行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e430e-228">To update the locally stored credentials on the Cloud Connector appliance, run the following from Administrator PowerShell on the host appliance:</span></span>
    
  ```powershell
  Set-CcCredential -AccountType TenantAdmin
  ```

- <span data-ttu-id="e430e-229">**问题：更改用于部署的主机服务器帐户的密码后，收到以下错误消息： "ConvertTo-SecureString： Key 不适合在指定状态下使用。" 在%ProgramFiles%\Skype for Business Cloud Connector 中使用Edition\ManagementService\CceManagementService.log 或运行 CcCredential cmdlet 时运行。**</span><span class="sxs-lookup"><span data-stu-id="e430e-229">**Issue: After you change the password for the host server account you used for the deployment, you receive the following error message: "ConvertTo-SecureString : Key not valid for use in specified state." in %ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log or while running the Get-CcCredential cmdlet.**</span></span>
    
    <span data-ttu-id="e430e-230">**解决方案：** 所有云连接器凭据均存储在以下文件中： "%SystemDrive%\Programdata\Cloudconnector\credentials。\<CurrentUser\>"。</span><span class="sxs-lookup"><span data-stu-id="e430e-230">**Resolution:** All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="e430e-231">当主机服务器上的密码更改时，需要更新本地存储的凭据。</span><span class="sxs-lookup"><span data-stu-id="e430e-231">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
    
    <span data-ttu-id="e430e-232">**如果你运行的是云连接器 1.4.2 版，** 请通过执行以下步骤来重新生成所有云连接器密码：</span><span class="sxs-lookup"><span data-stu-id="e430e-232">**If you are running Cloud Connector version 1.4.2,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  1. <span data-ttu-id="e430e-233">重新启动主机服务器。</span><span class="sxs-lookup"><span data-stu-id="e430e-233">Restart the host server.</span></span>
    
  2. <span data-ttu-id="e430e-234">删除以下文件： "%SystemDrive%\Programdata\Cloudconnector\credentials。\<CurrentUser\>"。</span><span class="sxs-lookup"><span data-stu-id="e430e-234">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
  3. <span data-ttu-id="e430e-235">以管理员身份启动 PowerShell 控制台，然后运行 "Register-CcAppliance" 以在描述后重新输入密码。</span><span class="sxs-lookup"><span data-stu-id="e430e-235">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="e430e-236">输入之前输入的用于云连接器部署的相同密码。</span><span class="sxs-lookup"><span data-stu-id="e430e-236">Enter the same passwords you entered before for the Cloud Connector deployment.</span></span>
    
     <span data-ttu-id="e430e-237">**如果你运行的是云连接器版本2.0 或更高版本，请**按照以下步骤重新生成所有云连接器密码：</span><span class="sxs-lookup"><span data-stu-id="e430e-237">**If you are running Cloud Connector version 2.0 or later,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  4. <span data-ttu-id="e430e-238">重新启动主机服务器。</span><span class="sxs-lookup"><span data-stu-id="e430e-238">Restart the host server.</span></span>
    
  5. <span data-ttu-id="e430e-239">删除以下文件： "%SystemDrive%\Programdata\Cloudconnector\credentials。\<CurrentUser\>"。</span><span class="sxs-lookup"><span data-stu-id="e430e-239">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" .</span></span>
    
  6. <span data-ttu-id="e430e-240">以管理员身份启动 PowerShell 控制台，然后运行 "Register-CcAppliance" 以在描述后重新输入密码。</span><span class="sxs-lookup"><span data-stu-id="e430e-240">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> 
    
     <span data-ttu-id="e430e-p128">如果缓存的密码文件是用云连接器 1.4.2 版生成的，请在系统提示时将 VMAdmin 密码用作 CceService 密码。输入之前用于云连接器部署的所有其他帐户的相同密码。</span><span class="sxs-lookup"><span data-stu-id="e430e-p128">If the cached password file was generated with Cloud Connector version 1.4.2, use the VMAdmin password for the CceService password when prompted. Enter the same password you entered before for the Cloud Connector deployment for all other accounts.</span></span>
    
     <span data-ttu-id="e430e-243">如果缓存的密码文件是用云连接器 1.4.2 版生成的，并且 DomainAdmin 和 VMAdmin 密码不同，则必须执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="e430e-243">If the cached password file was generated with Cloud Connector version 1.4.2 and the DomainAdmin and VMAdmin passwords are different, you must perform the following steps:</span></span>
    
  7. <span data-ttu-id="e430e-244">按如下所述运行 Set-CcCredential -AccountType DomainAdmin：</span><span class="sxs-lookup"><span data-stu-id="e430e-244">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
  8. <span data-ttu-id="e430e-245">当系统提示输入旧帐户凭据时，请输入用于 CceService 密码的凭据。</span><span class="sxs-lookup"><span data-stu-id="e430e-245">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
  9. <span data-ttu-id="e430e-246">当系统提示输入新帐户凭据时，请输入之前用于 DomainAdmin 密码的密码。</span><span class="sxs-lookup"><span data-stu-id="e430e-246">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
     <span data-ttu-id="e430e-247">如果缓存的密码文件是使用云连接器版本2.0 或更高版本生成的，则默认情况下，VmAdmin 和 DomainAdmin 使用与 CceService 相同的密码。</span><span class="sxs-lookup"><span data-stu-id="e430e-247">If the cached password file was generated with Cloud Connector version 2.0 or later, by default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="e430e-248">如果更改了 DomainAdmin 和 VMAdmin 密码，则必须执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="e430e-248">If you changed the DomainAdmin and VMAdmin passwords, you must perform the following steps:</span></span>
    
  10. <span data-ttu-id="e430e-249">按如下所述运行 Set-CcCredential -AccountType DomainAdmin：</span><span class="sxs-lookup"><span data-stu-id="e430e-249">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
       1. <span data-ttu-id="e430e-250">当系统提示输入旧帐户凭据时，请输入用于 CceService 密码的凭据。</span><span class="sxs-lookup"><span data-stu-id="e430e-250">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="e430e-251">当系统提示输入新帐户凭据时，请输入之前用于 DomainAdmin 密码的密码。</span><span class="sxs-lookup"><span data-stu-id="e430e-251">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
  11. <span data-ttu-id="e430e-252">按如下所述运行 Set-CcCredential -AccountType VmAdmin：</span><span class="sxs-lookup"><span data-stu-id="e430e-252">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
       1. <span data-ttu-id="e430e-253">当系统提示输入旧帐户凭据时，请输入用于 CceService 密码的凭据。</span><span class="sxs-lookup"><span data-stu-id="e430e-253">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="e430e-254">当系统提示输入新帐户凭据时，请输入之前用于 VmAdmin 密码的密码。</span><span class="sxs-lookup"><span data-stu-id="e430e-254">When prompted for the new account credential, enter the password for the VmAdmin password you used before.</span></span> 
    
- <span data-ttu-id="e430e-255">**问题：使用云连接器版本2.1 和更高版本时，在设备上运行 Register-CcAppliance 或其他 cmdlet 时，将收到一条错误消息，如： "对于每个对象：在此对象上找不到属性" Common "。验证该属性是否存在。在 C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1： 681 char： 14 "**</span><span class="sxs-lookup"><span data-stu-id="e430e-255">**Issue: With Cloud Connector version 2.1 and later, when running Register-CcAppliance or other cmdlets on the appliance, you receive an error message such as: "For Each-Object : The property 'Common' cannot be found on this object. Verify that the property exists. At C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char:14"**</span></span>
    
    <span data-ttu-id="e430e-256">**解决方案：** 云连接器2.1 及更高版本需要 .NET Framework 4.6.1 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="e430e-256">**Resolution:** Cloud Connector 2.1 and later requires .NET Framework 4.6.1 or later.</span></span> <span data-ttu-id="e430e-257">请将设备上的 .NET Framework 更新到版本4.6.1 或更高版本，然后再次运行 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e430e-257">Please update .NET Framework on the appliance to version 4.6.1 or later and run the cmdlet(s) again.</span></span>

- <span data-ttu-id="e430e-258">**问题：使用云连接器 Edition 2.1 时，你将收到一条错误消息，如下所示： "未能安装新实例，出现错误：无法设置" State "，因为只有字符串可以用作值来设置 XmlNode 属性"**</span><span class="sxs-lookup"><span data-stu-id="e430e-258">**Issue: With Cloud Connector Edition 2.1, when running Install-CcAppliance, you receive an error message such as: "Failed to install new instance with error: Cannot set "State" because only strings can be used as values to set XmlNode properties"**</span></span>

   <span data-ttu-id="e430e-259">**解决方案：** 在 Cloudconnector 中的 "[Common]" 部分下，请添加 "State" config，如下所示： CountryCode = US State = WA 市 = Redmond</span><span class="sxs-lookup"><span data-stu-id="e430e-259">**Resolution:** In Cloudconnector.ini, under the [Common] section, please add the “State” config as below:  CountryCode=US  State=WA  City=Redmond</span></span>

   <span data-ttu-id="e430e-260">不强制 "State" 行具有值，但无法从 Cloudconnector 文件中删除 "State" 行。</span><span class="sxs-lookup"><span data-stu-id="e430e-260">It is not mandatory for the "State" line to have value, however the "State" line cannot be removed from the Cloudconnector.ini file.</span></span>

- <span data-ttu-id="e430e-261">**问题：收到以下错误消息 "卸载-WindowsImage：卸载-WindowsImage 失败。安装或升级云连接器版本时出现错误代码 = 0xc1550115 "错误代码 ="。**</span><span class="sxs-lookup"><span data-stu-id="e430e-261">**Issue: You receive the following error message "Dismount-WindowsImage : Dismount-WindowsImage failed. Error code = 0xc1550115" when installing or upgrading Cloud Connector Edition.**</span></span>
    
    <span data-ttu-id="e430e-262">**解决方案：** 以管理员身份启动 PowerShell 控制台，请运行 "DISM 清理-Wim"。</span><span class="sxs-lookup"><span data-stu-id="e430e-262">**Resolution:** Launch a PowerShell console as administrator, run "DISM -Cleanup-Wim'".</span></span> <span data-ttu-id="e430e-263">这将清理所有 troubled 图像。</span><span class="sxs-lookup"><span data-stu-id="e430e-263">This will clean up all troubled images.</span></span> <span data-ttu-id="e430e-264">再次运行安装-CcAppliance 或等待 bits 自动升级。</span><span class="sxs-lookup"><span data-stu-id="e430e-264">Run Install-CcAppliance again or wait for the bits to automatically upgrade.</span></span>
    
- <span data-ttu-id="e430e-265">**问题：在 HA 环境中部署第一个云连接器设备失败**</span><span class="sxs-lookup"><span data-stu-id="e430e-265">**Issue: Deployment of the first Cloud Connector appliance in an HA environment fails**</span></span>
    
    <span data-ttu-id="e430e-266">**解决方案：** 所采取的步骤取决于部署失败的原因：</span><span class="sxs-lookup"><span data-stu-id="e430e-266">**Resolution:** The steps you take depend on the reason the deployment failed:</span></span>
    
  - <span data-ttu-id="e430e-267">如果第一个云连接器装置出现故障，而你无法确定失败的原因，则必须再次安装该装置，直到部署成功，然后再安装其他设备。</span><span class="sxs-lookup"><span data-stu-id="e430e-267">If the first Cloud Connector appliance fails and you cannot determine the reason for the failure, you must install the appliance again until the deployment is successful, and then install the other appliances.</span></span>
    
  - <span data-ttu-id="e430e-268">如果第一个云连接器设备在出现小问题（如外部证书问题）时失败，则可以在不重新安装设备的情况下修复该问题。</span><span class="sxs-lookup"><span data-stu-id="e430e-268">If the first Cloud Connector appliance fails with a minor issue, such as an external certificate issue, you might be able to fix the problem without re-installing the appliance.</span></span> <span data-ttu-id="e430e-269">然后，你可以使用租户远程 PowerShell 将部署标记为成功，如下所示。</span><span class="sxs-lookup"><span data-stu-id="e430e-269">You can then use tenant remote PowerShell to mark the deployment as successful as follows.</span></span> <span data-ttu-id="e430e-270">（如果第一个部署成功，但由于某些原因，云连接器无法将部署报告为成功，也可以使用以下步骤。）</span><span class="sxs-lookup"><span data-stu-id="e430e-270">(You can also use the following steps if the first deployment was successful, but, for some reason, Cloud Connector fails to report the deployment as a success.)</span></span>
    
  - <span data-ttu-id="e430e-271">若要获取第一个云连接器设备的标识（GUID），请运行 CsHybridPSTNAppliance cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e430e-271">To get the Identity (GUID) of the first Cloud Connector appliance, run the Get-CsHybridPSTNAppliance cmdlet.</span></span>
    
  - <span data-ttu-id="e430e-272">要将设备标记为已成功部署，请按如下方式运行 CsCceApplianceDeploymentStatus：</span><span class="sxs-lookup"><span data-stu-id="e430e-272">To mark the appliance as successfully deployed, run the Set-CsCceApplianceDeploymentStatus as follows:</span></span>
    
  ```powershell
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- <span data-ttu-id="e430e-273">**问题：你需要在主机服务器或虚拟机上手动检查并安装 Windows 更新。**</span><span class="sxs-lookup"><span data-stu-id="e430e-273">**Issue: You need to check for and install Windows updates manually on the host server or virtual machines.**</span></span>
    
   <span data-ttu-id="e430e-p133">**解决方法：** 建议你利用 Skype for Business 云连接器版本提供的操作系统自动更新。当设备经过注册以实现联机管理并且启用了操作系统自动更新之后，主机服务器和虚拟机将根据操作系统更新时间窗口设置自动检查并安装 Windows 更新。</span><span class="sxs-lookup"><span data-stu-id="e430e-p133">**Resolution:** We recommend that you take advantage of automated OS updates provided by Skype for Business Cloud Connector Edition. After an appliance is registered for online management and auto OS update is enabled, the host server and virtual machines will check and install Windows Updates automatically according to the OS update time window settings.</span></span>
    
   <span data-ttu-id="e430e-p134">如果你需要手动检查并安装 Windows 更新，请按照本节提供的适用于你的部署类型的步骤操作。你需要同时规划主机服务器及其上运行的虚拟机的更新，以便尽可能降低更新所需要的总停机时间。</span><span class="sxs-lookup"><span data-stu-id="e430e-p134">If you need to check for and install Windows Updates manually, follow the steps in this section that apply to your type of deployment. You should plan on updating both the host server and the virtual machines running on it at the same time to minimize the amount of down time necessary for the updates.</span></span>
    
   <span data-ttu-id="e430e-p135">如果你愿意，可以使用 Windows Server 更新服务 (WSUS) 服务器向云连接器服务器提供更新。只需确保将 Windows 更新配置为**不要**自动安装即可。</span><span class="sxs-lookup"><span data-stu-id="e430e-p135">If you prefer, you can use a Windows Server Update Services (WSUS) server to provide updates to Cloud Connector servers. Just be sure to configure the Windows Update to **not** install automatically.</span></span>
    
   <span data-ttu-id="e430e-280">有关如何手动更新云连接器部署的信息，请参阅下节。</span><span class="sxs-lookup"><span data-stu-id="e430e-280">For information about how to manually update your Cloud Connector deployment, see the following section.</span></span>
    
- <span data-ttu-id="e430e-281">**问题：当云连接器更新新版本时，不会更新云连接器 cmdlet。**</span><span class="sxs-lookup"><span data-stu-id="e430e-281">**Issue: When Cloud Connector updates to a new build, Cloud Connector cmdlets are not updated.**</span></span> <span data-ttu-id="e430e-282">如果在自动更新发生时，PowerShell 窗口保持打开，有时会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="e430e-282">This sometimes happens if a PowerShell window is left open when automatic update occurs.</span></span>
    
  <span data-ttu-id="e430e-283">**解决方案：** 若要加载更新的 cmdlet，可以执行以下任一步骤：</span><span class="sxs-lookup"><span data-stu-id="e430e-283">**Resolution:** To load the updated cmdlets, you can do either of the following steps:</span></span>
    
   - <span data-ttu-id="e430e-284">在云连接器设备上关闭 PowerShell，然后重新打开 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="e430e-284">Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.</span></span>
    
     - <span data-ttu-id="e430e-285">或者，你可以运行 Import-Module CloudConnector。</span><span class="sxs-lookup"><span data-stu-id="e430e-285">Or, you can run Import-Module CloudConnector -Force.</span></span> 
 
-   <span data-ttu-id="e430e-286">**问题： "无法将术语" Stop-CsWindowsService "识别为 cmdlet、函数、脚本文件或可运行程序的名称。尝试运行 CcUpdate cmdlet 时出错。**</span><span class="sxs-lookup"><span data-stu-id="e430e-286">**Issue: "The term 'Stop-CsWindowsService' is not recognized as the name of a cmdlet, function, script file, or operable program." error when attempting to run Enter-CcUpdate cmdlet.**</span></span>

    <span data-ttu-id="e430e-287">**解决方案：** 删除 $HOME \AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache 文件。</span><span class="sxs-lookup"><span data-stu-id="e430e-287">**Resolution:** Delete the $HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache file.</span></span>
<span data-ttu-id="e430e-288">PowerShell 将此文件创建为它所发现的模块中的 cmdlet 的缓存，这样就不必每次重新分析所有模块，因为这样做会非常慢。</span><span class="sxs-lookup"><span data-stu-id="e430e-288">PowerShell creates this file as a cache of cmdlets from modules that it finds so that it doesn’t have to re-analyze all the modules each time as that would make things really slow.</span></span> <span data-ttu-id="e430e-289">在从该缓存中读取时，很可能是出现了一些文件损坏，可向 PowerShell 提供误导性结果。</span><span class="sxs-lookup"><span data-stu-id="e430e-289">Most likely, there was some file corruption that provided misleading results to PowerShell when it was reading back from that cache.</span></span>

-   <span data-ttu-id="e430e-290">**问题： "Import-Module CloudConnector" 生成错误 "Import-模块：未加载指定的模块" CloudConnector "，因为在任何模块目录中都找不到有效的模块文件"**</span><span class="sxs-lookup"><span data-stu-id="e430e-290">**Issue: “Import-Module CloudConnector” generates error “Import-Module: The specified module “CloudConnector” was not loaded because no valid module file was found in any module directory”**</span></span>

    <span data-ttu-id="e430e-291">**解决方法：**</span><span class="sxs-lookup"><span data-stu-id="e430e-291">**Resolution:**</span></span>
    - <span data-ttu-id="e430e-292">验证在 c:\Program Files\WindowsPowerShell\Modules 下确实存在 CloudConnector 模块</span><span class="sxs-lookup"><span data-stu-id="e430e-292">Validate that indeed the CloudConnector module exists under c:\Program Files\WindowsPowerShell\Modules</span></span>
    
    - <span data-ttu-id="e430e-293">验证 CloudConnector 模块存在于此位置下后，可以更改存储模块位置的 PSModulePath 环境变量：</span><span class="sxs-lookup"><span data-stu-id="e430e-293">After validating that CloudConnector module exists under this location, the PSModulePath environment variable storing the path to the locations of the modules can be changed:</span></span>
    
     <span data-ttu-id="e430e-294">a.</span><span class="sxs-lookup"><span data-stu-id="e430e-294">a.</span></span> <span data-ttu-id="e430e-295">临时更改：以管理员身份启动 Powershell，并运行以下命令： $env:P SModulePath = $env:P SModulePath + ";C:\Program Files\WindowsPowerShell\Modules\"</span><span class="sxs-lookup"><span data-stu-id="e430e-295">Temporary change: Start Powershell as an Administrator and run the following command: $env:PSModulePath = $env:PSModulePath + ";C:\Program Files\WindowsPowerShell\Modules\"</span></span>
        
     <span data-ttu-id="e430e-296">b.</span><span class="sxs-lookup"><span data-stu-id="e430e-296">b.</span></span> <span data-ttu-id="e430e-297">对于永久更改，以管理员身份启动 PowerShell，并逐个运行以下命令： $CurrentValue = [环境]：： GetEnvironmentVariable （"PSModulePath"、"Machine"） SetEnvironmentVariable （"PSModulePath"，"Machine"）（""，$CurrentValue + ";C:\Program Files\WindowsPowerShell\Modules "，" Machine "）</span><span class="sxs-lookup"><span data-stu-id="e430e-297">For persistent change, Start PowerShell as an Administrator and run the following commands, one by one: $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine") SetEnvironmentVariable("PSModulePath", $CurrentValue + "; C:\Program Files\WindowsPowerShell\Modules", "Machine")</span></span>

    
## <a name="install-windows-updates-manually"></a><span data-ttu-id="e430e-298">手动安装 Windows 更新</span><span class="sxs-lookup"><span data-stu-id="e430e-298">Install Windows updates manually</span></span>

<span data-ttu-id="e430e-299">如果你不想在自己的环境中使用自动更新，请按照以下步骤操作，以手动检查并应用 Windows 更新。</span><span class="sxs-lookup"><span data-stu-id="e430e-299">If you do not want to use automatic updates in your environment, follow these steps to manually check for and apply Windows updates.</span></span> <span data-ttu-id="e430e-300">检查并安装 Windows 更新可能需要重新启动服务器。</span><span class="sxs-lookup"><span data-stu-id="e430e-300">Checking for and installing Windows updates may require a server restart.</span></span> <span data-ttu-id="e430e-301">当主机服务器重新启动时，用户将无法使用云连接器进行呼叫或接收呼叫。</span><span class="sxs-lookup"><span data-stu-id="e430e-301">When a host server is restarting, users will not be able to use Cloud Connector to place or receive calls.</span></span> <span data-ttu-id="e430e-302">你可以手动检查并安装更新，以控制更新发生时间，然后根据需要在你选择的时间重新启动计算机，以避免服务中断。</span><span class="sxs-lookup"><span data-stu-id="e430e-302">You can manually check for and install updates to control when the updates take place, and then restart the machines as needed during times you choose to avoid disruption of services.</span></span>
  
<span data-ttu-id="e430e-303">要手动检查更新，请连接到每台主机服务器，并打开“**控制面板**”。</span><span class="sxs-lookup"><span data-stu-id="e430e-303">To manually check for updates, connect to each host server and open the **Control Panel**.</span></span> <span data-ttu-id="e430e-304">选择 "**系统和\>安全 Windows 更新**"，然后根据你的环境相应地管理更新和服务器重启。</span><span class="sxs-lookup"><span data-stu-id="e430e-304">Select **System and Security \>Windows Update**, and then manage the updates and server restarts as appropriate for your environment.</span></span>
  
- <span data-ttu-id="e430e-305">如果站点中只有一个设备，请连接到每个虚拟机，并打开“**控制面板**”。</span><span class="sxs-lookup"><span data-stu-id="e430e-305">If there is only one appliance in the site, connect to each virtual machine and open the **Control Panel**.</span></span> <span data-ttu-id="e430e-306">选择 "**系统和\>安全 Windows 更新**"，然后根据需要配置更新和服务器重启。</span><span class="sxs-lookup"><span data-stu-id="e430e-306">Select **System and Security \>Windows Update**, and then configure the updates and server restarts as appropriate.</span></span>
    
- <span data-ttu-id="e430e-p143">如果站点中有多个设备，更新期间用户将无法访问正在更新和重新启动的实例。用户将连接到部署中的其他实例，直到更新完成后所有虚拟机及虚拟机上的所有 Skype for Business 服务启动为止。为避免任何潜在的服务中断，可以在应用更新时从 HA 删除实例，然后在完成后将其还原。为此：</span><span class="sxs-lookup"><span data-stu-id="e430e-p143">If there are more than one appliance in the site, the instance being updated and restarted cannot be accessed by users during the updates. Users will connect to other instances in the deployment until all virtual machines and all Skype for Business services start on the virtual machines after the updates are completed. To avoid any potential disruption to service, you can remove the instance from HA while you apply the updates, and then restore it when complete. To do so:</span></span>
    
1. <span data-ttu-id="e430e-311">在每台主机服务器上，以管理员身份打开 PowerShell 控制台。</span><span class="sxs-lookup"><span data-stu-id="e430e-311">On each host server, open a PowerShell console as administrator.</span></span>
    
2. <span data-ttu-id="e430e-312">使用以下 cmdlet 从 HA 删除实例：</span><span class="sxs-lookup"><span data-stu-id="e430e-312">Remove the instance from HA with the following cmdlet:</span></span>
    
   ```powershell
   Enter-CcUpdate
   ```

3. 
    
    <span data-ttu-id="e430e-313">按照适用于单个实例的步骤，手动应用更新并重新启动虚拟机。</span><span class="sxs-lookup"><span data-stu-id="e430e-313">Follow the steps for a single instance to manually apply the updates and restart the virtual machine.</span></span>
    
4. <span data-ttu-id="e430e-314">使用以下 cmdlet 将实例重新设置为 HA：</span><span class="sxs-lookup"><span data-stu-id="e430e-314">Set the instance back to HA with the following cmdlet:</span></span>
    
   ```powershell
   Exit-CcUpdate
   ```

<span data-ttu-id="e430e-315">对于多站点部署，请为部署中的每个站点执行适用于单个站点的步骤，每次向一个站点应用更新。</span><span class="sxs-lookup"><span data-stu-id="e430e-315">For multi-site deployments, follow the steps for a single site for each site in the deployment, applying updates to one site at a time.</span></span>
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a><span data-ttu-id="e430e-316">在云连接器主机计算机上安装防病毒软件时的提示</span><span class="sxs-lookup"><span data-stu-id="e430e-316">Tips when installing anti-virus software on the Cloud Connector host machine</span></span>

<span data-ttu-id="e430e-317">如果需要在云连接器主机上安装防病毒软件，您需要添加以下排除项：</span><span class="sxs-lookup"><span data-stu-id="e430e-317">If you need to install anti-virus software on the Cloud Connector host machine, you need to add the following exclusions:</span></span>
  
- <span data-ttu-id="e430e-318">每台计算机上的本地装置目录。</span><span class="sxs-lookup"><span data-stu-id="e430e-318">Local Appliance Directory on each machine.</span></span>
    
- <span data-ttu-id="e430e-319">每台计算机上的远程网站目录。</span><span class="sxs-lookup"><span data-stu-id="e430e-319">Remote Site Directory on each machine.</span></span>
    
- <span data-ttu-id="e430e-320">计算机上的本地网站目录托管了共享网站根文件夹。</span><span class="sxs-lookup"><span data-stu-id="e430e-320">Local Site Directory on the machine hosts the shared site root folder.</span></span>
    
- <span data-ttu-id="e430e-321">%ProgramFiles%\Skype for Business 云连接器版</span><span class="sxs-lookup"><span data-stu-id="e430e-321">%ProgramFiles%\Skype for Business Cloud Connector Edition</span></span>
    
- <span data-ttu-id="e430e-322">%ALLUSERSPROFILE%\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="e430e-322">%ALLUSERSPROFILE%\CloudConnector</span></span>
    
- <span data-ttu-id="e430e-323">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="e430e-323">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span></span>
    
- <span data-ttu-id="e430e-324">进程 Microsoft .aspx. ManagementService。</span><span class="sxs-lookup"><span data-stu-id="e430e-324">The process Microsoft.Rtc.CCE.ManagementService.exe.</span></span>
