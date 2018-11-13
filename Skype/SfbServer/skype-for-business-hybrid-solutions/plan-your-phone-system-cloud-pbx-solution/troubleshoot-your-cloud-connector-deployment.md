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
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e6cf58cc-dbd9-4f35-a51a-3e2fea71b5a5
description: 解决云连接器 Edition 部署。
ms.openlocfilehash: 5dbb046680824f2af72688844914db0096e2ded1
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295469"
---
# <a name="troubleshoot-your-cloud-connector-deployment"></a><span data-ttu-id="4e1d1-103">云连接器部署故障排除</span><span class="sxs-lookup"><span data-stu-id="4e1d1-103">Troubleshoot your Cloud Connector deployment</span></span>
 
<span data-ttu-id="4e1d1-104">解决云连接器 Edition 部署。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-104">Troubleshoot your Cloud Connector Edition deployment.</span></span>
  
<span data-ttu-id="4e1d1-p101">本主题介绍云连接器版本部署常见问题的解决方案。如果你在通过公用电话交换网 (PSTN) 拨打和接听电话时遇到问题，可以按照本主题中介绍的解决方案进行调查。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-p101">This topic describes solutions to common issues with Cloud Connector Edition deployments. If you are experiencing issues with calls to and from the Public Switched Telephone Network (PSTN), you can investigate by following the solutions described in this topic.</span></span>
  
<span data-ttu-id="4e1d1-107">云连接器提供用于自动解决某些问题的内置机制。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-107">Cloud Connector provides built-in mechanisms for automatically resolving some issues.</span></span> <span data-ttu-id="4e1d1-108">自动检测过程与云连接器 appliance，查找潜在问题，如果可能，请采取纠正操作解决这些问题，无需管理员干预。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-108">An automatic detection process looks for potential issues with the Cloud Connector appliances, and, if possible, takes corrective action to resolve those issues without the need for administrator intervention.</span></span> <span data-ttu-id="4e1d1-109">检测过程工作方式如下：</span><span class="sxs-lookup"><span data-stu-id="4e1d1-109">The detection process works as follows:</span></span>
  
- <span data-ttu-id="4e1d1-110">**检测序列：** 云连接器管理服务过程每 60 秒运行用于检测装置是否已关闭。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-110">**Detection sequence:** The Cloud Connector Management service runs a process every 60 seconds for detecting whether an appliance is down.</span></span> <span data-ttu-id="4e1d1-111">在云连接器 2.0 及更高版本，检测过程使用 Skype 业务 Corpnet 开关进行 PowerShell 连接到云连接器机中;对于 2.0 之前的版本，检测过程使用云连接器管理开关。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-111">In Cloud Connector version 2.0 and later, the detection process uses the Skype for Business Corpnet switch for making PowerShell connections to the Cloud Connector machines; for versions previous to 2.0, the detection process uses the Cloud Connector management switch.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4e1d1-112">自动恢复，若要成功执行，必须有主机和虚拟机之间的网络连接通过主机网络交换机。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-112">For automatic recovery to succeed, there must be network connectivity between the host and virtual machines over the host network switch.</span></span> <span data-ttu-id="4e1d1-113">一定要检查网络连接，以确保该自动检测并恢复才能成功。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-113">Be sure to check network connectivity to ensure that automatic detection and recovery can succeed.</span></span> 
  
- <span data-ttu-id="4e1d1-114">**监控：** 云 Connector 2.0 及更高版本中监视以下服务：</span><span class="sxs-lookup"><span data-stu-id="4e1d1-114">**Monitoring:** The following services are monitored in Cloud Connector version 2.0 and later:</span></span>
    
  - <span data-ttu-id="4e1d1-115">虚拟机未连接到云连接器公司或 Internet 虚拟交换机</span><span class="sxs-lookup"><span data-stu-id="4e1d1-115">Virtual Machines are not connected to the Cloud Connector Corporate or Internet virtual switches</span></span>
    
  - <span data-ttu-id="4e1d1-116">虚拟机处于保存还是已停止的状态</span><span class="sxs-lookup"><span data-stu-id="4e1d1-116">Virtual Machines are in a saved or stopped status</span></span>
    
  - <span data-ttu-id="4e1d1-117">中央管理服务器服务： 副本、 主控形状</span><span class="sxs-lookup"><span data-stu-id="4e1d1-117">Central Management Server services: REPLICA, MASTER</span></span>
    
  - <span data-ttu-id="4e1d1-118">中介服务器服务： 副本、 RTCSRV 和 MEDSVC</span><span class="sxs-lookup"><span data-stu-id="4e1d1-118">Mediation Server services: REPLICA, RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="4e1d1-119">边缘服务器服务： 副本、 RTCSRV、 RTCDATAPROXY、 RTCMRAUTH、 RTCMEDIARELAY</span><span class="sxs-lookup"><span data-stu-id="4e1d1-119">Edge Server services: REPLICA, RTCSRV, RTCDATAPROXY, RTCMRAUTH, RTCMEDIARELAY</span></span>
    
  - <span data-ttu-id="4e1d1-120">对于边缘服务器，中介服务器上的 CS RTCMEDSRV CS RTCSRV 禁用规则的防火墙的入站邮件</span><span class="sxs-lookup"><span data-stu-id="4e1d1-120">Inbound firewall rules are disabled for CS RTCSRV on Edge server, CS RTCMEDSRV on Mediation server</span></span>
    
    <span data-ttu-id="4e1d1-121">在云连接器版本 1.4.2，监视仅以下服务：</span><span class="sxs-lookup"><span data-stu-id="4e1d1-121">In Cloud Connector version 1.4.2, only the following services are monitored:</span></span>
    
  - <span data-ttu-id="4e1d1-122">中介服务器服务： RTCSRV 和 MEDSVC</span><span class="sxs-lookup"><span data-stu-id="4e1d1-122">Mediation Server services: RTCSRV and MEDSVC</span></span>
    
  - <span data-ttu-id="4e1d1-123">边缘服务器服务： RTCSRV</span><span class="sxs-lookup"><span data-stu-id="4e1d1-123">Edge Server service: RTCSRV</span></span>
    
- <span data-ttu-id="4e1d1-124">**恢复过程：** 如果任何监控的服务不可用，装置标记下，并已停止并可以解决所有问题之前标记手动服务。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-124">**Recovery process:** If any monitored services are down, an appliance is marked down, and services are stopped and marked manual until all issues can be resolved.</span></span> <span data-ttu-id="4e1d1-125">这将防止路由至装置可能会导致呼叫失败的呼叫。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-125">This will prevent calls from routing to an appliance that may cause call failures.</span></span>
    
    <span data-ttu-id="4e1d1-126">云连接器管理服务，如下所示将重试自动恢复</span><span class="sxs-lookup"><span data-stu-id="4e1d1-126">The Cloud Connector Management service will retry automatic recovery as follows</span></span>
    
  - <span data-ttu-id="4e1d1-127">初始重试间隔为最大的间隔时间为一小时每个十秒。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-127">The initial retry interval is every ten seconds with a maximum interval time of one hour.</span></span>
    
  - <span data-ttu-id="4e1d1-128">前三个恢复尝试时，间隔时间为 10 秒。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-128">For the first three recovery attempts, the interval time is 10 seconds.</span></span> <span data-ttu-id="4e1d1-129">从第四个重试，由两次以前间隔时间增加的间隔时间。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-129">Starting from the fourth retry, the interval time increases by two times the previous interval time.</span></span> <span data-ttu-id="4e1d1-130">例如，第四个重试将出现在 20 秒内，以 40 秒为单位，为第五个，依此类推。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-130">For example, the fourth retry will occur in 20 seconds, the fifth in 40 seconds, and so on.</span></span> 
    
  - <span data-ttu-id="4e1d1-131">达到一小时的最大的间隔时间后，重试次数将继续每小时一次。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-131">When the maximum interval time of one hour is reached, retries will continue once per hour.</span></span>
    
  - <span data-ttu-id="4e1d1-132">成功恢复时，为其初始值设置间隔，然后重试计数。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-132">When recovery is successful, the interval and retry counts are set to their initial values.</span></span>
    
  - <span data-ttu-id="4e1d1-133">如果重新启动管理服务，则的时间间隔，然后重试的计数将重置为其初始的值。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-133">If the Management service is restarted, the interval and retry counts are reset to their initial values.</span></span>
    
