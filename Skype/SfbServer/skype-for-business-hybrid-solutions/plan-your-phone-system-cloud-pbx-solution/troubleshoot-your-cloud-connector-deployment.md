---
title: 云连接器部署故障排除
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/5/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom:
- Strat_SB_Hybrid
- Strat_SB_Hybrid
ms.assetid: e6cf58cc-dbd9-4f35-a51a-3e2fea71b5a5
description: 解决您的云连接器版部署。
ms.openlocfilehash: 1fb4f65c0fefd335865c5babb0e69090ab824908
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a><span data-ttu-id="5a7d2-103">云连接器部署故障排除</span><span class="sxs-lookup"><span data-stu-id="5a7d2-103">Troubleshoot your Cloud Connector deployment</span></span>
 
<span data-ttu-id="5a7d2-104">解决您的云连接器版部署。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-104">Troubleshoot your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="5a7d2-p101">本主题介绍云连接器版本部署常见问题的解决方案。如果你在通过公用电话交换网 (PSTN) 拨打和接听电话时遇到问题，可以按照本主题中介绍的解决方案进行调查。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-p101">This topic describes solutions to common issues with Cloud Connector Edition deployments. If you are experiencing issues with calls to and from the Public Switched Telephone Network (PSTN), you can investigate by following the solutions described in this topic.</span></span>
  
<span data-ttu-id="5a7d2-107">云的连接器提供用于自动解决某些问题的内置机制。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-107">Cloud Connector provides built-in mechanisms for automatically resolving some issues.</span></span> <span data-ttu-id="5a7d2-108">自动检测进程与云接头装置中，寻找潜在的问题，并如有可能，采取纠正措施来解决这些问题，而不需要管理员干预。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-108">An automatic detection process looks for potential issues with the Cloud Connector appliances, and, if possible, takes corrective action to resolve those issues without the need for administrator intervention.</span></span> <span data-ttu-id="5a7d2-109">检测过程工作方式如下：</span><span class="sxs-lookup"><span data-stu-id="5a7d2-109">The detection process works as follows:</span></span>
  
- <span data-ttu-id="5a7d2-110">**检测序列：**云连接器管理服务运行过程每隔 60 秒来检测装置是否已关闭。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-110">**Detection sequence:** The Cloud Connector Management service runs a process every 60 seconds for detecting whether an appliance is down.</span></span> <span data-ttu-id="5a7d2-111">在云连接器 2.0 及更高版本中，检测过程使用 Skype 业务企业网络交换机进行 PowerShell 连接到云接头机;对于 2.0 之前的版本，检测过程使用云连接器管理交换机。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-111">In Cloud Connector version 2.0 and later, the detection process uses the Skype for Business Corpnet switch for making PowerShell connections to the Cloud Connector machines; for versions previous to 2.0, the detection process uses the Cloud Connector management switch.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5a7d2-112">自动恢复为取得成功，必须有虚拟机与主机之间的网络连接主机网络交换机上。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-112">For automatic recovery to succeed, there must be network connectivity between the host and virtual machines over the host network switch.</span></span> <span data-ttu-id="5a7d2-113">一定要检查网络连接，以确保该自动检测和恢复可能会成功。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-113">Be sure to check network connectivity to ensure that automatic detection and recovery can succeed.</span></span> 
  
- <span data-ttu-id="5a7d2-114">**监控：**在云连接器 2.0 及更高版本中监视以下服务：</span><span class="sxs-lookup"><span data-stu-id="5a7d2-114">**Monitoring:** The following services are monitored in Cloud Connector version 2.0 and later:</span></span>
    
  - <span data-ttu-id="5a7d2-115">虚拟机未连接到云连接器公司或 Internet 虚拟交换机</span><span class="sxs-lookup"><span data-stu-id="5a7d2-115">Virtual Machines are not connected to the Cloud Connector Corporate or Internet virtual switches</span></span>
    
  - <span data-ttu-id="5a7d2-116">虚拟机处于已保存或已停止的状态</span><span class="sxs-lookup"><span data-stu-id="5a7d2-116">Virtual Machines are in a saved or stopped status</span></span>
    
  - <span data-ttu-id="5a7d2-117">中央管理服务器服务： 副本、 母版</span><span class="sxs-lookup"><span data-stu-id="5a7d2-117">Central Management Server services: REPLICA, MASTER</span></span>
    
  - <span data-ttu-id="5a7d2-118">中介服务器服务： 副本、 RTCSRV 和 MEDSVC</span><span class="sxs-lookup"><span data-stu-id="5a7d2-118">Mediation Server services: REPLICA, RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="5a7d2-119">边缘服务器服务： 副本、 RTCSRV、 RTCDATAPROXY、 RTCMRAUTH、 RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="5a7d2-119">Edge Server services: REPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY</span></span>
    
  - <span data-ttu-id="5a7d2-120">入站的防火墙规则在边缘服务器上，CS RTCMEDSRV 中介服务器上禁用 CS RTCSRV</span><span class="sxs-lookup"><span data-stu-id="5a7d2-120">Inbound firewall rules are disabled for CS RTCSRV on Edge server, CS RTCMEDSRV on Mediation server</span></span>
    
    <span data-ttu-id="5a7d2-121">在云接头 1.4.2 版，监视仅以下服务：</span><span class="sxs-lookup"><span data-stu-id="5a7d2-121">In Cloud Connector version 1.4.2, only the following services are monitored:</span></span>
    
  - <span data-ttu-id="5a7d2-122">中介服务器服务： RTCSRV 和 MEDSVC</span><span class="sxs-lookup"><span data-stu-id="5a7d2-122">Mediation Server services: RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="5a7d2-123">边缘服务器服务： RTCSRV</span><span class="sxs-lookup"><span data-stu-id="5a7d2-123">Edge Server service: RTCSRV</span></span>
    
- <span data-ttu-id="5a7d2-124">**恢复过程：**如果任何被监视的服务下，装置将被标记为关闭，和服务被停止并标记为手动，直到就可以解决所有的问题。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-124">**Recovery process:** If any monitored services are down, an appliance is marked down, and services are stopped and marked manual until all issues can be resolved.</span></span> <span data-ttu-id="5a7d2-125">这将会阻止调用路由到装置，可能会导致调用失败。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-125">This will prevent calls from routing to an appliance that may cause call failures.</span></span>
    
    <span data-ttu-id="5a7d2-126">该云连接器管理服务，如下所示将重试自动恢复</span><span class="sxs-lookup"><span data-stu-id="5a7d2-126">The Cloud Connector Management service will retry automatic recovery as follows</span></span>
    
  - <span data-ttu-id="5a7d2-127">初始的重试间隔是每十秒，最大间隔时间为一小时。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-127">The initial retry interval is every ten seconds with a maximum interval time of one hour.</span></span>
    
  - <span data-ttu-id="5a7d2-128">对于前三个故障恢复尝试的间隔时间为 10 秒。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-128">For the first three recovery attempts, the interval time is 10 seconds.</span></span> <span data-ttu-id="5a7d2-129">从第四重试，间隔时间将增加执行前一个时间间隔时间的两倍。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-129">Starting from the fourth retry, the interval time increases by two times the previous interval time.</span></span> <span data-ttu-id="5a7d2-130">例如，第四重试将在 20 秒钟内，在 40 秒内，第五个发生等等。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-130">For example, the fourth retry will occur in 20 seconds, the fifth in 40 seconds, and so on.</span></span> 
    
  - <span data-ttu-id="5a7d2-131">达到最大间隔时间在一个小时后，重试将继续每小时一次。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-131">When the maximum interval time of one hour is reached, retries will continue once per hour.</span></span>
    
  - <span data-ttu-id="5a7d2-132">成功恢复时，时间间隔，然后重试计数设置为它们的初始值。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-132">When recovery is successful, the interval and retry counts are set to their initial values.</span></span>
    
  - <span data-ttu-id="5a7d2-133">管理服务重新启动时，如果时间间隔，然后重试计数被重置为其初始值。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-133">If the Management service is restarted, the interval and retry counts are reset to their initial values.</span></span>
    
