---
title: 对云连接器部署进行故障排除
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/5/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e6cf58cc-dbd9-4f35-a51a-3e2fea71b5a5
description: 对你的云连接器版本部署进行故障排除。
ms.openlocfilehash: 7a1caea67c5b5899c2dc0909ef771a57c7c50389
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359328"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a><span data-ttu-id="52001-103">对云连接器部署进行故障排除</span><span class="sxs-lookup"><span data-stu-id="52001-103">Troubleshoot your Cloud Connector deployment</span></span>

> [!Important]
> <span data-ttu-id="52001-104">云连接器版本将在2021年7月31日和 Skype for Business Online 之间终止。</span><span class="sxs-lookup"><span data-stu-id="52001-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="52001-105">组织升级到团队后，了解如何使用 [直接路由](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)将本地电话网络连接到团队。</span><span class="sxs-lookup"><span data-stu-id="52001-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>
 
<span data-ttu-id="52001-106">对你的云连接器版本部署进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="52001-106">Troubleshoot your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="52001-107">本主题介绍云连接器版本部署的常见问题的解决方案。</span><span class="sxs-lookup"><span data-stu-id="52001-107">This topic describes solutions to common issues with Cloud Connector Edition deployments.</span></span> <span data-ttu-id="52001-108">如果从公开交换的电话网络 (PSTN) 遇到问题，可以按照本主题中所述的解决方案进行调查。</span><span class="sxs-lookup"><span data-stu-id="52001-108">If you are experiencing issues with calls to and from the Public Switched Telephone Network (PSTN), you can investigate by following the solutions described in this topic.</span></span>
  
<span data-ttu-id="52001-109">云连接器提供了用于自动解决某些问题的内置机制。</span><span class="sxs-lookup"><span data-stu-id="52001-109">Cloud Connector provides built-in mechanisms for automatically resolving some issues.</span></span> <span data-ttu-id="52001-110">自动检测过程会查找云连接器设备的潜在问题，如果可能，则会采取纠正措施来解决这些问题，而无需管理员干预。</span><span class="sxs-lookup"><span data-stu-id="52001-110">An automatic detection process looks for potential issues with the Cloud Connector appliances, and, if possible, takes corrective action to resolve those issues without the need for administrator intervention.</span></span> <span data-ttu-id="52001-111">检测过程按如下方式工作：</span><span class="sxs-lookup"><span data-stu-id="52001-111">The detection process works as follows:</span></span>
  
- <span data-ttu-id="52001-112">**检测序列：** 云连接器管理服务每60秒运行一次进程，以检测设备是否已关闭。</span><span class="sxs-lookup"><span data-stu-id="52001-112">**Detection sequence:** The Cloud Connector Management service runs a process every 60 seconds for detecting whether an appliance is down.</span></span> <span data-ttu-id="52001-113">在云连接器版本2.0 及更高版本中，检测过程使用 Skype for Business 公司网络交换机建立到云连接器计算机的 PowerShell 连接;对于2.0 之前的版本，检测过程使用云连接器管理交换机。</span><span class="sxs-lookup"><span data-stu-id="52001-113">In Cloud Connector version 2.0 and later, the detection process uses the Skype for Business Corpnet switch for making PowerShell connections to the Cloud Connector machines; for versions previous to 2.0, the detection process uses the Cloud Connector management switch.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="52001-114">若要成功进行自动恢复，主机和虚拟机之间必须有主机网络交换机之间的网络连接。</span><span class="sxs-lookup"><span data-stu-id="52001-114">For automatic recovery to succeed, there must be network connectivity between the host and virtual machines over the host network switch.</span></span> <span data-ttu-id="52001-115">请务必检查网络连接，以确保自动检测和恢复能够成功。</span><span class="sxs-lookup"><span data-stu-id="52001-115">Be sure to check network connectivity to ensure that automatic detection and recovery can succeed.</span></span> 
  
- <span data-ttu-id="52001-116">**监控：** 在云连接器版本2.0 和更高版本中监视以下服务：</span><span class="sxs-lookup"><span data-stu-id="52001-116">**Monitoring:** The following services are monitored in Cloud Connector version 2.0 and later:</span></span>
    
  - <span data-ttu-id="52001-117">虚拟机未连接到云连接器企业或 Internet 虚拟交换机</span><span class="sxs-lookup"><span data-stu-id="52001-117">Virtual Machines are not connected to the Cloud Connector Corporate or Internet virtual switches</span></span>
    
  - <span data-ttu-id="52001-118">虚拟机处于 "已保存" 或 "已停止" 状态</span><span class="sxs-lookup"><span data-stu-id="52001-118">Virtual Machines are in a saved or stopped status</span></span>
    
  - <span data-ttu-id="52001-119">中央管理服务器服务：副本、主机</span><span class="sxs-lookup"><span data-stu-id="52001-119">Central Management Server services: REPLICA, MASTER</span></span>
    
  - <span data-ttu-id="52001-120">中介服务器服务：副本、RTCSRV 和 MEDSVC</span><span class="sxs-lookup"><span data-stu-id="52001-120">Mediation Server services: REPLICA, RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="52001-121">边缘服务器服务：副本、RTCSRV、RTCDATAPROXY、RTCMRAUTH、RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="52001-121">Edge Server services: REPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY</span></span>
    
  - <span data-ttu-id="52001-122">在边缘服务器上对 CS RTCSRV 禁用了入站防火墙规则，在中介服务器上的 CS RTCMEDSRV</span><span class="sxs-lookup"><span data-stu-id="52001-122">Inbound firewall rules are disabled for CS RTCSRV on Edge server, CS RTCMEDSRV on Mediation server</span></span>
    
    <span data-ttu-id="52001-123">在云连接器1.4.2 版中，仅监视以下服务：</span><span class="sxs-lookup"><span data-stu-id="52001-123">In Cloud Connector version 1.4.2, only the following services are monitored:</span></span>
    
  - <span data-ttu-id="52001-124">中介服务器服务： RTCSRV 和 MEDSVC</span><span class="sxs-lookup"><span data-stu-id="52001-124">Mediation Server services: RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="52001-125">边缘服务器服务： RTCSRV</span><span class="sxs-lookup"><span data-stu-id="52001-125">Edge Server service: RTCSRV</span></span>
    
- <span data-ttu-id="52001-126">**恢复过程：** 如果任何受监控的服务关闭，则会将设备标为关闭状态，并将其停止并标记为手动，直到解决所有问题。</span><span class="sxs-lookup"><span data-stu-id="52001-126">**Recovery process:** If any monitored services are down, an appliance is marked down, and services are stopped and marked manual until all issues can be resolved.</span></span> <span data-ttu-id="52001-127">这将阻止呼叫路由到可能导致呼叫故障的设备。</span><span class="sxs-lookup"><span data-stu-id="52001-127">This will prevent calls from routing to an appliance that may cause call failures.</span></span>
    
    <span data-ttu-id="52001-128">云连接器管理服务将重试自动恢复，如下所示</span><span class="sxs-lookup"><span data-stu-id="52001-128">The Cloud Connector Management service will retry automatic recovery as follows</span></span>
    
  - <span data-ttu-id="52001-129">初始重试间隔为10秒，最长间隔时间为一小时。</span><span class="sxs-lookup"><span data-stu-id="52001-129">The initial retry interval is every ten seconds with a maximum interval time of one hour.</span></span>
    
  - <span data-ttu-id="52001-130">对于前三次恢复尝试，间隔时间为10秒。</span><span class="sxs-lookup"><span data-stu-id="52001-130">For the first three recovery attempts, the interval time is 10 seconds.</span></span> <span data-ttu-id="52001-131">从第四次重试开始，间隔时间将增加上一个间隔时间的两倍。</span><span class="sxs-lookup"><span data-stu-id="52001-131">Starting from the fourth retry, the interval time increases by two times the previous interval time.</span></span> <span data-ttu-id="52001-132">例如，第四次重试将在20秒内发生，第五次为40秒，依此类推。</span><span class="sxs-lookup"><span data-stu-id="52001-132">For example, the fourth retry will occur in 20 seconds, the fifth in 40 seconds, and so on.</span></span> 
    
  - <span data-ttu-id="52001-133">当达到一个小时的最长间隔时间时，每小时的重试次数将继续进行一次。</span><span class="sxs-lookup"><span data-stu-id="52001-133">When the maximum interval time of one hour is reached, retries will continue once per hour.</span></span>
    
  - <span data-ttu-id="52001-134">恢复成功后，间隔和重试次数将设置为其初始值。</span><span class="sxs-lookup"><span data-stu-id="52001-134">When recovery is successful, the interval and retry counts are set to their initial values.</span></span>
    
  - <span data-ttu-id="52001-135">如果重新启动管理服务，则会将间隔和重试次数重置为其初始值。</span><span class="sxs-lookup"><span data-stu-id="52001-135">If the Management service is restarted, the interval and retry counts are reset to their initial values.</span></span>
    