## <a name="troubleshooting"></a><span data-ttu-id="4e1d1-134">故障排除</span><span class="sxs-lookup"><span data-stu-id="4e1d1-134">Troubleshooting</span></span>

<span data-ttu-id="4e1d1-135">以下是常见的问题的解决方案：</span><span class="sxs-lookup"><span data-stu-id="4e1d1-135">Following are solutions to commonly encountered issues:</span></span>
  
- <span data-ttu-id="4e1d1-136">**问题：运行部署脚本时部署失败或停止响应。登录每个虚拟机后，管理/内部/外部 NIC 的 IP 地址缺失或不正确。**</span><span class="sxs-lookup"><span data-stu-id="4e1d1-136">**Issue: Deployment fails or stops responding when running the deployment scripts. After logging on to each VM, the IP address is missing or incorrect for the Management/Internal/External NIC.**</span></span>
    
    <span data-ttu-id="4e1d1-137">**解决方法：** 无法自动解决此问题。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-137">**Resolution:** This issue cannot be resolved automatically.</span></span> <span data-ttu-id="4e1d1-138">在运行时，无法将 Nic 添加到虚拟机。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-138">NICs cannot be added to VMs while they are running.</span></span> <span data-ttu-id="4e1d1-139">请关闭和删除 hyper-v 管理器中的这些虚拟机，然后运行以下 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="4e1d1-139">Please shut down and remove these VMs in hyper-v manager, then run the following cmdlets:</span></span>
    
  ```
  Uninstall-CcAppliance
  ```

  ```
  Install-CcAppliance
  ```

- 
    
    <span data-ttu-id="4e1d1-140">**问题：安装 Active Directory 服务器和林后，CMS 服务器和/或中介服务器未正确加入域。**</span><span class="sxs-lookup"><span data-stu-id="4e1d1-140">**Issue: After the Active Directory Server and forest are installed, the CMS Server and/or Mediation Server did not join the domain correctly.**</span></span>
    
    <span data-ttu-id="4e1d1-141">**解决方法：** 要解决此问题，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="4e1d1-141">**Resolution:** To resolve this issue, take the following steps:</span></span>
    
  - <span data-ttu-id="4e1d1-142">登录 Active Directory 服务器并验证是否已正确创建域。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-142">Log on to the Active Directory Server and verify that the domain was created correctly.</span></span>
    
  - <span data-ttu-id="4e1d1-143">登录 CMS/中介服务器，并验证公司网络 NIC 上是否分配了有效的 IP 地址，以及是否将有效的静态 IP 和 DNS 配置为 AD 服务器的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-143">Log on to the CMS/Mediation Server and verify that on the corpnet NIC a valid IP address is assigned, and that valid static IP and DNS is configured as the AD server's IP address.</span></span>
    
  - <span data-ttu-id="4e1d1-144">登录到 CMS/中介服务器，并打开命令提示符。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-144">Log on to the CMS/Mediation Server, and open a command prompt.</span></span> <span data-ttu-id="4e1d1-145">确保可以 ping Active Directory 服务器的 FQDN 和 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-145">Make sure you can ping the FQDN and IP address of the Active Directory Server.</span></span> <span data-ttu-id="4e1d1-146">如果不可以，则可能存在 IP 地址冲突。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-146">If you cannot, there may be an IP address conflict.</span></span> <span data-ttu-id="4e1d1-147">请尝试为 Active Directory 分配新 IP 并相应更新 CMS/中介服务器上的 DNS。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-147">Please try to assign a new IP for Active Directory and update DNS on the CMS/Mediation server accordingly.</span></span>
    
- <span data-ttu-id="4e1d1-148">**问题： 您将收到以下错误消息，"删除 VMSwitch： 移除虚拟以太网开关时失败。云连接器管理切换在虚拟交换机无法删除因为它正在由运行虚拟机或分配给子池。"**</span><span class="sxs-lookup"><span data-stu-id="4e1d1-148">**Issue: You receive the following error message, "Remove-VMSwitch : Failed while removing virtual Ethernet switch. The virtual switch 'Cloud Connector Management Switch' cannot be deleted because it is being used by running virtual machines or assigned to child pools."**</span></span>
    
    <span data-ttu-id="4e1d1-149">**解决方法：**"云连接器管理开关"未在部署后删除。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-149">**Resolution:** The "Cloud Connector Management Switch" was not deleted after the deployment.</span></span> <span data-ttu-id="4e1d1-150">如果遇到此错误，请转到 hyper-v 管理器，并验证是否存在不仍仍为连接到该虚拟机。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-150">If you hit this error, please go to Hyper-v manager and verify that there is not still a virtual machine still connected to it.</span></span> <span data-ttu-id="4e1d1-151">如果有仍为连接状态的虚拟机，在断开连接，并删除管理开关。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-151">If there are virtual machines still connected, disconnect them and delete the management switch.</span></span> <span data-ttu-id="4e1d1-152">如果仍然不能删除管理开关，重新启动的主机服务器，然后重试。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-152">If the management switch still cannot be deleted, restart the host server and try again.</span></span>
    
- <span data-ttu-id="4e1d1-153">**问题： 您将收到以下错误消息，"RTCMRAUTH 服务未能启动。检查以确保不禁用该服务。"**</span><span class="sxs-lookup"><span data-stu-id="4e1d1-153">**Issue: You receive the following error message, "Service RTCMRAUTH failed to start. Check to make sure the service is not disabled."**</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4e1d1-154">此问题仅适用于云连接器版本早于 1.4.2。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-154">This issue only applies to Cloud Connector versions earlier than 1.4.2.</span></span> 
  
    <span data-ttu-id="4e1d1-p110">无法启动也可能是因为此前端服务器之前经过故障转移（使用计算机故障转移）。如果是这种情况，请调用故障回复（使用计算机故障回复）。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-p110">The failure to start could also be because this Front End server was previously failed over (using computer fail over). If that's the case, please invoke fail back (using computer fail back).</span></span>
    
    <span data-ttu-id="4e1d1-p111">**解决方法：** 当边缘服务器不信任根 CA 证书或中间 CA 证书时，边缘服务器上会出现此问题。即使可以导入外部证书，但证书链已损坏。在这种情况下，RTCMRAUTH 和/或 RTCSRV 服务无法启动。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-p111">**Resolution:** This issue happens on an Edge Server when the root CA certificate or intermediate CA certificate is not trusted by the Edge Server. Even if the external certificate can be imported but the certificate chain is broken. Under this condition, the RTCMRAUTH and/or RTCSRV service can not start.</span></span>
    
    <span data-ttu-id="4e1d1-p112">请手动将外部证书的根 CA 证书和所有中间 CA 证书导入到边缘服务器，然后重新启动边缘服务器。看到 RTCMRAUTH 和 RTCSRV 服务在边缘服务器上启动之后，返回到主机服务器，以管理员身份启动 PowerShell 控制台，并运行以下 cmdlet 以便切换到新部署：</span><span class="sxs-lookup"><span data-stu-id="4e1d1-p112">Please import the root CA certificate and all intermediate CA certificates of your external certificate manually into the Edge Server and then restart the Edge Server. After you see the RTCMRAUTH and RTCSRV services started on the Edge Server, go back to your host server, launch a PowerShell console as administrator, and run following cmdlet to switch to the new deployment:</span></span>
    
  ```
  Switch-CcVersion
  ```

