---
title: 前端常规设置扩展器
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FrontEndGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8a5f21d0-f6c8-4907-9958-5ca36f702542
description: 要编辑现有前端池或 Standard Edition Server 的设置，可参考以下各节内容：
ms.openlocfilehash: d992854753cf3b6c11481c0b3725d0e5bb30329b
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/20/2018
ms.locfileid: "19973071"
---
# <a name="front-end-general-settings-expander"></a><span data-ttu-id="e8f72-103">前端常规设置扩展器</span><span class="sxs-lookup"><span data-stu-id="e8f72-103">Front End General Settings Expander</span></span>
 
<span data-ttu-id="e8f72-104">要编辑现有前端池或 Standard Edition Server 的设置，可参考以下各节内容：</span><span class="sxs-lookup"><span data-stu-id="e8f72-104">To edit the settings for an existing Front End pool or Standard Edition server, you are presented with the following sections:</span></span>
  
- <span data-ttu-id="e8f72-105">常规设置</span><span class="sxs-lookup"><span data-stu-id="e8f72-105">General settings</span></span>
    
- <span data-ttu-id="e8f72-106">复原设置</span><span class="sxs-lookup"><span data-stu-id="e8f72-106">Resiliency settings</span></span>
    
- <span data-ttu-id="e8f72-107">Web 服务设置</span><span class="sxs-lookup"><span data-stu-id="e8f72-107">Web services settings</span></span>
    
- <span data-ttu-id="e8f72-108">中介服务器设置</span><span class="sxs-lookup"><span data-stu-id="e8f72-108">Mediation Server settings</span></span>
    
## <a name="front-end-pool"></a><span data-ttu-id="e8f72-109">前端池</span><span class="sxs-lookup"><span data-stu-id="e8f72-109">Front End pool</span></span>

