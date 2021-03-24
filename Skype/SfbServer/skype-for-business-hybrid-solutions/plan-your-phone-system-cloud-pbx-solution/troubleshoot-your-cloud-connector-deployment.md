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
description: 云连接器版本部署疑难解答。
ms.openlocfilehash: 9da10f1b3e8dd800e57b46f6a56eb6a82c29e22c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094820"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a><span data-ttu-id="97ddb-103">对云连接器部署进行故障排除</span><span class="sxs-lookup"><span data-stu-id="97ddb-103">Troubleshoot your Cloud Connector deployment</span></span>

> [!Important]
> <span data-ttu-id="97ddb-104">云连接器版本将于 2021 年 7 月 31 日与 Skype for Business Online 一起停用。</span><span class="sxs-lookup"><span data-stu-id="97ddb-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="97ddb-105">组织升级到 Teams 后，了解如何使用直接路由将本地电话网络连接到[Teams。](/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="97ddb-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>
 
<span data-ttu-id="97ddb-106">云连接器版本部署疑难解答。</span><span class="sxs-lookup"><span data-stu-id="97ddb-106">Troubleshoot your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="97ddb-107">本主题介绍云连接器版本部署常见问题的解决方案。</span><span class="sxs-lookup"><span data-stu-id="97ddb-107">This topic describes solutions to common issues with Cloud Connector Edition deployments.</span></span> <span data-ttu-id="97ddb-108">如果在呼叫公用电话交换网 (PSTN) 时遇到问题，可以按照本主题中所述的解决方案进行调查。</span><span class="sxs-lookup"><span data-stu-id="97ddb-108">If you are experiencing issues with calls to and from the Public Switched Telephone Network (PSTN), you can investigate by following the solutions described in this topic.</span></span>
  
<span data-ttu-id="97ddb-109">云连接器提供自动解决某些问题的内置机制。</span><span class="sxs-lookup"><span data-stu-id="97ddb-109">Cloud Connector provides built-in mechanisms for automatically resolving some issues.</span></span> <span data-ttu-id="97ddb-110">自动检测过程会查找云连接器设备的潜在问题，如果可能，采取纠正措施来解决这些问题，而无需管理员干预。</span><span class="sxs-lookup"><span data-stu-id="97ddb-110">An automatic detection process looks for potential issues with the Cloud Connector appliances, and, if possible, takes corrective action to resolve those issues without the need for administrator intervention.</span></span> <span data-ttu-id="97ddb-111">检测过程的工作方式如下：</span><span class="sxs-lookup"><span data-stu-id="97ddb-111">The detection process works as follows:</span></span>
  
- <span data-ttu-id="97ddb-112">**检测序列：** 云连接器管理服务每 60 秒运行一个进程，以检测设备是否关闭。</span><span class="sxs-lookup"><span data-stu-id="97ddb-112">**Detection sequence:** The Cloud Connector Management service runs a process every 60 seconds for detecting whether an appliance is down.</span></span> <span data-ttu-id="97ddb-113">在云连接器 2.0 版和更高版本中，检测过程使用 Skype for Business Corpnet 开关建立与云连接器计算机之间的 PowerShell 连接;对于 2.0 以前的版本，检测过程使用云连接器管理开关。</span><span class="sxs-lookup"><span data-stu-id="97ddb-113">In Cloud Connector version 2.0 and later, the detection process uses the Skype for Business Corpnet switch for making PowerShell connections to the Cloud Connector machines; for versions previous to 2.0, the detection process uses the Cloud Connector management switch.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="97ddb-114">若要成功进行自动恢复，主机和虚拟机之间必须通过主机网络交换机建立网络连接。</span><span class="sxs-lookup"><span data-stu-id="97ddb-114">For automatic recovery to succeed, there must be network connectivity between the host and virtual machines over the host network switch.</span></span> <span data-ttu-id="97ddb-115">请务必检查网络连接，以确保自动检测和恢复可以成功。</span><span class="sxs-lookup"><span data-stu-id="97ddb-115">Be sure to check network connectivity to ensure that automatic detection and recovery can succeed.</span></span> 
  
- <span data-ttu-id="97ddb-116">**监视：** 在云连接器 2.0 版和更高版本中监视以下服务：</span><span class="sxs-lookup"><span data-stu-id="97ddb-116">**Monitoring:** The following services are monitored in Cloud Connector version 2.0 and later:</span></span>
    
  - <span data-ttu-id="97ddb-117">虚拟机未连接到云连接器公司或 Internet 虚拟交换机</span><span class="sxs-lookup"><span data-stu-id="97ddb-117">Virtual Machines are not connected to the Cloud Connector Corporate or Internet virtual switches</span></span>
    
  - <span data-ttu-id="97ddb-118">虚拟机已保存或已停止状态</span><span class="sxs-lookup"><span data-stu-id="97ddb-118">Virtual Machines are in a saved or stopped status</span></span>
    
  - <span data-ttu-id="97ddb-119">中央管理服务器服务：REPLICA、MASTER</span><span class="sxs-lookup"><span data-stu-id="97ddb-119">Central Management Server services: REPLICA, MASTER</span></span>
    
  - <span data-ttu-id="97ddb-120">中介服务器服务：REPLICA、RTCSRV 和 MEDSVC</span><span class="sxs-lookup"><span data-stu-id="97ddb-120">Mediation Server services: REPLICA, RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="97ddb-121">边缘服务器服务：REPLICA、RTCSRV、RTCDATAPROXY、RTCMRAUTH、RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="97ddb-121">Edge Server services: REPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY</span></span>
    
  - <span data-ttu-id="97ddb-122">在边缘服务器上为 CS RTCSRV 禁用入站防火墙规则，在中介服务器上禁用 CS RTCMEDSRV</span><span class="sxs-lookup"><span data-stu-id="97ddb-122">Inbound firewall rules are disabled for CS RTCSRV on Edge server, CS RTCMEDSRV on Mediation server</span></span>
    
    <span data-ttu-id="97ddb-123">在云连接器版本 1.4.2 中，仅监视以下服务：</span><span class="sxs-lookup"><span data-stu-id="97ddb-123">In Cloud Connector version 1.4.2, only the following services are monitored:</span></span>
    
  - <span data-ttu-id="97ddb-124">中介服务器服务：RTCSRV 和 MEDSVC</span><span class="sxs-lookup"><span data-stu-id="97ddb-124">Mediation Server services: RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="97ddb-125">边缘服务器服务：RTCSRV</span><span class="sxs-lookup"><span data-stu-id="97ddb-125">Edge Server service: RTCSRV</span></span>
    
- <span data-ttu-id="97ddb-126">**恢复过程：** 如果任何受监视的服务关闭，设备将标记为关闭，服务将停止并标记为手动，直到可以解决所有问题。</span><span class="sxs-lookup"><span data-stu-id="97ddb-126">**Recovery process:** If any monitored services are down, an appliance is marked down, and services are stopped and marked manual until all issues can be resolved.</span></span> <span data-ttu-id="97ddb-127">这将阻止呼叫路由到可能导致呼叫失败的设备。</span><span class="sxs-lookup"><span data-stu-id="97ddb-127">This will prevent calls from routing to an appliance that may cause call failures.</span></span>
    
    <span data-ttu-id="97ddb-128">云连接器管理服务将重试自动恢复，如下所示</span><span class="sxs-lookup"><span data-stu-id="97ddb-128">The Cloud Connector Management service will retry automatic recovery as follows</span></span>
    
  - <span data-ttu-id="97ddb-129">初始重试间隔是十秒，最大间隔时间为一小时。</span><span class="sxs-lookup"><span data-stu-id="97ddb-129">The initial retry interval is every ten seconds with a maximum interval time of one hour.</span></span>
    
  - <span data-ttu-id="97ddb-130">对于前三次恢复尝试，间隔时间为 10 秒。</span><span class="sxs-lookup"><span data-stu-id="97ddb-130">For the first three recovery attempts, the interval time is 10 seconds.</span></span> <span data-ttu-id="97ddb-131">从第四次重试开始，间隔时间将增加上一间隔时间两倍。</span><span class="sxs-lookup"><span data-stu-id="97ddb-131">Starting from the fourth retry, the interval time increases by two times the previous interval time.</span></span> <span data-ttu-id="97ddb-132">例如，第四次重试将在 20 秒后发生，第五次重试将在 40 秒后发生，以此类举。</span><span class="sxs-lookup"><span data-stu-id="97ddb-132">For example, the fourth retry will occur in 20 seconds, the fifth in 40 seconds, and so on.</span></span> 
    
  - <span data-ttu-id="97ddb-133">当达到 1 小时的最大间隔时间时，重试将继续每小时一次。</span><span class="sxs-lookup"><span data-stu-id="97ddb-133">When the maximum interval time of one hour is reached, retries will continue once per hour.</span></span>
    
  - <span data-ttu-id="97ddb-134">恢复成功后，间隔和重试次数将设置为初始值。</span><span class="sxs-lookup"><span data-stu-id="97ddb-134">When recovery is successful, the interval and retry counts are set to their initial values.</span></span>
    
  - <span data-ttu-id="97ddb-135">如果重新启动管理服务，则时间间隔和重试次数将重置为初始值。</span><span class="sxs-lookup"><span data-stu-id="97ddb-135">If the Management service is restarted, the interval and retry counts are reset to their initial values.</span></span>
    