- 
    
    <span data-ttu-id="4e1d1-162">**问题：应用 Windows 更新时主机服务器重新启动，由此服务器支持的调用失败。**</span><span class="sxs-lookup"><span data-stu-id="4e1d1-162">**Issue: The host server was restarted when Windows updates were applied, and calls serviced by the server are failing.**</span></span>
    
    <span data-ttu-id="4e1d1-p113">**解决方法：** 如果你已部署高可用性环境，Microsoft 提供的 cmdlet 可以帮助你在手动检查和安装 Windows 更新时将一台主机（部署实例）移入或移出当前拓扑。要完成此操作，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="4e1d1-p113">**Resolution:** If you deployed a high availability environment, Microsoft provides a cmdlet to help move one host machine (deployment instance) into or out of the current topology when you check and install Windows update manually. Use the following steps to accomplish this:</span></span>
    
1. <span data-ttu-id="4e1d1-165">在主机服务器上，以管理员身份启动 PowerShell 控制台，然后运行：</span><span class="sxs-lookup"><span data-stu-id="4e1d1-165">On the host server, start a PowerShell console as administrator, then run:</span></span>
    
   ```
   Enter-CcUpdate
   ```

2. <span data-ttu-id="4e1d1-166">检查更新并安装所有可用更新。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-166">Check for updates and install any that are available.</span></span>
    
3. <span data-ttu-id="4e1d1-167">在 PowerShell 控制台中，运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="4e1d1-167">In the PowerShell console, run the following cmdlet:</span></span>
    
   ```
   Exit-CcUpdate
   ```

- 
    
    <span data-ttu-id="4e1d1-168">**问题：使用 PSTN 号码从 Skype for Business 客户端进行呼叫时，无法通过邀请其他 PSTN 号码将该呼叫提升为会议。**</span><span class="sxs-lookup"><span data-stu-id="4e1d1-168">**Issue: When a call is made from a Skype for Business client using a PSTN number, the call cannot be escalated to a conference by inviting another PSTN number.**</span></span>
    
    <span data-ttu-id="4e1d1-169">**解决方法：** 若要解决此问题，请参阅[配置联机混合中介服务器设置](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer)。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-169">**Resolution:** To resolve this issue, see [Configure online hybrid Mediation Server Settings](configure-cloud-connector-integration-with-your-office-365-tenant.md#BKMK_ConfigureMediationServer).</span></span>
    
- <span data-ttu-id="4e1d1-170">**问题：安装 Active Directory 服务器时，显示关于 Windows 更新的警告消息 -“未启用 Windows 自动更新。为确保新安装的角色或功能将自动更新，请启用 Windows 更新。”**</span><span class="sxs-lookup"><span data-stu-id="4e1d1-170">**Issue: A warning message is displayed about Windows Update when you are installing Active Directory server - "Windows automatic updating is not enabled. To ensure that your newly-installed role or feature is automatically updated, turn on Windows Update."**</span></span>
    
    <span data-ttu-id="4e1d1-171">**解决方法：** 启动租户远程 PowerShell 会话 Skype 用于业务租户管理员凭据，然后运行以下 cmdlet 以检查您的网站的_EnableAutoUpdate_配置：</span><span class="sxs-lookup"><span data-stu-id="4e1d1-171">**Resolution:** Launch a Tenant Remote PowerShell session using Skype for Business tenant admin credentials, then run the following cmdlet to check the _EnableAutoUpdate_ configuration of your site:</span></span>
    
  ```
  Get-CsHybridPSTNSite
  ```

    <span data-ttu-id="4e1d1-172">_EnableAutoUpdate_设置为**True**，如果可以安全地忽略此警告消息，因为 CCEManagement 服务将处理下载并安装 Windows 更新的虚拟机和主服务器。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-172">If  _EnableAutoUpdate_ is set to **True**, you can safely ignore this warning message because the CCEManagement service will handle downloading and installing Windows updates for both virtual machines and the host server.</span></span> <span data-ttu-id="4e1d1-173">如果_EnableAutoUpdate_设置为**False**，则运行以下 cmdlet 以将其设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-173">If  _EnableAutoUpdate_ is set to **False**, run following cmdlet to set it to **True**.</span></span>
    
  ```
  Set-CsHybridPSTNSite -EnableAutoUpdate $true
  ```

    <span data-ttu-id="4e1d1-174">此外，你还可以手动检查并安装更新。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-174">Alternatively, you can manually check for and install updates.</span></span> <span data-ttu-id="4e1d1-175">请参阅下节内容。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-175">See the next section.</span></span>
    
- <span data-ttu-id="4e1d1-176">**问题： 您将收到一条错误消息： 无法注册 appliance，因为每个配置当前的输入\<SiteName\>或\<装置名称\>或\<中介服务器 FQDN\>或\<中介服务器的 IP 地址\>与现有装置冲突。删除冲突装置或更新您的输入/配置信息，然后再次注册。注册-CcAppliance 注册到 online 当前装置运行时。**</span><span class="sxs-lookup"><span data-stu-id="4e1d1-176">**Issue: You receive an error message: Cannot register appliance because your current input/configuration \<SiteName\> or \<ApplianceName\> or \<Mediation Server FQDN\> or \<Mediation Server IP Address\> conflicts with existing appliance(s). Remove conflict appliance or update your input/configuration information then register again. ' when run Register-CcAppliance to register current appliance to online.**</span></span>
    
    <span data-ttu-id="4e1d1-177">**解决方法：** 值\<装置名称\>，\<中介服务器 FQDN\>和\<中介服务器的 IP 地址\>必须是唯一的并且仅用于一个 appliance 注册。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-177">**Resolution:** Values for the \<ApplianceName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> must be unique and only used for one appliance registration.</span></span> <span data-ttu-id="4e1d1-178">默认情况下，\<装置名称\>来自的主机名称。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-178">By default, \<ApplianceName\> comes from the host name.</span></span> <span data-ttu-id="4e1d1-179">\<中介服务器 FQDN\>和\<中介服务器的 IP 地址\>配置 ini 文件中定义。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-179">\<Mediation Server FQDN\> and \<Mediation Server IP Address\> defined in configuration ini file.</span></span>
    
    <span data-ttu-id="4e1d1-180">例如，使用 (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) 来注册 SiteName=MySite 时，如果存在已注册设备 (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10)，则会出现冲突。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-180">For example, using (ApplianceName= MyserverNew, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10) to register to SiteName=MySite, but if there is a registered appliance (ApplianceName= Myserver, Mediation Server FQDN=ms.contoso.com, Mediation Server IP Address=10.10.10.10), you will have the conflict.</span></span>
    
    <span data-ttu-id="4e1d1-181">首先，请检查 ApplianceRoot 目录部分中的 CloudConnector.ini 文件。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-181">First, please check your CloudConnector.ini file in ApplianceRoot directory section.</span></span> <span data-ttu-id="4e1d1-182">您将收到\<SiteName\>，\<中介服务器 FQDN\>和\<中介服务器的 IP 地址\>文件中的值。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-182">You will get \<SiteName\>, \<Mediation Server FQDN\> and \<Mediation Server IP Address\> values in the file.</span></span> <span data-ttu-id="4e1d1-183">\<装置名称\>是主机服务器名称。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-183">\<ApplianceName\> is your host server name.</span></span>
    
    <span data-ttu-id="4e1d1-184">其次，启动租户远程 PowerShell 您 Skype 用于业务租户管理员凭据，然后运行以下 cmdlet 以检查注册的装置。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-184">Second, Launch Tenant Remote PowerShell using your Skype for Business tenant admin credentials, then run the following cmdlet to check the registered appliance(s).</span></span>
    
  ```
  Get-CsHybridPSTNAppliance
  ```

    <span data-ttu-id="4e1d1-185">确定任何冲突后，可以使用与已注册设备匹配的信息更新 CloudConnector.ini 文件，或注销现有设备以解决冲突。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-185">After identifying any conflicts, you can either update your CloudConnector.ini file with information that matches the registered appliance, or unregister the existing appliance to resolve the conflicts.</span></span>
    
  ```
  Unregister-CsHybridPSTNAppliance -Force
  ```

    