<span data-ttu-id="e8f72-110">对于前端池，可以配置常规设置、复原设置、Web 服务设置和中介服务器设置。</span><span class="sxs-lookup"><span data-stu-id="e8f72-110">For a Front End pool, you can configure general, resiliency, web services, and Mediation Server settings.</span></span> <span data-ttu-id="e8f72-111">有关详细信息，请参阅以下子节中的信息。</span><span class="sxs-lookup"><span data-stu-id="e8f72-111">For details, see the information in the following subsections.</span></span> <span data-ttu-id="e8f72-112">有关定义和配置前端池设置的详细信息，请参阅[Deploying Mediation Servers and Defining Peers](http://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx)。</span><span class="sxs-lookup"><span data-stu-id="e8f72-112">For details about defining and configuring the settings for the Front End pool, see [Deploying Mediation Servers and Defining Peers](http://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).</span></span>
  
### <a name="general-settings"></a><span data-ttu-id="e8f72-113">常规设置</span><span class="sxs-lookup"><span data-stu-id="e8f72-113">General Settings</span></span>

<span data-ttu-id="e8f72-114">可以配置以下常规设置：</span><span class="sxs-lookup"><span data-stu-id="e8f72-114">You can configure the following general settings:</span></span>
  
- <span data-ttu-id="e8f72-p102">**FQDN**。编辑要更改的池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="e8f72-p102">**FQDN**. Edit the FQDN of the pool to change it.</span></span>
    
- <span data-ttu-id="e8f72-p103">**启用硬件负载平衡器监控端口**。选中该复选框并输入您的硬件负载平衡器将用于监控池服务器状态的端口号。</span><span class="sxs-lookup"><span data-stu-id="e8f72-p103">**Enable hardware load balancer monitoring port**. Select the check box and enter the port number that your Hardware Load Balancer will use to monitor the state of the pool servers.</span></span>
    
- <span data-ttu-id="e8f72-p104">在“**功能**”中，定义该池将并置的其他角色。可以配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="e8f72-p104">In **Features and Functionality**, define the additional roles that you want to collocate with this pool. You can configure the following settings:</span></span>
    
  - <span data-ttu-id="e8f72-p105">**会议**。包含音频、视频和应用程序共享。选择此选项后，您可以选择电话拨入式 (PSTN) 会议。可以在本节后面的“中介服务器设置”子节下指定并定义公用电话交换网 (PSTN) 网关。</span><span class="sxs-lookup"><span data-stu-id="e8f72-p105">**Conferencing**. Includes audio, video and application sharing. After you select this option, you can select Dial-in (PSTN) conferencing. You specify and define a public switched telephone network (PSTN) gateway in the "Mediation Server Settings" subsection later in this section.</span></span>
    
  - <span data-ttu-id="e8f72-125">**企业语音**。</span><span class="sxs-lookup"><span data-stu-id="e8f72-125">**Enterprise Voice**.</span></span> <span data-ttu-id="e8f72-126">启用业务客户端通过 IP 限定的话筒设备和 Skype 调用内部语音。</span><span class="sxs-lookup"><span data-stu-id="e8f72-126">Enables internal voice over IP calls to qualified handsets and devices and Skype for Business clients.</span></span> <span data-ttu-id="e8f72-127">若要启用外部呼叫功能，需要包含中介服务器。</span><span class="sxs-lookup"><span data-stu-id="e8f72-127">To enable external call capabilities, you need to include a Mediation Server.</span></span> <span data-ttu-id="e8f72-128">有关详细信息，请参阅本主题后面的“中介服务器”。</span><span class="sxs-lookup"><span data-stu-id="e8f72-128">For details, see "Mediation Server" later in this topic.</span></span>
    
- <span data-ttu-id="e8f72-129">在“**关联**”中，编辑或指定以下内容：</span><span class="sxs-lookup"><span data-stu-id="e8f72-129">In **Associations**, edit or specify the following:</span></span>
    
  - <span data-ttu-id="e8f72-p107">**SQL 存储**。修改现有 SQL Server 服务器或新建基于 SQL Server 的数据库以保存前端池数据库。可以从列表中选择新的 SQL Server 实例或通过单击“**新建**”创建新的条目。</span><span class="sxs-lookup"><span data-stu-id="e8f72-p107">**SQL Store**. Modify an existing SQL Server database or create a new SQL Server-based database to hold the Front End pool databases. You can select a new instance of SQL Server from the list or create a new entry by clicking **New**.</span></span>
    
    <span data-ttu-id="e8f72-p108">选择“**启用 SQL Server 存储镜像**”，然后选择要用于镜像的服务器。单击“**新建**”可创建新的 SQL Server 存储。</span><span class="sxs-lookup"><span data-stu-id="e8f72-p108">Select **Enable SQL Server store mirroring**, and then select the server to use for mirroring. Click **New** to create a new SQL Server store.</span></span>
    
    <span data-ttu-id="e8f72-p109">选择“**使用 SQL Server 镜像见证启用自动故障转移**”以选择将某台服务器用作镜像见证。单击“**新建**”可创建新的 SQL Server 存储。</span><span class="sxs-lookup"><span data-stu-id="e8f72-p109">Select **Use SQL Server mirroring witness to enable automatic failover** to select a server to use as a mirroring witness. Click **New** to create a new SQL Server store.</span></span>
    
  - <span data-ttu-id="e8f72-p110">**文件共享**。修改前端池正在使用的文件存储。通过从列表中选择，可以从已定义的文件存储中选择新的文件存储。单击“**新建**”可创建新的文件存储。</span><span class="sxs-lookup"><span data-stu-id="e8f72-p110">**File share**. Modify the file store that the Front End pool is using. You can select a new file store from those already defined by selecting it from the list. You can create a new file store by clicking **New**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="e8f72-141">发布新定义的拓扑之前，所指定的服务器必须存在并已加入到域。</span><span class="sxs-lookup"><span data-stu-id="e8f72-141">Before publishing the newly defined topology, the server that you specify must exist and be joined to the domain.</span></span> 
  
  - <span data-ttu-id="e8f72-p111">**存档**。将存档服务器存储与前端池关联。通过从列表中选择服务器，可以从已定义的存档 SQL Server 存储中进行选择，或单击“**新建**”以指定新的存档服务器。</span><span class="sxs-lookup"><span data-stu-id="e8f72-p111">**Archiving**. Associate an Archiving Server store with the Front End pool. You can select from an already defined Archiving SQL Server store by selecting the server from the list, or click **New** to specify a new Archiving Server.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="e8f72-145">发布新定义的拓扑之前，所指定的服务器必须存在并已加入到域。</span><span class="sxs-lookup"><span data-stu-id="e8f72-145">Before publishing the newly defined topology, the server that you specify must exist and be joined to the domain.</span></span> 
  
    <span data-ttu-id="e8f72-p112">选择“**启用 SQL Server 存储镜像**”，然后选择要用于镜像的服务器。单击“**新建**”可创建新的 SQL Server 存储。</span><span class="sxs-lookup"><span data-stu-id="e8f72-p112">Select **Enable SQL Server store mirroring**, and then select the server to use for mirroring. Click **New** to create a new SQL Server store.</span></span>
    
    <span data-ttu-id="e8f72-p113">选择“**使用 SQL Server 镜像见证启用自动故障转移**”以选择将某台服务器用作镜像见证。单击“**新建**”可创建新的 SQL Server 存储。</span><span class="sxs-lookup"><span data-stu-id="e8f72-p113">Select **Use SQL Server mirroring witness to enable automatic failover** to select a server to use as a mirroring witness. Click **New** to create a new SQL Server store.</span></span>
    
  - <span data-ttu-id="e8f72-p114">**监视（CDR 和 QoE 度量）**。选择此选项将监控 SQL Server 存储与前端池关联。通过从列表中选择服务器，可以从已定义的监控服务器中进行选择，或单击“**新建**”以指定新的监控服务器。</span><span class="sxs-lookup"><span data-stu-id="e8f72-p114">**Monitoring (CDR and QoE metrics)**. Select to associate a Monitoring SQL Server store with the Front End pool. You can select from an already defined Monitoring Server by selecting the server from the list, or click **New** to specify a new Monitoring Server.</span></span>
    
    <span data-ttu-id="e8f72-p115">选择“**启用 SQL Server 存储镜像**”，然后选择要用于镜像的服务器。单击“**新建**”可创建新的 SQL Server 存储。</span><span class="sxs-lookup"><span data-stu-id="e8f72-p115">Select **Enable SQL Server store mirroring**, and then select the server to use for mirroring. Click **New** to create a new SQL Server store.</span></span>
    
    <span data-ttu-id="e8f72-p116">选择“**使用 SQL Server 镜像见证启用自动故障转移**”以选择将某台服务器用作镜像见证。单击“**新建**”可创建新的 SQL Server 存储。</span><span class="sxs-lookup"><span data-stu-id="e8f72-p116">Select **Use SQL Server mirroring witness to enable automatic failover** to select a server to use as a mirroring witness. Click **New** to create a new SQL Server store.</span></span>
    
  - <span data-ttu-id="e8f72-p117">**关联边缘池（用于媒体组件）**。将边缘服务器或池与前端池关联。通过从列表中选择服务器，可以从已定义的边缘服务器或池中进行选择，或单击“**新建**”以指定新的边缘服务器或池。</span><span class="sxs-lookup"><span data-stu-id="e8f72-p117">**Associate Edge pool (for media components)**. Associate an Edge Server or pool with the Front End pool. You can select from an already defined Edge Server or pool by selecting the server from the list, or click **New** to specify a new Edge Server or pool.</span></span>
    
  - <span data-ttu-id="e8f72-p118">**将池与一个 Office Web Apps 服务器关联**。选择此选项可将 Office Web Apps 服务器与前端池关联。从列表中选择现有服务器，或单击“**新建**”以创建新的 Office Web Apps 服务器。</span><span class="sxs-lookup"><span data-stu-id="e8f72-p118">**Associate pool with an Office Web Apps Server**. Select this option to associate an Office Web Apps Server with the Front End pool. Select an existing server from the list, or click **New** to create a new Office Web Apps Server.</span></span>
    
### <a name="resiliency"></a><span data-ttu-id="e8f72-163">复原</span><span class="sxs-lookup"><span data-stu-id="e8f72-163">Resiliency</span></span>

<span data-ttu-id="e8f72-p119">复原为池提供灾难恢复和高可用性。它提供了备份，如果主服务器发生故障，备份服务器可以接管发生故障的服务器，允许用户登录和进行通信。用户可能会发现功能降低，具体取决于哪些系统上的主服务器发生故障。</span><span class="sxs-lookup"><span data-stu-id="e8f72-p119">Resiliency provides disaster recovery and high availability for the pool. By providing a backup, if the primary server fails, the backup server can take over, enabling users to sign in and communicate. There may be reduced functionality for users, depending on which systems have failed with the primary server.</span></span>
  
<span data-ttu-id="e8f72-p120">从列表中选择充当池的备份服务器的前端池或 Standard Edition Server。还可以选择启用故障转移和回退时间间隔。启用故障转移和回退时间设置（以秒为单位指定）后，可自动检测发生故障的服务器，回退时间用于自动确定主服务器是否已备份。</span><span class="sxs-lookup"><span data-stu-id="e8f72-p120">From the list, select the Front End pool or Standard Edition server that will act as the backup server for the pool. You can also select to enable Failover and Fallback time intervals. Enabling the failover and fallback time settings (specified in seconds) enables automatic detection of a failed server, and a fallback time to allow for automatic determination that the primary is back up.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e8f72-p121">定义故障检测和回退间隔时，应注意不要输入在服务器短时间内未做出响应的情况下会导致发生故障转移和回退的间隔。主服务器可能会在短时间内没有响应，这取决于池或服务器的加载状况。对于池到池或池到 Standard Edition Server，故障转移和回退的默认值是 300 秒和 600 秒。对于站点中的 Survivable Branch Appliance 或 Survivable Branch Server 到池或到 Standard Edition Server，故障转移的默认值是 120 秒，回退的默认值是 240 秒。</span><span class="sxs-lookup"><span data-stu-id="e8f72-p121">When defining the Failure detection and the Fallback interval, you should be careful not to enter an interval that will cause the failover and fallback to occur if the server fails to respond for a short period of time. It is possible that the primary server may not respond for short periods of time, depending on the loading of the pool or servers. The default values for the failover and fallback are 300 seconds and 600 seconds for pool to pool, or pool to Standard Edition server. In the event of a Survivable Branch Appliance or a Survivable Branch Server in a site to a pool or Standard Edition server, the default values are 120 seconds for failover and 240 seconds for fallback.</span></span> 
  
> [!CAUTION]
> <span data-ttu-id="e8f72-p122">“**故障转移间隔**”的最小值不应该设置为低于 90 秒的值。如果将此值设置为低于 90 秒的值，将使用 90 秒。Intercluster Ping 时间为 30 秒，设置为低于 90 秒的值将导致主服务器和备份服务器循环开关机，进而因服务器尝试解析其他服务器的正常状态，会对生产产生不适当的影响。小于 90 秒的值将不足以确定主服务器是否可用。</span><span class="sxs-lookup"><span data-stu-id="e8f72-p122">The minimum value for the **failover interval** should not be set lower than 90 seconds. If you do set the value to less than 90 seconds, the value of 90 seconds is used. The intercluster ping time is 30 seconds, and a setting lower than 90 seconds may cause the primary and backup servers to cycle up and down, causing an undesirable impact to production, as the servers try to resolve the viable status of the other. Less than 90 seconds does not allow for enough time to determine that the primary server is actually unavailable or not.</span></span>
  
### <a name="web-services"></a><span data-ttu-id="e8f72-178">Web 服务</span><span class="sxs-lookup"><span data-stu-id="e8f72-178">Web Services</span></span>

<span data-ttu-id="e8f72-179">要为前端池上的 Web 服务编辑或指定其他设置，请在“**内部 Web 服务**”和“**外部 Web 服务**”中修改或指定设置。</span><span class="sxs-lookup"><span data-stu-id="e8f72-179">To edit or specify additional setting for the web services on the Front End pool, modify or specify settings in **Internal Web services** and **External Web services**.</span></span>
  
<span data-ttu-id="e8f72-180">对于“**内部 Web 服务**”，请指定以下内容：</span><span class="sxs-lookup"><span data-stu-id="e8f72-180">In **Internal Web services**, specify the following:</span></span>
  
> [!CAUTION]
> <span data-ttu-id="e8f72-181">如果您有多个前端池或前端服务器，外部 Web 服务 FQDN 必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="e8f72-181">If you have more than one Front End pool or Front End Server, the external Web services FQDN must be unique.</span></span> <span data-ttu-id="e8f72-182">例如，如果您定义的外部 Web 服务的前端服务器的 FQDN 为**pool01.contoso.com**，不能使用**pool01.contoso.com** ，另一个前端池或前端服务器。</span><span class="sxs-lookup"><span data-stu-id="e8f72-182">For example, if you define the external Web services FQDN of a Front End Server as **pool01.contoso.com**, you cannot use **pool01.contoso.com** for another Front End pool or Front End Server.</span></span> <span data-ttu-id="e8f72-183">如果您还部署控制器、 外部 Web 服务 FQDN 定义任何控制器或控制器池必须不同于任何其他控制器或控制器池，如也来任何前端池或前端服务器。</span><span class="sxs-lookup"><span data-stu-id="e8f72-183">If you are also deploying Directors, the external Web services FQDN defined for any Director or Director pool must be unique from any other Director or Director pool, as well as from any Front End pool or Front End Server.</span></span> <span data-ttu-id="e8f72-184">如果您决定覆盖内部 web 服务与自定义的 FQDN，每个 FQDN 必须是唯一从任何其他前端池、 控制器或控制器池。</span><span class="sxs-lookup"><span data-stu-id="e8f72-184">If you decide to override the Internal web services with a self-defined FQDN, each FQDN must be unique from any other Front End pool, Director, or Director pool.</span></span>
  
- <span data-ttu-id="e8f72-p124">如果选择“**覆盖 FQDN**”，则可以为池上的“**内部 Web 服务**”标识指定不同的 FQDN。默认情况下，该设置是为前端池定义的当前池名称。</span><span class="sxs-lookup"><span data-stu-id="e8f72-p124">If you select **Override FQDN**, you can specify a different FQDN for the **Internal Web** services identity on the pool. By default, the setting is the current pool name as defined for the Front End pool.</span></span>
    
- <span data-ttu-id="e8f72-p125">部署所需的 HTTP 和 HTTPS 侦听端口和已发布端口。端口 80（对于 HTTP）和端口 443（对于 HTTPS）的默认设置是最常见的设置，通常不需要更改，除非在您的组织和基础结构设计中有具体的要求。</span><span class="sxs-lookup"><span data-stu-id="e8f72-p125">Listening and published ports for HTTP and HTTPS that your deployment requires. The default settings of port 80 for HTTP and port 443 for HTTPS are the most common settings and typically do not need to be changed, unless you have specific requirements within your organization and infrastructure design.</span></span>
    
<span data-ttu-id="e8f72-189">对于“**外部 Web 服务**”，请指定以下内容：</span><span class="sxs-lookup"><span data-stu-id="e8f72-189">In **External Web services**, specify the following:</span></span>
  
- <span data-ttu-id="e8f72-p126">外部 Web 服务的 FQDN。此处指定的 FQDN 通常由外部连接要求（如反向代理）定义。</span><span class="sxs-lookup"><span data-stu-id="e8f72-p126">The FQDN of the External Web services. The FQDN specified here will usually be defined by the requirements of your external connection requirements, such as the reverse proxy.</span></span>
    
- <span data-ttu-id="e8f72-192">部署所需的 HTTP 和 HTTPS 侦听端口和已发布端口。</span><span class="sxs-lookup"><span data-stu-id="e8f72-192">Listening and published ports for HTTP and HTTPS that your deployment requires.</span></span> <span data-ttu-id="e8f72-193">最初定义为端口 8080（对于 HTTP）和端口 4443（对于 HTTPS）的默认设置。</span><span class="sxs-lookup"><span data-stu-id="e8f72-193">The default settings of port 8080 for HTTP and port 4443 for HTTPS are defined initially.</span></span> <span data-ttu-id="e8f72-194">根据反向代理的要求和外部网络要求，更改侦听端口的这些设置。</span><span class="sxs-lookup"><span data-stu-id="e8f72-194">You change these settings for the listening ports based on what the requirements are for your reverse proxy and external network requirements.</span></span> <span data-ttu-id="e8f72-195">已发布端口设置为端口 80（对于 HTTP）和端口 443（对于 HTTPS）的默认值。</span><span class="sxs-lookup"><span data-stu-id="e8f72-195">The published ports are set to default of port 80 for HTTP and port 443 for HTTPS.</span></span> <span data-ttu-id="e8f72-196">这些值确定了该池将侦听哪些端口的传入请求。</span><span class="sxs-lookup"><span data-stu-id="e8f72-196">These values determine what ports the pool will listen for incoming requests.</span></span> <span data-ttu-id="e8f72-197">通常，这些不需要更改，除非存在冲突的池上的端口要求。</span><span class="sxs-lookup"><span data-stu-id="e8f72-197">Typically, these do not need to be changed, unless there is a conflict of port requirements on the pool.</span></span> <span data-ttu-id="e8f72-198">建议使用相同端口值的内部和外部已发布端口。</span><span class="sxs-lookup"><span data-stu-id="e8f72-198">Internal and external published ports using the same port values are expected.</span></span> <span data-ttu-id="e8f72-199">这不会出现冲突。</span><span class="sxs-lookup"><span data-stu-id="e8f72-199">This is not a conflict.</span></span>
    
### <a name="mediation-server"></a><span data-ttu-id="e8f72-200">中介服务器</span><span class="sxs-lookup"><span data-stu-id="e8f72-200">Mediation Server</span></span>

<span data-ttu-id="e8f72-201">对于“**中介服务器**”，请指定以下内容：</span><span class="sxs-lookup"><span data-stu-id="e8f72-201">In **Mediation Server**, specify the following:</span></span>
  
- <span data-ttu-id="e8f72-p128">如果要将中介服务器并置到该池上，请选中“**并置中介服务器已启用**”复选框。如果选择不并置中介服务器，则本节中没有可用的设置。</span><span class="sxs-lookup"><span data-stu-id="e8f72-p128">If you collocate the Mediation Server with the pool, select the **Collocated Mediation Server enabled** check box. If you choose not to collocate the Mediation Server, none of the settings are available in this section.</span></span>
    
- <span data-ttu-id="e8f72-p129">如果启用中介服务器并置，请在池服务器上为传输层安全性 (TLS) 定义侦听端口范围。默认情况下，此端口为 5067。如果选择“**启用 TCP 端口**”，则必须为并置的中介服务器定义传输控制协议 (TCP) 端口。这是一个可选设置，您应该参考网关要求或 PSTN 要求以确定是否需要此设置。默认情况下，TCP 端口值为 5068。</span><span class="sxs-lookup"><span data-stu-id="e8f72-p129">If you enable the collocation of the Mediation Server, define the listening port range on the pool servers for Transport Layer Security (TLS). By default, this port is 5067. If you select **Enable TCP port**, you must define a Transmission Control Protocol (TCP) port for the collocated Mediation Server. This is an optional setting, and you should refer to the requirements of your gateway or PSTN requirements to determine if you need this. By default, the TCP port value is 5068.</span></span>
    
- <span data-ttu-id="e8f72-p130">与并置的中介服务器关联的中继。如果已经定义中继，则可以将它们与中介服务器关联。</span><span class="sxs-lookup"><span data-stu-id="e8f72-p130">Trunks that are associated with the collocated Mediation Server. If you have already defined trunks, they will be available to associate with the Mediation Server.</span></span> 
    
- <span data-ttu-id="e8f72-p131">如果有多个中继与中介服务器关联，可以通过选择相应中继，然后单击“**设为默认值**”，指定默认中继。若要取消选择中继作为默认中继，请单击“**取消设为默认值**”。</span><span class="sxs-lookup"><span data-stu-id="e8f72-p131">If you have more than one trunk associated with a Mediation Server, you can specify a default trunk by selecting the gateway and then clicking **Make Default**. To unselect a gateway as the default, click **Unmake Default**.</span></span> 
    
<span data-ttu-id="e8f72-213">有关定义和配置前端池设置的详细信息，请参阅[Deploying Mediation Servers and Defining Peers](http://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx)。</span><span class="sxs-lookup"><span data-stu-id="e8f72-213">For details about defining and configuring the settings for the Front End pool, see [Deploying Mediation Servers and Defining Peers](http://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).</span></span>
  
## <a name="standard-edition-server"></a><span data-ttu-id="e8f72-214">Standard Edition Server</span><span class="sxs-lookup"><span data-stu-id="e8f72-214">Standard Edition Server</span></span>

<span data-ttu-id="e8f72-215">对于 Standard Edition Server，可以配置常规设置、复原设置、Web 服务设置和中介服务器设置。</span><span class="sxs-lookup"><span data-stu-id="e8f72-215">For a Standard Edition server, you can configure general, resiliency, web services, and Mediation Server settings.</span></span> <span data-ttu-id="e8f72-216">有关详细信息，请参阅以下子节中的信息。</span><span class="sxs-lookup"><span data-stu-id="e8f72-216">For details, see the information in the following subsections.</span></span> <span data-ttu-id="e8f72-217">有关定义和配置设置的 Standard Edition server 的详细信息，请参阅[Defining and Configuring the Topology](http://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx)和[Deploying Mediation Servers and Defining Peers](http://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx)。</span><span class="sxs-lookup"><span data-stu-id="e8f72-217">For details about defining and configuring the settings for the Standard Edition server, see [Defining and Configuring the Topology](http://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) and [Deploying Mediation Servers and Defining Peers](http://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).</span></span>
  
### <a name="general-settings"></a><span data-ttu-id="e8f72-218">常规设置</span><span class="sxs-lookup"><span data-stu-id="e8f72-218">General Settings</span></span>

<span data-ttu-id="e8f72-219">可以配置以下常规设置：</span><span class="sxs-lookup"><span data-stu-id="e8f72-219">You can configure the following general settings:</span></span>
  
- <span data-ttu-id="e8f72-220">* * FQDN * *。</span><span class="sxs-lookup"><span data-stu-id="e8f72-220">** FQDN**.</span></span> <span data-ttu-id="e8f72-221">请注意，无法更改 FQDN。</span><span class="sxs-lookup"><span data-stu-id="e8f72-221">Note that the FQDN cannot be changed.</span></span> <span data-ttu-id="e8f72-222">必须删除并重新定义 Standard Edition Server 才能更改与其关联的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="e8f72-222">You must remove and redefine the Standard Edition server to change the FQDN associated with it.</span></span>
    
- <span data-ttu-id="e8f72-p134">选择“**使用所有已配置的 IP 地址**”或“**将服务用途限制为所选 IP 地址**”。如果选择将服务用途限制为定义的 IP 地址，则需要定义服务器用于除 PSTN 外的所有通信的主 IP 地址。需要定义单独的 IP 地址用于 PSTN。也可以选择“**启用 IPv6**”为此服务器启用 IPv6。</span><span class="sxs-lookup"><span data-stu-id="e8f72-p134">Select **Use all configured IP addresses** or to **Limit service usage to selected IP addresses**. If you select to limit the service to defined IP addresses, you will define the Primary IP address that the server will use for all communications, except for PSTN. You define a separate IP address for PSTN usage. You can also select **Enable IPv6** to enable IPv6 for this server.</span></span>
    
- <span data-ttu-id="e8f72-p135">**启用硬件负载平衡器监控端口**。选中该复选框并输入您的硬件负载平衡器将用于监控服务器状态的端口号。</span><span class="sxs-lookup"><span data-stu-id="e8f72-p135">**Enable Hardware Load Balancer monitoring port**. Select the check box and enter the port number that your Hardware Load Balancer will use to monitor the state of the server.</span></span>
    
- <span data-ttu-id="e8f72-p136">在“**功能**”中，定义要与该服务器并置的其他角色。可以配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="e8f72-p136">In **Features and Functionality**, define the additional roles that you want to collocate with this server. You can configure the following settings:</span></span>
    
  - <span data-ttu-id="e8f72-p137">**会议**。包含音频、视频和应用程序共享。选择此选项后，您可以选择“**电话拨入式 (PSTN) 会议**”。稍后可以在中介服务器设置下指定并定义 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="e8f72-p137">**Conferencing**. Includes audio, video and application sharing. After you select this option, you can select **Dial-in (PSTN) conferencing**. You can specify and define a PSTN gateway later under Mediation Server settings.</span></span>
    
  - <span data-ttu-id="e8f72-235">**企业语音**。</span><span class="sxs-lookup"><span data-stu-id="e8f72-235">**Enterprise Voice**.</span></span> <span data-ttu-id="e8f72-236">启用业务客户端通过 IP 限定的话筒设备和 Skype 调用内部语音。</span><span class="sxs-lookup"><span data-stu-id="e8f72-236">Enables internal voice over IP calls to qualified handsets and devices and Skype for Business clients.</span></span> <span data-ttu-id="e8f72-237">若要启用外部呼叫功能，需要包含中介服务器。</span><span class="sxs-lookup"><span data-stu-id="e8f72-237">To enable external call capabilities, you need to include a Mediation Server.</span></span> <span data-ttu-id="e8f72-238">有关详细信息，请参阅本主题后面的“中介服务器”。</span><span class="sxs-lookup"><span data-stu-id="e8f72-238">For details, see "Mediation Server" later in this topic.</span></span>
    
- <span data-ttu-id="e8f72-239">在“**关联**”中，可以编辑或指定以下内容：</span><span class="sxs-lookup"><span data-stu-id="e8f72-239">In **Associations** you can edit or specify the following:</span></span>
    
  - <span data-ttu-id="e8f72-p139">选择“**SQL Server 存储**”将 SQL Server 存储与前端服务器关联。也可以启用镜像并选择镜像见证服务器。</span><span class="sxs-lookup"><span data-stu-id="e8f72-p139">Select **SQL Server store** to associate a SQL Server store with the Front End server. You can also enable mirroring and select a mirroring witness server.</span></span>
    
  - <span data-ttu-id="e8f72-p140">**文件共享**。修改 Standard Edition Server 正在使用的文件存储。通过从列表中选择，可以从已定义的文件存储中选择新的文件存储。单击“**新建**”可创建新的文件存储。</span><span class="sxs-lookup"><span data-stu-id="e8f72-p140">**File share**. Modify the file store that the Standard Edition server is using. You can select a new file store from those already defined by selecting it from the list. You can create a new file store by clicking **New**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="e8f72-246">发布新定义的拓扑之前，所指定的服务器必须存在并已加入到域。</span><span class="sxs-lookup"><span data-stu-id="e8f72-246">Before publishing the newly defined topology, the server that you specify must exist and be joined to the domain.</span></span> 
  
  - <span data-ttu-id="e8f72-p141">**存档**。将存档 SQL Server 存储与 Standard Edition Server 关联。通过从列表中选择服务器，可以从已定义的存档存储中进行选择，或单击“**新建**”以指定新的存档存储。</span><span class="sxs-lookup"><span data-stu-id="e8f72-p141">**Archiving**. Associate an Archiving SQL Server store with the Standard Edition server. You can select from an already defined Archiving store by selecting the server from the list, or click **New** to specify a new Archiving store.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="e8f72-250">发布新定义的拓扑之前，所指定的服务器必须存在并已加入到域。</span><span class="sxs-lookup"><span data-stu-id="e8f72-250">Before publishing the newly defined topology, the server that you specify must exist and be joined to the domain.</span></span> 
  
  - <span data-ttu-id="e8f72-p142">**监视（CDR 和 QoE 度量）**。将监控 SQL Server 存储与 Standard Edition Server 关联。通过从列表中选择服务器，可以从已定义的监控服务器中进行选择，或单击“**新建**”以指定新的监控服务器。</span><span class="sxs-lookup"><span data-stu-id="e8f72-p142">**Monitoring (CDR and QoE metrics**. Associate a Monitoring SQL Server store with the Standard Edition server. You can select from an already defined Monitoring Server by selecting the server from the list, or click **New** to specify a new Monitoring Server.</span></span>
    
  - <span data-ttu-id="e8f72-p143">**将池与一个 Office Web Apps 服务器关联**。选择此选项可将 Office Web Apps 服务器与前端池关联。从列表中选择现有服务器，或单击“**新建**”以创建新的 Office Web Apps 服务器。</span><span class="sxs-lookup"><span data-stu-id="e8f72-p143">**Associate pool with an Office Web Apps Server**. Select this option to associate an Office Web Apps Server with the Front End pool. Select an existing server from the list, or click **New** to create a new Office Web Apps Server.</span></span>
    
  - <span data-ttu-id="e8f72-p144">**关联边缘池**。将边缘服务器或池与 Standard Edition Server 进行关联。通过从列表中选择服务器，可以从已定义的边缘服务器或池中进行选择，或单击“**新建**”以指定新的边缘服务器或池。</span><span class="sxs-lookup"><span data-stu-id="e8f72-p144">**Associate Edge pool**. Associate an Edge Server or pool with the Standard Edition server. You can select from an already defined Edge Server or pool by selecting the server from the list, or click **New** to specify a new Edge Server or pool.</span></span>
    
### <a name="resiliency"></a><span data-ttu-id="e8f72-260">复原</span><span class="sxs-lookup"><span data-stu-id="e8f72-260">Resiliency</span></span>

<span data-ttu-id="e8f72-p145">复原为服务器提供灾难恢复和高可用性。它提供了备份，如果主服务器发生故障，备份服务器可以接管发生故障的服务器，允许用户登录和进行通信。用户可能会发现功能降低，具体取决于哪些系统发生故障。</span><span class="sxs-lookup"><span data-stu-id="e8f72-p145">Resiliency provides disaster recovery and high availability for the server. By providing a backup, if the primary server fails, the backup can take over, enabling users to sign in and communicate. It is possible that there will be reduced functionality for users, depending on what systems have also failed.</span></span>
  
<span data-ttu-id="e8f72-p146">从列表中选择充当备份服务器的前端池或 Standard Edition Server。还可以选择启用故障转移和回退时间间隔。启用故障转移和回退时间设置（以秒为单位指定）后，可自动检测发生故障的注册器，回退时间用于自动确定主注册器是否已备份。</span><span class="sxs-lookup"><span data-stu-id="e8f72-p146">From the list, select the Front End pool or Standard Edition server that will act as the backup for the server. You can also select to enable Failover and Fallback time intervals. Enabling the failover and fallback time settings (specified in seconds) enables automatic detection of a failed Registrar, and a fallback time to allow for automatic determination that the primary is back up.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e8f72-p147">定义故障检测和回退间隔时，应注意不要输入在服务器短时间内未做出响应的情况下会导致发生故障转移和回退的间隔。主服务器可能会在短时间内没有响应，这取决于池或服务器的加载状况。对于池到池或池到 Standard Edition Server，故障转移和回退的默认值是 300 秒和 600 秒。对于站点中的 Survivable Branch Appliance 或 Survivable Branch Server 到池或到 Standard Edition Server，故障转移的默认值是 120 秒，回退的默认值是 240 秒。</span><span class="sxs-lookup"><span data-stu-id="e8f72-p147">When defining the Failure detection and the Fallback interval, you should be careful not to enter an interval that will cause the failover and fallback to occur if the server should fail to respond for a short period of time. It is possible that the primary server may not respond for short periods of time, based on the loading of the pool or servers. The default values for the failover and fallback are 300 seconds and 600 seconds for pool to pool, or pool to Standard Edition server. In the event of a Survivable Branch Appliance or a Survivable Branch Server in a site to a pool or Standard Edition server, the default values are 120 seconds for failover and 240 seconds for fallback.</span></span> 
  
### <a name="web-services"></a><span data-ttu-id="e8f72-271">Web 服务</span><span class="sxs-lookup"><span data-stu-id="e8f72-271">Web Services</span></span>

<span data-ttu-id="e8f72-272">要为服务器上的 Web 服务编辑或指定其他设置，请在“**内部 Web 服务**”和“**外部 Web 服务**”中修改或指定设置。</span><span class="sxs-lookup"><span data-stu-id="e8f72-272">To edit or specify additional setting for the web services on the server, modify or specify settings in **Internal Web services** and **External Web services**.</span></span>
  
<span data-ttu-id="e8f72-273">对于“**内部 Web 服务**”，可以指定以下内容：</span><span class="sxs-lookup"><span data-stu-id="e8f72-273">For **Internal Web services**, you can specify the following:</span></span>
  
- <span data-ttu-id="e8f72-p148">如果选择“覆盖 FQDN”，则可以为服务器上的内部 Web 服务标识指定不同的 FQDN。默认情况下，该设置是为 Standard Edition Server 定义的当前服务器名称。</span><span class="sxs-lookup"><span data-stu-id="e8f72-p148">If you select Override FQDN, you can specify a different FQDN for the Internal Web services identity on the server. By default, the setting is the current server name as defined for the Standard Edition server.</span></span>
    
- <span data-ttu-id="e8f72-p149">部署所需的 HTTP 和 HTTPS 侦听端口和已发布端口。端口 80（对于 HTTP）和端口 443（对于 HTTPS）的默认设置是最常见的设置，通常不需要更改，除非在您的组织和基础结构设计中有具体的要求。</span><span class="sxs-lookup"><span data-stu-id="e8f72-p149">Listening and published ports for HTTP and HTTPS that your deployment requires. The default setting of port 80 for HTTP and port 443 for HTTPS are the most common settings, and typically do not need to be changed unless you have specific requirements within your organization and infrastructure design.</span></span>
    
<span data-ttu-id="e8f72-278">对于“**外部 Web 服务**”，可以指定以下内容：</span><span class="sxs-lookup"><span data-stu-id="e8f72-278">For **External Web services**, you can specify the following:</span></span>
  
- <span data-ttu-id="e8f72-p150">外部 Web 服务的 FQDN。此处指定的 FQDN 通常由外部连接要求（如反向代理）定义。</span><span class="sxs-lookup"><span data-stu-id="e8f72-p150">The FQDN of the External Web services. The FQDN specified here will usually be defined by the requirements of your external connection requirements, such as the reverse proxy.</span></span>
    
- <span data-ttu-id="e8f72-p151">部署所需的 HTTP 和 HTTPS 侦听端口。最初定义为端口 8080（对于 HTTP）和端口 4443（对于 HTTPS）的默认设置。根据反向代理的要求和外部网络要求，更改侦听端口的这些设置。这些值确定了该服务器将侦听哪些端口的传入请求。通常，这些值不需要更改，除非服务器上的端口要求有冲突。</span><span class="sxs-lookup"><span data-stu-id="e8f72-p151">Listening ports for HTTP and HTTPS that your deployment requires. The default setting of port 8080 for HTTP and port 4443 for HTTPS is defined initially. You change these settings for the listening ports based on what the requirements are for your reverse proxy and external network requirements. These values determine what ports the server will listen for incoming requests. Typically, these do not need to be changed, unless there is conflict of port requirements on the server.</span></span> 
    
### <a name="mediation-server"></a><span data-ttu-id="e8f72-286">中介服务器</span><span class="sxs-lookup"><span data-stu-id="e8f72-286">Mediation Server</span></span>

<span data-ttu-id="e8f72-287">对于“**中介服务器**”，可以指定以下内容：</span><span class="sxs-lookup"><span data-stu-id="e8f72-287">For **Mediation Server**, you can specify the following:</span></span>
  
- <span data-ttu-id="e8f72-p152">如果要将中介服务器与该服务器并置，请选中“**并置中介服务器已启用**”复选框。如果选择不并置中介服务器，则本节中没有可用的设置。</span><span class="sxs-lookup"><span data-stu-id="e8f72-p152">If you collocate the Mediation Server with the server, select the check box **Collocated Mediation Server enabled**. If you choose not to collocate the Mediation Server, none of the settings are available in this section.</span></span> 
    
- <span data-ttu-id="e8f72-p153">如果已启用中介服务器并置，请在服务器上为 TLS 定义侦听端口范围。默认情况下，此端口为 5067。如果选择“**启用 TCP 端口**”，则必须为并置的中介服务器定义 TCP 端口。这是一个可选设置，您应该参考网关要求或 PSTN 要求以确定是否需要此设置。默认情况下，TCP 端口值为 5068。</span><span class="sxs-lookup"><span data-stu-id="e8f72-p153">If you have enabled the collocation of the Mediation Server, you define the listening port range on the server for TLS. By default, this port is 5067. If you select **Enable TCP port**, you must define a TCP port for the collocated Mediation Server. This is an optional setting, and you should refer to the requirements of your gateway or PSTN requirements to determine if you need this. By default, the TCP port value is 5068.</span></span>
    
- <span data-ttu-id="e8f72-p154">与并置的中介服务器关联的中继。如果已经定义中继，则可以将它们与中介服务器关联。</span><span class="sxs-lookup"><span data-stu-id="e8f72-p154">Trunks that are associated with the collocated Mediation Server. If you have already defined trunks, they will be available to associate with the Mediation Server.</span></span> 
    
- <span data-ttu-id="e8f72-p155">如果有多个网关与中介服务器关联，可以通过选择相应网关，然后单击“**设为默认值**”，指定默认网关。若要取消选择网关作为默认网关，请单击“**取消设为默认值**”。</span><span class="sxs-lookup"><span data-stu-id="e8f72-p155">If you have more than one gateway associated with a Mediation Server, you can specify a default gateway by selecting the gateway and then clicking **Make Default**. To unselect a gateway as the default, click **Unmake Default**.</span></span> 
    
<span data-ttu-id="e8f72-299">有关定义和配置设置的 Standard Edition server 的详细信息，请参阅[Defining and Configuring the Topology](http://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx)和[Deploying Mediation Servers and Defining Peers](http://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx)。</span><span class="sxs-lookup"><span data-stu-id="e8f72-299">For details about defining and configuring the settings for the Standard Edition server, see [Defining and Configuring the Topology](http://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) and [Deploying Mediation Servers and Defining Peers](http://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).</span></span>
  