## <a name="troubleshooting"></a><span data-ttu-id="5a7d2-134">疑难解答</span><span class="sxs-lookup"><span data-stu-id="5a7d2-134">Troubleshooting</span></span>

<span data-ttu-id="5a7d2-135">下面是通常遇到的问题的解决方案：</span><span class="sxs-lookup"><span data-stu-id="5a7d2-135">Following are solutions to commonly encountered issues:</span></span>
  
- <span data-ttu-id="5a7d2-136">**问题：运行部署脚本时部署失败或停止响应。登录每个虚拟机后，管理/内部/外部 NIC 的 IP 地址缺失或不正确。**</span><span class="sxs-lookup"><span data-stu-id="5a7d2-136">**Issue: Deployment fails or stops responding when running the deployment scripts. After logging on to each VM, the IP address is missing or incorrect for the Management/Internal/External NIC.**</span></span>
    
    <span data-ttu-id="5a7d2-137">**解决方案：**不能自动解决该问题。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-137">**Resolution:** This issue cannot be resolved automatically.</span></span> <span data-ttu-id="5a7d2-138">在运行时，无法将 Nic 添加到虚拟机。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-138">NICs cannot be added to VMs while they are running.</span></span> <span data-ttu-id="5a7d2-139">请关闭并在超 v 管理器中，删除这些虚拟机，然后运行以下 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="5a7d2-139">Please shut down and remove these VMs in hyper-v manager, then run the following cmdlets:</span></span>
    
  ```
  Uninstall-CcAppliance
  ```

  ```
  Install-CcAppliance
  ```

- 
    
    <span data-ttu-id="5a7d2-140">**问题： 安装在活动目录服务器和林后，CMS 服务器和/或中介服务器未加入域正确。**</span><span class="sxs-lookup"><span data-stu-id="5a7d2-140">**Issue: After the Active Directory Server and forest are installed, the CMS Server and/or Mediation Server did not join the domain correctly.**</span></span>
    
    <span data-ttu-id="5a7d2-141">**解决方法：**要解决此问题，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="5a7d2-141">**Resolution:** To resolve this issue, take the following steps:</span></span>
    
  - <span data-ttu-id="5a7d2-142">登录 Active Directory 服务器并验证是否已正确创建域。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-142">Log on to the Active Directory Server and verify that the domain was created correctly.</span></span>
    
  - <span data-ttu-id="5a7d2-143">登录 CMS/中介服务器，并验证公司网络 NIC 上是否分配了有效的 IP 地址，以及是否将有效的静态 IP 和 DNS 配置为 AD 服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-143">Log on to the CMS/Mediation Server and verify that on the corpnet NIC a valid IP address is assigned, and that valid static IP and DNS is configured as the AD server's IP address.</span></span>
    
  - <span data-ttu-id="5a7d2-144">登录到 CMS/中介服务器，然后打开一个命令提示符。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-144">Log on to the CMS/Mediation Server, and open a command prompt.</span></span> <span data-ttu-id="5a7d2-145">请确保您可以 ping 活动目录服务器的 FQDN 和 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-145">Make sure you can ping the FQDN and IP address of the Active Directory Server.</span></span> <span data-ttu-id="5a7d2-146">如果不能则表明可能存在 IP 地址冲突。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-146">If you cannot, there may be an IP address conflict.</span></span> <span data-ttu-id="5a7d2-147">请尝试为 Active Directory 中分配新的 IP，并相应地更新 CMS/中介服务器上的 DNS。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-147">Please try to assign a new IP for Active Directory and update DNS on the CMS/Mediation server accordingly.</span></span>
    
- <span data-ttu-id="5a7d2-148">**问题： 您收到下面的错误消息，"删除 VMSwitch： 在删除虚拟以太网交换机时失败。云连接器管理交换机虚拟交换机无法删除，因为它正由运行的虚拟机或分配给子池。"**</span><span class="sxs-lookup"><span data-stu-id="5a7d2-148">**Issue: You receive the following error message, "Remove-VMSwitch : Failed while removing virtual Ethernet switch. The virtual switch 'Cloud Connector Management Switch' cannot be deleted because it is being used by running virtual machines or assigned to child pools."**</span></span>
    
    <span data-ttu-id="5a7d2-149">**解决方案：**"云连接器管理开关"在部署后未被删除。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-149">**Resolution:** The "Cloud Connector Management Switch" was not deleted after the deployment.</span></span> <span data-ttu-id="5a7d2-150">如果遇到此错误，请转到 hyper-v 管理器，并验证是否存在不仍然仍然连接到该虚拟机。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-150">If you hit this error, please go to Hyper-v manager and verify that there is not still a virtual machine still connected to it.</span></span> <span data-ttu-id="5a7d2-151">如果有仍然保持连接的虚拟机，请断开它们的连接并删除管理交换机。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-151">If there are virtual machines still connected, disconnect them and delete the management switch.</span></span> <span data-ttu-id="5a7d2-152">如果仍然无法删除管理交换机，请重新启动主机服务器，然后重试。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-152">If the management switch still cannot be deleted, restart the host server and try again.</span></span>
    