## <a name="troubleshooting"></a><span data-ttu-id="97ddb-136">疑难解答</span><span class="sxs-lookup"><span data-stu-id="97ddb-136">Troubleshooting</span></span>

<span data-ttu-id="97ddb-137">以下是常见问题的解决方案：</span><span class="sxs-lookup"><span data-stu-id="97ddb-137">Following are solutions to commonly encountered issues:</span></span>
  
- <span data-ttu-id="97ddb-138">**问题：运行部署脚本时部署失败或停止响应。登录到每个 VM 后，管理/内部/外部 NIC 的 IP 地址缺失或不正确。**</span><span class="sxs-lookup"><span data-stu-id="97ddb-138">**Issue: Deployment fails or stops responding when running the deployment scripts. After logging on to each VM, the IP address is missing or incorrect for the Management/Internal/External NIC.**</span></span>
    
    <span data-ttu-id="97ddb-139">**解决方法：** 此问题无法自动解决。</span><span class="sxs-lookup"><span data-stu-id="97ddb-139">**Resolution:** This issue cannot be resolved automatically.</span></span> <span data-ttu-id="97ddb-140">NIC 无法添加到 VM 运行时。</span><span class="sxs-lookup"><span data-stu-id="97ddb-140">NICs cannot be added to VMs while they are running.</span></span> <span data-ttu-id="97ddb-141">请在 hyper-v 管理器中关闭并删除这些 VM，然后运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="97ddb-141">Please shut down and remove these VMs in hyper-v manager, then run the following cmdlets:</span></span>
    
  ```powershell
  Uninstall-CcAppliance
  ```

  ```powershell
  Install-CcAppliance
  ```

- 
    
    <span data-ttu-id="97ddb-142">**问题：安装 Active Directory 服务器和林后，CMS 服务器和/或中介服务器未正确加入域。**</span><span class="sxs-lookup"><span data-stu-id="97ddb-142">**Issue: After the Active Directory Server and forest are installed, the CMS Server and/or Mediation Server did not join the domain correctly.**</span></span>
    
    <span data-ttu-id="97ddb-143">**解决方法：** 若要解决此问题，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="97ddb-143">**Resolution:** To resolve this issue, take the following steps:</span></span>
    
  - <span data-ttu-id="97ddb-144">登录到 Active Directory 服务器并验证域是否创建正确。</span><span class="sxs-lookup"><span data-stu-id="97ddb-144">Log on to the Active Directory Server and verify that the domain was created correctly.</span></span>
    
  - <span data-ttu-id="97ddb-145">登录到 CMS/中介服务器，并验证在公司网络 NIC 上是否分配了有效的 IP 地址，以及是否将有效的静态 IP 和 DNS 配置为 AD 服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="97ddb-145">Log on to the CMS/Mediation Server and verify that on the corpnet NIC a valid IP address is assigned, and that valid static IP and DNS is configured as the AD server's IP address.</span></span>
    
  - <span data-ttu-id="97ddb-146">登录到 CMS/中介服务器，然后打开命令提示符。</span><span class="sxs-lookup"><span data-stu-id="97ddb-146">Log on to the CMS/Mediation Server, and open a command prompt.</span></span> <span data-ttu-id="97ddb-147">确保可以 ping Active Directory 服务器的 FQDN 和 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="97ddb-147">Make sure you can ping the FQDN and IP address of the Active Directory Server.</span></span> <span data-ttu-id="97ddb-148">如果无法，则可能是 IP 地址冲突。</span><span class="sxs-lookup"><span data-stu-id="97ddb-148">If you cannot, there may be an IP address conflict.</span></span> <span data-ttu-id="97ddb-149">请尝试为 Active Directory 分配新 IP，并相应地更新 CMS/中介服务器的 DNS。</span><span class="sxs-lookup"><span data-stu-id="97ddb-149">Please try to assign a new IP for Active Directory and update DNS on the CMS/Mediation server accordingly.</span></span>
    
- <span data-ttu-id="97ddb-150">**问题：您收到以下错误消息："Remove-VMSwitch ： Failed while removing virtual Ethernet switch.无法删除虚拟交换机"云连接器管理交换机"，因为它正由运行虚拟机使用或分配给子池。"**</span><span class="sxs-lookup"><span data-stu-id="97ddb-150">**Issue: You receive the following error message, "Remove-VMSwitch : Failed while removing virtual Ethernet switch. The virtual switch 'Cloud Connector Management Switch' cannot be deleted because it is being used by running virtual machines or assigned to child pools."**</span></span>
    
    <span data-ttu-id="97ddb-151">**解决方法：** 部署后未删除"云连接器管理交换机"。</span><span class="sxs-lookup"><span data-stu-id="97ddb-151">**Resolution:** The "Cloud Connector Management Switch" was not deleted after the deployment.</span></span> <span data-ttu-id="97ddb-152">如果发生此错误，请转到 Hyper-v 管理器并验证是否仍有虚拟机仍连接到它。</span><span class="sxs-lookup"><span data-stu-id="97ddb-152">If you hit this error, please go to Hyper-v manager and verify that there is not still a virtual machine still connected to it.</span></span> <span data-ttu-id="97ddb-153">如果仍有虚拟机连接，请断开它们连接并删除管理开关。</span><span class="sxs-lookup"><span data-stu-id="97ddb-153">If there are virtual machines still connected, disconnect them and delete the management switch.</span></span> <span data-ttu-id="97ddb-154">如果仍然无法删除管理交换机，请重新启动主机服务器并重试。</span><span class="sxs-lookup"><span data-stu-id="97ddb-154">If the management switch still cannot be deleted, restart the host server and try again.</span></span>
    
- <span data-ttu-id="97ddb-155">**问题：收到以下错误消息："服务 RTCMRAUTH 无法启动。检查以确保服务未禁用。"**</span><span class="sxs-lookup"><span data-stu-id="97ddb-155">**Issue: You receive the following error message, "Service RTCMRAUTH failed to start. Check to make sure the service is not disabled."**</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="97ddb-156">此问题仅适用于早于 1.4.2 的云连接器版本。</span><span class="sxs-lookup"><span data-stu-id="97ddb-156">This issue only applies to Cloud Connector versions earlier than 1.4.2.</span></span> 
  
    <span data-ttu-id="97ddb-157">启动失败还可能是因为此前端服务器之前已故障转移到 (计算机故障转移) 。</span><span class="sxs-lookup"><span data-stu-id="97ddb-157">The failure to start could also be because this Front End server was previously failed over (using computer fail over).</span></span> <span data-ttu-id="97ddb-158">如果是这种情况，请使用计算机故障回复 (调用故障回复) 。</span><span class="sxs-lookup"><span data-stu-id="97ddb-158">If that's the case, please invoke fail back (using computer fail back).</span></span>
    
    <span data-ttu-id="97ddb-159">**解决方法：** 边缘服务器不信任根 CA 证书或中间 CA 证书时，边缘服务器上会发生此问题。</span><span class="sxs-lookup"><span data-stu-id="97ddb-159">**Resolution:** This issue happens on an Edge Server when the root CA certificate or intermediate CA certificate is not trusted by the Edge Server.</span></span> <span data-ttu-id="97ddb-160">即使可以导入外部证书，但证书链断开。</span><span class="sxs-lookup"><span data-stu-id="97ddb-160">Even if the external certificate can be imported but the certificate chain is broken.</span></span> <span data-ttu-id="97ddb-161">在这种情况下，RTCMRAUTH 和/或 RTCSRV 服务无法启动。</span><span class="sxs-lookup"><span data-stu-id="97ddb-161">Under this condition, the RTCMRAUTH and/or RTCSRV service can not start.</span></span>
    
    <span data-ttu-id="97ddb-162">请手动将外部证书的根 CA 证书和所有中间 CA 证书导入边缘服务器，然后重新启动边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="97ddb-162">Please import the root CA certificate and all intermediate CA certificates of your external certificate manually into the Edge Server and then restart the Edge Server.</span></span> <span data-ttu-id="97ddb-163">在看到 RTCMRAUTH 和 RTCSRV 服务在边缘服务器上启动后，返回到主机服务器，以管理员角色启动 PowerShell 控制台，然后运行以下 cmdlet 以切换到新部署：</span><span class="sxs-lookup"><span data-stu-id="97ddb-163">After you see the RTCMRAUTH and RTCSRV services started on the Edge Server, go back to your host server, launch a PowerShell console as administrator, and run following cmdlet to switch to the new deployment:</span></span>
    
  ```powershell
  Switch-CcVersion
  ```