- <span data-ttu-id="4e1d1-186">**问题： 运行在主机上部署的设备时，获取 CcRunningVersion cmdlet 返回一个空值。**</span><span class="sxs-lookup"><span data-stu-id="4e1d1-186">**Issue: The Get-CcRunningVersion cmdlet returns an empty value if there is a deployed appliance running on the host.**</span></span>
    
  <span data-ttu-id="4e1d1-p118">**解决方法：** 从 1.3.4 或 1.3.8 升级到 1.4.1 之后，可能会出现此情况。使用 .msi 安装 1.4.1 版之后，必须先运行 `Register-CcAppliance`，才能运行任何其他 cmdlet。`Register-CcAppliance` 会将 module.ini 文件从 %UserProfile%\CloudConnector 迁移到 %ProgramData%\CloudConnector。如果你没有运行此 cmdlet，将会在 %ProgramData%\CloudConnector 文件夹中创建一个新的 module.ini 文件，并替换 1.3.4 或 1.3.8 的运行/备份版本信息。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-p118">**Resolution:** This can happen when you upgrade from 1.3.4 or 1.3.8 to 1.4.1. After you install version 1.4.1 with the .msi, you must run `Register-CcAppliance` before you run any other cmdlet. `Register-CcAppliance` will migrate the module.ini file from %UserProfile%\CloudConnector to %ProgramData%\CloudConnector. If you missed it, a new module.ini will be created in %ProgramData%\CloudConnector folder and replace the running/backup version information for 1.3.4 or 1.3.8.</span></span>
    
  <span data-ttu-id="4e1d1-191">比较 %UserProfile%\CloudConnector 和 %ProgramData%\CloudConnector 文件夹中的 module.ini 文件。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-191">Compare module.ini files in %UserProfile%\CloudConnector and %ProgramData%\CloudConnector folder.</span></span> <span data-ttu-id="4e1d1-192">如果有区别，删除 %ProgramData%\CloudConnector 并重新运行中的 module.ini 文件`Register-CcAppliance`。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-192">If there are differences, delete the module.ini file in %ProgramData%\CloudConnector and rerun  `Register-CcAppliance`.</span></span> <span data-ttu-id="4e1d1-193">您还可以修改手动向正确运行和备份版本的文件。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-193">You could also modify the file manually to the correct running and backup version.</span></span>
    
- <span data-ttu-id="4e1d1-194">**问题： 运行开关 CcVersion cmdlet 以切换到从中当前脚本版本不同的旧版本后，没有高可用性支持此旧版本。**</span><span class="sxs-lookup"><span data-stu-id="4e1d1-194">**Issue: After you run the Switch-CcVersion cmdlet to switch to an old version which is different from current script version, there is no High Availability support for this old version.**</span></span>
    
    <span data-ttu-id="4e1d1-195">**解决方法：** 例如，已从 1.4.1 升级到 1.4.2。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-195">**Resolution:** For example, you have upgraded from 1.4.1 to 1.4.2.</span></span> <span data-ttu-id="4e1d1-196">您当前的脚本版本，可以通过运行确定`Get-CcVersion`，并且您运行的版本，可以通过运行确定`Get-CcRunningVersion`是这两个 1.4.2。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-196">Your current script version, which can be determined by running `Get-CcVersion`, and your running version, which can be determined by running  `Get-CcRunningVersion` are both 1.4.2.</span></span> <span data-ttu-id="4e1d1-197">此时，如果您运行`Switch-CcVersion`来切换回 1.4.1 运行的版本，然后将有此旧版本不高可用性支持。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-197">At this time, if you run `Switch-CcVersion` to switch the running version back to 1.4.1, then there will be no High Availability support for this old version.</span></span>
    
    <span data-ttu-id="4e1d1-p121">要获得完整的高可用性支持，请切换回 1.4.2，从而使运行版本和脚本版本相同。如果 1.4.2 部署出现问题，请尽快将其卸载并重新安装。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-p121">To get full High Availability support, please switch back to 1.4.2, so the running version and script version are the same. If you are experiencing problems with your 1.4.2 deployment, please uninstall and reinstall it as soon as possible.</span></span>
    
- <span data-ttu-id="4e1d1-200">**问题：证书颁发机构证书或颁发给中央管理存储、中介服务器和边缘服务器的内部证书即将过期或已损坏。**</span><span class="sxs-lookup"><span data-stu-id="4e1d1-200">**Issue: Certificate authority certificates or internal certificates issued to Central Management Store, Mediation Server, and Edge Server are near expiration or are compromised.**</span></span>
    
    <span data-ttu-id="4e1d1-p122">**解决方法：** Skype for Business 证书颁发机构证书有效期为 5 年。颁发给中央管理存储、中介服务器和边缘服务器的内部证书有效期为 2 年。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-p122">**Resolution:** Skype for Business certification authority certificates are valid for five years. Internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are valid for two years.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4e1d1-203">在云连接器 2.0 及更高版本，续订 CcServerCertificate cmdlet 已更改为更新 CcServerCertificate 和续订 CcCACertificate cmdlet 已更改为更新 CcCACertificate。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-203">In Cloud Connector version 2.0 and later, the Renew-CcServerCertificate cmdlet has changed to Update-CcServerCertificate and the Renew-CcCACertificate cmdlet has changed to Update-CcCACertificate.</span></span> 
  
    <span data-ttu-id="4e1d1-204">如果颁发给的中央管理存储、 中介服务器和边缘服务器内部证书临近过期或威胁，运行要续订证书的续订 CcServerCertificate 或更新 CcServerCertificate cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-204">If internal certificates issued to the Central Management Store, Mediation Server, and Edge Server are near expiration or compromised, run the Renew-CcServerCertificate or Update-CcServerCertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="4e1d1-205">如果证书颁发机构证书过期附近，运行续订 CcCACertificate 或更新 CcCACertificate cmdlet 续订您的证书。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-205">If certification authority certificates are near expiration, run the Renew-CcCACertificate or Update-CcCACertificate cmdlet to renew your certificates.</span></span>
    
    <span data-ttu-id="4e1d1-206">**如果证书颁发机构证书受到威胁，并且只有一个装置的站点中，** 执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="4e1d1-206">**If certification authority certificates are compromised and there is only one appliance in the site,** perform the following steps:</span></span>
    
1. <span data-ttu-id="4e1d1-207">运行 Enter-CcUpdate cmdlet 以排出服务并将该设备置于维护模式。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-207">Run the Enter-CcUpdate cmdlet to drain services and put the appliance in maintenance mode.</span></span>
    