- <span data-ttu-id="5a7d2-153">**问题： 您收到下面的错误消息、"RTCMRAUTH 服务无法启动。请检查以确保未禁用该服务。**</span><span class="sxs-lookup"><span data-stu-id="5a7d2-153">**Issue: You receive the following error message, "Service RTCMRAUTH failed to start. Check to make sure the service is not disabled."**</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5a7d2-154">此问题仅适用于云连接器版本早于 1.4.2。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-154">This issue only applies to Cloud Connector versions earlier than 1.4.2.</span></span> 
  
    <span data-ttu-id="5a7d2-p110">无法启动也可能是因为此前端服务器之前经过故障转移（使用计算机故障转移）。如果是这种情况，请调用故障回复（使用计算机故障回复）。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-p110">The failure to start could also be because this Front End server was previously failed over (using computer fail over). If that's the case, please invoke fail back (using computer fail back).</span></span>
    
    <span data-ttu-id="5a7d2-p111">**解决方法：**当边缘服务器不信任根 CA 证书或中间 CA 证书时，边缘服务器上会出现此问题。即使可以导入外部证书，但证书链已损坏。在这种情况下，RTCMRAUTH 和/或 RTCSRV 服务无法启动。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-p111">**Resolution:** This issue happens on an Edge Server when the root CA certificate or intermediate CA certificate is not trusted by the Edge Server. Even if the external certificate can be imported but the certificate chain is broken. Under this condition, the RTCMRAUTH and/or RTCSRV service can not start.</span></span>
    
    <span data-ttu-id="5a7d2-p112">请手动将外部证书的根 CA 证书和所有中间 CA 证书导入到边缘服务器，然后重新启动边缘服务器。看到 RTCMRAUTH 和 RTCSRV 服务在边缘服务器上启动之后，返回到主机服务器，以管理员身份启动 PowerShell 控制台，并运行以下 cmdlet 以便切换到新部署：</span><span class="sxs-lookup"><span data-stu-id="5a7d2-p112">Please import the root CA certificate and all intermediate CA certificates of your external certificate manually into the Edge Server and then restart the Edge Server. After you see the RTCMRAUTH and RTCSRV services started on the Edge Server, go back to your host server, launch a PowerShell console as administrator, and run following cmdlet to switch to the new deployment:</span></span>
    
  ```
  Switch-CcVersion
  ```

- 
    
    <span data-ttu-id="5a7d2-162">**问题：应用 Windows 更新时主机服务器重新启动，由此服务器支持的调用失败。**</span><span class="sxs-lookup"><span data-stu-id="5a7d2-162">**Issue: The host server was restarted when Windows updates were applied, and calls serviced by the server are failing.**</span></span>
    
    <span data-ttu-id="5a7d2-163">**解决方案：**如果您部署高可用性环境，Microsoft 提供的 cmdlet 来帮助移动一台宿主机器 （部署实例） 或当前拓扑时检查并手动安装 Windows 更新。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-163">**Resolution:** If you deployed a high availability environment, Microsoft provides a cmdlet to help move one host machine (deployment instance) into or out of the current topology when you check and install Windows update manually.</span></span> <span data-ttu-id="5a7d2-164">使用以下步骤完成此操作：</span><span class="sxs-lookup"><span data-stu-id="5a7d2-164">Use the following steps to accomplish this:</span></span>
    
1. <span data-ttu-id="5a7d2-165">在主机服务器上，以管理员身份启动 PowerShell 控制台，然后运行：</span><span class="sxs-lookup"><span data-stu-id="5a7d2-165">On the host server, start a PowerShell console as administrator, then run:</span></span>
    
  ```
  Enter-CcUpdate
  ```

2. <span data-ttu-id="5a7d2-166">检查更新并安装所有可用更新。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-166">Check for updates and install any that are available.</span></span>
    
3. <span data-ttu-id="5a7d2-167">在 PowerShell 控制台中，运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="5a7d2-167">In the PowerShell console, run the following cmdlet:</span></span>
    
  ```
  Exit-CcUpdate
  ```

- 
    
    <span data-ttu-id="5a7d2-168">**问题：使用 PSTN 号码从 Skype for Business 客户端进行呼叫时，无法通过邀请其他 PSTN 号码将该呼叫提升为会议。**</span><span class="sxs-lookup"><span data-stu-id="5a7d2-168">**Issue: When a call is made from a Skype for Business client using a PSTN number, the call cannot be escalated to a conference by inviting another PSTN number.**</span></span>
    
    <span data-ttu-id="5a7d2-169">**解决方案：**若要解决此问题，请参阅[配置在线混合中介服务器设置](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer)。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-169">**Resolution:** To resolve this issue, see [Configure online hybrid Mediation Server Settings](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).</span></span>
    