- 
    
    <span data-ttu-id="97ddb-164">**问题：应用 Windows 更新时主机服务器已重新启动，并且由服务器服务的呼叫失败。**</span><span class="sxs-lookup"><span data-stu-id="97ddb-164">**Issue: The host server was restarted when Windows updates were applied, and calls serviced by the server are failing.**</span></span>
    
    <span data-ttu-id="97ddb-165">**解决方法：** 如果部署了高可用性环境，Microsoft 将提供一个 cmdlet 来帮助在手动检查和安装 Windows 更新时将一台主机 (部署实例) 移入或退出当前拓扑。</span><span class="sxs-lookup"><span data-stu-id="97ddb-165">**Resolution:** If you deployed a high availability environment, Microsoft provides a cmdlet to help move one host machine (deployment instance) into or out of the current topology when you check and install Windows update manually.</span></span> <span data-ttu-id="97ddb-166">若要完成此操作，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="97ddb-166">Use the following steps to accomplish this:</span></span>
    
1. <span data-ttu-id="97ddb-167">在主机服务器上，以管理员角色启动 PowerShell 控制台，然后运行：</span><span class="sxs-lookup"><span data-stu-id="97ddb-167">On the host server, start a PowerShell console as administrator, then run:</span></span>
    
   ```powershell
   Enter-CcUpdate
   ```

2. <span data-ttu-id="97ddb-168">检查更新并安装任何可用更新。</span><span class="sxs-lookup"><span data-stu-id="97ddb-168">Check for updates and install any that are available.</span></span>
    
3. <span data-ttu-id="97ddb-169">在 PowerShell 控制台中，运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="97ddb-169">In the PowerShell console, run the following cmdlet:</span></span>
    
   ```powershell
   Exit-CcUpdate
   ```

- 
    
    <span data-ttu-id="97ddb-170">**问题：使用 PSTN 号码从 Skype for Business 客户端发出呼叫时，无法通过邀请其他 PSTN 号码将呼叫提升为会议。**</span><span class="sxs-lookup"><span data-stu-id="97ddb-170">**Issue: When a call is made from a Skype for Business client using a PSTN number, the call cannot be escalated to a conference by inviting another PSTN number.**</span></span>
    
    <span data-ttu-id="97ddb-171">**解决方法：** 若要解决此问题，请参阅配置 [联机混合中介服务器设置](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer)。</span><span class="sxs-lookup"><span data-stu-id="97ddb-171">**Resolution:** To resolve this issue, see [Configure online hybrid Mediation Server Settings](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).</span></span>
    
- <span data-ttu-id="97ddb-172">**问题：安装 Active Directory 服务器时，会显示有关 Windows 更新的警告消息 -"未启用 Windows 自动更新。若要确保新安装的角色或功能自动更新，请打开 Windows 更新。"**</span><span class="sxs-lookup"><span data-stu-id="97ddb-172">**Issue: A warning message is displayed about Windows Update when you are installing Active Directory server - "Windows automatic updating is not enabled. To ensure that your newly-installed role or feature is automatically updated, turn on Windows Update."**</span></span>
    
    <span data-ttu-id="97ddb-173">**解决方法：** 使用 Skype for Business 租户管理员凭据启动租户远程 PowerShell 会话，然后运行以下 cmdlet 检查站点的 _EnableAutoUpdate_ 配置：</span><span class="sxs-lookup"><span data-stu-id="97ddb-173">**Resolution:** Launch a Tenant Remote PowerShell session using Skype for Business tenant admin credentials, then run the following cmdlet to check the _EnableAutoUpdate_ configuration of your site:</span></span>
    
  ```powershell
  Get-CsHybridPSTNSite
  ```

    <span data-ttu-id="97ddb-174">如果  _EnableAutoUpdate_ 设置为 **True，** 可以安全地忽略此警告消息，因为 CCEManagement 服务将同时为虚拟机和主机服务器处理 Windows 更新的下载和安装。</span><span class="sxs-lookup"><span data-stu-id="97ddb-174">If  _EnableAutoUpdate_ is set to **True**, you can safely ignore this warning message because the CCEManagement service will handle downloading and installing Windows updates for both virtual machines and the host server.</span></span> <span data-ttu-id="97ddb-175">如果  _EnableAutoUpdate_ 设置为 **False**，请运行以下 cmdlet 以将设置为 **True**。</span><span class="sxs-lookup"><span data-stu-id="97ddb-175">If  _EnableAutoUpdate_ is set to **False**, run following cmdlet to set it to **True**.</span></span>
    
  ```powershell
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    <span data-ttu-id="97ddb-176">或者，可以手动检查并安装更新。</span><span class="sxs-lookup"><span data-stu-id="97ddb-176">Alternatively, you can manually check for and install updates.</span></span> <span data-ttu-id="97ddb-177">请参阅下一部分。</span><span class="sxs-lookup"><span data-stu-id="97ddb-177">See the next section.</span></span>
    
- <span data-ttu-id="97ddb-178">**问题：收到错误消息：无法注册设备，因为当前输入/配置或与设备 \<SiteName\> (\<ApplianceName\> \<Mediation Server FQDN\> \<Mediation Server IP Address\> 冲突) 。删除冲突设备或更新输入/配置信息，然后重新注册。在运行 Register-CcAppliance将当前设备注册到联机时。**</span><span class="sxs-lookup"><span data-stu-id="97ddb-178">**Issue: You receive an error message: Cannot register appliance because your current input/configuration \<SiteName\> or \<ApplianceName\> or \<Mediation Server FQDN\> or \<Mediation Server IP Address\> conflicts with existing appliance(s). Remove conflict appliance or update your input/configuration information then register again. ' when run Register-CcAppliance to register current appliance to online.**</span></span>
    
    <span data-ttu-id="97ddb-179">**解决方法：**\<ApplianceName\>和 的值 \<Mediation Server FQDN\> \<Mediation Server IP Address\> 必须是唯一的，并且仅用于一个设备注册。</span><span class="sxs-lookup"><span data-stu-id="97ddb-179">**Resolution:** Values for the \<ApplianceName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> must be unique and only used for one appliance registration.</span></span> <span data-ttu-id="97ddb-180">默认情况下， \<ApplianceName\> 来自主机名。</span><span class="sxs-lookup"><span data-stu-id="97ddb-180">By default, \<ApplianceName\> comes from the host name.</span></span> <span data-ttu-id="97ddb-181">\<Mediation Server FQDN\> 和 \<Mediation Server IP Address\> 在配置 ini 文件中定义。</span><span class="sxs-lookup"><span data-stu-id="97ddb-181">\<Mediation Server FQDN\> and \<Mediation Server IP Address\> defined in configuration ini file.</span></span>
    
    <span data-ttu-id="97ddb-182">例如，使用 (ApplianceName= MyserverNew、中介服务器 FQDN=ms.contoso.com、 要注册到 SiteName=MySite 的中介服务器 IP Address=10.10.10.10) ，但如果存在注册设备 (ApplianceName= Myserver、中介服务器 FQDN=ms.contoso.com、中介服务器 IP Address=10.10.10.10) ，则存在冲突。</span><span class="sxs-lookup"><span data-stu-id="97ddb-182">For example, using (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) to register to SiteName=MySite, but if there is a registered appliance (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10), you will have the conflict.</span></span>
    
    <span data-ttu-id="97ddb-183">首先，请检查 ApplianceRoot CloudConnector.ini部分中的文件。</span><span class="sxs-lookup"><span data-stu-id="97ddb-183">First, please check your CloudConnector.ini file in ApplianceRoot directory section.</span></span> <span data-ttu-id="97ddb-184">你将在 \<SiteName\> \<Mediation Server FQDN\> 文件中 \<Mediation Server IP Address\> 获取 和 值。</span><span class="sxs-lookup"><span data-stu-id="97ddb-184">You will get \<SiteName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> values in the file.</span></span> <span data-ttu-id="97ddb-185">\<ApplianceName\> 是主机服务器名称。</span><span class="sxs-lookup"><span data-stu-id="97ddb-185">\<ApplianceName\> is your host server name.</span></span>
    
    <span data-ttu-id="97ddb-186">其次，使用 Skype for Business 租户管理员凭据启动租户远程 PowerShell，然后运行以下 cmdlet 检查注册 (设备) 。</span><span class="sxs-lookup"><span data-stu-id="97ddb-186">Second, Launch Tenant Remote PowerShell using your Skype for Business tenant admin credentials, then run the following cmdlet to check the registered appliance(s).</span></span>
    
  ```powershell
  Get-CsHybridPSTNAppliance
  ```

    <span data-ttu-id="97ddb-187">识别任何冲突后，可以使用与已注册设备匹配的信息更新 CloudConnector.ini 文件，或者注销现有设备以解决冲突。</span><span class="sxs-lookup"><span data-stu-id="97ddb-187">After identifying any conflicts, you can either update your CloudConnector.ini file with information that matches the registered appliance, or unregister the existing appliance to resolve the conflicts.</span></span>
    
  ```powershell
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- <span data-ttu-id="97ddb-188">**问题：如果Get-CcRunningVersion已部署的设备，则此 cmdlet 将返回空值。**</span><span class="sxs-lookup"><span data-stu-id="97ddb-188">**Issue: The Get-CcRunningVersion cmdlet returns an empty value if there is a deployed appliance running on the host.**</span></span>
    
  <span data-ttu-id="97ddb-189">**解决方法：** 从 1.3.4 或 1.3.8 升级到 1.4.1 时，可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="97ddb-189">**Resolution:** This can happen when you upgrade from 1.3.4 or 1.3.8 to 1.4.1.</span></span> <span data-ttu-id="97ddb-190">使用 .msi 安装版本 1.4.1 后，必须先运行 ，然后才能运行任何其他 `Register-CcAppliance` cmdlet。</span><span class="sxs-lookup"><span data-stu-id="97ddb-190">After you install version 1.4.1 with the .msi, you must run `Register-CcAppliance` before you run any other cmdlet.</span></span> <span data-ttu-id="97ddb-191">`Register-CcAppliance` 将文件module.ini %UserProfile%\CloudConnector 迁移到 %ProgramData%\CloudConnector。</span><span class="sxs-lookup"><span data-stu-id="97ddb-191">`Register-CcAppliance` will migrate the module.ini file from %UserProfile%\CloudConnector to %ProgramData%\CloudConnector.</span></span> <span data-ttu-id="97ddb-192">如果你错过它，将在 %ProgramData%\CloudConnector 文件夹中module.ini一个新的数据库，并替换 1.3.4 或 1.3.8 的运行/备份版本信息。</span><span class="sxs-lookup"><span data-stu-id="97ddb-192">If you missed it, a new module.ini will be created in %ProgramData%\CloudConnector folder and replace the running/backup version information for 1.3.4 or 1.3.8.</span></span>
    
  <span data-ttu-id="97ddb-193">比较module.ini %UserProfile%\CloudConnector 和 %ProgramData%\CloudConnector 文件夹中的文件。</span><span class="sxs-lookup"><span data-stu-id="97ddb-193">Compare module.ini files in %UserProfile%\CloudConnector and %ProgramData%\CloudConnector folder.</span></span> <span data-ttu-id="97ddb-194">如果存在差异，请删除 %ProgramData%\CloudConnector module.ini文件，然后重新运行  `Register-CcAppliance` 。</span><span class="sxs-lookup"><span data-stu-id="97ddb-194">If there are differences, delete the module.ini file in %ProgramData%\CloudConnector and rerun  `Register-CcAppliance`.</span></span> <span data-ttu-id="97ddb-195">您还可以手动将该文件修改为正确的运行和备份版本。</span><span class="sxs-lookup"><span data-stu-id="97ddb-195">You could also modify the file manually to the correct running and backup version.</span></span>
    