## <a name="troubleshooting"></a><span data-ttu-id="52001-136">疑难解答</span><span class="sxs-lookup"><span data-stu-id="52001-136">Troubleshooting</span></span>

<span data-ttu-id="52001-137">以下是经常遇到的问题的解决方案：</span><span class="sxs-lookup"><span data-stu-id="52001-137">Following are solutions to commonly encountered issues:</span></span>
  
- <span data-ttu-id="52001-138">**问题：运行部署脚本时，部署失败或停止响应。登录到每个 VM 后，管理/内部/外部 NIC 的 IP 地址缺失或不正确。**</span><span class="sxs-lookup"><span data-stu-id="52001-138">**Issue: Deployment fails or stops responding when running the deployment scripts. After logging on to each VM, the IP address is missing or incorrect for the Management/Internal/External NIC.**</span></span>
    
    <span data-ttu-id="52001-139">**解决方法：** 无法自动解决此问题。</span><span class="sxs-lookup"><span data-stu-id="52001-139">**Resolution:** This issue cannot be resolved automatically.</span></span> <span data-ttu-id="52001-140">Nic 在运行时无法添加到虚拟机。</span><span class="sxs-lookup"><span data-stu-id="52001-140">NICs cannot be added to VMs while they are running.</span></span> <span data-ttu-id="52001-141">请在 hyper-v 管理器中关闭并删除这些虚拟机，然后运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="52001-141">Please shut down and remove these VMs in hyper-v manager, then run the following cmdlets:</span></span>
    
  ```powershell
  Uninstall-CcAppliance
  ```

  ```powershell
  Install-CcAppliance
  ```

- 
    
    <span data-ttu-id="52001-142">**问题：安装 Active Directory 服务器和林后，CMS 服务器和/或中介服务器未正确加入域。**</span><span class="sxs-lookup"><span data-stu-id="52001-142">**Issue: After the Active Directory Server and forest are installed, the CMS Server and/or Mediation Server did not join the domain correctly.**</span></span>
    
    <span data-ttu-id="52001-143">**解决方法：** 若要解决此问题，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="52001-143">**Resolution:** To resolve this issue, take the following steps:</span></span>
    
  - <span data-ttu-id="52001-144">登录到 Active Directory 服务器，并验证是否已正确创建域。</span><span class="sxs-lookup"><span data-stu-id="52001-144">Log on to the Active Directory Server and verify that the domain was created correctly.</span></span>
    
  - <span data-ttu-id="52001-145">登录到 CMS/中介服务器，并验证在 "企业网络 NIC" 上是否分配了有效的 IP 地址，以及是否将有效的静态 IP 和 DNS 配置为 AD 服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="52001-145">Log on to the CMS/Mediation Server and verify that on the corpnet NIC a valid IP address is assigned, and that valid static IP and DNS is configured as the AD server's IP address.</span></span>
    
  - <span data-ttu-id="52001-146">登录到 CMS/中介服务器，打开命令提示符。</span><span class="sxs-lookup"><span data-stu-id="52001-146">Log on to the CMS/Mediation Server, and open a command prompt.</span></span> <span data-ttu-id="52001-147">请确保您可以 ping Active Directory 服务器的 FQDN 和 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="52001-147">Make sure you can ping the FQDN and IP address of the Active Directory Server.</span></span> <span data-ttu-id="52001-148">如果不能，则可能存在 IP 地址冲突。</span><span class="sxs-lookup"><span data-stu-id="52001-148">If you cannot, there may be an IP address conflict.</span></span> <span data-ttu-id="52001-149">请尝试为 Active Directory 分配新 IP 并相应更新 CMS/中介服务器上的 DNS。</span><span class="sxs-lookup"><span data-stu-id="52001-149">Please try to assign a new IP for Active Directory and update DNS on the CMS/Mediation server accordingly.</span></span>
    
- <span data-ttu-id="52001-150">**问题：在删除虚拟以太网交换机时收到以下错误消息 "Remove-VMSwitch：失败"。无法删除虚拟交换机 "云连接器管理交换机"，因为它正在被运行虚拟机或分配到子池。 "**</span><span class="sxs-lookup"><span data-stu-id="52001-150">**Issue: You receive the following error message, "Remove-VMSwitch : Failed while removing virtual Ethernet switch. The virtual switch 'Cloud Connector Management Switch' cannot be deleted because it is being used by running virtual machines or assigned to child pools."**</span></span>
    
    <span data-ttu-id="52001-151">**解决方法：** 部署后，不会删除 "云连接器管理开关"。</span><span class="sxs-lookup"><span data-stu-id="52001-151">**Resolution:** The "Cloud Connector Management Switch" was not deleted after the deployment.</span></span> <span data-ttu-id="52001-152">如果遇到此错误，请转到 Hyper-v 管理器，并验证是否仍有虚拟机仍连接到它。</span><span class="sxs-lookup"><span data-stu-id="52001-152">If you hit this error, please go to Hyper-v manager and verify that there is not still a virtual machine still connected to it.</span></span> <span data-ttu-id="52001-153">如果仍有虚拟机处于连接状态，请将其断开连接并删除管理交换机。</span><span class="sxs-lookup"><span data-stu-id="52001-153">If there are virtual machines still connected, disconnect them and delete the management switch.</span></span> <span data-ttu-id="52001-154">如果仍无法删除管理交换机，请重新启动主机服务器并重试。</span><span class="sxs-lookup"><span data-stu-id="52001-154">If the management switch still cannot be deleted, restart the host server and try again.</span></span>
    