- <span data-ttu-id="5a7d2-170">**问题：安装 Active Directory 服务器时，显示关于 Windows 更新的警告消息 -“未启用 Windows 自动更新。为确保新安装的角色或功能将自动更新，请启用 Windows 更新。”**</span><span class="sxs-lookup"><span data-stu-id="5a7d2-170">**Issue: A warning message is displayed about Windows Update when you are installing Active Directory server - "Windows automatic updating is not enabled. To ensure that your newly-installed role or feature is automatically updated, turn on Windows Update."**</span></span>
    
    <span data-ttu-id="5a7d2-171">**解决方案：**启动业务租户管理凭据，使用 Skype 的租户远程 PowerShell 会话，然后运行以下 cmdlet 以检查您的网站的_EnableAutoUpdate_配置：</span><span class="sxs-lookup"><span data-stu-id="5a7d2-171">**Resolution:** Launch a Tenant Remote PowerShell session using Skype for Business tenant admin credentials, then run the following cmdlet to check the _EnableAutoUpdate_ configuration of your site:</span></span>
    
  ```
  Get-CsHybridPSTNSite
  ```

    <span data-ttu-id="5a7d2-172">如果_EnableAutoUpdate_设置为**True**时，可以安全地忽略此警告消息，因为下载和安装 Windows 更新虚拟机及其主机服务器将处理的 CCEManagement 服务。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-172">If  _EnableAutoUpdate_ is set to **True**, you can safely ignore this warning message because the CCEManagement service will handle downloading and installing Windows updates for both virtual machines and the host server.</span></span> <span data-ttu-id="5a7d2-173">如果_EnableAutoUpdate_设置为**False**，则运行以下 cmdlet 将其设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-173">If  _EnableAutoUpdate_ is set to **False**, run following cmdlet to set it to **True**.</span></span>
    
  ```
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    <span data-ttu-id="5a7d2-p115">此外，你还可以手动检查并安装更新。请参阅下节内容。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-p115">Alternatively, you can manually check for and install updates. See the next section.</span></span>
    
- <span data-ttu-id="5a7d2-176">**问题： 您收到的错误消息： 无法注册装置，因为每个配置当前的输入\<网站名称\>或\<装置名称\>或\<中介服务器 FQDN\>或\<中介服务器的 IP 地址\>现有装置与冲突。删除冲突装置或更新您输入/配置的信息，然后重新注册。运行时注册的 CcAppliance 注册当前装置为联机。**</span><span class="sxs-lookup"><span data-stu-id="5a7d2-176">**Issue: You receive an error message: Cannot register appliance because your current input/configuration \<SiteName\> or \<ApplianceName\> or \<Mediation Server FQDN\> or \<Mediation Server IP Address\> conflicts with existing appliance(s). Remove conflict appliance or update your input/configuration information then register again. ' when run Register-CcAppliance to register current appliance to online.**</span></span>
    
    <span data-ttu-id="5a7d2-177">**解决方案：**值为\<装置名称\>，\<中介服务器 FQDN\>和\<中介服务器的 IP 地址\>必须是唯一的并且只用于一个装置登记。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-177">**Resolution:** Values for the \<ApplianceName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> must be unique and only used for one appliance registration.</span></span> <span data-ttu-id="5a7d2-178">默认情况下，\<装置名称\>来自主机名。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-178">By default, \<ApplianceName\> comes from the host name.</span></span> <span data-ttu-id="5a7d2-179">\<中介服务器 FQDN\>和\<中介服务器的 IP 地址\>配置 ini 文件中定义。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-179">\<Mediation Server FQDN\> and \<Mediation Server IP Address\> defined in configuration ini file.</span></span>
    
    <span data-ttu-id="5a7d2-180">例如，使用 (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) 来注册 SiteName=MySite 时，如果存在已注册设备 (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10)，则会出现冲突。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-180">For example, using (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) to register to SiteName=MySite, but if there is a registered appliance (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10), you will have the conflict.</span></span>
    
    <span data-ttu-id="5a7d2-181">首先，请检查 ApplianceRoot 目录部分中的 CloudConnector.ini 文件。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-181">First, please check your CloudConnector.ini file in ApplianceRoot directory section.</span></span> <span data-ttu-id="5a7d2-182">您将获得\<网站名称\>，\<中介服务器 FQDN\>和\<中介服务器的 IP 地址\>文件中的值。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-182">You will get \<SiteName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> values in the file.</span></span> <span data-ttu-id="5a7d2-183">\<装置名称\>是您主机的服务器名称。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-183">\<ApplianceName\> is your host server name.</span></span>
    
    <span data-ttu-id="5a7d2-184">第二，启动租户远程 PowerShell 您 Skype 用于商业租户管理员凭据，然后运行以下 cmdlet 来检查已注册的装置。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-184">Second, Launch Tenant Remote PowerShell using your Skype for Business tenant admin credentials, then run the following cmdlet to check the registered appliance(s).</span></span>
    
  ```
  Get-CsHybridPSTNAppliance
  ```

    <span data-ttu-id="5a7d2-185">确定任何冲突后，可以使用与已注册设备匹配的信息更新 CloudConnector.ini 文件，或注销现有设备以解决冲突。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-185">After identifying any conflicts, you can either update your CloudConnector.ini file with information that matches the registered appliance, or unregister the existing appliance to resolve the conflicts.</span></span>
    
  ```
  Unregister-CsHybridPSTNAppliance -Force
  ```

- 
    
    <span data-ttu-id="5a7d2-186">**问题： 如果主机上运行的部署的装置，获取 CcRunningVersion cmdlet 返回空值。**</span><span class="sxs-lookup"><span data-stu-id="5a7d2-186">**Issue: The Get-CcRunningVersion cmdlet returns an empty value if there is a deployed appliance running on the host.**</span></span>
    
    <span data-ttu-id="5a7d2-p118">**解决方法：**从 1.3.4 或 1.3.8 升级到 1.4.1 之后，可能会出现此情况。使用 .msi 安装 1.4.1 版之后，必须先运行 `Register-CcAppliance`，才能运行任何其他 cmdlet。`Register-CcAppliance` 会将 module.ini 文件从 %UserProfile%\CloudConnector 迁移到 %ProgramData%\CloudConnector。如果你没有运行此 cmdlet，将会在 %ProgramData%\CloudConnector 文件夹中创建一个新的 module.ini 文件，并替换 1.3.4 或 1.3.8 的运行/备份版本信息。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-p118">**Resolution:** This can happen when you upgrade from 1.3.4 or 1.3.8 to 1.4.1. After you install version 1.4.1 with the .msi, you must run `Register-CcAppliance` before you run any other cmdlet. `Register-CcAppliance` will migrate the module.ini file from %UserProfile%\CloudConnector to %ProgramData%\CloudConnector. If you missed it, a new module.ini will be created in %ProgramData%\CloudConnector folder and replace the running/backup version information for 1.3.4 or 1.3.8.</span></span>
    
    <span data-ttu-id="5a7d2-191">比较 %UserProfile%\CloudConnector 和 %ProgramData%\CloudConnector 文件夹中的 module.ini 文件。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-191">Compare module.ini files in %UserProfile%\CloudConnector and %ProgramData%\CloudConnector folder.</span></span> <span data-ttu-id="5a7d2-192">如果有差异，删除在 %ProgramData%\CloudConnector 和重新运行 module.ini 文件`Register-CcAppliance`。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-192">If there are differences, delete the module.ini file in %ProgramData%\CloudConnector and rerun  `Register-CcAppliance`.</span></span> <span data-ttu-id="5a7d2-193">您还可以修改文件手动的正确运行和备份版本。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-193">You could also modify the file manually to the correct running and backup version.</span></span>
    
- <span data-ttu-id="5a7d2-194">**问题： 开关 CcVersion 用于切换到旧版本不同于当前的脚本版本，运行后，没有高可用性支持此旧版本。**</span><span class="sxs-lookup"><span data-stu-id="5a7d2-194">**Issue: After you run the Switch-CcVersion cmdlet to switch to an old version which is different from current script version, there is no High Availability support for this old version.**</span></span>
    
    <span data-ttu-id="5a7d2-195">**解决方案：**例如，您已从 1.4.1 升级到 1.4.2。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-195">**Resolution:** For example, you have upgraded from 1.4.1 to 1.4.2.</span></span> <span data-ttu-id="5a7d2-196">您当前的脚本版本，可以确定通过运行`Get-CcVersion`，和您正在运行的版本，可由运行`Get-CcRunningVersion`是两个 1.4.2。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-196">Your current script version, which can be determined by running `Get-CcVersion`, and your running version, which can be determined by running  `Get-CcRunningVersion` are both 1.4.2.</span></span> <span data-ttu-id="5a7d2-197">此时，如果您运行`Switch-CcVersion`回到运行版本 1.4.1，然后会有这个旧的版本没有高可用性支持。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-197">At this time, if you run `Switch-CcVersion` to switch the running version back to 1.4.1, then there will be no High Availability support for this old version.</span></span>
    
    <span data-ttu-id="5a7d2-p121">要获得完整的高可用性支持，请切换回 1.4.2，从而使运行版本和脚本版本相同。如果 1.4.2 部署出现问题，请尽快将其卸载并重新安装。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-p121">To get full High Availability support, please switch back to 1.4.2, so the running version and script version are the same. If you are experiencing problems with your 1.4.2 deployment, please uninstall and reinstall it as soon as possible.</span></span>
    
- <span data-ttu-id="5a7d2-200">**问题：证书颁发机构证书或颁发给中央管理存储、中介服务器和边缘服务器的内部证书即将过期或已损坏。**</span><span class="sxs-lookup"><span data-stu-id="5a7d2-200">**Issue: Certificate authority certificates or internal certificates issued to Central Management Store, Mediation Server, and Edge Server are near expiration or are compromised.**</span></span>
    
    <span data-ttu-id="5a7d2-p122">**解决方法：**Skype for Business 证书颁发机构证书有效期为 5 年。颁发给中央管理存储、中介服务器和边缘服务器的内部证书有效期为 2 年。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-p122">**Resolution:** Skype for Business certification authority certificates are valid for five years. Internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5a7d2-203">在云接头 2.0 及更高版本，更新 CcServerCertificate cmdlet 已更改为更新 CcServerCertificate 并更新 CcCACertificate cmdlet 已更改为更新 CcCACertificate。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-203">In Cloud Connector version 2.0 and later, the Renew-CcServerCertificate cmdlet has changed to Update-CcServerCertificate and the Renew-CcCACertificate cmdlet has changed to Update-CcCACertificate.</span></span> 
  
    <span data-ttu-id="5a7d2-204">如果内部证书颁发给中央管理存储、 中介服务器和边缘服务器临近到期或泄露，运行更新 CcServerCertificate 或者更新 CcServerCertificate cmdlet 续订证书。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-204">If internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are near expiration or compromised, run the Renew-CcServerCertificate or Update-CcServerCertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="5a7d2-205">如果证书颁发机构证书过期附近，运行更新 CcCACertificate 或更新 CcCACertificate cmdlet 来续订证书。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-205">If certification authority certificates are near expiration, run the Renew-CcCACertificate or Update-CcCACertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="5a7d2-206">**如果证书颁发机构证书也不怕，并且只有一个装置在站点，**请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="5a7d2-206">**If certification authority certificates are compromised and there is only one appliance in the site,** perform the following steps:</span></span>
    
1. <span data-ttu-id="5a7d2-207">运行输入 CcUpdate cmdlet 耗尽服务并将该装置放入维护模式。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-207">Run the Enter-CcUpdate cmdlet to drain services and put the appliance in maintenance mode.</span></span>
    
2. <span data-ttu-id="5a7d2-208">运行以下 cmdlet 以重置证书颁发机构证书和所有内部服务器证书并创建相应的新证书：</span><span class="sxs-lookup"><span data-stu-id="5a7d2-208">Run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
    <span data-ttu-id="5a7d2-209">对于云连接器 2.0 之前的版本：</span><span class="sxs-lookup"><span data-stu-id="5a7d2-209">For Cloud Connector releases before 2.0:</span></span>
    
  ```
  Reset-CcCACertificate 