- <span data-ttu-id="97ddb-196">**问题：运行 Switch-CcVersion cmdlet 以切换到与当前脚本版本不同的旧版本后，此旧版本没有高可用性支持。**</span><span class="sxs-lookup"><span data-stu-id="97ddb-196">**Issue: After you run the Switch-CcVersion cmdlet to switch to an old version which is different from current script version, there is no High Availability support for this old version.**</span></span>
    
    <span data-ttu-id="97ddb-197">**解决方法：** 例如，您从 1.4.1 升级到 1.4.2。</span><span class="sxs-lookup"><span data-stu-id="97ddb-197">**Resolution:** For example, you have upgraded from 1.4.1 to 1.4.2.</span></span> <span data-ttu-id="97ddb-198">当前脚本版本（可通过运行 确定）和正在运行的版本（可通过运行确定） `Get-CcVersion`  `Get-CcRunningVersion` 都是 1.4.2。</span><span class="sxs-lookup"><span data-stu-id="97ddb-198">Your current script version, which can be determined by running `Get-CcVersion`, and your running version, which can be determined by running  `Get-CcRunningVersion` are both 1.4.2.</span></span> <span data-ttu-id="97ddb-199">此时，如果运行 以将正在运行的版本切换回 `Switch-CcVersion` 1.4.1，则此旧版本将没有高可用性支持。</span><span class="sxs-lookup"><span data-stu-id="97ddb-199">At this time, if you run `Switch-CcVersion` to switch the running version back to 1.4.1, then there will be no High Availability support for this old version.</span></span>
    
    <span data-ttu-id="97ddb-200">若要获得完整的高可用性支持，请切换回 1.4.2，以便运行的版本和脚本版本相同。</span><span class="sxs-lookup"><span data-stu-id="97ddb-200">To get full High Availability support, please switch back to 1.4.2, so the running version and script version are the same.</span></span> <span data-ttu-id="97ddb-201">如果 1.4.2 部署出现问题，请尽快卸载并重新安装。</span><span class="sxs-lookup"><span data-stu-id="97ddb-201">If you are experiencing problems with your 1.4.2 deployment, please uninstall and reinstall it as soon as possible.</span></span>
    
- <span data-ttu-id="97ddb-202">**问题：颁发给中央管理存储、中介服务器和边缘服务器的证书颁发机构证书或内部证书即将过期或受到威胁。**</span><span class="sxs-lookup"><span data-stu-id="97ddb-202">**Issue: Certificate authority certificates or internal certificates issued to Central Management Store, Mediation Server, and Edge Server are near expiration or are compromised.**</span></span>
    
    <span data-ttu-id="97ddb-203">**解决方法：** Skype for Business 证书颁发机构证书的有效期为五年。</span><span class="sxs-lookup"><span data-stu-id="97ddb-203">**Resolution:** Skype for Business certification authority certificates are valid for five years.</span></span> <span data-ttu-id="97ddb-204">颁发给中央管理存储、中介服务器和边缘服务器的内部证书有效期为两年。</span><span class="sxs-lookup"><span data-stu-id="97ddb-204">Internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="97ddb-205">在云连接器 2.0 版和更高版本中，Renew-CcServerCertificate cmdlet 已更改为 Update-CcServerCertificate 并且 Renew-CcCACertificate cmdlet 已更改为 Update-CcCACertificate。</span><span class="sxs-lookup"><span data-stu-id="97ddb-205">In Cloud Connector version 2.0 and later, the Renew-CcServerCertificate cmdlet has changed to Update-CcServerCertificate and the Renew-CcCACertificate cmdlet has changed to Update-CcCACertificate.</span></span> 
  
    <span data-ttu-id="97ddb-206">如果颁发给中央管理存储、中介服务器和边缘服务器的内部证书即将过期或受到威胁，请运行 Renew-CcServerCertificate 或 Update-CcServerCertificate cmdlet 来续订证书。</span><span class="sxs-lookup"><span data-stu-id="97ddb-206">If internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are near expiration or compromised, run the Renew-CcServerCertificate or Update-CcServerCertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="97ddb-207">如果证书颁发机构证书即将过期，请运行 Renew-CcCACertificate 或 Update-CcCACertificate cmdlet 来续订证书。</span><span class="sxs-lookup"><span data-stu-id="97ddb-207">If certification authority certificates are near expiration, run the Renew-CcCACertificate or Update-CcCACertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="97ddb-208">**如果证书颁发机构证书受到威胁，并且** 站点中只有一个设备，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="97ddb-208">**If certification authority certificates are compromised and there is only one appliance in the site,** perform the following steps:</span></span>
    
1. <span data-ttu-id="97ddb-209">运行 Enter-CcUpdate cmdlet 以排出服务，将设备置于维护模式。</span><span class="sxs-lookup"><span data-stu-id="97ddb-209">Run the Enter-CcUpdate cmdlet to drain services and put the appliance in maintenance mode.</span></span>
   
   ```powershell
   Enter-CcUpdate
   ```
   