- <span data-ttu-id="52001-155">**问题：收到以下错误消息： "服务 RTCMRAUTH 无法启动。请进行检查以确保该服务未被禁用。**</span><span class="sxs-lookup"><span data-stu-id="52001-155">**Issue: You receive the following error message, "Service RTCMRAUTH failed to start. Check to make sure the service is not disabled."**</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="52001-156">此问题仅适用于1.4.2 之前的云连接器版本。</span><span class="sxs-lookup"><span data-stu-id="52001-156">This issue only applies to Cloud Connector versions earlier than 1.4.2.</span></span> 
  
    <span data-ttu-id="52001-157">启动失败也可能是因为此前端服务器以前通过使用计算机故障转移) 进行了故障转移 (。</span><span class="sxs-lookup"><span data-stu-id="52001-157">The failure to start could also be because this Front End server was previously failed over (using computer fail over).</span></span> <span data-ttu-id="52001-158">如果是这种情况，请使用计算机故障回复调用故障回复 () 。</span><span class="sxs-lookup"><span data-stu-id="52001-158">If that's the case, please invoke fail back (using computer fail back).</span></span>
    
    <span data-ttu-id="52001-159">**解决方法：** 如果边缘服务器不信任根 CA 证书或中间 CA 证书，则会在边缘服务器上发生此问题。</span><span class="sxs-lookup"><span data-stu-id="52001-159">**Resolution:** This issue happens on an Edge Server when the root CA certificate or intermediate CA certificate is not trusted by the Edge Server.</span></span> <span data-ttu-id="52001-160">即使可以导入外部证书，但证书链已断开。</span><span class="sxs-lookup"><span data-stu-id="52001-160">Even if the external certificate can be imported but the certificate chain is broken.</span></span> <span data-ttu-id="52001-161">在此情况下，RTCMRAUTH 和/或 RTCSRV 服务无法启动。</span><span class="sxs-lookup"><span data-stu-id="52001-161">Under this condition, the RTCMRAUTH and/or RTCSRV service can not start.</span></span>
    
    <span data-ttu-id="52001-162">请手动将外部证书的根 CA 证书和所有中间 CA 证书导入边缘服务器，然后重新启动边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="52001-162">Please import the root CA certificate and all intermediate CA certificates of your external certificate manually into the Edge Server and then restart the Edge Server.</span></span> <span data-ttu-id="52001-163">在边缘服务器上看到 RTCMRAUTH 和 RTCSRV 服务启动后，返回到主机服务器，以管理员身份启动 PowerShell 控制台，然后运行以下 cmdlet 以切换到新部署：</span><span class="sxs-lookup"><span data-stu-id="52001-163">After you see the RTCMRAUTH and RTCSRV services started on the Edge Server, go back to your host server, launch a PowerShell console as administrator, and run following cmdlet to switch to the new deployment:</span></span>
    
  ```powershell
  Switch-CcVersion
  ```

- 
    
    <span data-ttu-id="52001-164">**问题：应用 Windows 更新时主机服务器重新启动，并且由服务器提供服务的呼叫失败。**</span><span class="sxs-lookup"><span data-stu-id="52001-164">**Issue: The host server was restarted when Windows updates were applied, and calls serviced by the server are failing.**</span></span>
    
    <span data-ttu-id="52001-165">**解决方法：** 如果您部署了高可用性环境，Microsoft 将提供一个 cmdlet，可帮助您在手动检查和安装 Windows 更新时将一台主机计算机 (部署) 移入或移出当前拓扑。</span><span class="sxs-lookup"><span data-stu-id="52001-165">**Resolution:** If you deployed a high availability environment, Microsoft provides a cmdlet to help move one host machine (deployment instance) into or out of the current topology when you check and install Windows update manually.</span></span> <span data-ttu-id="52001-166">使用以下步骤来实现此目的：</span><span class="sxs-lookup"><span data-stu-id="52001-166">Use the following steps to accomplish this:</span></span>
    
1. <span data-ttu-id="52001-167">在主机服务器上，以管理员身份启动 PowerShell 控制台，然后运行：</span><span class="sxs-lookup"><span data-stu-id="52001-167">On the host server, start a PowerShell console as administrator, then run:</span></span>
    
   ```powershell
   Enter-CcUpdate
   ```

2. <span data-ttu-id="52001-168">检查并安装可用的更新程序。</span><span class="sxs-lookup"><span data-stu-id="52001-168">Check for updates and install any that are available.</span></span>
    
3. <span data-ttu-id="52001-169">在 PowerShell 控制台中，运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="52001-169">In the PowerShell console, run the following cmdlet:</span></span>
    
   ```powershell
   Exit-CcUpdate
   ```

- 
    
    <span data-ttu-id="52001-170">**问题：使用 PSTN 号码从 Skype for Business 客户端进行呼叫时，无法通过邀请其他 PSTN 号码将该呼叫提升为会议。**</span><span class="sxs-lookup"><span data-stu-id="52001-170">**Issue: When a call is made from a Skype for Business client using a PSTN number, the call cannot be escalated to a conference by inviting another PSTN number.**</span></span>
    
    <span data-ttu-id="52001-171">**解决方法：** 若要解决此问题，请参阅 [配置联机混合中介服务器设置](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer)。</span><span class="sxs-lookup"><span data-stu-id="52001-171">**Resolution:** To resolve this issue, see [Configure online hybrid Mediation Server Settings](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).</span></span>
    
- <span data-ttu-id="52001-172">**问题：安装 Active Directory 服务器时显示有关 Windows 更新的警告消息-"未启用 Windows 自动更新。若要确保新安装的角色或功能自动更新，请打开 Windows Update。**</span><span class="sxs-lookup"><span data-stu-id="52001-172">**Issue: A warning message is displayed about Windows Update when you are installing Active Directory server - "Windows automatic updating is not enabled. To ensure that your newly-installed role or feature is automatically updated, turn on Windows Update."**</span></span>
    
    <span data-ttu-id="52001-173">**解决方法：** 使用 Skype for Business 租户管理员凭据启动租户远程 PowerShell 会话，然后运行以下 cmdlet 以检查网站的 _EnableAutoUpdate_ 配置：</span><span class="sxs-lookup"><span data-stu-id="52001-173">**Resolution:** Launch a Tenant Remote PowerShell session using Skype for Business tenant admin credentials, then run the following cmdlet to check the _EnableAutoUpdate_ configuration of your site:</span></span>
    
  ```powershell
  Get-CsHybridPSTNSite
  ```

    <span data-ttu-id="52001-174">如果将  _EnableAutoUpdate_ 设置为 **True**，则可以安全地忽略此警告消息，因为 CCEManagement 服务将处理为虚拟机和主机服务器下载和安装 Windows 更新。</span><span class="sxs-lookup"><span data-stu-id="52001-174">If  _EnableAutoUpdate_ is set to **True**, you can safely ignore this warning message because the CCEManagement service will handle downloading and installing Windows updates for both virtual machines and the host server.</span></span> <span data-ttu-id="52001-175">如果  _EnableAutoUpdate_ 设置为 **False**，则运行以下 cmdlet 以将其设置为 **True**。</span><span class="sxs-lookup"><span data-stu-id="52001-175">If  _EnableAutoUpdate_ is set to **False**, run following cmdlet to set it to **True**.</span></span>
    
  ```powershell
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    <span data-ttu-id="52001-176">或者，您也可以手动检查并安装更新。</span><span class="sxs-lookup"><span data-stu-id="52001-176">Alternatively, you can manually check for and install updates.</span></span> <span data-ttu-id="52001-177">请参阅下一部分。</span><span class="sxs-lookup"><span data-stu-id="52001-177">See the next section.</span></span>
    
- <span data-ttu-id="52001-178">**问题：你收到一条错误消息：无法注册设备，因为当前的输入/配置 \<SiteName\> 或 \<ApplianceName\> \<Mediation Server FQDN\> \<Mediation Server IP Address\> 与现有设备 (s) 相同。删除冲突设备或更新输入/配置信息，然后重新注册。' 在运行 Register-ccappliance 注册当前设备以供联机时。**</span><span class="sxs-lookup"><span data-stu-id="52001-178">**Issue: You receive an error message: Cannot register appliance because your current input/configuration \<SiteName\> or \<ApplianceName\> or \<Mediation Server FQDN\> or \<Mediation Server IP Address\> conflicts with existing appliance(s). Remove conflict appliance or update your input/configuration information then register again. ' when run Register-CcAppliance to register current appliance to online.**</span></span>
    
    <span data-ttu-id="52001-179">**解决方法：** 的值 \<ApplianceName\> ， \<Mediation Server FQDN\> 并且 \<Mediation Server IP Address\> 必须是唯一的，并且仅用于一个设备注册。</span><span class="sxs-lookup"><span data-stu-id="52001-179">**Resolution:** Values for the \<ApplianceName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> must be unique and only used for one appliance registration.</span></span> <span data-ttu-id="52001-180">默认情况下，来自 \<ApplianceName\> 主机名。</span><span class="sxs-lookup"><span data-stu-id="52001-180">By default, \<ApplianceName\> comes from the host name.</span></span> <span data-ttu-id="52001-181">\<Mediation Server FQDN\> 并 \<Mediation Server IP Address\> 在配置 ini 文件中定义。</span><span class="sxs-lookup"><span data-stu-id="52001-181">\<Mediation Server FQDN\> and \<Mediation Server IP Address\> defined in configuration ini file.</span></span>
    
    <span data-ttu-id="52001-182">例如，使用 (ApplianceName = MyserverNew，中介服务器 FQDN =，中介服务器 IP 地址 = 10.10.10.10) 注册到 SiteName = 我的用户，但是如果有已注册的设备 (ApplianceName = Myserver，中介服务器 FQDN =，中介服务器 IP 地址 = 10.10.10.10) ，则会发生冲突。</span><span class="sxs-lookup"><span data-stu-id="52001-182">For example, using (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) to register to SiteName=MySite, but if there is a registered appliance (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10), you will have the conflict.</span></span>
    
    <span data-ttu-id="52001-183">首先，请在 ApplianceRoot 目录部分中检查 CloudConnector.ini 文件。</span><span class="sxs-lookup"><span data-stu-id="52001-183">First, please check your CloudConnector.ini file in ApplianceRoot directory section.</span></span> <span data-ttu-id="52001-184">您将获得 \<SiteName\> \<Mediation Server FQDN\> 并 \<Mediation Server IP Address\> 在文件中显示值。</span><span class="sxs-lookup"><span data-stu-id="52001-184">You will get \<SiteName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> values in the file.</span></span> <span data-ttu-id="52001-185">\<ApplianceName\> 是您的主机服务器名称。</span><span class="sxs-lookup"><span data-stu-id="52001-185">\<ApplianceName\> is your host server name.</span></span>
    
    <span data-ttu-id="52001-186">其次，使用你的 Skype for Business 租户管理员凭据启动租户远程 PowerShell，然后运行以下 cmdlet 以检查注册的设备 (s) 。</span><span class="sxs-lookup"><span data-stu-id="52001-186">Second, Launch Tenant Remote PowerShell using your Skype for Business tenant admin credentials, then run the following cmdlet to check the registered appliance(s).</span></span>
    
  ```powershell
  Get-CsHybridPSTNAppliance
  ```

    <span data-ttu-id="52001-187">在确定任何冲突之后，可以使用与注册设备匹配的信息更新 CloudConnector.ini 文件，或注销现有设备以解决冲突。</span><span class="sxs-lookup"><span data-stu-id="52001-187">After identifying any conflicts, you can either update your CloudConnector.ini file with information that matches the registered appliance, or unregister the existing appliance to resolve the conflicts.</span></span>
    
  ```powershell
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- <span data-ttu-id="52001-188">**问题：如果在主机上运行已部署的设备，Get-ccrunningversion cmdlet 将返回空值。**</span><span class="sxs-lookup"><span data-stu-id="52001-188">**Issue: The Get-CcRunningVersion cmdlet returns an empty value if there is a deployed appliance running on the host.**</span></span>
    
  <span data-ttu-id="52001-189">**解决方法：** 从1.3.4 或1.3.8 升级到1.4.1 时，可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="52001-189">**Resolution:** This can happen when you upgrade from 1.3.4 or 1.3.8 to 1.4.1.</span></span> <span data-ttu-id="52001-190">在使用 .msi 安装版本1.4.1 之后，您必须 `Register-CcAppliance` 先运行任何其他 cmdlet，然后才能运行。</span><span class="sxs-lookup"><span data-stu-id="52001-190">After you install version 1.4.1 with the .msi, you must run `Register-CcAppliance` before you run any other cmdlet.</span></span> <span data-ttu-id="52001-191">`Register-CcAppliance` 会将 module.ini 文件从%UserProfile%\CloudConnector 迁移到%ProgramData%\CloudConnector。</span><span class="sxs-lookup"><span data-stu-id="52001-191">`Register-CcAppliance` will migrate the module.ini file from %UserProfile%\CloudConnector to %ProgramData%\CloudConnector.</span></span> <span data-ttu-id="52001-192">如果你错过了它，将在%ProgramData%\CloudConnector 文件夹中创建一个新的 module.ini，并替换1.3.4 或1.3.8 的运行/备份版本信息。</span><span class="sxs-lookup"><span data-stu-id="52001-192">If you missed it, a new module.ini will be created in %ProgramData%\CloudConnector folder and replace the running/backup version information for 1.3.4 or 1.3.8.</span></span>
    
  <span data-ttu-id="52001-193">比较%UserProfile%\CloudConnector 和%ProgramData%\CloudConnector 文件夹中的 module.ini 文件。</span><span class="sxs-lookup"><span data-stu-id="52001-193">Compare module.ini files in %UserProfile%\CloudConnector and %ProgramData%\CloudConnector folder.</span></span> <span data-ttu-id="52001-194">如果存在差异，请在%ProgramData%\CloudConnector 中删除 module.ini 文件，然后重新运行  `Register-CcAppliance` 。</span><span class="sxs-lookup"><span data-stu-id="52001-194">If there are differences, delete the module.ini file in %ProgramData%\CloudConnector and rerun  `Register-CcAppliance`.</span></span> <span data-ttu-id="52001-195">您还可以手动将文件修改为正确的运行和备份版本。</span><span class="sxs-lookup"><span data-stu-id="52001-195">You could also modify the file manually to the correct running and backup version.</span></span>
    
- <span data-ttu-id="52001-196">**问题：在运行 Switch-ccversion cmdlet 以切换到不同于当前脚本版本的旧版本之后，此旧版本不提供高可用性支持。**</span><span class="sxs-lookup"><span data-stu-id="52001-196">**Issue: After you run the Switch-CcVersion cmdlet to switch to an old version which is different from current script version, there is no High Availability support for this old version.**</span></span>
    
    <span data-ttu-id="52001-197">**解决方法：** 例如，您已从1.4.1 升级到1.4.2。</span><span class="sxs-lookup"><span data-stu-id="52001-197">**Resolution:** For example, you have upgraded from 1.4.1 to 1.4.2.</span></span> <span data-ttu-id="52001-198">您的当前脚本版本（可通过运行 `Get-CcVersion` ）和运行版本（这两个版本都可以确定）  `Get-CcRunningVersion` 。</span><span class="sxs-lookup"><span data-stu-id="52001-198">Your current script version, which can be determined by running `Get-CcVersion`, and your running version, which can be determined by running  `Get-CcRunningVersion` are both 1.4.2.</span></span> <span data-ttu-id="52001-199">此时，如果您运行以将 `Switch-CcVersion` 正在运行的版本切换回1.4.1，则此旧版本将不提供高可用性支持。</span><span class="sxs-lookup"><span data-stu-id="52001-199">At this time, if you run `Switch-CcVersion` to switch the running version back to 1.4.1, then there will be no High Availability support for this old version.</span></span>
    
    <span data-ttu-id="52001-200">若要获取完整的高可用性支持，请切换回1.4.2，以便运行版本和脚本版本相同。</span><span class="sxs-lookup"><span data-stu-id="52001-200">To get full High Availability support, please switch back to 1.4.2, so the running version and script version are the same.</span></span> <span data-ttu-id="52001-201">如果您在1.4.2 部署中遇到问题，请尽快卸载并重新安装它。</span><span class="sxs-lookup"><span data-stu-id="52001-201">If you are experiencing problems with your 1.4.2 deployment, please uninstall and reinstall it as soon as possible.</span></span>
    
- <span data-ttu-id="52001-202">**问题：证书颁发机构证书或颁发给中央管理存储、中介服务器和边缘服务器的内部证书即将过期或已泄露。**</span><span class="sxs-lookup"><span data-stu-id="52001-202">**Issue: Certificate authority certificates or internal certificates issued to Central Management Store, Mediation Server, and Edge Server are near expiration or are compromised.**</span></span>
    
    <span data-ttu-id="52001-203">**解决方法：** Skype for Business 证书颁发机构证书有效期为五年。</span><span class="sxs-lookup"><span data-stu-id="52001-203">**Resolution:** Skype for Business certification authority certificates are valid for five years.</span></span> <span data-ttu-id="52001-204">颁发给中央管理存储、中介服务器和边缘服务器的内部证书有效期为两年。</span><span class="sxs-lookup"><span data-stu-id="52001-204">Internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="52001-205">在云连接器版本2.0 及更高版本中，Renew-ccservercertificate cmdlet 已更改为 Renew-ccservercertificate，并且 Renew-cccacertificate cmdlet 已更改为更新-Renew-cccacertificate。</span><span class="sxs-lookup"><span data-stu-id="52001-205">In Cloud Connector version 2.0 and later, the Renew-CcServerCertificate cmdlet has changed to Update-CcServerCertificate and the Renew-CcCACertificate cmdlet has changed to Update-CcCACertificate.</span></span> 
  
    <span data-ttu-id="52001-206">如果颁发给中央管理存储、中介服务器和边缘服务器的内部证书即将过期或已损坏，请运行 Renew-ccservercertificate 或 Renew-ccservercertificate cmdlet 来续订证书。</span><span class="sxs-lookup"><span data-stu-id="52001-206">If internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are near expiration or compromised, run the Renew-CcServerCertificate or Update-CcServerCertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="52001-207">如果证书颁发机构证书即将过期，请运行 Renew-cccacertificate 或 Renew-cccacertificate cmdlet 来续订证书。</span><span class="sxs-lookup"><span data-stu-id="52001-207">If certification authority certificates are near expiration, run the Renew-CcCACertificate or Update-CcCACertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="52001-208">**如果证书颁发机构证书已损坏，并且站点中只有一台设备，请** 执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="52001-208">**If certification authority certificates are compromised and there is only one appliance in the site,** perform the following steps:</span></span>
    
1. <span data-ttu-id="52001-209">运行 Enter-ccupdate cmdlet 以排出服务并将设备置于维护模式。</span><span class="sxs-lookup"><span data-stu-id="52001-209">Run the Enter-CcUpdate cmdlet to drain services and put the appliance in maintenance mode.</span></span>
   
   ```powershell
   Enter-CcUpdate
   ```
   
2. <span data-ttu-id="52001-210">运行以下 cmdlet 以重置并创建新的证书颁发机构证书和所有内部服务器证书：</span><span class="sxs-lookup"><span data-stu-id="52001-210">Run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
    <span data-ttu-id="52001-211">对于在2.0 之前的云连接器版本：</span><span class="sxs-lookup"><span data-stu-id="52001-211">For Cloud Connector releases before 2.0:</span></span>
    
    ```powershell
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    <span data-ttu-id="52001-212">或云连接器版本2.0 及更高版本：</span><span class="sxs-lookup"><span data-stu-id="52001-212">Or for Cloud Connector release 2.0 and later:</span></span>
    
    ```powershell
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```
    
3. <span data-ttu-id="52001-213">如果在网关和中介服务器之间使用 TLS，请从设备运行 Export-ccrootcertificate cmdlet，然后将导出的证书安装到 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="52001-213">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from the appliance, and then install the exported certificate to your PSTN gateways.</span></span> <span data-ttu-id="52001-214">你可能还需要在你的网关上重新颁发证书。</span><span class="sxs-lookup"><span data-stu-id="52001-214">You may also be required to re-issue the certificate on your gateway.</span></span>

   ```powershell
   Export-CcRootCertificate
   ```

4. <span data-ttu-id="52001-215">运行 Enter-ccupdate cmdlet 以启动服务并退出维护模式。</span><span class="sxs-lookup"><span data-stu-id="52001-215">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span>

   ```powershell
   Exit-CcUpdate
   ```


    <span data-ttu-id="52001-216">**如果证书颁发机构证书已损坏，并且站点中有多个设备，请** 在站点中的每台设备上执行以下连续步骤。</span><span class="sxs-lookup"><span data-stu-id="52001-216">**If certification authority certificates are compromised and there are multiple appliances in the site,** perform the following sequential steps on each appliance in the site.</span></span>
    
    <span data-ttu-id="52001-217">Microsoft 建议您在非高峰使用时间执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="52001-217">Microsoft recommends that you perform these steps during non-peak usage times.</span></span>
    
1. <span data-ttu-id="52001-218">在第一个设备上，运行 Remove-cccertificationauthorityfile cmdlet 以清理目录中的 CA 备份文件 \<SiteRoot\> 。</span><span class="sxs-lookup"><span data-stu-id="52001-218">On the first appliance, run the Remove-CcCertificationAuthorityFile cmdlet to clean up the CA backup files in the \<SiteRoot\> directory.</span></span>

     ```powershell
     Remove-CcCertificationAuthorityFile
     ```
    
2. <span data-ttu-id="52001-219">运行 Enter-ccupdate cmdlet 以排出服务并将每个设备置于维护模式。</span><span class="sxs-lookup"><span data-stu-id="52001-219">Run the Enter-CcUpdate cmdlet to drain services and put each appliance in maintenance mode.</span></span>

     ```powershell
     Enter-CcUpdate
     ```
    
3. <span data-ttu-id="52001-220">在第一个设备上，运行以下 cmdlet 以重置并创建新的证书颁发机构证书和所有内部服务器证书：</span><span class="sxs-lookup"><span data-stu-id="52001-220">On the first appliance, run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
     <span data-ttu-id="52001-221">对于在2.0 之前的云连接器版本：</span><span class="sxs-lookup"><span data-stu-id="52001-221">For Cloud Connector releases before 2.0:</span></span>
    
     ```powershell
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     <span data-ttu-id="52001-222">或云连接器版本2.0 及更高版本：</span><span class="sxs-lookup"><span data-stu-id="52001-222">Or for Cloud Connector release 2.0 and later:</span></span>
    
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

4. <span data-ttu-id="52001-223">在第一个设备上，运行以下 cmdlet 以将 CA 文件备份到该 \<SiteRoot\> 文件夹。</span><span class="sxs-lookup"><span data-stu-id="52001-223">On the first appliance, run the following cmdlet to back up the CA files to the \<SiteRoot\> folder.</span></span>
    
     ```powershell
     Backup-CcCertificationAuthority
     ```
   
5. <span data-ttu-id="52001-224">在同一站点中的所有其他设备上，运行以下命令以使用 CA 备份文件，这样设备将使用相同的根证书，然后请求新的证书。</span><span class="sxs-lookup"><span data-stu-id="52001-224">On all other appliance's in the same site, run the following commands to consume the CA backup files, so that the appliances all use the same root certificate, and then request new certificates.</span></span> 
   
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```
     
6. <span data-ttu-id="52001-225">如果在网关和中介服务器之间使用 TLS，请在站点中的任何设备上运行 Export-ccrootcertificate cmdlet，然后将导出的证书安装到 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="52001-225">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from any appliance in the site, and then install the exported certificate to your PSTN gateways.</span></span> <span data-ttu-id="52001-226">你可能还需要在你的网关上重新颁发证书。</span><span class="sxs-lookup"><span data-stu-id="52001-226">You may also be required to re-issue the certificate on your gateway.</span></span>
  
     ```powershell
     Export-CcRootCertificate
     ```
     
7. <span data-ttu-id="52001-227">运行 Enter-ccupdate cmdlet 以启动服务并退出维护模式。</span><span class="sxs-lookup"><span data-stu-id="52001-227">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span> 

     ```powershell
     Exit-CcUpdate
     ```
    
    
- <span data-ttu-id="52001-228">**问题：在云连接器管理服务日志中收到以下错误消息： "C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log"： CceService 错误：0：将状态报告为联机时出现意外异常：：用户的登录失败 \<Global Tenant Admin\> 。请创建一个新的 credential 对象，确保您使用了正确的用户名和密码。---\>**</span><span class="sxs-lookup"><span data-stu-id="52001-228">**Issue: You receive the following error message in the Cloud Connector Management Service Log, "C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": CceService Error: 0 : Unexpected exception when reporting status to online: System.Management.Automation.CmdletInvocationException: Logon failed for the user \<Global Tenant Admin\>. Please create a new credential object, making sure that you have used the correct user name and password. ---\>**</span></span>
    
    <span data-ttu-id="52001-229">**解决方法：** Microsoft 365 或 Office 365 全局租户管理员凭据在云连接器设备注册后进行了更改。</span><span class="sxs-lookup"><span data-stu-id="52001-229">**Resolution:** The Microsoft 365 or Office 365 global tenant admin credentials have been changed since the Cloud Connector appliance was registered.</span></span> <span data-ttu-id="52001-230">若要在云连接器设备上更新本地存储的凭据，请从主机设备上的管理员 PowerShell 中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="52001-230">To update the locally stored credentials on the Cloud Connector appliance, run the following from Administrator PowerShell on the host appliance:</span></span>
    
  ```powershell
  Set-CcCredential -AccountType TenantAdmin
  ```

- <span data-ttu-id="52001-231">**问题：在您更改用于部署的主机服务器帐户的密码之后，您会收到以下错误消息： "ConvertTo-SecureString：密钥在指定状态下使用时无效。" 在%ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log 或运行 Set-cccredential cmdlet 时使用。**</span><span class="sxs-lookup"><span data-stu-id="52001-231">**Issue: After you change the password for the host server account you used for the deployment, you receive the following error message: "ConvertTo-SecureString : Key not valid for use in specified state." in %ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log or while running the Get-CcCredential cmdlet.**</span></span>
    
    <span data-ttu-id="52001-232">**解决方法：** 所有云连接器凭据都存储在以下文件中： "%Systemdrive%\programdata\cloudconnector\credentials. .xml" \<CurrentUser\> 。xml "。</span><span class="sxs-lookup"><span data-stu-id="52001-232">**Resolution:** All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="52001-233">当主机服务器上的密码更改时，您将需要更新本地存储的凭据。</span><span class="sxs-lookup"><span data-stu-id="52001-233">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
    
    <span data-ttu-id="52001-234">**如果您运行的是云连接器1.4.2 版，请** 通过执行以下步骤来重新生成所有云连接器密码：</span><span class="sxs-lookup"><span data-stu-id="52001-234">**If you are running Cloud Connector version 1.4.2,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  1. <span data-ttu-id="52001-235">重新启动主机服务器。</span><span class="sxs-lookup"><span data-stu-id="52001-235">Restart the host server.</span></span>
    
  2. <span data-ttu-id="52001-236">删除以下文件： "%Systemdrive%\programdata\cloudconnector\credentials. .xml" \<CurrentUser\> 。xml "。</span><span class="sxs-lookup"><span data-stu-id="52001-236">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
  3. <span data-ttu-id="52001-237">以管理员身份启动 PowerShell 控制台，然后运行 "Register-ccappliance-Local" 以在说明后面重新输入密码。</span><span class="sxs-lookup"><span data-stu-id="52001-237">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="52001-238">输入您在云连接器部署之前输入的相同密码。</span><span class="sxs-lookup"><span data-stu-id="52001-238">Enter the same passwords you entered before for the Cloud Connector deployment.</span></span>
    
     <span data-ttu-id="52001-239">**如果您运行的是云连接器版本2.0 或更高版本，请** 通过执行以下步骤来重新生成所有云连接器密码：</span><span class="sxs-lookup"><span data-stu-id="52001-239">**If you are running Cloud Connector version 2.0 or later,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  4. <span data-ttu-id="52001-240">重新启动主机服务器。</span><span class="sxs-lookup"><span data-stu-id="52001-240">Restart the host server.</span></span>
    
  5. <span data-ttu-id="52001-241">删除以下文件： "%Systemdrive%\programdata\cloudconnector\credentials. .xml" \<CurrentUser\> 。xml "。</span><span class="sxs-lookup"><span data-stu-id="52001-241">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" .</span></span>
    
  6. <span data-ttu-id="52001-242">以管理员身份启动 PowerShell 控制台，然后运行 "Register-ccappliance-Local" 以在说明后面重新输入密码。</span><span class="sxs-lookup"><span data-stu-id="52001-242">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> 
    
     <span data-ttu-id="52001-243">如果缓存的密码文件是使用云连接器1.4.2 版生成的，则在收到提示时，请使用 CceService 密码的 VMAdmin 密码。</span><span class="sxs-lookup"><span data-stu-id="52001-243">If the cached password file was generated with Cloud Connector version 1.4.2, use the VMAdmin password for the CceService password when prompted.</span></span> <span data-ttu-id="52001-244">输入您在云连接器部署之前为所有其他帐户输入的相同密码。</span><span class="sxs-lookup"><span data-stu-id="52001-244">Enter the same password you entered before for the Cloud Connector deployment for all other accounts.</span></span>
    
     <span data-ttu-id="52001-245">如果缓存的密码文件是使用云连接器1.4.2 版生成的，并且 DomainAdmin 和 VMAdmin 密码不同，则必须执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="52001-245">If the cached password file was generated with Cloud Connector version 1.4.2 and the DomainAdmin and VMAdmin passwords are different, you must perform the following steps:</span></span>
    
  7. <span data-ttu-id="52001-246">运行 Set-cccredential-AccountType DomainAdmin，如下所示：</span><span class="sxs-lookup"><span data-stu-id="52001-246">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
  8. <span data-ttu-id="52001-247">当系统提示输入旧帐户凭据时，请输入用于 CceService 密码的凭据。</span><span class="sxs-lookup"><span data-stu-id="52001-247">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
  9. <span data-ttu-id="52001-248">当系统提示输入新帐户凭据时，请输入您之前使用的 DomainAdmin 密码的密码。</span><span class="sxs-lookup"><span data-stu-id="52001-248">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
     <span data-ttu-id="52001-249">如果缓存的密码文件是使用云连接器版本2.0 或更高版本生成的，则默认情况下，VmAdmin 和 DomainAdmin 使用与 CceService 相同的密码。</span><span class="sxs-lookup"><span data-stu-id="52001-249">If the cached password file was generated with Cloud Connector version 2.0 or later, by default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="52001-250">如果更改了 DomainAdmin 和 VMAdmin 密码，则必须执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="52001-250">If you changed the DomainAdmin and VMAdmin passwords, you must perform the following steps:</span></span>
    
  10. <span data-ttu-id="52001-251">运行 Set-cccredential-AccountType DomainAdmin，如下所示：</span><span class="sxs-lookup"><span data-stu-id="52001-251">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
       1. <span data-ttu-id="52001-252">当系统提示输入旧帐户凭据时，请输入用于 CceService 密码的凭据</span><span class="sxs-lookup"><span data-stu-id="52001-252">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="52001-253">当系统提示输入新帐户凭据时，请输入您之前使用的 DomainAdmin 密码的密码。</span><span class="sxs-lookup"><span data-stu-id="52001-253">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
  11. <span data-ttu-id="52001-254">运行 Set-cccredential-AccountType VmAdmin，如下所示：</span><span class="sxs-lookup"><span data-stu-id="52001-254">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
       1. <span data-ttu-id="52001-255">当系统提示输入旧帐户凭据时，请输入用于 CceService 密码的凭据</span><span class="sxs-lookup"><span data-stu-id="52001-255">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="52001-256">当系统提示输入新帐户凭据时，请输入您之前使用的 VmAdmin 密码的密码。</span><span class="sxs-lookup"><span data-stu-id="52001-256">When prompted for the new account credential, enter the password for the VmAdmin password you used before.</span></span> 
    
- <span data-ttu-id="52001-257">**问题：在云连接器版本2.1 及更高版本中，在设备上运行 Register-ccappliance 或其他 cmdlet 时，会收到一条错误消息，例如： "对于每个对象：在此对象上找不到属性 ' Common '。验证该属性是否存在。在 C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1： 681 char： 14 "**</span><span class="sxs-lookup"><span data-stu-id="52001-257">**Issue: With Cloud Connector version 2.1 and later, when running Register-CcAppliance or other cmdlets on the appliance, you receive an error message such as: "For Each-Object : The property 'Common' cannot be found on this object. Verify that the property exists. At C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char:14"**</span></span>
    
    <span data-ttu-id="52001-258">**解决方法：** 云连接器2.1 及更高版本需要 .NET Framework 4.6.1 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="52001-258">**Resolution:** Cloud Connector 2.1 and later requires .NET Framework 4.6.1 or later.</span></span> <span data-ttu-id="52001-259">请将设备上的 .NET Framework 更新为版本4.6.1 或更高版本，并再次运行 cmdlet (s) 。</span><span class="sxs-lookup"><span data-stu-id="52001-259">Please update .NET Framework on the appliance to version 4.6.1 or later and run the cmdlet(s) again.</span></span>

- <span data-ttu-id="52001-260">**问题：使用云连接器版本2.1 时，在运行 Register-ccappliance 时，您会收到一条错误消息，例如： "未能安装新实例，出现错误：无法设置" State "，因为只有字符串可用作值来设置 XmlNode 属性"**</span><span class="sxs-lookup"><span data-stu-id="52001-260">**Issue: With Cloud Connector Edition 2.1, when running Install-CcAppliance, you receive an error message such as: "Failed to install new instance with error: Cannot set "State" because only strings can be used as values to set XmlNode properties"**</span></span>

   <span data-ttu-id="52001-261">**解决方法：** 在 Cloudconnector.ini 中的 "[Common]" 部分，请将 "State" 配置添加如下： CountryCode = US State = WA City = Redmond</span><span class="sxs-lookup"><span data-stu-id="52001-261">**Resolution:** In Cloudconnector.ini, under the [Common] section, please add the “State” config as below:  CountryCode=US  State=WA  City=Redmond</span></span>

   <span data-ttu-id="52001-262">"State" 行不是必需的，但不能从 Cloudconnector.ini 文件中删除 "State" 行。</span><span class="sxs-lookup"><span data-stu-id="52001-262">It is not mandatory for the "State" line to have value, however the "State" line cannot be removed from the Cloudconnector.ini file.</span></span>

- <span data-ttu-id="52001-263">**问题：收到以下错误消息 "Dismount-windowsimage：卸载-Dismount-windowsimage 失败。错误代码 = 0xc1550115 "安装或升级云连接器版本时"。**</span><span class="sxs-lookup"><span data-stu-id="52001-263">**Issue: You receive the following error message "Dismount-WindowsImage : Dismount-WindowsImage failed. Error code = 0xc1550115" when installing or upgrading Cloud Connector Edition.**</span></span>
    
    <span data-ttu-id="52001-264">**解决方法：** 以管理员身份启动 PowerShell 控制台，请运行 "DISM-清理-Wim" "。</span><span class="sxs-lookup"><span data-stu-id="52001-264">**Resolution:** Launch a PowerShell console as administrator, run "DISM -Cleanup-Wim'".</span></span> <span data-ttu-id="52001-265">这将清除所有 troubled 图像。</span><span class="sxs-lookup"><span data-stu-id="52001-265">This will clean up all troubled images.</span></span> <span data-ttu-id="52001-266">再次运行安装-Register-ccappliance 或等待 bits 自动升级。</span><span class="sxs-lookup"><span data-stu-id="52001-266">Run Install-CcAppliance again or wait for the bits to automatically upgrade.</span></span>
    
- <span data-ttu-id="52001-267">**问题：在 HA 环境中部署第一个云连接器设备失败**</span><span class="sxs-lookup"><span data-stu-id="52001-267">**Issue: Deployment of the first Cloud Connector appliance in an HA environment fails**</span></span>
    
    <span data-ttu-id="52001-268">**解决方法：** 您执行的步骤取决于部署失败的原因：</span><span class="sxs-lookup"><span data-stu-id="52001-268">**Resolution:** The steps you take depend on the reason the deployment failed:</span></span>
    
  - <span data-ttu-id="52001-269">如果第一个云连接器设备出现故障，并且您无法确定故障原因，则必须重新安装该设备，直到部署成功，然后再安装其他设备。</span><span class="sxs-lookup"><span data-stu-id="52001-269">If the first Cloud Connector appliance fails and you cannot determine the reason for the failure, you must install the appliance again until the deployment is successful, and then install the other appliances.</span></span>
    
  - <span data-ttu-id="52001-270">如果第一个云连接器设备出现问题，如外部证书问题，则可能能够在不重新安装设备的情况下解决问题。</span><span class="sxs-lookup"><span data-stu-id="52001-270">If the first Cloud Connector appliance fails with a minor issue, such as an external certificate issue, you might be able to fix the problem without re-installing the appliance.</span></span> <span data-ttu-id="52001-271">然后，可以使用租户远程 PowerShell 将部署标记为成功，如下所示。</span><span class="sxs-lookup"><span data-stu-id="52001-271">You can then use tenant remote PowerShell to mark the deployment as successful as follows.</span></span> <span data-ttu-id="52001-272"> (如果首次部署成功，则还可以使用以下步骤，但出于某种原因，云连接器无法将部署报告为成功。 ) </span><span class="sxs-lookup"><span data-stu-id="52001-272">(You can also use the following steps if the first deployment was successful, but, for some reason, Cloud Connector fails to report the deployment as a success.)</span></span>
    
  - <span data-ttu-id="52001-273">若要获取第一个云连接器设备的标识 (GUID) ，请运行 CsHybridPSTNAppliance cmdlet。</span><span class="sxs-lookup"><span data-stu-id="52001-273">To get the Identity (GUID) of the first Cloud Connector appliance, run the Get-CsHybridPSTNAppliance cmdlet.</span></span>
    
  - <span data-ttu-id="52001-274">若要将设备标记为已成功部署，请运行 CsCceApplianceDeploymentStatus，如下所示：</span><span class="sxs-lookup"><span data-stu-id="52001-274">To mark the appliance as successfully deployed, run the Set-CsCceApplianceDeploymentStatus as follows:</span></span>
    
  ```powershell
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- <span data-ttu-id="52001-275">**问题：你需要在主机服务器或虚拟机上手动检查并安装 Windows 更新。**</span><span class="sxs-lookup"><span data-stu-id="52001-275">**Issue: You need to check for and install Windows updates manually on the host server or virtual machines.**</span></span>
    
   <span data-ttu-id="52001-276">**解决方法：** 我们建议您利用由 Skype for Business 云连接器版本提供的自动 OS 更新。</span><span class="sxs-lookup"><span data-stu-id="52001-276">**Resolution:** We recommend that you take advantage of automated OS updates provided by Skype for Business Cloud Connector Edition.</span></span> <span data-ttu-id="52001-277">在为联机管理注册设备并启用自动 OS 更新之后，主机服务器和虚拟机将根据 OS update time window 设置自动检查并安装 Windows 更新。</span><span class="sxs-lookup"><span data-stu-id="52001-277">After an appliance is registered for online management and auto OS update is enabled, the host server and virtual machines will check and install Windows Updates automatically according to the OS update time window settings.</span></span>
    
   <span data-ttu-id="52001-278">如果你需要手动检查并安装 Windows 更新，请按照本节中适用于你的部署类型的步骤进行操作。</span><span class="sxs-lookup"><span data-stu-id="52001-278">If you need to check for and install Windows Updates manually, follow the steps in this section that apply to your type of deployment.</span></span> <span data-ttu-id="52001-279">您应规划同时更新主机服务器和同时在其上运行的虚拟机，以最大限度地减少更新所需的停机时间量。</span><span class="sxs-lookup"><span data-stu-id="52001-279">You should plan on updating both the host server and the virtual machines running on it at the same time to minimize the amount of down time necessary for the updates.</span></span>
    
   <span data-ttu-id="52001-280">如果你愿意，可以使用 Windows Server Update Services (WSUS) 服务器来提供云连接器服务器的更新。</span><span class="sxs-lookup"><span data-stu-id="52001-280">If you prefer, you can use a Windows Server Update Services (WSUS) server to provide updates to Cloud Connector servers.</span></span> <span data-ttu-id="52001-281">只需确保将 Windows 更新配置为 **不** 自动安装。</span><span class="sxs-lookup"><span data-stu-id="52001-281">Just be sure to configure the Windows Update to **not** install automatically.</span></span>
    
   <span data-ttu-id="52001-282">有关如何手动更新云连接器部署的信息，请参阅下一节。</span><span class="sxs-lookup"><span data-stu-id="52001-282">For information about how to manually update your Cloud Connector deployment, see the following section.</span></span>
    
- <span data-ttu-id="52001-283">**问题：当云连接器更新新版本时，将不会更新云连接器 cmdlet。**</span><span class="sxs-lookup"><span data-stu-id="52001-283">**Issue: When Cloud Connector updates to a new build, Cloud Connector cmdlets are not updated.**</span></span> <span data-ttu-id="52001-284">如果在自动更新发生时，PowerShell 窗口保持打开，有时会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="52001-284">This sometimes happens if a PowerShell window is left open when automatic update occurs.</span></span>
    
  <span data-ttu-id="52001-285">**解决方法：** 若要加载更新的 cmdlet，您可以执行以下任一步骤：</span><span class="sxs-lookup"><span data-stu-id="52001-285">**Resolution:** To load the updated cmdlets, you can do either of the following steps:</span></span>
    
   - <span data-ttu-id="52001-286">在云连接器设备上关闭 PowerShell，然后重新打开 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="52001-286">Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.</span></span>
    
     - <span data-ttu-id="52001-287">或者，您可以运行导入模块 Cloudconnector.ini。</span><span class="sxs-lookup"><span data-stu-id="52001-287">Or, you can run Import-Module CloudConnector -Force.</span></span> 
 
-   <span data-ttu-id="52001-288">**问题： "无法将术语" Start-cswindowsservice "识别为 cmdlet、函数、脚本文件或可运行程序的名称。尝试运行 Enter-ccupdate cmdlet 时出错。**</span><span class="sxs-lookup"><span data-stu-id="52001-288">**Issue: "The term 'Stop-CsWindowsService' is not recognized as the name of a cmdlet, function, script file, or operable program." error when attempting to run Enter-CcUpdate cmdlet.**</span></span>

    <span data-ttu-id="52001-289">**解决方法：** 删除 $HOME \AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache 文件。</span><span class="sxs-lookup"><span data-stu-id="52001-289">**Resolution:** Delete the $HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache file.</span></span>
<span data-ttu-id="52001-290">PowerShell 将此文件创建为它所发现的模块中的 cmdlet 的缓存，以便无需每次都重新分析所有模块，因为这样做会导致某些事情变得非常慢。</span><span class="sxs-lookup"><span data-stu-id="52001-290">PowerShell creates this file as a cache of cmdlets from modules that it finds so that it doesn’t have to re-analyze all the modules each time as that would make things really slow.</span></span> <span data-ttu-id="52001-291">大多数情况下，在从缓存中读取时，会有一些文件损坏向 PowerShell 提供误导性结果。</span><span class="sxs-lookup"><span data-stu-id="52001-291">Most likely, there was some file corruption that provided misleading results to PowerShell when it was reading back from that cache.</span></span>

-   <span data-ttu-id="52001-292">**问题： "Import-Module Cloudconnector.ini" 生成错误 "Import-Module：未加载指定的模块" Cloudconnector.ini "，因为在任何模块目录中都找不到有效的模块文件"**</span><span class="sxs-lookup"><span data-stu-id="52001-292">**Issue: “Import-Module CloudConnector” generates error “Import-Module: The specified module “CloudConnector” was not loaded because no valid module file was found in any module directory”**</span></span>

    <span data-ttu-id="52001-293">**解决方案：**</span><span class="sxs-lookup"><span data-stu-id="52001-293">**Resolution:**</span></span>
    - <span data-ttu-id="52001-294">验证 Cloudconnector.ini 模块是否确实存在于 c:\Program Files\WindowsPowerShell\Modules 下。</span><span class="sxs-lookup"><span data-stu-id="52001-294">Validate that indeed the CloudConnector module exists under c:\Program Files\WindowsPowerShell\Modules</span></span>
    
    - <span data-ttu-id="52001-295">在验证 Cloudconnector.ini 模块位于此位置下后，可以更改存储模块位置的 PSModulePath 环境变量：</span><span class="sxs-lookup"><span data-stu-id="52001-295">After validating that CloudConnector module exists under this location, the PSModulePath environment variable storing the path to the locations of the modules can be changed:</span></span>
    
     <span data-ttu-id="52001-296">a.</span><span class="sxs-lookup"><span data-stu-id="52001-296">a.</span></span> <span data-ttu-id="52001-297">临时更改：以管理员身份启动 Powershell 并运行以下命令： $env:P SModulePath = $env:P SModulePath + ";C:\Program Files\WindowsPowerShell\Modules\"</span><span class="sxs-lookup"><span data-stu-id="52001-297">Temporary change: Start Powershell as an Administrator and run the following command: $env:PSModulePath = $env:PSModulePath + ";C:\Program Files\WindowsPowerShell\Modules\"</span></span>
        
     <span data-ttu-id="52001-298">b.</span><span class="sxs-lookup"><span data-stu-id="52001-298">b.</span></span> <span data-ttu-id="52001-299">对于 "永久更改"，以管理员身份启动 PowerShell，并逐个运行以下命令： $CurrentValue = [环境]：： GetEnvironmentVariable ( "PSModulePath"、"Machine" ) SetEnvironmentVariable ( "PSModulePath"、$CurrentValue + ";C:\Program Files\WindowsPowerShell\Modules "，" Machine ") </span><span class="sxs-lookup"><span data-stu-id="52001-299">For persistent change, Start PowerShell as an Administrator and run the following commands, one by one: $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine") SetEnvironmentVariable("PSModulePath", $CurrentValue + "; C:\Program Files\WindowsPowerShell\Modules", "Machine")</span></span>

    
## <a name="install-windows-updates-manually"></a><span data-ttu-id="52001-300">手动安装 Windows 更新</span><span class="sxs-lookup"><span data-stu-id="52001-300">Install Windows updates manually</span></span>

<span data-ttu-id="52001-301">如果您不想在您的环境中使用自动更新，请按照以下步骤手动检查并应用 Windows 更新。</span><span class="sxs-lookup"><span data-stu-id="52001-301">If you do not want to use automatic updates in your environment, follow these steps to manually check for and apply Windows updates.</span></span> <span data-ttu-id="52001-302">检查并安装 Windows 更新可能需要重新启动服务器。</span><span class="sxs-lookup"><span data-stu-id="52001-302">Checking for and installing Windows updates may require a server restart.</span></span> <span data-ttu-id="52001-303">当主机服务器重新启动时，用户将无法使用云连接器发出或接收呼叫。</span><span class="sxs-lookup"><span data-stu-id="52001-303">When a host server is restarting, users will not be able to use Cloud Connector to place or receive calls.</span></span> <span data-ttu-id="52001-304">您可以手动检查并安装更新，以控制更新发生的时间，然后根据需要在选择的时间内重新启动计算机，以避免服务中断。</span><span class="sxs-lookup"><span data-stu-id="52001-304">You can manually check for and install updates to control when the updates take place, and then restart the machines as needed during times you choose to avoid disruption of services.</span></span>
  
<span data-ttu-id="52001-305">若要手动检查更新，请连接到每台主机服务器并打开 " **控制面板"**。</span><span class="sxs-lookup"><span data-stu-id="52001-305">To manually check for updates, connect to each host server and open the **Control Panel**.</span></span> <span data-ttu-id="52001-306">选择 " **系统和安全" " \> Windows 更新**"，然后根据您的环境相应地管理更新和服务器重新启动。</span><span class="sxs-lookup"><span data-stu-id="52001-306">Select **System and Security \>Windows Update**, and then manage the updates and server restarts as appropriate for your environment.</span></span>
  
- <span data-ttu-id="52001-307">如果站点中只有一个设备，请连接到每个虚拟机，然后打开 " **控制面板"**。</span><span class="sxs-lookup"><span data-stu-id="52001-307">If there is only one appliance in the site, connect to each virtual machine and open the **Control Panel**.</span></span> <span data-ttu-id="52001-308">选择 " **系统和安全" " \> Windows 更新**"，然后根据需要配置更新和服务器重新启动。</span><span class="sxs-lookup"><span data-stu-id="52001-308">Select **System and Security \>Windows Update**, and then configure the updates and server restarts as appropriate.</span></span>
    
- <span data-ttu-id="52001-309">如果站点中有多个设备，则在更新过程中用户无法访问正在更新和重新启动的实例。</span><span class="sxs-lookup"><span data-stu-id="52001-309">If there are more than one appliance in the site, the instance being updated and restarted cannot be accessed by users during the updates.</span></span> <span data-ttu-id="52001-310">在更新完成后，用户将连接到部署中的其他实例，直到所有虚拟机和所有 Skype for Business 服务在虚拟机上启动。</span><span class="sxs-lookup"><span data-stu-id="52001-310">Users will connect to other instances in the deployment until all virtual machines and all Skype for Business services start on the virtual machines after the updates are completed.</span></span> <span data-ttu-id="52001-311">为避免任何潜在的服务中断，可以在应用更新时从 HA 中删除该实例，然后在完成后将其还原。</span><span class="sxs-lookup"><span data-stu-id="52001-311">To avoid any potential disruption to service, you can remove the instance from HA while you apply the updates, and then restore it when complete.</span></span> <span data-ttu-id="52001-312">为此，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="52001-312">To do so:</span></span>
    
1. <span data-ttu-id="52001-313">在每台主机服务器上，以管理员身份打开 PowerShell 控制台。</span><span class="sxs-lookup"><span data-stu-id="52001-313">On each host server, open a PowerShell console as administrator.</span></span>
    
2. <span data-ttu-id="52001-314">使用以下 cmdlet 从 HA 中删除实例：</span><span class="sxs-lookup"><span data-stu-id="52001-314">Remove the instance from HA with the following cmdlet:</span></span>
    
   ```powershell
   Enter-CcUpdate
   ```

3. 
    
    <span data-ttu-id="52001-315">按照单个实例的步骤操作，手动应用更新并重新启动虚拟机。</span><span class="sxs-lookup"><span data-stu-id="52001-315">Follow the steps for a single instance to manually apply the updates and restart the virtual machine.</span></span>
    
4. <span data-ttu-id="52001-316">使用以下 cmdlet 将实例设置回 HA：</span><span class="sxs-lookup"><span data-stu-id="52001-316">Set the instance back to HA with the following cmdlet:</span></span>
    
   ```powershell
   Exit-CcUpdate
   ```

<span data-ttu-id="52001-317">对于多站点部署，请遵循部署中每个站点的单个站点的步骤，同时将更新应用到一个站点。</span><span class="sxs-lookup"><span data-stu-id="52001-317">For multi-site deployments, follow the steps for a single site for each site in the deployment, applying updates to one site at a time.</span></span>
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a><span data-ttu-id="52001-318">在云连接器主机计算机上安装防病毒软件的提示</span><span class="sxs-lookup"><span data-stu-id="52001-318">Tips when installing anti-virus software on the Cloud Connector host machine</span></span>

<span data-ttu-id="52001-319">如果需要在云连接器主机上安装防病毒软件，则需要添加以下排除项：</span><span class="sxs-lookup"><span data-stu-id="52001-319">If you need to install anti-virus software on the Cloud Connector host machine, you need to add the following exclusions:</span></span>
  
- <span data-ttu-id="52001-320">每台计算机上的本地设备目录。</span><span class="sxs-lookup"><span data-stu-id="52001-320">Local Appliance Directory on each machine.</span></span>
    
- <span data-ttu-id="52001-321">每台计算机上的远程网站目录。</span><span class="sxs-lookup"><span data-stu-id="52001-321">Remote Site Directory on each machine.</span></span>
    
- <span data-ttu-id="52001-322">计算机上的本地网站目录承载共享网站根文件夹。</span><span class="sxs-lookup"><span data-stu-id="52001-322">Local Site Directory on the machine hosts the shared site root folder.</span></span>
    
- <span data-ttu-id="52001-323">适用于商业云连接器版本的%ProgramFiles%\Skype</span><span class="sxs-lookup"><span data-stu-id="52001-323">%ProgramFiles%\Skype for Business Cloud Connector Edition</span></span>
    
- <span data-ttu-id="52001-324">%ALLUSERSPROFILE%\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="52001-324">%ALLUSERSPROFILE%\CloudConnector</span></span>
    
- <span data-ttu-id="52001-325">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="52001-325">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span></span>
    
- <span data-ttu-id="52001-326">过程 Microsoft.Rtc.CCE.ManagementService.exe。</span><span class="sxs-lookup"><span data-stu-id="52001-326">The process Microsoft.Rtc.CCE.ManagementService.exe.</span></span>