Renew-CcServerCertificate 
Remove-CcLegacyServerCertificate 

  ```

    <span data-ttu-id="5a7d2-210">或云连接器版本 2.0 及更高版本：</span><span class="sxs-lookup"><span data-stu-id="5a7d2-210">Or for Cloud Connector release 2.0 and later:</span></span>
    
  ```
  Reset-CcCACertificate 
Update-CcServerCertificate 
Remove-CcLegacyServerCertificate 

  ```

3. <span data-ttu-id="5a7d2-211">运行启动服务退出 CcUpdate cmdlet 和退出维护模式。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-211">Run the Exit-CcUpdate cmdlet to start services and and exit maintenance mode.</span></span>
    
4. <span data-ttu-id="5a7d2-212">的装置中的本地文件上运行导出 CcRootCertificate cmdlet 然后复制并将导出的证书安装到您的 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-212">Run the Export-CcRootCertificate cmdlet on the local file in the appliance, and then copy and install the exported certificate to your PSTN gateways.</span></span>
    
    <span data-ttu-id="5a7d2-213">**如果证书颁发机构证书被泄露，有多个装置在站点，**站点中的每个装置上执行以下顺序步骤。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-213">**If certification authority certificates are compromised and there are multiple appliances in the site,** perform the following sequential steps on each appliance in the site.</span></span>
    
    <span data-ttu-id="5a7d2-214">Microsoft 建议您在非高峰使用时间段执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-214">Microsoft recommends that you perform these steps during non-peak usage times.</span></span>
    
  - <span data-ttu-id="5a7d2-215">第一个应用装置，在运行用于清理 CA 备份中的文件，然后删除 CcCertificationAuthorityFile \<SiteRoot\>目录。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-215">On the first appliance, run the Remove-CcCertificationAuthorityFile cmdlet to clean up the CA backup files in the \<SiteRoot\> directory.</span></span>
    
  - <span data-ttu-id="5a7d2-216">运行输入 CcUpdate 用于数据包服务，每个装置置于维护模式。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-216">Run the Enter-CcUpdate cmdlet to drain services and put each appliance in maintenance mode.</span></span>
    
  - <span data-ttu-id="5a7d2-217">运行以下 cmdlet 以重置证书颁发机构证书和所有内部服务器证书并创建相应的新证书：</span><span class="sxs-lookup"><span data-stu-id="5a7d2-217">Run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
    <span data-ttu-id="5a7d2-218">对于云连接器 2.0 之前的版本：</span><span class="sxs-lookup"><span data-stu-id="5a7d2-218">For Cloud Connector releases before 2.0:</span></span>
    
  ```
  Reset-CcCACertificate
Renew-CcServerCertificate
Remove-CcLegacyServerCertificate 

  ```

    <span data-ttu-id="5a7d2-219">或云连接器版本 2.0 及更高版本：</span><span class="sxs-lookup"><span data-stu-id="5a7d2-219">Or for Cloud Connector release 2.0 and later:</span></span>
    
  ```
  Reset-CcCACertificate