2. <span data-ttu-id="97ddb-210">运行以下 cmdlet 以重置并创建新的证书颁发机构证书以及所有内部服务器证书：</span><span class="sxs-lookup"><span data-stu-id="97ddb-210">Run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
    <span data-ttu-id="97ddb-211">对于 2.0 之前发布的云连接器：</span><span class="sxs-lookup"><span data-stu-id="97ddb-211">For Cloud Connector releases before 2.0:</span></span>
    
    ```powershell
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    <span data-ttu-id="97ddb-212">或者对于云连接器 2.0 版和更高版本：</span><span class="sxs-lookup"><span data-stu-id="97ddb-212">Or for Cloud Connector release 2.0 and later:</span></span>
    
    ```powershell
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```
    
3. <span data-ttu-id="97ddb-213">如果在网关和中介服务器之间使用了 TLS，请从设备运行 Export-CcRootCertificate cmdlet，然后将导出的证书安装到 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="97ddb-213">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from the appliance, and then install the exported certificate to your PSTN gateways.</span></span> <span data-ttu-id="97ddb-214">您可能还需要在网关上重新颁发证书。</span><span class="sxs-lookup"><span data-stu-id="97ddb-214">You may also be required to re-issue the certificate on your gateway.</span></span>

   ```powershell
   Export-CcRootCertificate
   ```

4. <span data-ttu-id="97ddb-215">运行 Exit-CcUpdate cmdlet 以启动服务并退出维护模式。</span><span class="sxs-lookup"><span data-stu-id="97ddb-215">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span>

   ```powershell
   Exit-CcUpdate
   ```


    <span data-ttu-id="97ddb-216">**如果证书颁发机构证书受到威胁** ，并且站点中有多个设备，请对站点中的每个设备执行以下顺序步骤。</span><span class="sxs-lookup"><span data-stu-id="97ddb-216">**If certification authority certificates are compromised and there are multiple appliances in the site,** perform the following sequential steps on each appliance in the site.</span></span>
    
    <span data-ttu-id="97ddb-217">Microsoft 建议您在非高峰使用时段执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="97ddb-217">Microsoft recommends that you perform these steps during non-peak usage times.</span></span>
    
1. <span data-ttu-id="97ddb-218">第一个设备运行 Remove-CcCertificationAuthorityFile cmdlet 以清理目录中的 CA 备份 \<SiteRoot\> 文件。</span><span class="sxs-lookup"><span data-stu-id="97ddb-218">On the first appliance, run the Remove-CcCertificationAuthorityFile cmdlet to clean up the CA backup files in the \<SiteRoot\> directory.</span></span>

     ```powershell
     Remove-CcCertificationAuthorityFile
     ```
    
2. <span data-ttu-id="97ddb-219">运行 Enter-CcUpdate cmdlet 以排出服务，将每台设备置于维护模式。</span><span class="sxs-lookup"><span data-stu-id="97ddb-219">Run the Enter-CcUpdate cmdlet to drain services and put each appliance in maintenance mode.</span></span>

     ```powershell
     Enter-CcUpdate
     ```
    
3. <span data-ttu-id="97ddb-220">在首个设备中，运行以下 cmdlet 以重置并创建新的证书颁发机构证书以及所有内部服务器证书：</span><span class="sxs-lookup"><span data-stu-id="97ddb-220">On the first appliance, run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
     <span data-ttu-id="97ddb-221">对于 2.0 之前发布的云连接器：</span><span class="sxs-lookup"><span data-stu-id="97ddb-221">For Cloud Connector releases before 2.0:</span></span>
    
     ```powershell
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     <span data-ttu-id="97ddb-222">或者对于云连接器 2.0 版和更高版本：</span><span class="sxs-lookup"><span data-stu-id="97ddb-222">Or for Cloud Connector release 2.0 and later:</span></span>
    
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

4. <span data-ttu-id="97ddb-223">在首个设备中，运行以下 cmdlet 将 CA 文件备份到 \<SiteRoot\> 文件夹。</span><span class="sxs-lookup"><span data-stu-id="97ddb-223">On the first appliance, run the following cmdlet to back up the CA files to the \<SiteRoot\> folder.</span></span>
    
     ```powershell
     Backup-CcCertificationAuthority
     ```
   
5. <span data-ttu-id="97ddb-224">在同一站点中的所有其他设备中，运行以下命令以使用 CA 备份文件，以便设备全部使用相同的根证书，然后请求新证书。</span><span class="sxs-lookup"><span data-stu-id="97ddb-224">On all other appliance's in the same site, run the following commands to consume the CA backup files, so that the appliances all use the same root certificate, and then request new certificates.</span></span> 
   
     ```powershell
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```
     
6. <span data-ttu-id="97ddb-225">如果在网关和中介服务器之间使用 TLS，请从站点中任何设备运行 Export-CcRootCertificate cmdlet，然后将导出的证书安装到 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="97ddb-225">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from any appliance in the site, and then install the exported certificate to your PSTN gateways.</span></span> <span data-ttu-id="97ddb-226">您可能还需要在网关上重新颁发证书。</span><span class="sxs-lookup"><span data-stu-id="97ddb-226">You may also be required to re-issue the certificate on your gateway.</span></span>
  
     ```powershell
     Export-CcRootCertificate
     ```
     
7. <span data-ttu-id="97ddb-227">运行 Exit-CcUpdate cmdlet 以启动服务并退出维护模式。</span><span class="sxs-lookup"><span data-stu-id="97ddb-227">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span> 

     ```powershell
     Exit-CcUpdate
     ```
    
    
- <span data-ttu-id="97ddb-228">**问题：在云连接器管理服务日志中收到以下错误消息"C：\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log"： CceService Error： 0 ： Unexpected exception when reporting status to online： System.Management.Automation.CmdletInvocationException： Logon failed for the user \<Global Tenant Admin\> .请创建新的凭据对象，确保已使用正确的用户名和密码。---\>**</span><span class="sxs-lookup"><span data-stu-id="97ddb-228">**Issue: You receive the following error message in the Cloud Connector Management Service Log, "C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": CceService Error: 0 : Unexpected exception when reporting status to online: System.Management.Automation.CmdletInvocationException: Logon failed for the user \<Global Tenant Admin\>. Please create a new credential object, making sure that you have used the correct user name and password. ---\>**</span></span>
    
    <span data-ttu-id="97ddb-229">**解决方法：** 自云连接器设备注册后，Microsoft 365 或 Office 365 全局租户管理员凭据已更改。</span><span class="sxs-lookup"><span data-stu-id="97ddb-229">**Resolution:** The Microsoft 365 or Office 365 global tenant admin credentials have been changed since the Cloud Connector appliance was registered.</span></span> <span data-ttu-id="97ddb-230">若要更新云连接器设备本地存储的凭据，请从主机上的管理员 PowerShell 运行以下代码：</span><span class="sxs-lookup"><span data-stu-id="97ddb-230">To update the locally stored credentials on the Cloud Connector appliance, run the following from Administrator PowerShell on the host appliance:</span></span>
    
  ```powershell
  Set-CcCredential -AccountType TenantAdmin
  ```