2. <span data-ttu-id="4e1d1-208">运行以下 cmdlet 以重置证书颁发机构证书和所有内部服务器证书并创建相应的新证书：</span><span class="sxs-lookup"><span data-stu-id="4e1d1-208">Run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
    <span data-ttu-id="4e1d1-209">对于云连接器 2.0 之前的版本：</span><span class="sxs-lookup"><span data-stu-id="4e1d1-209">For Cloud Connector releases before 2.0:</span></span>
    
    ```
    Reset-CcCACertificate 
    Renew-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

    <span data-ttu-id="4e1d1-210">或云连接器版本 2.0 及更高版本：</span><span class="sxs-lookup"><span data-stu-id="4e1d1-210">Or for Cloud Connector release 2.0 and later:</span></span>
    
    ```
    Reset-CcCACertificate 
    Update-CcServerCertificate 
    Remove-CcLegacyServerCertificate 
    ```

3. <span data-ttu-id="4e1d1-211">运行 Exit-CcUpdate cmdlet 以启动服务并退出维护模式。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-211">Run the Exit-CcUpdate cmdlet to start services and and exit maintenance mode.</span></span>
    
4. <span data-ttu-id="4e1d1-212">对设备上的本地文件运行 Export-CcRootCertificate cmdlet，然后将导出的证书复制并安装到 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-212">Run the Export-CcRootCertificate cmdlet on the local file in the appliance, and then copy and install the exported certificate to your PSTN gateways.</span></span>
    
    <span data-ttu-id="4e1d1-213">**如果证书颁发机构证书受到威胁，并且有多个装置的站点中，** 执行以下顺序步骤在网站中每个设备上。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-213">**If certification authority certificates are compromised and there are multiple appliances in the site,** perform the following sequential steps on each appliance in the site.</span></span>
    
    <span data-ttu-id="4e1d1-214">Microsoft 建议您在非高峰使用时间段执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-214">Microsoft recommends that you perform these steps during non-peak usage times.</span></span>
    
   - <span data-ttu-id="4e1d1-215">第一台设备上运行删除 CcCertificationAuthorityFile cmdlet CA 清理备份文件\<SiteRoot\>目录。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-215">On the first appliance, run the Remove-CcCertificationAuthorityFile cmdlet to clean up the CA backup files in the \<SiteRoot\> directory.</span></span>
    
   - <span data-ttu-id="4e1d1-216">运行 Enter CcUpdate cmdlet 排出服务并将每个装置放在维护模式。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-216">Run the Enter-CcUpdate cmdlet to drain services and put each appliance in maintenance mode.</span></span>
    
   - <span data-ttu-id="4e1d1-217">运行以下 cmdlet 以重置证书颁发机构证书和所有内部服务器证书并创建相应的新证书：</span><span class="sxs-lookup"><span data-stu-id="4e1d1-217">Run the following cmdlets to reset and create new certification authority certificates and all internal server certificates:</span></span>
    
     <span data-ttu-id="4e1d1-218">对于云连接器 2.0 之前的版本：</span><span class="sxs-lookup"><span data-stu-id="4e1d1-218">For Cloud Connector releases before 2.0:</span></span>
    
     ```
     Reset-CcCACertificate
     Renew-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

     <span data-ttu-id="4e1d1-219">或云连接器版本 2.0 及更高版本：</span><span class="sxs-lookup"><span data-stu-id="4e1d1-219">Or for Cloud Connector release 2.0 and later:</span></span>
    
     ```
     Reset-CcCACertificate
     Update-CcServerCertificate
     Remove-CcLegacyServerCertificate 
     ```

   - <span data-ttu-id="4e1d1-220">在第一个设备，运行以下 cmdlet，以备份到的 CA 文件\<SiteRoot\>文件夹。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-220">On the first appliance, run the following cmdlet to back up the CA files to the \<SiteRoot\> folder.</span></span> <span data-ttu-id="4e1d1-221">更高版本，在同一站点中的所有其他设备，重置 CcCACertificate cmdlet 将自动使用 CA 备份文件，设备将使用相同的根证书。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-221">Later, on all other appliances in the same site, the Reset-CcCACertificate cmdlet will consume the CA backup files automatically and appliances will use the same root certificate.</span></span>
    
     ```
     Backup-CcCertificationAuthority
     ```

   - <span data-ttu-id="4e1d1-222">运行退出 CcUpdate cmdlet 启动服务并退出维护模式。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-222">Run the Exit-CcUpdate cmdlet to start services and exit maintenance mode.</span></span> 
    
   - <span data-ttu-id="4e1d1-223">如果网关和中介服务器之间使用 TLS，则从网站中的任意设备运行导出 CcRootCertificate cmdlet，然后将导出的证书安装到 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-223">If TLS is used between the gateway and the Mediation Server, run the Export-CcRootCertificate cmdlet from any appliance in the site, and then install the exported certificate to your PSTN gateways.</span></span> 
    
- <span data-ttu-id="4e1d1-224">**问题： 您在云中连接器管理服务日志"C:\Program Files\Skype 的业务云连接器 Edition\ManagementService\CceManagementService.log"中收到以下错误消息： CceService 错误： 0： 意外的异常时向联机报告状态： System.Management.Automation.CmdletInvocationException: 用户登录失败\<全局租户管理员\>。请创建一个新的凭据对象，并确保您已经使用正确的用户名和密码。---\>**</span><span class="sxs-lookup"><span data-stu-id="4e1d1-224">**Issue: You receive the following error message in the Cloud Connector Management Service Log, "C:\Program Files\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log": CceService Error: 0 : Unexpected exception when reporting status to online: System.Management.Automation.CmdletInvocationException: Logon failed for the user \<Global Tenant Admin\>. Please create a new credential object, making sure that you have used the correct user name and password. ---\>**</span></span>
    
    <span data-ttu-id="4e1d1-225">**解决方法：** 由于注册云连接器装置已更改的 Office 365 全局租户管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-225">**Resolution:** The Office 365 global tenant admin credentials have been changed since the Cloud Connector appliance was registered.</span></span> <span data-ttu-id="4e1d1-226">若要更新云连接器装置上本地存储的凭据，运行以下命令从管理员 PowerShell 主机装置上：</span><span class="sxs-lookup"><span data-stu-id="4e1d1-226">To update the locally stored credentials on the Cloud Connector appliance, run the following from Administrator PowerShell on the host appliance:</span></span>
    
  ```
  Set-CcCredential -AccountType TenantAdmin
  ```