Update-CcServerCertificate
Remove-CcLegacyServerCertificate 

  ```

  - <span data-ttu-id="5a7d2-220">在第一个应用装置，运行以下 cmdlet 来备份 CA 文件\<SiteRoot\>文件夹。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-220">On the first appliance, run the following cmdlet to back up the CA files to the \<SiteRoot\> folder.</span></span> <span data-ttu-id="5a7d2-221">以后，在同一站点中的所有其他装置，重置 CcCACertificate cmdlet 将自动使用 CA 备份文件，装置将使用相同的根证书。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-221">Later, on all other appliances in the same site, the Reset-CcCACertificate cmdlet will consume the CA backup files automatically and appliances will use the same root certificate.</span></span>
    
  ```
  Backup-CcCertificationAuthority
  ```

  - <span data-ttu-id="5a7d2-222">运行该退出 CcUpdate cmdlet 以启动服务并退出维护模式。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-222">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span> 
    
  - <span data-ttu-id="5a7d2-223">如果网关和中介服务器之间使用 TLS，则从网站中的任意设备上运行导出 CcRootCertificate cmdlet，然后将导出的证书安装到您的 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-223">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from any appliance in the site, and then install the exported certificate to your PSTN gateways.</span></span> 
    
- <span data-ttu-id="5a7d2-224">**问题： 您在云中连接器管理服务日志"C:\Program Files\Skype 的业务云连接器 Edition\ManagementService\CceManagementService.log"中收到下面的错误消息： 错误 CceService: 0： 意外的异常时向联机报告状态： System.Management.Automation.CmdletInvocationException： 登录失败的用户\<全局租户管理\>。请创建新的凭据对象，并确保使用正确的用户名称和密码。---\>**</span><span class="sxs-lookup"><span data-stu-id="5a7d2-224">**Issue: You receive the following error message in the Cloud Connector Management Service Log, "C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": CceService Error: 0 : Unexpected exception when reporting status to online: System.Management.Automation.CmdletInvocationException: Logon failed for the user \<Global Tenant Admin\>. Please create a new credential object, making sure that you have used the correct user name and password. ---\>**</span></span>
    
    <span data-ttu-id="5a7d2-225">**解决方案：**因为云接头装置已注册 Office 365 全局租户管理员凭据已更改。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-225">**Resolution:** The Office 365 global tenant admin credentials have been changed since the Cloud Connector appliance was registered.</span></span> <span data-ttu-id="5a7d2-226">要更新云接头装置上本地存储的凭据，请运行以下命令从管理员 PowerShell 主机设备上：</span><span class="sxs-lookup"><span data-stu-id="5a7d2-226">To update the locally stored credentials on the Cloud Connector appliance, run the following from Administrator PowerShell on the host appliance:</span></span>
    
  ```
  Set-CcCredential -AccountType TenantAdmin
  ```

- 
    
    <span data-ttu-id="5a7d2-227">**问题： 您更改用来部署主机服务器帐户的密码后，您收到以下错误消息:"ConvertTo SecureString： 指定用于无效的键状态。"在 %ProgramFiles%\Skype 业务云连接器Edition\ManagementService\CceManagementService.log 或同时运行 Get CcCredential cmdlet。**</span><span class="sxs-lookup"><span data-stu-id="5a7d2-227">**Issue: After you change the password for the host server account you used for the deployment, you receive the following error message: "ConvertTo-SecureString : Key not valid for use in specified state." in %ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log or while running the Get-CcCredential cmdlet.**</span></span>
    
    <span data-ttu-id="5a7d2-228">**解决方案：**所有的云连接器凭据存储在下列文件:"%systemdrive%\programdata\cloudconnector\credentials。\<CurrentUser\>.xml"。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-228">**Resolution:** All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="5a7d2-229">在主机服务器上的密码更改时，您将需要更新本地存储的凭据。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-229">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
    
    <span data-ttu-id="5a7d2-230">**如果您正在运行云连接器版本 1.4.2，**再生云连接器的所有密码通过执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="5a7d2-230">**If you are running Cloud Connector version 1.4.2,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
1. <span data-ttu-id="5a7d2-231">重新启动主机服务器。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-231">Restart the host server.</span></span>
    
2. <span data-ttu-id="5a7d2-232">删除以下文件:"%systemdrive%\programdata\cloudconnector\credentials。\<CurrentUser\>.xml"。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-232">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
3. <span data-ttu-id="5a7d2-233">启动作为管理员，PowerShell 控制台，然后运行"登记 CcAppliance-本地"以重新输入描述的密码。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-233">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="5a7d2-234">输入云连接器部署之前输入的相同密码。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-234">Enter the same passwords you entered before for the Cloud Connector deployment.</span></span>
    
    <span data-ttu-id="5a7d2-235">**如果您正在运行云连接器 2.0 版或更高版本，**请按照下面的步骤再生云连接器的所有密码：</span><span class="sxs-lookup"><span data-stu-id="5a7d2-235">**If you are running Cloud Connector version 2.0 or later,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
1. <span data-ttu-id="5a7d2-236">重新启动主机服务器。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-236">Restart the host server.</span></span>
    
2. <span data-ttu-id="5a7d2-237">删除以下文件:"%systemdrive%\programdata\cloudconnector\credentials。\<CurrentUser\>.xml"。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-237">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" .</span></span>
    
3. <span data-ttu-id="5a7d2-238">启动作为管理员，PowerShell 控制台，然后运行"登记 CcAppliance-本地"以重新输入描述的密码。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-238">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> 
    
    <span data-ttu-id="5a7d2-p127">如果缓存的密码文件是用云连接器 1.4.2 版生成的，请在系统提示时将 VMAdmin 密码用作 CceService 密码。输入之前用于云连接器部署的所有其他帐户的相同密码。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-p127">If the cached password file was generated with Cloud Connector version 1.4.2, use the VMAdmin password for the CceService password when prompted. Enter the same password you entered before for the Cloud Connector deployment for all other accounts.</span></span>
    
    <span data-ttu-id="5a7d2-241">如果缓存的密码文件是用云连接器 1.4.2 版生成的，并且 DomainAdmin 和 VMAdmin 密码不同，则必须执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="5a7d2-241">If the cached password file was generated with Cloud Connector version 1.4.2 and the DomainAdmin and VMAdmin passwords are different, you must perform the following steps:</span></span>
    
1. <span data-ttu-id="5a7d2-242">按如下所述运行 Set-CcCredential -AccountType DomainAdmin：</span><span class="sxs-lookup"><span data-stu-id="5a7d2-242">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
1. <span data-ttu-id="5a7d2-243">当系统提示输入旧帐户凭据时，请输入用于 CceService 密码的凭据。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-243">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
2. <span data-ttu-id="5a7d2-244">当系统提示输入新帐户凭据时，请输入之前用于 DomainAdmin 密码的密码。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-244">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
    <span data-ttu-id="5a7d2-245">如果缓存的密码文件生成云接头 2.0 版或更高版本中，默认情况下，VmAdmin 和 DomainAdmin CceService 为使用相同的密码。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-245">If the cached password file was generated with Cloud Connector version 2.0 or later, by default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="5a7d2-246">如果您更改了 DomainAdmin 和 VMAdmin 的密码，您必须执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="5a7d2-246">If you changed the DomainAdmin and VMAdmin passwords, you must perform the following steps:</span></span>
    
1. <span data-ttu-id="5a7d2-247">按如下所述运行 Set-CcCredential -AccountType DomainAdmin：</span><span class="sxs-lookup"><span data-stu-id="5a7d2-247">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
1. <span data-ttu-id="5a7d2-248">当系统提示输入旧帐户凭据时，请输入用于 CceService 密码的凭据。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-248">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
2. <span data-ttu-id="5a7d2-249">当系统提示输入新帐户凭据时，请输入之前用于 DomainAdmin 密码的密码。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-249">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
2. <span data-ttu-id="5a7d2-250">按如下所述运行 Set-CcCredential -AccountType VmAdmin：</span><span class="sxs-lookup"><span data-stu-id="5a7d2-250">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
1. <span data-ttu-id="5a7d2-251">当系统提示输入旧帐户凭据时，请输入用于 CceService 密码的凭据。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-251">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
2. <span data-ttu-id="5a7d2-252">当系统提示输入新帐户凭据时，请输入之前用于 VmAdmin 密码的密码。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-252">When prompted for the new account credential, enter the password for the VmAdmin password you used before.</span></span> 
    
- 
    
    <span data-ttu-id="5a7d2-253">**问题： 云接口版本 2.1 或更高版本，装置，运行注册 CcAppliance 或其他 cmdlet 时您会收到一条错误消息如:"为每个对象: '公共' 找不到该对象的属性。验证该属性存在。在 C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 字符： 14"**</span><span class="sxs-lookup"><span data-stu-id="5a7d2-253">**Issue: With Cloud Connector version 2.1 and later, when running Register-CcAppliance or other cmdlets on the appliance, you receive an error message such as: "For Each-Object : The property 'Common' cannot be found on this object. Verify that the property exists. At C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char:14"**</span></span>
    
    <span data-ttu-id="5a7d2-254">**解决方案：**云的连接器 2.1 和以后需要.NET Framework 4.6.1 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-254">**Resolution:** Cloud Connector 2.1 and later requires .NET Framework 4.6.1 or later.</span></span> <span data-ttu-id="5a7d2-255">请更新至版本 4.6.1 装置上的.NET Framework 或更高版本，然后再次运行 cmdlet(s)。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-255">Please update .NET Framework on the appliance to version 4.6.1 or later and run the cmdlet(s) again.</span></span>
    
- <span data-ttu-id="5a7d2-256">**问题： 您收到下面的错误消息"卸除 WindowsImage： 卸除 WindowsImage 失败。错误代码 = 0xc1550115"安装或升级云连接器版时。**</span><span class="sxs-lookup"><span data-stu-id="5a7d2-256">**Issue: You receive the following error message "Dismount-WindowsImage : Dismount-WindowsImage failed. Error code = 0xc1550115" when installing or upgrading Cloud Connector Edition.**</span></span>
    
    <span data-ttu-id="5a7d2-257">**解决方案：**启动 PowerShell 控制台，请以管理员身份运行"DISM-清理-Wim'"。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-257">**Resolution:** Launch a PowerShell console as administrator, run "DISM -Cleanup-Wim'".</span></span> <span data-ttu-id="5a7d2-258">这将清除所有故障的图像。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-258">This will clean up all troubled images.</span></span> <span data-ttu-id="5a7d2-259">再次运行安装 CcAppliance 或等待的位自动升级。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-259">Run Install-CcAppliance again or wait for the bits to automatically upgrade.</span></span>
    
- <span data-ttu-id="5a7d2-260">**问题： 高可用性环境中的第一个云接头装置部署失败**</span><span class="sxs-lookup"><span data-stu-id="5a7d2-260">**Issue: Deployment of the first Cloud Connector appliance in an HA environment fails**</span></span>
    
    <span data-ttu-id="5a7d2-261">**解决方案：**所采取的步骤取决于部署失败的原因：</span><span class="sxs-lookup"><span data-stu-id="5a7d2-261">**Resolution:** The steps you take depend on the reason the deployment failed:</span></span>
    
  - <span data-ttu-id="5a7d2-262">如果第一个云接头装置出现故障，无法确定失败的原因，必须重新安装设备之前部署成功，并再安装其他设备。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-262">If the first Cloud Connector appliance fails and you cannot determine the reason for the failure, you must install the appliance again until the deployment is successful, and then install the other appliances.</span></span>
    
  - <span data-ttu-id="5a7d2-263">如果第一个云接头装置失败，出现小问题，如外部证书问题，您可能能够解决问题，而无需重新安装设备。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-263">If the first Cloud Connector appliance fails with a minor issue, such as an external certificate issue, you might be able to fix the problem without re-installing the appliance.</span></span> <span data-ttu-id="5a7d2-264">您可以使用租户远程 PowerShell 如下标记为成功的部署。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-264">You can then use tenant remote PowerShell to mark the deployment as successful as follows.</span></span> <span data-ttu-id="5a7d2-265">（还可以使用以下步骤如果在首次部署成功，但由于某种原因，云连接器无法报告为成功部署。）</span><span class="sxs-lookup"><span data-stu-id="5a7d2-265">(You can also use the following steps if the first deployment was successful, but, for some reason, Cloud Connector fails to report the deployment as a success.)</span></span>
    
  - <span data-ttu-id="5a7d2-266">若要获取第一个云接口装置的标识 (GUID)，运行 Get CsHybridPSTNAppliance cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-266">To get the Identity (GUID) of the first Cloud Connector appliance, run the Get-CsHybridPSTNAppliance cmdlet.</span></span>
    
  - <span data-ttu-id="5a7d2-267">若要标记为已成功部署设备，请按如下所示运行一组 CsCceApplianceDeploymentStatus:</span><span class="sxs-lookup"><span data-stu-id="5a7d2-267">To mark the appliance as successfully deployed, run the Set-CsCceApplianceDeploymentStatus as follows:</span></span>
    
  ```
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- 
    
    <span data-ttu-id="5a7d2-268">**问题：你需要在主机服务器或虚拟机上手动检查并安装 Windows 更新。**</span><span class="sxs-lookup"><span data-stu-id="5a7d2-268">**Issue: You need to check for and install Windows updates manually on the host server or virtual machines.**</span></span>
    
    <span data-ttu-id="5a7d2-p132">**解决方法：**建议你利用 Skype for Business 云连接器版本提供的操作系统自动更新。当设备经过注册以实现联机管理并且启用了操作系统自动更新之后，主机服务器和虚拟机将根据操作系统更新时间窗口设置自动检查并安装 Windows 更新。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-p132">**Resolution:** We recommend that you take advantage of automated OS updates provided by Skype for Business Cloud Connector Edition. After an appliance is registered for online management and auto OS update is enabled, the host server and virtual machines will check and install Windows Updates automatically according to the OS update time window settings.</span></span>
    
    <span data-ttu-id="5a7d2-p133">如果你需要手动检查并安装 Windows 更新，请按照本节提供的适用于你的部署类型的步骤操作。你需要同时规划主机服务器及其上运行的虚拟机的更新，以便尽可能降低更新所需要的总停机时间。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-p133">If you need to check for and install Windows Updates manually, follow the steps in this section that apply to your type of deployment. You should plan on updating both the host server and the virtual machines running on it at the same time to minimize the amount of down time necessary for the updates.</span></span>
    
    <span data-ttu-id="5a7d2-p134">如果你愿意，可以使用 Windows Server 更新服务 (WSUS) 服务器向云连接器服务器提供更新。只需确保将 Windows 更新配置为**不要**自动安装即可。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-p134">If you prefer, you can use a Windows Server Update Services (WSUS) server to provide updates to Cloud Connector servers. Just be sure to configure the Windows Update to **not** install automatically.</span></span>
    
    <span data-ttu-id="5a7d2-275">有关如何手动更新云连接器部署的信息，请参阅下节。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-275">For information about how to manually update your Cloud Connector deployment, see the following section.</span></span>
    
