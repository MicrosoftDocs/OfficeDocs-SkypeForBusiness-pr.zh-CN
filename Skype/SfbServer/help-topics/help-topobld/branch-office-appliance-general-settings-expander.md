---
title: 分支机构设备常规设置扩展器
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.BranchOfficeApplianceGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 86860416-7c9b-49af-b9d2-658c172852de
description: 若要编辑现有 Survivable Branch Appliance 或 Survivable Branch Server 的设置，可参考以下各节内容：
ms.openlocfilehash: 8994bb04234242021149f1155fde8dfa0b62a223
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "21000982"
---
# <a name="branch-office-appliance-general-settings-expander"></a><span data-ttu-id="617d8-103">分支机构设备常规设置扩展器</span><span class="sxs-lookup"><span data-stu-id="617d8-103">Branch Office Appliance General Settings Expander</span></span>
 
<span data-ttu-id="617d8-104">若要编辑现有 Survivable Branch Appliance 或 Survivable Branch Server 的设置，可参考以下各节内容：</span><span class="sxs-lookup"><span data-stu-id="617d8-104">To edit the settings for an existing Survivable Branch Appliance or Survivable Branch Server, you are presented with the following sections:</span></span>
  
- <span data-ttu-id="617d8-105">常规设置</span><span class="sxs-lookup"><span data-stu-id="617d8-105">General settings</span></span>
    
- <span data-ttu-id="617d8-106">复原设置</span><span class="sxs-lookup"><span data-stu-id="617d8-106">Resiliency settings</span></span>
    
- <span data-ttu-id="617d8-107">中介服务器设置</span><span class="sxs-lookup"><span data-stu-id="617d8-107">Mediation Server settings</span></span>
    


<span data-ttu-id="617d8-108">对于 Survivable Branch Appliance 或 Survivable Branch Server，可参考以下：</span><span class="sxs-lookup"><span data-stu-id="617d8-108">For a Survivable Branch Appliance or Survivable Branch Server, you are presented with the following:</span></span>
  
## <a name="general-settings"></a><span data-ttu-id="617d8-109">常规设置</span><span class="sxs-lookup"><span data-stu-id="617d8-109">General settings</span></span>

<span data-ttu-id="617d8-110">Survivable Branch Appliance 或 Survivable Branch Server 的完全限定域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="617d8-110">The fully qualified domain name (FQDN) of the Survivable Branch Appliance or Survivable Branch Server.</span></span> <span data-ttu-id="617d8-111">编辑服务器的 FQDN 以更改该值。</span><span class="sxs-lookup"><span data-stu-id="617d8-111">Edit the FQDN of the server to change the value.</span></span> <span data-ttu-id="617d8-112">必须具有与新值一致的域名系统 (DNS) 主机 (A) 记录。</span><span class="sxs-lookup"><span data-stu-id="617d8-112">You must have a Domain Name System (DNS) host (A) record that coincides with the new value.</span></span>
  
<span data-ttu-id="617d8-p102">您可以选择“**使用所有已配置的 IP 地址**”或“**将服务用途限制为所选 IP 地址**”。如果选择“**将服务用途限制为所选 IP 地址**”，则需要定义服务器用于除公用电话交换网 (PSTN) 网关外的所有通信的主 IP 地址。需要定义单独的 IP 地址用于 PSTN。</span><span class="sxs-lookup"><span data-stu-id="617d8-p102">You can select to **Use all configured IP addresses** or to **Limit service usage to selected IP addresses**. If you select to **Limit the service to defined IP addresses**, you will define the primary IP address that the server will use for all communications, except for the public switched telephone network (PSTN) gateway. You define a separate IP address for PSTN usage.</span></span>
  
<span data-ttu-id="617d8-116">在“**关联**”中，可以编辑或指定以下内容：</span><span class="sxs-lookup"><span data-stu-id="617d8-116">In **Associations**, you can edit or specify the following:</span></span>
  
- <span data-ttu-id="617d8-117">关联存档服务器，可以选择此选项可将存档服务器与 Survivable Branch Appliance 或 Survivable Branch Server 关联。</span><span class="sxs-lookup"><span data-stu-id="617d8-117">Associate Archiving Server enables you to select to associate an Archiving Server with the Survivable Branch Appliance or Survivable Branch Server.</span></span> <span data-ttu-id="617d8-118">可以通过从下拉列表中，选择服务器选择从已定义存档服务器，或单击**新建**以指定新的存档服务器。</span><span class="sxs-lookup"><span data-stu-id="617d8-118">You can select from an already defined Archiving Server by selecting the server from the drop-down list, or click **New** to specify a new Archiving Server.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="617d8-119">发布新定义的拓扑之前，所指定的服务器必须存在并已加入到域。</span><span class="sxs-lookup"><span data-stu-id="617d8-119">Before publishing the newly defined topology, the server that you specify must exist and must be joined to the domain.</span></span> 
  