- <span data-ttu-id="4e1d1-227">**问题： 更改用于部署的主机服务器帐户的密码后，您收到以下错误消息:"ConvertTo SecureString： 密钥无效用于指定状态。"中的商业云连接器 %ProgramFiles%\SkypeEdition\ManagementService\CceManagementService.log 或同时运行 Get CcCredential cmdlet。**</span><span class="sxs-lookup"><span data-stu-id="4e1d1-227">**Issue: After you change the password for the host server account you used for the deployment, you receive the following error message: "ConvertTo-SecureString : Key not valid for use in specified state." in %ProgramFiles%\Skype for Business Cloud Connector Edition\ManagementService\CceManagementService.log or while running the Get-CcCredential cmdlet.**</span></span>
    
    <span data-ttu-id="4e1d1-228">**解决方法：** 所有云连接器凭据都存储在以下文件:"%systemdrive%\programdata\cloudconnector\credentials。\<CurrentUser\>.xml"。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-228">**Resolution:** All Cloud Connector credentials are stored in the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span> <span data-ttu-id="4e1d1-229">当主机服务器上的密码更改时，需要更新本地存储的凭据。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-229">When the password on the host server changes, you will need to update the locally stored credentials.</span></span>
    
    <span data-ttu-id="4e1d1-230">**如果你运行的是云连接器 1.4.2 版，** 请通过执行以下步骤来重新生成所有云连接器密码：</span><span class="sxs-lookup"><span data-stu-id="4e1d1-230">**If you are running Cloud Connector version 1.4.2,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  1. <span data-ttu-id="4e1d1-231">重新启动主机服务器。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-231">Restart the host server.</span></span>
    
  2. <span data-ttu-id="4e1d1-232">删除以下文件:"%systemdrive%\programdata\cloudconnector\credentials。\<CurrentUser\>.xml"。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-232">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml".</span></span>
    
  3. <span data-ttu-id="4e1d1-233">启动作为管理员，PowerShell 控制台，然后运行"注册 CcAppliance-本地"以重新输入以下说明的密码。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-233">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> <span data-ttu-id="4e1d1-234">输入之前输入的用于云连接器部署的相同密码。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-234">Enter the same passwords you entered before for the Cloud Connector deployment.</span></span>
    
     <span data-ttu-id="4e1d1-235">**如果您运行的云连接器版本 2.0 或更高版本，** 重新生成所有云连接器密码，按照以下步骤：</span><span class="sxs-lookup"><span data-stu-id="4e1d1-235">**If you are running Cloud Connector version 2.0 or later,** regenerate all Cloud Connector passwords by following these steps:</span></span>
    
  4. <span data-ttu-id="4e1d1-236">重新启动主机服务器。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-236">Restart the host server.</span></span>
    
  5. <span data-ttu-id="4e1d1-237">删除以下文件:"%systemdrive%\programdata\cloudconnector\credentials。\<CurrentUser\>.xml"。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-237">Delete the following file: "%SystemDrive%\Programdata\Cloudconnector\credentials.\<CurrentUser\>.xml" .</span></span>
    
  6. <span data-ttu-id="4e1d1-238">启动作为管理员，PowerShell 控制台，然后运行"注册 CcAppliance-本地"以重新输入以下说明的密码。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-238">Launch a PowerShell console as administrator, and then run "Register-CcAppliance -Local" to re-enter the passwords following the description.</span></span> 
    
     <span data-ttu-id="4e1d1-p127">如果缓存的密码文件是用云连接器 1.4.2 版生成的，请在系统提示时将 VMAdmin 密码用作 CceService 密码。输入之前用于云连接器部署的所有其他帐户的相同密码。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-p127">If the cached password file was generated with Cloud Connector version 1.4.2, use the VMAdmin password for the CceService password when prompted. Enter the same password you entered before for the Cloud Connector deployment for all other accounts.</span></span>
    
     <span data-ttu-id="4e1d1-241">如果缓存的密码文件是用云连接器 1.4.2 版生成的，并且 DomainAdmin 和 VMAdmin 密码不同，则必须执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="4e1d1-241">If the cached password file was generated with Cloud Connector version 1.4.2 and the DomainAdmin and VMAdmin passwords are different, you must perform the following steps:</span></span>
    
  7. <span data-ttu-id="4e1d1-242">按如下所述运行 Set-CcCredential -AccountType DomainAdmin：</span><span class="sxs-lookup"><span data-stu-id="4e1d1-242">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
  8. <span data-ttu-id="4e1d1-243">当系统提示输入旧帐户凭据时，请输入用于 CceService 密码的凭据。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-243">When prompted for the old account credential, enter the credential you used for the CceService password.</span></span>
    
  9. <span data-ttu-id="4e1d1-244">当系统提示输入新帐户凭据时，请输入之前用于 DomainAdmin 密码的密码。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-244">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
     <span data-ttu-id="4e1d1-245">如果缓存的密码文件生成使用云连接器版本 2.0 或更高版本，默认情况下，VmAdmin 和 DomainAdmin 作为 CceService 使用相同的密码。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-245">If the cached password file was generated with Cloud Connector version 2.0 or later, by default, VmAdmin and DomainAdmin use the same password as CceService.</span></span> <span data-ttu-id="4e1d1-246">如果更改了 DomainAdmin 和 VMAdmin 密码，则必须执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="4e1d1-246">If you changed the DomainAdmin and VMAdmin passwords, you must perform the following steps:</span></span>
    
  10. <span data-ttu-id="4e1d1-247">按如下所述运行 Set-CcCredential -AccountType DomainAdmin：</span><span class="sxs-lookup"><span data-stu-id="4e1d1-247">Run Set-CcCredential -AccountType DomainAdmin as follows:</span></span>
    
       1. <span data-ttu-id="4e1d1-248">当系统提示输入旧帐户凭据时，请输入用于 CceService 密码的凭据。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-248">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="4e1d1-249">当系统提示输入新帐户凭据时，请输入之前用于 DomainAdmin 密码的密码。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-249">When prompted for the new account credential, enter the password for the DomainAdmin password you used before.</span></span>
    
  11. <span data-ttu-id="4e1d1-250">按如下所述运行 Set-CcCredential -AccountType VmAdmin：</span><span class="sxs-lookup"><span data-stu-id="4e1d1-250">Run Set-CcCredential -AccountType VmAdmin as follows:</span></span>
    
       1. <span data-ttu-id="4e1d1-251">当系统提示输入旧帐户凭据时，请输入用于 CceService 密码的凭据。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-251">When prompted for the old account credential, enter the credential you used for the CceService password</span></span>
    
       2. <span data-ttu-id="4e1d1-252">当系统提示输入新帐户凭据时，请输入之前用于 VmAdmin 密码的密码。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-252">When prompted for the new account credential, enter the password for the VmAdmin password you used before.</span></span> 
    
- <span data-ttu-id="4e1d1-253">**问题： 云连接器 2.1 及更高版本，设备上运行注册 CcAppliance 或其他 cmdlet 时您会收到一条错误消息如:"为每个对象: 常用找不到此对象的属性。验证属性存在。在 C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 字符： 14"**</span><span class="sxs-lookup"><span data-stu-id="4e1d1-253">**Issue: With Cloud Connector version 2.1 and later, when running Register-CcAppliance or other cmdlets on the appliance, you receive an error message such as: "For Each-Object : The property 'Common' cannot be found on this object. Verify that the property exists. At C:\Program Files\WindowsPowerShell\Modules\CloudConnector\Internal\MtHostCommon.ps1:681 char:14"**</span></span>
    
    <span data-ttu-id="4e1d1-254">**解决方法：** 云连接器 2.1 和更高版本需要.NET Framework 4.6.1 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-254">**Resolution:** Cloud Connector 2.1 and later requires .NET Framework 4.6.1 or later.</span></span> <span data-ttu-id="4e1d1-255">请.NET Framework 更新至版本 4.6.1 设备上或更高版本，然后再次运行 cmdlet(s)。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-255">Please update .NET Framework on the appliance to version 4.6.1 or later and run the cmdlet(s) again.</span></span>

- <span data-ttu-id="4e1d1-256">**问题： 云连接器 Edition 2.1，运行安装 CcAppliance 时，您会收到一条错误消息如:"安装错误的新实例失败： 无法设置"状态"，因为仅字符串可用作值来设置 XmlNode 属性"**</span><span class="sxs-lookup"><span data-stu-id="4e1d1-256">**Issue: With Cloud Connector Edition 2.1, when running Install-CcAppliance, you receive an error message such as: "Failed to install new instance with error: Cannot set "State" because only strings can be used as values to set XmlNode properties"**</span></span>

   <span data-ttu-id="4e1d1-257">**解决方法：** 在 Cloudconnector.ini 下 [常见] 部分，, 请添加"State"配置，如下所示： 国家/地区代码 = 美国状态 = WA 市/县 = 雷德蒙德</span><span class="sxs-lookup"><span data-stu-id="4e1d1-257">**Resolution:** In Cloudconnector.ini, under the [Common] section, please add the “State” config as below:  CountryCode=US  State=WA  City=Redmond</span></span>

   <span data-ttu-id="4e1d1-258">就不强制"State"行具有值，但不能从 Cloudconnector.ini 文件中删除"State"行。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-258">It is not mandatory for the "State" line to have value, however the "State" line cannot be removed from the Cloudconnector.ini file.</span></span>

- <span data-ttu-id="4e1d1-259">**问题： 您将收到以下错误消息"卸除 WindowsImage： 卸除 WindowsImage 失败。错误代码 = 0xc1550115"安装或升级云连接器 Edition 时。**</span><span class="sxs-lookup"><span data-stu-id="4e1d1-259">**Issue: You receive the following error message "Dismount-WindowsImage : Dismount-WindowsImage failed. Error code = 0xc1550115" when installing or upgrading Cloud Connector Edition.**</span></span>
    
    <span data-ttu-id="4e1d1-260">**解决方法：** 启动 PowerShell 控制台，请以管理员身份运行"DISM-清理-Wim'"。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-260">**Resolution:** Launch a PowerShell console as administrator, run "DISM -Cleanup-Wim'".</span></span> <span data-ttu-id="4e1d1-261">这将清除所有故障的图像。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-261">This will clean up all troubled images.</span></span> <span data-ttu-id="4e1d1-262">再次运行安装 CcAppliance 或等待的位自动升级。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-262">Run Install-CcAppliance again or wait for the bits to automatically upgrade.</span></span>
    