- 
    
    <span data-ttu-id="5a7d2-276">**问题： 当云接头更新到新版本时，云连接器 cmdlet 都不更新。**</span><span class="sxs-lookup"><span data-stu-id="5a7d2-276">**Issue: When Cloud Connector updates to a new build, Cloud Connector cmdlets are not updated.**</span></span> <span data-ttu-id="5a7d2-277">只有 PowerShell 窗口处于打开状态时自动更新发生时，有时会出现此问题。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-277">This sometimes happens if a PowerShell window is left open when automatic update occurs.</span></span>
    
    <span data-ttu-id="5a7d2-278">**解决方案：**若要加载更新后的 cmdlet，可以执行以下步骤之一：</span><span class="sxs-lookup"><span data-stu-id="5a7d2-278">**Resolution:** To load the updated cmdlets, you can do either of the following steps:</span></span>
    
  - <span data-ttu-id="5a7d2-279">对云连接器的装置，关闭 PowerShell，然后重新打开 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-279">Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.</span></span>
    
  - <span data-ttu-id="5a7d2-280">或者，您可以运行导入模块 CloudConnector 的力。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-280">Or, you can run Import-Module CloudConnector -Force.</span></span> 
    
## <a name="install-windows-updates-manually"></a><span data-ttu-id="5a7d2-281">手动安装 Windows 更新</span><span class="sxs-lookup"><span data-stu-id="5a7d2-281">Install Windows updates manually</span></span>