- <span data-ttu-id="617d8-120">关联监控服务器，可以选择此选项可将监控服务器与 Survivable Branch Appliance 或 Survivable Branch Server 关联。</span><span class="sxs-lookup"><span data-stu-id="617d8-120">Associate Monitoring Server allows you to select to associate a Monitoring Server with the Survivable Branch Appliance or Survivable Branch Server.</span></span> <span data-ttu-id="617d8-121">您可以通过从下拉列表中，选择服务器选择从已定义监控服务器，或单击**新建**以指定新的监控服务器。</span><span class="sxs-lookup"><span data-stu-id="617d8-121">You can select from an already defined Monitoring Server by selecting the server from the drop-down list, or click **New** to specify a new Monitoring Server.</span></span>
    
- <span data-ttu-id="617d8-122">关联的边缘池，可以选择此选项可与 Survivable Branch Appliance 或 Survivable Branch Server 关联的边缘服务器或池。</span><span class="sxs-lookup"><span data-stu-id="617d8-122">Associate Edge pool enables you to select to associate an Edge Server or pool with the Survivable Branch Appliance or Survivable Branch Server.</span></span> <span data-ttu-id="617d8-123">通过从下拉列表中选择服务器，可以从已定义的边缘服务器或池中进行选择，或单击“**新建**”以指定新的边缘服务器或池。</span><span class="sxs-lookup"><span data-stu-id="617d8-123">You can select from an already defined Edge Server or pool by selecting the server from the drop-down list, or click **New** to specify a new Edge Server or pool.</span></span>
    
## <a name="resiliency"></a><span data-ttu-id="617d8-124">复原</span><span class="sxs-lookup"><span data-stu-id="617d8-124">Resiliency</span></span>

<span data-ttu-id="617d8-p106">复原为注册器池提供了高可用性。它提供了备份注册器，如果主注册器发生故障，备份注册器可以接管发生故障的注册器，允许用户登录和进行通信。用户可能会发现功能降低，具体取决于哪些系统的主注册器发生故障。</span><span class="sxs-lookup"><span data-stu-id="617d8-p106">Resiliency provides high availability for the Registrar pool. By providing a backup Registrar, if the primary Registrar fails, the backup Registrar can take over for the failed Registrar, enabling users to log on and communicate. There may be reduced functionality for users, depending on what systems have failed with the primary Registrar.</span></span>
  
<span data-ttu-id="617d8-128">从下拉列表中，选择 Enterprise Edition 前端池或 Standard Edition 前端服务器将充当 Survivable Branch Appliance 或 Survivable Branch Server 的备份注册器。</span><span class="sxs-lookup"><span data-stu-id="617d8-128">From the drop-down list, select the Enterprise Edition Front End pool or Standard Edition Front End Server that will act as the backup Registrar for the Survivable Branch Appliance or Survivable Branch Server.</span></span> <span data-ttu-id="617d8-129">还可以选择启用故障转移和回退时间间隔。</span><span class="sxs-lookup"><span data-stu-id="617d8-129">You can also select to enable Failover and Fallback time intervals.</span></span> <span data-ttu-id="617d8-130">启用故障转移和回退时间设置（以秒为单位指定）后，可自动检测发生故障的注册器，回退时间用于自动确定主注册器是否已备份以及是否可以接管注册器进程。</span><span class="sxs-lookup"><span data-stu-id="617d8-130">Enabling the failover and fallback time settings (specified in seconds) allows for the automatic detection of a failed Registrar, and a fallback time to allow for automatic determination that the primary is back up and can take over the Registrar process.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="617d8-131">定义故障检测和回退间隔时，应注意不要输入在注册器短时间内未做出响应的情况下会导致发生故障转移和回退的间隔。</span><span class="sxs-lookup"><span data-stu-id="617d8-131">When defining the failure detection and the fallback interval, be careful not to enter an interval that will cause the failover and fallback to occur if the Registrar fails to respond for a short period of time.</span></span> <span data-ttu-id="617d8-132">主注册器可能会在短时间内没有响应，这取决于池或服务器的加载状况。</span><span class="sxs-lookup"><span data-stu-id="617d8-132">It is possible that the primary Registrar may not respond for short periods of time, based on the loading of the pool or servers.</span></span> <span data-ttu-id="617d8-133">Survivable Branch Appliance 或 Survivable Branch Server 到池网站中或 Standard Edition 前端服务器的默认值为 120 秒故障转移和回退 240 秒。</span><span class="sxs-lookup"><span data-stu-id="617d8-133">The default values for a Survivable Branch Appliance or a Survivable Branch Server in a site to a pool or Standard Edition Front End Server is 120 seconds for failover and 240 seconds for fallback.</span></span> 
  