- <span data-ttu-id="4e1d1-263">**问题： HA 环境中的第一个云连接器装置的部署失败**</span><span class="sxs-lookup"><span data-stu-id="4e1d1-263">**Issue: Deployment of the first Cloud Connector appliance in an HA environment fails**</span></span>
    
    <span data-ttu-id="4e1d1-264">**解决方法：** 您采取的步骤取决于部署失败的原因：</span><span class="sxs-lookup"><span data-stu-id="4e1d1-264">**Resolution:** The steps you take depend on the reason the deployment failed:</span></span>
    
  - <span data-ttu-id="4e1d1-265">如果第一个云连接器装置失败，并且无法确定失败的原因，您必须部署成功，直到重新安装设备，然后安装其他设备。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-265">If the first Cloud Connector appliance fails and you cannot determine the reason for the failure, you must install the appliance again until the deployment is successful, and then install the other appliances.</span></span>
    
  - <span data-ttu-id="4e1d1-266">如果第一个云连接器装置操作失败，次要问题，例如外部证书问题，您可能能够解决问题，但不重新安装设备。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-266">If the first Cloud Connector appliance fails with a minor issue, such as an external certificate issue, you might be able to fix the problem without re-installing the appliance.</span></span> <span data-ttu-id="4e1d1-267">您还可以然后使用租户远程 PowerShell，可以将标记为成功部署，如下所示。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-267">You can then use tenant remote PowerShell to mark the deployment as successful as follows.</span></span> <span data-ttu-id="4e1d1-268">（您可以使用以下步骤在首次部署已成功，但由于某种原因，云连接器失败时报告为成功部署如果。）</span><span class="sxs-lookup"><span data-stu-id="4e1d1-268">(You can also use the following steps if the first deployment was successful, but, for some reason, Cloud Connector fails to report the deployment as a success.)</span></span>
    
  - <span data-ttu-id="4e1d1-269">若要获取的第一个云连接器装置标识 (GUID)，请运行 Get CsHybridPSTNAppliance cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-269">To get the Identity (GUID) of the first Cloud Connector appliance, run the Get-CsHybridPSTNAppliance cmdlet.</span></span>
    
  - <span data-ttu-id="4e1d1-270">要将标记为已成功部署设备，请运行设置 CsCceApplianceDeploymentStatus，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4e1d1-270">To mark the appliance as successfully deployed, run the Set-CsCceApplianceDeploymentStatus as follows:</span></span>
    
  ```
  Set-CsCceApplianceDeploymentStatus -Identity <Appliance Identity GUID> -Action Deploy -Status Finished
  ```

- <span data-ttu-id="4e1d1-271">**问题：你需要在主机服务器或虚拟机上手动检查并安装 Windows 更新。**</span><span class="sxs-lookup"><span data-stu-id="4e1d1-271">**Issue: You need to check for and install Windows updates manually on the host server or virtual machines.**</span></span>
    
   <span data-ttu-id="4e1d1-p132">**解决方法：** 建议你利用 Skype for Business 云连接器版本提供的操作系统自动更新。当设备经过注册以实现联机管理并且启用了操作系统自动更新之后，主机服务器和虚拟机将根据操作系统更新时间窗口设置自动检查并安装 Windows 更新。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-p132">**Resolution:** We recommend that you take advantage of automated OS updates provided by Skype for Business Cloud Connector Edition. After an appliance is registered for online management and auto OS update is enabled, the host server and virtual machines will check and install Windows Updates automatically according to the OS update time window settings.</span></span>
    
   <span data-ttu-id="4e1d1-p133">如果你需要手动检查并安装 Windows 更新，请按照本节提供的适用于你的部署类型的步骤操作。你需要同时规划主机服务器及其上运行的虚拟机的更新，以便尽可能降低更新所需要的总停机时间。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-p133">If you need to check for and install Windows Updates manually, follow the steps in this section that apply to your type of deployment. You should plan on updating both the host server and the virtual machines running on it at the same time to minimize the amount of down time necessary for the updates.</span></span>
    
   <span data-ttu-id="4e1d1-p134">如果你愿意，可以使用 Windows Server 更新服务 (WSUS) 服务器向云连接器服务器提供更新。只需确保将 Windows 更新配置为**不要**自动安装即可。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-p134">If you prefer, you can use a Windows Server Update Services (WSUS) server to provide updates to Cloud Connector servers. Just be sure to configure the Windows Update to **not** install automatically.</span></span>
    
   <span data-ttu-id="4e1d1-278">有关如何手动更新云连接器部署的信息，请参阅下节。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-278">For information about how to manually update your Cloud Connector deployment, see the following section.</span></span>
    
- <span data-ttu-id="4e1d1-279">**问题： 当云连接器更新为新版本时，云连接器 cmdlet 不会更新。**</span><span class="sxs-lookup"><span data-stu-id="4e1d1-279">**Issue: When Cloud Connector updates to a new build, Cloud Connector cmdlets are not updated.**</span></span> <span data-ttu-id="4e1d1-280">只有在 PowerShell 窗口处于打开状态时自动更新，发生此事件时，有时会出现此问题。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-280">This sometimes happens if a PowerShell window is left open when automatic update occurs.</span></span>
    
  <span data-ttu-id="4e1d1-281">**解决方法：** 若要加载的更新的 cmdlet，可以执行以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="4e1d1-281">**Resolution:** To load the updated cmdlets, you can do either of the following steps:</span></span>
    
   - <span data-ttu-id="4e1d1-282">云连接器装置上, 关闭 PowerShell，然后重新打开 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-282">Close PowerShell on the Cloud Connector appliance, and then reopen PowerShell.</span></span>
    
     - <span data-ttu-id="4e1d1-283">或者，您可以运行导入模块 CloudConnector-Force。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-283">Or, you can run Import-Module CloudConnector -Force.</span></span> 
 
-   <span data-ttu-id="4e1d1-284">**问题:"术语 Stop-cswindowsservice 无法识别为名称 cmdlet、 函数、 脚本文件，或可操作的程序。"错误时尝试运行 Enter CcUpdate cmdlet。**</span><span class="sxs-lookup"><span data-stu-id="4e1d1-284">**Issue: "The term 'Stop-CsWindowsService' is not recognized as the name of a cmdlet, function, script file, or operable program." error when attempting to run Enter-CcUpdate cmdlet.**</span></span>

    <span data-ttu-id="4e1d1-285">**解决方法：** 删除 $HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache 文件。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-285">**Resolution:** Delete the $HOME\AppData\Local\Microsoft\Windows\PowerShell\ModuleAnalysisCache file.</span></span>
<span data-ttu-id="4e1d1-286">PowerShell cmdlet，以使它不需要为每次重新分析所有模块发现使事项真正慢的模块中的缓存作为创建此文件。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-286">PowerShell creates this file as a cache of cmdlets from modules that it finds so that it doesn’t have to re-analyze all the modules each time as that would make things really slow.</span></span> <span data-ttu-id="4e1d1-287">很可能有 PowerShell 提供令人误解的结果时它已返回从该缓存中读取某些文件损坏。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-287">Most likely, there was some file corruption that provided misleading results to PowerShell when it was reading back from that cache.</span></span>