- <span data-ttu-id="97ddb-231">**问题：更改用于部署的主机服务器帐户的密码后，在 %ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log 中或在运行 Get-CcCredential cmdlet 时收到以下错误消息："ConvertTo-SecureString： Key 无效 for use in specified state"。**</span><span class="sxs-lookup"><span data-stu-id="97ddb-231">**Issue: After you change the password for the host server account you used for the deployment, you receive the following error message: "ConvertTo-SecureString : Key not valid for use in specified state." in %ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log or while running the Get-CcCredential cmdlet.**</span></span>
    
    <span data-ttu-id="97ddb-232">**解决方法：** 所有云连接器凭据都存储在以下文件中："%SystemDrive%\Programdata\Cloudconnector\credentials." \<CurrentUser\>xml"。</span><span class="sxs-lookup"><span data-stu-id="97ddb-232">**Resolution:** All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="97ddb-233">当主机服务器上密码更改时，您需要更新本地存储的凭据。</span><span class="sxs-lookup"><span data-stu-id="97ddb-233">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
    
    <span data-ttu-id="97ddb-234">**如果运行的是云连接器版本 1.4.2，** 请执行以下步骤重新生成所有云连接器密码：</span><span class="sxs-lookup"><span data-stu-id="97ddb-234">**If you are running Cloud Connector version 1.4.2,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  1. <span data-ttu-id="97ddb-235">重新启动主机服务器。</span><span class="sxs-lookup"><span data-stu-id="97ddb-235">Restart the host server.</span></span>
    
  2. <span data-ttu-id="97ddb-236">删除以下文件："%SystemDrive%\Programdata\Cloudconnector\credentials." \<CurrentUser\>xml"。</span><span class="sxs-lookup"><span data-stu-id="97ddb-236">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
  3. <span data-ttu-id="97ddb-237">以管理员角色启动 PowerShell 控制台，然后运行"Register-CcAppliance -Local"，按照说明重新输入密码。</span><span class="sxs-lookup"><span data-stu-id="97ddb-237">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="97ddb-238">输入之前为云连接器部署输入的相同密码。</span><span class="sxs-lookup"><span data-stu-id="97ddb-238">Enter the same passwords you entered before for the Cloud Connector deployment.</span></span>
    
     <span data-ttu-id="97ddb-239">**如果运行的是云连接器 2.0** 版或更高版本，请执行以下步骤重新生成所有云连接器密码：</span><span class="sxs-lookup"><span data-stu-id="97ddb-239">**If you are running Cloud Connector version 2.0 or later,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  4. <span data-ttu-id="97ddb-240">重新启动主机服务器。</span><span class="sxs-lookup"><span data-stu-id="97ddb-240">Restart the host server.</span></span>
    
  5. <span data-ttu-id="97ddb-241">删除以下文件："%SystemDrive%\Programdata\Cloudconnector\credentials." \<CurrentUser\>xml" .</span><span class="sxs-lookup"><span data-stu-id="97ddb-241">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" .</span></span>
    
  6. <span data-ttu-id="97ddb-242">以管理员角色启动 PowerShell 控制台，然后运行"Register-CcAppliance -Local"，按照说明重新输入密码。</span><span class="sxs-lookup"><span data-stu-id="97ddb-242">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> 
    
     <span data-ttu-id="97ddb-243">如果缓存的密码文件是使用云连接器版本 1.4.2 生成的，则当系统提示时，请使用 CceService 密码的 VMAdmin 密码。</span><span class="sxs-lookup"><span data-stu-id="97ddb-243">If the cached password file was generated with Cloud Connector version 1.4.2, use the VMAdmin password for the CceService password when prompted.</span></span> <span data-ttu-id="97ddb-244">输入之前为所有其他帐户的云连接器部署输入的相同密码。</span><span class="sxs-lookup"><span data-stu-id="97ddb-244">Enter the same password you entered before for the Cloud Connector deployment for all other accounts.</span></span>
    
     <span data-ttu-id="97ddb-245">如果缓存的密码文件是使用云连接器版本 1.4.2 生成的，并且 DomainAdmin 和 VMAdmin 密码不同，则必须执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="97ddb-245">If the cached password file was generated with Cloud Connector version 1.4.2 and the DomainAdmin and VMAdmin passwords are different, you must perform the following steps:</span></span>
    
  7. <span data-ttu-id="97ddb-246">运行 Set-CcCredential -AccountType DomainAdmin，如下所示：</span><span class="sxs-lookup"><span data-stu-id="97ddb-246">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
  8. <span data-ttu-id="97ddb-247">当系统提示输入旧帐户凭据时，请输入用于 CceService 密码的凭据。</span><span class="sxs-lookup"><span data-stu-id="97ddb-247">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
  9. <span data-ttu-id="97ddb-248">当系统提示输入新帐户凭据时，请输入之前使用的 DomainAdmin 密码的密码。</span><span class="sxs-lookup"><span data-stu-id="97ddb-248">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
     <span data-ttu-id="97ddb-249">如果缓存的密码文件是使用云连接器版本 2.0 或更高版本生成的，则默认情况下，VmAdmin 和 DomainAdmin 使用与 CceService 相同的密码。</span><span class="sxs-lookup"><span data-stu-id="97ddb-249">If the cached password file was generated with Cloud Connector version 2.0 or later, by default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="97ddb-250">如果更改了 DomainAdmin 和 VMAdmin 密码，则必须执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="97ddb-250">If you changed the DomainAdmin and VMAdmin passwords, you must perform the following steps:</span></span>
    
  10. <span data-ttu-id="97ddb-251">运行 Set-CcCredential -AccountType DomainAdmin，如下所示：</span><span class="sxs-lookup"><span data-stu-id="97ddb-251">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
       1. <span data-ttu-id="97ddb-252">当系统提示输入旧帐户凭据时，输入用于 CceService 密码的凭据</span><span class="sxs-lookup"><span data-stu-id="97ddb-252">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="97ddb-253">当系统提示输入新帐户凭据时，请输入之前使用的 DomainAdmin 密码的密码。</span><span class="sxs-lookup"><span data-stu-id="97ddb-253">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
  11. <span data-ttu-id="97ddb-254">运行 Set-CcCredential -AccountType VmAdmin，如下所示：</span><span class="sxs-lookup"><span data-stu-id="97ddb-254">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
       1. <span data-ttu-id="97ddb-255">当系统提示输入旧帐户凭据时，输入用于 CceService 密码的凭据</span><span class="sxs-lookup"><span data-stu-id="97ddb-255">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="97ddb-256">当系统提示输入新帐户凭据时，请输入之前使用的 VmAdmin 密码的密码。</span><span class="sxs-lookup"><span data-stu-id="97ddb-256">When prompted for the new account credential, enter the password for the VmAdmin password you used before.</span></span> 
    
- <span data-ttu-id="97ddb-257">**问题：对于云连接器版本 2.1 及更高版本，当在设备中运行 Register-CcAppliance 或其他 cmdlet 时，将收到错误消息，例如："对于 Each-Object ：在此对象上找不到属性"Common"。验证属性是否存在。在 C：\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1：681 char：14"**</span><span class="sxs-lookup"><span data-stu-id="97ddb-257">**Issue: With Cloud Connector version 2.1 and later, when running Register-CcAppliance or other cmdlets on the appliance, you receive an error message such as: "For Each-Object : The property 'Common' cannot be found on this object. Verify that the property exists. At C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char:14"**</span></span>
    
    <span data-ttu-id="97ddb-258">**解决方法：** 云连接器 2.1 及更高版本.NET Framework 4.6.1 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="97ddb-258">**Resolution:** Cloud Connector 2.1 and later requires .NET Framework 4.6.1 or later.</span></span> <span data-ttu-id="97ddb-259">Please update .NET Framework on the appliance to version 4.6.1 or later and run the cmdlet (s) again.</span><span class="sxs-lookup"><span data-stu-id="97ddb-259">Please update .NET Framework on the appliance to version 4.6.1 or later and run the cmdlet(s) again.</span></span>

- <span data-ttu-id="97ddb-260">**问题：在云连接器版本 2.1 中，运行 Install-CcAppliance 时，会收到一条错误消息，例如："安装新实例失败，出现错误：无法设置"状态"，因为只能将字符串用作设置 XmlNode 属性的值"**</span><span class="sxs-lookup"><span data-stu-id="97ddb-260">**Issue: With Cloud Connector Edition 2.1, when running Install-CcAppliance, you receive an error message such as: "Failed to install new instance with error: Cannot set "State" because only strings can be used as values to set XmlNode properties"**</span></span>

   <span data-ttu-id="97ddb-261">**解决方法：** In Cloudconnector.ini， under the [Common] section， please add the "State" config as below： CountryCode=US State=WA City=Redmond</span><span class="sxs-lookup"><span data-stu-id="97ddb-261">**Resolution:** In Cloudconnector.ini, under the [Common] section, please add the “State” config as below:  CountryCode=US  State=WA  City=Redmond</span></span>

   <span data-ttu-id="97ddb-262">"State"行不一定必须具有值，但不能从"State"Cloudconnector.ini中删除。</span><span class="sxs-lookup"><span data-stu-id="97ddb-262">It is not mandatory for the "State" line to have value, however the "State" line cannot be removed from the Cloudconnector.ini file.</span></span>

- <span data-ttu-id="97ddb-263">**问题：收到以下错误消息"Dismount-WindowsImage ： Dismount-WindowsImage失败。安装或0xc1550115云连接器版本时，错误代码 = 0xc1550115"。**</span><span class="sxs-lookup"><span data-stu-id="97ddb-263">**Issue: You receive the following error message "Dismount-WindowsImage : Dismount-WindowsImage failed. Error code = 0xc1550115" when installing or upgrading Cloud Connector Edition.**</span></span>
    
    <span data-ttu-id="97ddb-264">**解决方法：** 以管理员角色启动 PowerShell 控制台，运行"DISM -Cleanup-Wim'"。</span><span class="sxs-lookup"><span data-stu-id="97ddb-264">**Resolution:** Launch a PowerShell console as administrator, run "DISM -Cleanup-Wim'".</span></span> <span data-ttu-id="97ddb-265">这将清理所有有问题的图像。</span><span class="sxs-lookup"><span data-stu-id="97ddb-265">This will clean up all troubled images.</span></span> <span data-ttu-id="97ddb-266">再次Install-CcAppliance或等待位自动升级。</span><span class="sxs-lookup"><span data-stu-id="97ddb-266">Run Install-CcAppliance again or wait for the bits to automatically upgrade.</span></span>
    