## <a name="mediation-server"></a><span data-ttu-id="617d8-134">中介服务器</span><span class="sxs-lookup"><span data-stu-id="617d8-134">Mediation Server</span></span>

<span data-ttu-id="617d8-135">对于“**中介服务器**”，可以指定以下内容：</span><span class="sxs-lookup"><span data-stu-id="617d8-135">For **Mediation Server** you can specify the following:</span></span>
  
<span data-ttu-id="617d8-136">由于中介服务器并置，**并置中介服务器启用**对应的复选框不可用 Survivable Branch Appliance 或 Survivable Branch Server 上。</span><span class="sxs-lookup"><span data-stu-id="617d8-136">The check box for **Collocated Mediation Server enabled** is not available on a Survivable Branch Appliance or Survivable Branch Server because the Mediation Server is collocated.</span></span>
  
<span data-ttu-id="617d8-137">在池服务器上为传输层安全性 (TLS) 定义侦听端口。</span><span class="sxs-lookup"><span data-stu-id="617d8-137">You define the listening port on the pool servers for Transport Layer Security (TLS).</span></span> <span data-ttu-id="617d8-138">默认情况下，此端口为 5067。</span><span class="sxs-lookup"><span data-stu-id="617d8-138">By default, this port is 5067.</span></span> <span data-ttu-id="617d8-139">如果选择“**启用 TCP 端口**”，则必须为并置的中介服务器定义 TCP 端口。</span><span class="sxs-lookup"><span data-stu-id="617d8-139">If you select **Enable TCP port**, you must define a TCP port for the collocated Mediation Server.</span></span> <span data-ttu-id="617d8-140">这是一个可选设置，您应该参考网关要求或 PSTN 要求以确定是否需要此设置。</span><span class="sxs-lookup"><span data-stu-id="617d8-140">This is an optional setting, and you should refer to the requirements of your gateway or PSTN requirements to determine if you need this.</span></span> <span data-ttu-id="617d8-141">默认情况下，TCP 端口值为 5068。</span><span class="sxs-lookup"><span data-stu-id="617d8-141">By default, the TCP port value is 5068.</span></span>
  
<span data-ttu-id="617d8-142">定义与并置的中介服务器关联的 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="617d8-142">You define PSTN gateways that are associated with the collocated Mediation Server.</span></span> <span data-ttu-id="617d8-143">如果已定义网关，它们将可用于与中介服务器相关联。</span><span class="sxs-lookup"><span data-stu-id="617d8-143">If you have already defined gateways, they will be available to associate with the Mediation Server.</span></span> <span data-ttu-id="617d8-144">如果尚未定义任何网关，但可以进行定义，则选择“**新建**”。</span><span class="sxs-lookup"><span data-stu-id="617d8-144">If you have not defined any gateways, but you have them available to define, you can select **New**.</span></span> <span data-ttu-id="617d8-145">您还可以删除为此中介服务器已配置的网关。</span><span class="sxs-lookup"><span data-stu-id="617d8-145">You can also remove gateways that are already configured for this Mediation Server.</span></span> <span data-ttu-id="617d8-146">选择相应的网关，然后单击“**删除**”。</span><span class="sxs-lookup"><span data-stu-id="617d8-146">Select the gateway, and then click **Remove**.</span></span>
  
<span data-ttu-id="617d8-147">如果您有多个网关与中介服务器相关联，关联的第一个网关将默认网关。</span><span class="sxs-lookup"><span data-stu-id="617d8-147">If you have more than one gateway associated with a Mediation Server, the first gateway associated will be the default gateway.</span></span> <span data-ttu-id="617d8-148">如果必须选择其他网关作为默认网关，请选择要设为默认值的网关，然后单击“**设为默认值**”。</span><span class="sxs-lookup"><span data-stu-id="617d8-148">If you must choose another gateway as the default gateway, select the gateway that you want to make the default, and click **Make Default**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="617d8-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="617d8-149">See also</span></span>

<span data-ttu-id="617d8-150">有关定义和配置 Survivable Branch Appliance 或 Survivable Branch Server 的设置的详细信息，请参阅[Branch-site Resiliency Solutions](http://technet.microsoft.com/library/1700f99b-709c-4e47-88eb-c0a5490e26e2.aspx)。</span><span class="sxs-lookup"><span data-stu-id="617d8-150">For details about defining and configuring the settings for the Survivable Branch Appliance or Survivable Branch Server, see [Branch-Site Resiliency Solutions](http://technet.microsoft.com/library/1700f99b-709c-4e47-88eb-c0a5490e26e2.aspx).</span></span>
  