-   <span data-ttu-id="4e1d1-288">**问题:"导入模块 CloudConnector"将生成错误"导入模块： 指定的模块"CloudConnector"未加载，因为在任何模块目录中不找到任何有效的模块文件"**</span><span class="sxs-lookup"><span data-stu-id="4e1d1-288">**Issue: “Import-Module CloudConnector” generates error “Import-Module: The specified module “CloudConnector” was not loaded because no valid module file was found in any module directory”**</span></span>

    <span data-ttu-id="4e1d1-289">**解决方法：**</span><span class="sxs-lookup"><span data-stu-id="4e1d1-289">**Resolution:**</span></span>
    - <span data-ttu-id="4e1d1-290">验证确实 CloudConnector 模块存在下 c:\Program Files\WindowsPowerShell\Modules</span><span class="sxs-lookup"><span data-stu-id="4e1d1-290">Validate that indeed the CloudConnector module exists under c:\Program Files\WindowsPowerShell\Modules</span></span>
    
    - <span data-ttu-id="4e1d1-291">在此位置下存在验证该 CloudConnector 模块后，可以更改 PSModulePath 环境变量存储模块的位置的路径：</span><span class="sxs-lookup"><span data-stu-id="4e1d1-291">After validating that CloudConnector module exists under this location, the PSModulePath environment variable storing the path to the locations of the modules can be changed:</span></span>
    
     <span data-ttu-id="4e1d1-292">a.</span><span class="sxs-lookup"><span data-stu-id="4e1d1-292">a.</span></span> <span data-ttu-id="4e1d1-293">临时更改： 开始 Powershell 作为管理员，并运行以下命令： $env: PSModulePath = $env: PSModulePath +";C:\Program Files\WindowsPowerShell\Modules\"</span><span class="sxs-lookup"><span data-stu-id="4e1d1-293">Temporary change: Start Powershell as an Administrator and run the following command: $env:PSModulePath = $env:PSModulePath + ";C:\Program Files\WindowsPowerShell\Modules\"</span></span>
        
     <span data-ttu-id="4e1d1-294">b.</span><span class="sxs-lookup"><span data-stu-id="4e1d1-294">b.</span></span> <span data-ttu-id="4e1d1-295">持久的更改，启动的 PowerShell 作为管理员，并运行以下命令，逐个： $CurrentValue = [环境]:: GetEnvironmentVariable("PSModulePath","Machine") SetEnvironmentVariable("PSModulePath", $CurrentValue +";C:\Program Files\WindowsPowerShell\Modules"，"计算机")</span><span class="sxs-lookup"><span data-stu-id="4e1d1-295">For persistent change, Start PowerShell as an Administrator and run the following commands, one by one: $CurrentValue = [Environment]::GetEnvironmentVariable("PSModulePath", "Machine") SetEnvironmentVariable("PSModulePath", $CurrentValue + "; C:\Program Files\WindowsPowerShell\Modules", "Machine")</span></span>

    
## <a name="install-windows-updates-manually"></a><span data-ttu-id="4e1d1-296">手动安装 Windows 更新</span><span class="sxs-lookup"><span data-stu-id="4e1d1-296">Install Windows updates manually</span></span>

<span data-ttu-id="4e1d1-297">如果你不想在自己的环境中使用自动更新，请按照以下步骤操作，以手动检查并应用 Windows 更新。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-297">If you do not want to use automatic updates in your environment, follow these steps to manually check for and apply Windows updates.</span></span> <span data-ttu-id="4e1d1-298">检查并安装 Windows 更新可能需要重新启动服务器。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-298">Checking for and installing Windows updates may require a server restart.</span></span> <span data-ttu-id="4e1d1-299">时重新启动的主服务器，用户不能使用云连接器来发出或接收呼叫。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-299">When a host server is restarting, users will not be able to use Cloud Connector to place or receive calls.</span></span> <span data-ttu-id="4e1d1-300">你可以手动检查并安装更新，以控制更新发生时间，然后根据需要在你选择的时间重新启动计算机，以避免服务中断。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-300">You can manually check for and install updates to control when the updates take place, and then restart the machines as needed during times you choose to avoid disruption of services.</span></span>
  
<span data-ttu-id="4e1d1-301">要手动检查更新，请连接到每台主机服务器，并打开“**控制面板**”。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-301">To manually check for updates, connect to each host server and open the **Control Panel**.</span></span> <span data-ttu-id="4e1d1-302">选中**系统和安全\>Windows Update**，然后管理的更新和服务器重新启动，适用于您的环境。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-302">Select **System and Security \>Windows Update**, and then manage the updates and server restarts as appropriate for your environment.</span></span>
  
- <span data-ttu-id="4e1d1-303">如果站点中只有一个设备，请连接到每个虚拟机，并打开“**控制面板**”。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-303">If there is only one appliance in the site, connect to each virtual machine and open the **Control Panel**.</span></span> <span data-ttu-id="4e1d1-304">选中**系统和安全\>Windows Update**，然后配置更新，并根据需要重新启动服务器。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-304">Select **System and Security \>Windows Update**, and then configure the updates and server restarts as appropriate.</span></span>
    
- <span data-ttu-id="4e1d1-p142">如果站点中有多个设备，更新期间用户将无法访问正在更新和重新启动的实例。用户将连接到部署中的其他实例，直到更新完成后所有虚拟机及虚拟机上的所有 Skype for Business 服务启动为止。为避免任何潜在的服务中断，可以在应用更新时从 HA 删除实例，然后在完成后将其还原。为此：</span><span class="sxs-lookup"><span data-stu-id="4e1d1-p142">If there are more than one appliance in the site, the instance being updated and restarted cannot be accessed by users during the updates. Users will connect to other instances in the deployment until all virtual machines and all Skype for Business services start on the virtual machines after the updates are completed. To avoid any potential disruption to service, you can remove the instance from HA while you apply the updates, and then restore it when complete. To do so:</span></span>
    
1. <span data-ttu-id="4e1d1-309">在每台主机服务器上，以管理员身份打开 PowerShell 控制台。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-309">On each host server, open a PowerShell console as administrator.</span></span>
    
2. <span data-ttu-id="4e1d1-310">使用以下 cmdlet 从 HA 删除实例：</span><span class="sxs-lookup"><span data-stu-id="4e1d1-310">Remove the instance from HA with the following cmdlet:</span></span>
    
   ```
   Enter-CcUpdate
   ```

3. 
    
    <span data-ttu-id="4e1d1-311">按照适用于单个实例的步骤，手动应用更新并重新启动虚拟机。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-311">Follow the steps for a single instance to manually apply the updates and restart the virtual machine.</span></span>
    
4. <span data-ttu-id="4e1d1-312">使用以下 cmdlet 将实例重新设置为 HA：</span><span class="sxs-lookup"><span data-stu-id="4e1d1-312">Set the instance back to HA with the following cmdlet:</span></span>
    
   ```
   Exit-CcUpdate
   ```

<span data-ttu-id="4e1d1-313">对于多站点部署，请为部署中的每个站点执行适用于单个站点的步骤，每次向一个站点应用更新。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-313">For multi-site deployments, follow the steps for a single site for each site in the deployment, applying updates to one site at a time.</span></span>
  
## <a name="tips-when-installing-anti-virus-software-on-the-cloud-connector-host-machine"></a><span data-ttu-id="4e1d1-314">云连接器主机计算机上安装防病毒软件时的提示</span><span class="sxs-lookup"><span data-stu-id="4e1d1-314">Tips when installing anti-virus software on the Cloud Connector host machine</span></span>

<span data-ttu-id="4e1d1-315">如果您需要在云连接器主机计算机上安装防病毒软件，您需要添加以下排除：</span><span class="sxs-lookup"><span data-stu-id="4e1d1-315">If you need to install anti-virus software on the Cloud Connector host machine, you need to add the following exclusions:</span></span>
  
- <span data-ttu-id="4e1d1-316">每台计算机上的本地装置目录。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-316">Local Appliance Directory on each machine.</span></span>
    
- <span data-ttu-id="4e1d1-317">每台计算机上的远程网站目录。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-317">Remote Site Directory on each machine.</span></span>
    
- <span data-ttu-id="4e1d1-318">在计算机上的本地网站目录承载共享的网站根文件夹。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-318">Local Site Directory on the machine hosts the shared site root folder.</span></span>
    
- <span data-ttu-id="4e1d1-319">对于业务云连接器 Edition %ProgramFiles%\Skype</span><span class="sxs-lookup"><span data-stu-id="4e1d1-319">%ProgramFiles%\Skype for Business Cloud Connector Edition</span></span>
    
- <span data-ttu-id="4e1d1-320">%ALLUSERSPROFILE%\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="4e1d1-320">%ALLUSERSPROFILE%\CloudConnector</span></span>
    
- <span data-ttu-id="4e1d1-321">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span><span class="sxs-lookup"><span data-stu-id="4e1d1-321">%ProgramFiles%\WindowsPowerShell\Modules\CloudConnector</span></span>
    
- <span data-ttu-id="4e1d1-322">Microsoft.Rtc.CCE.ManagementService.exe 过程。</span><span class="sxs-lookup"><span data-stu-id="4e1d1-322">The process Microsoft.Rtc.CCE.ManagementService.exe.</span></span>