- <span data-ttu-id="97ddb-267">**问题：HA 环境中第一个云连接器设备的部署失败**</span><span class="sxs-lookup"><span data-stu-id="97ddb-267">**Issue: Deployment of the first Cloud Connector appliance in an HA environment fails**</span></span>
    
    <span data-ttu-id="97ddb-268">**解决方法：** 您执行的步骤取决于部署失败的原因：</span><span class="sxs-lookup"><span data-stu-id="97ddb-268">**Resolution:** The steps you take depend on the reason the deployment failed:</span></span>
    
  - <span data-ttu-id="97ddb-269">如果第一个云连接器设备出现故障，并且无法确定故障原因，则必须在部署成功之前再次安装该设备，然后安装其他设备。</span><span class="sxs-lookup"><span data-stu-id="97ddb-269">If the first Cloud Connector appliance fails and you cannot determine the reason for the failure, you must install the appliance again until the deployment is successful, and then install the other appliances.</span></span>
    
  - <span data-ttu-id="97ddb-270">如果第一个云连接器设备出现故障，出现一个小问题（如外部证书问题）时，你可能能够在不重新安装该设备的情况下解决该问题。</span><span class="sxs-lookup"><span data-stu-id="97ddb-270">If the first Cloud Connector appliance fails with a minor issue, such as an external certificate issue, you might be able to fix the problem without re-installing the appliance.</span></span> <span data-ttu-id="97ddb-271">然后，可以使用租户远程 PowerShell 将部署标记为成功，如下所示。</span><span class="sxs-lookup"><span data-stu-id="97ddb-271">You can then use tenant remote PowerShell to mark the deployment as successful as follows.</span></span> <span data-ttu-id="97ddb-272"> (如果第一次部署成功，您也可以使用以下步骤，但出于某种原因，云连接器无法将部署报告为成功。) </span><span class="sxs-lookup"><span data-stu-id="97ddb-272">(You can also use the following steps if the first deployment was successful, but, for some reason, Cloud Connector fails to report the deployment as a success.)</span></span>
    
  - <span data-ttu-id="97ddb-273">若要获取第一 (设备的 IDENTITY) GUID，请运行 Get-CsHybridPSTNAppliance cmdlet。</span><span class="sxs-lookup"><span data-stu-id="97ddb-273">To get the Identity (GUID) of the first Cloud Connector appliance, run the Get-CsHybridPSTNAppliance cmdlet.</span></span>
    
  - <span data-ttu-id="97ddb-274">若要将设备标记为已成功部署，请Set-CsCceApplianceDeploymentStatus如下所示：</span><span class="sxs-lookup"><span data-stu-id="97ddb-274">To mark the appliance as successfully deployed, run the Set-CsCceApplianceDeploymentStatus as follows:</span></span>
    
  ```powershell
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- <span data-ttu-id="97ddb-275">**问题：需要在主机服务器或虚拟机上手动检查并安装 Windows 更新。**</span><span class="sxs-lookup"><span data-stu-id="97ddb-275">**Issue: You need to check for and install Windows updates manually on the host server or virtual machines.**</span></span>
    
   <span data-ttu-id="97ddb-276">**解决方法：** 我们建议你利用 Skype for Business 云连接器版本提供的自动操作系统更新。</span><span class="sxs-lookup"><span data-stu-id="97ddb-276">**Resolution:** We recommend that you take advantage of automated OS updates provided by Skype for Business Cloud Connector Edition.</span></span> <span data-ttu-id="97ddb-277">注册设备进行联机管理并启用自动更新操作系统后，主机服务器和虚拟机将根据操作系统更新时间窗口设置自动检查和安装 Windows 更新。</span><span class="sxs-lookup"><span data-stu-id="97ddb-277">After an appliance is registered for online management and auto OS update is enabled, the host server and virtual machines will check and install Windows Updates automatically according to the OS update time window settings.</span></span>
    
   <span data-ttu-id="97ddb-278">如果需要手动检查并安装 Windows 更新，请按照本节中适用于你的部署类型的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="97ddb-278">If you need to check for and install Windows Updates manually, follow the steps in this section that apply to your type of deployment.</span></span> <span data-ttu-id="97ddb-279">应计划同时更新主机服务器及其上运行的虚拟机，以最大限度地减少更新所需的停机时间。</span><span class="sxs-lookup"><span data-stu-id="97ddb-279">You should plan on updating both the host server and the virtual machines running on it at the same time to minimize the amount of down time necessary for the updates.</span></span>
    
   <span data-ttu-id="97ddb-280">如果愿意，可以使用 WSUS (Windows Server Update Services) 向云连接器服务器提供更新。</span><span class="sxs-lookup"><span data-stu-id="97ddb-280">If you prefer, you can use a Windows Server Update Services (WSUS) server to provide updates to Cloud Connector servers.</span></span> <span data-ttu-id="97ddb-281">只需确保将 Windows 更新配置为 **不自动** 安装。</span><span class="sxs-lookup"><span data-stu-id="97ddb-281">Just be sure to configure the Windows Update to **not** install automatically.</span></span>
    
   <span data-ttu-id="97ddb-282">若要了解如何手动更新云连接器部署，请参阅以下部分。</span><span class="sxs-lookup"><span data-stu-id="97ddb-282">For information about how to manually update your Cloud Connector deployment, see the following section.</span></span>
    
- <span data-ttu-id="97ddb-283">**问题：当云连接器更新到新内部版本时，不会更新云连接器 cmdlet。**</span><span class="sxs-lookup"><span data-stu-id="97ddb-283">**Issue: When Cloud Connector updates to a new build, Cloud Connector cmdlets are not updated.**</span></span> <span data-ttu-id="97ddb-284">当发生自动更新时，如果 PowerShell 窗口为打开状态，则有时会出现此情况。</span><span class="sxs-lookup"><span data-stu-id="97ddb-284">This sometimes happens if a PowerShell window is left open when automatic update occurs.</span></span>
    
  <span data-ttu-id="97ddb-285">**解决方法：** 若要加载更新的 cmdlet，可以执行以下步骤之一：</span><span class="sxs-lookup"><span data-stu-id="97ddb-285">**Resolution:** To load the updated cmdlets, you can do either of the following steps:</span></span>
    
   - <span data-ttu-id="97ddb-286">关闭云连接器设备的 PowerShell，然后重新打开 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="97ddb-286">Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.</span></span>
    
     - <span data-ttu-id="97ddb-287">或者，你可以运行 Import-Module -Force。</span><span class="sxs-lookup"><span data-stu-id="97ddb-287">Or, you can run Import-Module CloudConnector -Force.</span></span> 
 
-   <span data-ttu-id="97ddb-288">**问题："The term 'Stop-CsWindowsService' is not recognized as the name of a cmdlet， function， script file， or operable program." error when attempting to run Enter-CcUpdate cmdlet.**</span><span class="sxs-lookup"><span data-stu-id="97ddb-288">**Issue: "The term 'Stop-CsWindowsService' is not recognized as the name of a cmdlet, function, script file, or operable program." error when attempting to run Enter-CcUpdate cmdlet.**</span></span>

    <span data-ttu-id="97ddb-289">**解决方法：** 删除 $HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache 文件。</span><span class="sxs-lookup"><span data-stu-id="97ddb-289">**Resolution:** Delete the $HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache file.</span></span>
<span data-ttu-id="97ddb-290">PowerShell 将此文件创建为它找到的模块中的 cmdlet 缓存，这样它就不必每次重新分析所有模块，因为这样做会使操作变得很慢。</span><span class="sxs-lookup"><span data-stu-id="97ddb-290">PowerShell creates this file as a cache of cmdlets from modules that it finds so that it doesn’t have to re-analyze all the modules each time as that would make things really slow.</span></span> <span data-ttu-id="97ddb-291">很可能存在一些文件损坏，导致 PowerShell 在从该缓存中回读时产生令人误解的结果。</span><span class="sxs-lookup"><span data-stu-id="97ddb-291">Most likely, there was some file corruption that provided misleading results to PowerShell when it was reading back from that cache.</span></span>

-   <span data-ttu-id="97ddb-292">**问题："Import-Module CloudConnector"生成错误"Import-Module： 未加载指定的模块"CloudConnector"，因为在任何模块目录中都未找到有效的模块文件"**</span><span class="sxs-lookup"><span data-stu-id="97ddb-292">**Issue: “Import-Module CloudConnector” generates error “Import-Module: The specified module “CloudConnector” was not loaded because no valid module file was found in any module directory”**</span></span>

    <span data-ttu-id="97ddb-293">**解决办法：**</span><span class="sxs-lookup"><span data-stu-id="97ddb-293">**Resolution:**</span></span>
    - <span data-ttu-id="97ddb-294">验证 CloudConnector 模块是否确实位于 c：\Program Files\WindowsPowerShell\Modules 下</span><span class="sxs-lookup"><span data-stu-id="97ddb-294">Validate that indeed the CloudConnector module exists under c:\Program Files\WindowsPowerShell\Modules</span></span>
    
    - <span data-ttu-id="97ddb-295">在验证 CloudConnector 模块是否存在在此位置之后，可以更改存储模块位置路径的 PSModulePath 环境变量：</span><span class="sxs-lookup"><span data-stu-id="97ddb-295">After validating that CloudConnector module exists under this location, the PSModulePath environment variable storing the path to the locations of the modules can be changed:</span></span>
    
     <span data-ttu-id="97ddb-296">a.</span><span class="sxs-lookup"><span data-stu-id="97ddb-296">a.</span></span> <span data-ttu-id="97ddb-297">临时更改：以管理员角色启动 Powershell 并运行以下命令：$env：PSModulePath = $env：PSModulePath + ";C：\Program Files\WindowsPowerShell\Modules\"</span><span class="sxs-lookup"><span data-stu-id="97ddb-297">Temporary change: Start Powershell as an Administrator and run the following command: $env:PSModulePath = $env:PSModulePath + ";C:\Program Files\WindowsPowerShell\Modules\"</span></span>
        
     <span data-ttu-id="97ddb-298">b.</span><span class="sxs-lookup"><span data-stu-id="97ddb-298">b.</span></span> <span data-ttu-id="97ddb-299">对于永久性更改，请以管理员角色启动 PowerShell 并一一运行以下命令：$CurrentValue = [Environment]：：GetEnvironmentVariable ("PSModulePath"， "Machine") SetEnvironmentVariable ("PSModulePath"， $CurrentValue + ";C：\Program Files\WindowsPowerShell\Modules"， "Machine") </span><span class="sxs-lookup"><span data-stu-id="97ddb-299">For persistent change, Start PowerShell as an Administrator and run the following commands, one by one: $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine") SetEnvironmentVariable("PSModulePath", $CurrentValue + "; C:\Program Files\WindowsPowerShell\Modules", "Machine")</span></span>

    
## <a name="install-windows-updates-manually"></a><span data-ttu-id="97ddb-300">手动安装 Windows 更新</span><span class="sxs-lookup"><span data-stu-id="97ddb-300">Install Windows updates manually</span></span>

<span data-ttu-id="97ddb-301">如果你不希望在你的环境中使用自动更新，请按照以下步骤手动检查并应用 Windows 更新。</span><span class="sxs-lookup"><span data-stu-id="97ddb-301">If you do not want to use automatic updates in your environment, follow these steps to manually check for and apply Windows updates.</span></span> <span data-ttu-id="97ddb-302">检查并安装 Windows 更新可能需要重新启动服务器。</span><span class="sxs-lookup"><span data-stu-id="97ddb-302">Checking for and installing Windows updates may require a server restart.</span></span> <span data-ttu-id="97ddb-303">当主机服务器重新启动时，用户将不能使用云连接器拨打或接听呼叫。</span><span class="sxs-lookup"><span data-stu-id="97ddb-303">When a host server is restarting, users will not be able to use Cloud Connector to place or receive calls.</span></span> <span data-ttu-id="97ddb-304">你可以手动检查并安装更新，以控制更新发生的时间，然后在选择的时间根据需要重新启动计算机以避免服务中断。</span><span class="sxs-lookup"><span data-stu-id="97ddb-304">You can manually check for and install updates to control when the updates take place, and then restart the machines as needed during times you choose to avoid disruption of services.</span></span>
  
<span data-ttu-id="97ddb-305">若要手动检查更新，请连接到每台主机服务器并打开 **控制面板**。</span><span class="sxs-lookup"><span data-stu-id="97ddb-305">To manually check for updates, connect to each host server and open the **Control Panel**.</span></span> <span data-ttu-id="97ddb-306">选择 **"系统和安全 \> Windows 更新**"，然后根据你的环境管理更新和服务器重新启动。</span><span class="sxs-lookup"><span data-stu-id="97ddb-306">Select **System and Security \>Windows Update**, and then manage the updates and server restarts as appropriate for your environment.</span></span>
  
- <span data-ttu-id="97ddb-307">如果站点中只有一个设备，请连接到每台虚拟机并打开 **控制面板**。</span><span class="sxs-lookup"><span data-stu-id="97ddb-307">If there is only one appliance in the site, connect to each virtual machine and open the **Control Panel**.</span></span> <span data-ttu-id="97ddb-308">选择 **"系统和安全 \> Windows 更新"，** 然后根据情况配置更新和服务器重新启动。</span><span class="sxs-lookup"><span data-stu-id="97ddb-308">Select **System and Security \>Windows Update**, and then configure the updates and server restarts as appropriate.</span></span>
    
- <span data-ttu-id="97ddb-309">如果站点中存在多个设备，则更新期间用户无法访问正在更新和重新启动的实例。</span><span class="sxs-lookup"><span data-stu-id="97ddb-309">If there are more than one appliance in the site, the instance being updated and restarted cannot be accessed by users during the updates.</span></span> <span data-ttu-id="97ddb-310">更新完成后，用户将连接到部署中的其他实例，直到所有虚拟机和所有 Skype for Business 服务在虚拟机上启动。</span><span class="sxs-lookup"><span data-stu-id="97ddb-310">Users will connect to other instances in the deployment until all virtual machines and all Skype for Business services start on the virtual machines after the updates are completed.</span></span> <span data-ttu-id="97ddb-311">为避免任何潜在的服务中断，可以在应用更新时从 HA 中删除实例，然后在完成后还原它。</span><span class="sxs-lookup"><span data-stu-id="97ddb-311">To avoid any potential disruption to service, you can remove the instance from HA while you apply the updates, and then restore it when complete.</span></span> <span data-ttu-id="97ddb-312">为此，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="97ddb-312">To do so:</span></span>
    
1. <span data-ttu-id="97ddb-313">在每台主机服务器上，以管理员角色打开 PowerShell 控制台。</span><span class="sxs-lookup"><span data-stu-id="97ddb-313">On each host server, open a PowerShell console as administrator.</span></span>
    
2. <span data-ttu-id="97ddb-314">通过以下 cmdlet 从 HA 中删除实例：</span><span class="sxs-lookup"><span data-stu-id="97ddb-314">Remove the instance from HA with the following cmdlet:</span></span>
    
   ```powershell
   Enter-CcUpdate
   ```

3. 
    
    <span data-ttu-id="97ddb-315">按照单个实例的步骤手动应用更新并重新启动虚拟机。</span><span class="sxs-lookup"><span data-stu-id="97ddb-315">Follow the steps for a single instance to manually apply the updates and restart the virtual machine.</span></span>
    
4. <span data-ttu-id="97ddb-316">通过以下 cmdlet 将实例设置回 HA：</span><span class="sxs-lookup"><span data-stu-id="97ddb-316">Set the instance back to HA with the following cmdlet:</span></span>
    
   ```powershell
   Exit-CcUpdate
   ```

<span data-ttu-id="97ddb-317">对于多站点部署，请按照部署中每个站点的单个站点的步骤操作，一次将更新应用到一个站点。</span><span class="sxs-lookup"><span data-stu-id="97ddb-317">For multi-site deployments, follow the steps for a single site for each site in the deployment, applying updates to one site at a time.</span></span>
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a><span data-ttu-id="97ddb-318">在云连接器主机计算机上安装防病毒软件的提示</span><span class="sxs-lookup"><span data-stu-id="97ddb-318">Tips when installing anti-virus software on the Cloud Connector host machine</span></span>

<span data-ttu-id="97ddb-319">如果需要在云连接器主机计算机上安装防病毒软件，需要添加以下排除项：</span><span class="sxs-lookup"><span data-stu-id="97ddb-319">If you need to install anti-virus software on the Cloud Connector host machine, you need to add the following exclusions:</span></span>
  
- <span data-ttu-id="97ddb-320">每台计算机的本地设备目录。</span><span class="sxs-lookup"><span data-stu-id="97ddb-320">Local Appliance Directory on each machine.</span></span>
    
- <span data-ttu-id="97ddb-321">每台计算机上都有远程站点目录。</span><span class="sxs-lookup"><span data-stu-id="97ddb-321">Remote Site Directory on each machine.</span></span>
    
- <span data-ttu-id="97ddb-322">计算机上本地网站目录托管共享网站根文件夹。</span><span class="sxs-lookup"><span data-stu-id="97ddb-322">Local Site Directory on the machine hosts the shared site root folder.</span></span>
    
- <span data-ttu-id="97ddb-323">%ProgramFiles%\Skype for Business 云连接器版本</span><span class="sxs-lookup"><span data-stu-id="97ddb-323">%ProgramFiles%\Skype for Business Cloud Connector Edition</span></span>
    
- <span data-ttu-id="97ddb-324">%ALLUSERSPROFILE%\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="97ddb-324">%ALLUSERSPROFILE%\CloudConnector</span></span>
    
- <span data-ttu-id="97ddb-325">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="97ddb-325">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span></span>
    
- <span data-ttu-id="97ddb-326">此过程Microsoft.Rtc.CCE.ManagementService.exe。</span><span class="sxs-lookup"><span data-stu-id="97ddb-326">The process Microsoft.Rtc.CCE.ManagementService.exe.</span></span>