<span data-ttu-id="5a7d2-282">如果你不想在自己的环境中使用自动更新，请按照以下步骤操作，以手动检查并应用 Windows 更新。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-282">If you do not want to use automatic updates in your environment, follow these steps to manually check for and apply Windows updates.</span></span> <span data-ttu-id="5a7d2-283">检查并安装 Windows 更新可能需要重新启动服务器。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-283">Checking for and installing Windows updates may require a server restart.</span></span> <span data-ttu-id="5a7d2-284">当主机服务器正在重新启动时，用户不能使用云连接器发送或接收传呼。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-284">When a host server is restarting, users will not be able to use Cloud Connector to place or receive calls.</span></span> <span data-ttu-id="5a7d2-285">你可以手动检查并安装更新，以控制更新发生时间，然后根据需要在你选择的时间重新启动计算机，以避免服务中断。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-285">You can manually check for and install updates to control when the updates take place, and then restart the machines as needed during times you choose to avoid disruption of services.</span></span>
  
<span data-ttu-id="5a7d2-286">要手动检查更新，请连接到每台主机服务器，并打开“**控制面板**”。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-286">To manually check for updates, connect to each host server and open the **Control Panel**.</span></span> <span data-ttu-id="5a7d2-287">选择**系统和安全\>Windows 更新**，然后管理更新程序和服务器重启为适合于您的环境。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-287">Select **System and Security \>Windows Update**, and then manage the updates and server restarts as appropriate for your environment.</span></span>
  
- <span data-ttu-id="5a7d2-288">如果站点中只有一个设备，请连接到每个虚拟机，并打开“**控制面板**”。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-288">If there is only one appliance in the site, connect to each virtual machine and open the **Control Panel**.</span></span> <span data-ttu-id="5a7d2-289">选择**系统和安全\>Windows 更新**，然后将更新的配置，并根据需要重新启动服务器。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-289">Select **System and Security \>Windows Update**, and then configure the updates and server restarts as appropriate.</span></span>
    
- <span data-ttu-id="5a7d2-p139">如果站点中有多个设备，更新期间用户将无法访问正在更新和重新启动的实例。用户将连接到部署中的其他实例，直到更新完成后所有虚拟机及虚拟机上的所有 Skype for Business 服务启动为止。为避免任何潜在的服务中断，可以在应用更新时从 HA 删除实例，然后在完成后将其还原。为此：</span><span class="sxs-lookup"><span data-stu-id="5a7d2-p139">If there are more than one appliance in the site, the instance being updated and restarted cannot be accessed by users during the updates. Users will connect to other instances in the deployment until all virtual machines and all Skype for Business services start on the virtual machines after the updates are completed. To avoid any potential disruption to service, you can remove the instance from HA while you apply the updates, and then restore it when complete. To do so:</span></span>
    
1. <span data-ttu-id="5a7d2-294">在每台主机服务器上，以管理员身份打开 PowerShell 控制台。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-294">On each host server, open a PowerShell console as administrator.</span></span>
    
2. <span data-ttu-id="5a7d2-295">使用以下 cmdlet 从 HA 删除实例：</span><span class="sxs-lookup"><span data-stu-id="5a7d2-295">Remove the instance from HA with the following cmdlet:</span></span>
    
  ```
  Enter-CcUpdate
  ```

3. 
    
    <span data-ttu-id="5a7d2-296">按照适用于单个实例的步骤，手动应用更新并重新启动虚拟机。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-296">Follow the steps for a single instance to manually apply the updates and restart the virtual machine.</span></span>
    
4. <span data-ttu-id="5a7d2-297">使用以下 cmdlet 将实例重新设置为 HA：</span><span class="sxs-lookup"><span data-stu-id="5a7d2-297">Set the instance back to HA with the following cmdlet:</span></span>
    
  ```
  Exit-CcUpdate
  ```

<span data-ttu-id="5a7d2-298">对于多站点部署，请为部署中的每个站点执行适用于单个站点的步骤，每次向一个站点应用更新。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-298">For multi-site deployments, follow the steps for a single site for each site in the deployment, applying updates to one site at a time.</span></span>
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a><span data-ttu-id="5a7d2-299">在云连接器宿主计算机上安装防病毒软件时的提示</span><span class="sxs-lookup"><span data-stu-id="5a7d2-299">Tips when installing anti-virus software on the Cloud Connector host machine</span></span>

<span data-ttu-id="5a7d2-300">如果您需要在云连接器宿主计算机上安装防病毒软件，您需要添加以下排除项：</span><span class="sxs-lookup"><span data-stu-id="5a7d2-300">If you need to install anti-virus software on the Cloud Connector host machine, you need to add the following exclusions:</span></span>
  
- <span data-ttu-id="5a7d2-301">每台计算机上的本地设备目录。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-301">Local Appliance Directory on each machine.</span></span>
    
- <span data-ttu-id="5a7d2-302">每台计算机上的远程站点目录。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-302">Remote Site Directory on each machine.</span></span>
    
- <span data-ttu-id="5a7d2-303">本地计算机上的站点目录承载共享的站点根文件夹。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-303">Local Site Directory on the machine hosts the shared site root folder.</span></span>
    
- <span data-ttu-id="5a7d2-304">商务云连接器版的 %ProgramFiles%\Skype</span><span class="sxs-lookup"><span data-stu-id="5a7d2-304">%ProgramFiles%\Skype for Business Cloud Connector Edition</span></span>
    
- <span data-ttu-id="5a7d2-305">%ALLUSERSPROFILE%\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="5a7d2-305">%ALLUSERSPROFILE%\CloudConnector</span></span>
    
- <span data-ttu-id="5a7d2-306">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="5a7d2-306">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span></span>
    
- <span data-ttu-id="5a7d2-307">Microsoft.Rtc.CCE.ManagementService.exe 过程。</span><span class="sxs-lookup"><span data-stu-id="5a7d2-307">The process Microsoft.Rtc.CCE.ManagementService.exe.</span></span>
    

