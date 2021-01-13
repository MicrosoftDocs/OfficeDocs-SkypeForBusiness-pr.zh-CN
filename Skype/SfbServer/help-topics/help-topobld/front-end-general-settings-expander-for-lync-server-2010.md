---
title: Lync Server 2010 的前端常规设置扩展器
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FrontEndGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58269c38-98d9-499f-ab69-6a63a6e5530e
description: 通过编辑或配置以下属性编辑前端服务器或前端池的属性。 配置页面分为以下几个部分：
ms.openlocfilehash: 8616d65a73f1fb618a72ab41bc628527aa6e2a59
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818392"
---
# <a name="front-end-general-settings-expander-for-lync-server-2010"></a><span data-ttu-id="c4267-104">适合于 Lync Server 2010 的前端常规设置扩展器</span><span class="sxs-lookup"><span data-stu-id="c4267-104">Front End General Settings Expander for Lync Server 2010</span></span>

<span data-ttu-id="c4267-105">通过编辑或配置以下属性编辑前端服务器或前端池的属性。</span><span class="sxs-lookup"><span data-stu-id="c4267-105">You edit the properties of the Front End Server or Front End pool by editing or configuring the following attributes.</span></span> <span data-ttu-id="c4267-106">配置页面分为以下几个部分：</span><span class="sxs-lookup"><span data-stu-id="c4267-106">The configuration page is separated into the following sections:</span></span>

 <span data-ttu-id="c4267-107">**常规**</span><span class="sxs-lookup"><span data-stu-id="c4267-107">**General**</span></span>

- <span data-ttu-id="c4267-108">**FQDN**：前端服务器或前端池的完全限定域名。</span><span class="sxs-lookup"><span data-stu-id="c4267-108">**FQDN**: The fully qualified domain name of the Front End Server or Front End pool.</span></span>

- <span data-ttu-id="c4267-109">**选择"使用所有已配置的 IP 地址**"，以使用在前端服务器或前端池上配置的所有地址。</span><span class="sxs-lookup"><span data-stu-id="c4267-109">Select **Use all configured IP addresses** to make use of all addresses configured on Front End Server or Front End pool.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="c4267-110">如果将中介服务器并排在前端服务器或前端池上，则不应选择此选项。</span><span class="sxs-lookup"><span data-stu-id="c4267-110">You should not select this option if you collocate the Mediation Server on the Front End Server or Front End pool.</span></span> <span data-ttu-id="c4267-111">中介服务器和前端服务器需要要通信的专用 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="c4267-111">Mediation Servers and Front End Servers need dedicated IP addresses on which to communicate.</span></span>

- <span data-ttu-id="c4267-112">选择 **"将服务用途限制为** 所选 IP 地址"，并输入前端服务器或前端池与部署其余部分通信的主 **IP** 地址的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="c4267-112">Select **Limit service usage to selected IP addresses** and enter the IP address for **Primary IP address** for the Front End Server or Front End pool communication with the rest of the deployment.</span></span> <span data-ttu-id="c4267-113">键入 **PSTN IP 地址** 与中介服务器关联的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="c4267-113">Type in **PSTN IP address** the IP address that is associated with the Mediation Server.</span></span>

    <span data-ttu-id="c4267-114">**特性和功能**</span><span class="sxs-lookup"><span data-stu-id="c4267-114">**Features and functionality**</span></span>

- <span data-ttu-id="c4267-115">**会议**：如果在部署中需要会议功能，则选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="c4267-115">**Conferencing**: Select the check box if you want conferencing features in your deployment.</span></span> <span data-ttu-id="c4267-116">会议包括音频、视频、应用程序共享、桌面共享和 Web 会议。</span><span class="sxs-lookup"><span data-stu-id="c4267-116">Conferencing includes audio, video, application sharing, desktop sharing, and Web conferencing.</span></span> <span data-ttu-id="c4267-117">您需要为 Web 会议创建和关联 Office Web Apps Server (稍后在此"属性"页中定义) 。</span><span class="sxs-lookup"><span data-stu-id="c4267-117">You will need to create and associate an Office Web Apps Server for Web conferencing (defined later in this Properties page).</span></span>

- <span data-ttu-id="c4267-118">如果选择了会议，则可以选中“电话拨入式(PSTN)会议”。</span><span class="sxs-lookup"><span data-stu-id="c4267-118">If you selected Conferencing, **Dial-in (PSTN) conferencing** can be selected.</span></span> <span data-ttu-id="c4267-119">选中此复选框可启用电话拨入式会议功能。</span><span class="sxs-lookup"><span data-stu-id="c4267-119">Select the check box to enable dial-in conferencing features.</span></span>

- <span data-ttu-id="c4267-120">如果要部署使Lync Server 2013 能够使用 IP 语音 (VoIP) 技术充当电话语音系统的功能，包括根据设计和要求，选择部署话筒电话、SIP 中继或使用中介服务器、PSTN 网关和 IP-PBX 的公共电话交换网络连接的选项，请选中复选框 企业语音。</span><span class="sxs-lookup"><span data-stu-id="c4267-120">Select the check box **Enterprise Voice** if you intend to deploy features to enable Lync Server 2013 to act as your telephone voice system using voice over IP (VoIP) technologies, including the option of deploying handset telephones, SIP trunks, or public switched telephone network connectivity using Mediation Server, PSTN Gateways, and IP-PBX, in combination or alone, based on the design and requirements.</span></span> <span data-ttu-id="c4267-121">有关此企业语音的详细信息，请参阅[企业语音](https://technet.microsoft.com/library/c9da8099-6f4f-4346-ac67-f041bb96072c.aspx)Skype for Business [Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)中的 企业语音 和计划</span><span class="sxs-lookup"><span data-stu-id="c4267-121">For detail on Enterprise Voice, see [Enterprise Voice](https://technet.microsoft.com/library/c9da8099-6f4f-4346-ac67-f041bb96072c.aspx) and [Plan for Enterprise Voice in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice.md)</span></span>

    <span data-ttu-id="c4267-122">**关联**</span><span class="sxs-lookup"><span data-stu-id="c4267-122">**Associations**</span></span>

- <span data-ttu-id="c4267-123">**SQL Server存储**：SQL Server (前端服务器或前端池) 命名实例的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="c4267-123">**SQL Server store**: The FQDN of the SQL Server (and optionally a named instance) associated with the Front End Server or Front End pool.</span></span> <span data-ttu-id="c4267-124">从列表选择 SQL Server 存储或通过单击“新建”创建一个新的 SQL Server 存储</span><span class="sxs-lookup"><span data-stu-id="c4267-124">You select the SQL Server store from the list or you create a new SQL Server store by clicking **New**</span></span>

- <span data-ttu-id="c4267-125">文件存储：选择服务器的 FQDN 和共享 (，格式为) ，它将充当 Lync Server 2013 创建并用于复制、会议目录和其他用途的共享文件的文件存储位置。 `\\<FQDN of server>\<share name>`</span><span class="sxs-lookup"><span data-stu-id="c4267-125">**File store**: You select the FQDN of the server and the share (in the format  `\\<FQDN of server>\<share name>`) that will act as the file store location for the shared files that Lync Server 2013 creates and uses for replication, conference directories, and other purposes.</span></span> <span data-ttu-id="c4267-126">从列表选择文件存储或通过单击“新建”创建一个新的文件存储。</span><span class="sxs-lookup"><span data-stu-id="c4267-126">You select the File store from the list or you create a new File store by clicking **New**.</span></span>

- <span data-ttu-id="c4267-127">选中" **关联存档服务器** "复选框可为此前端服务器或前端池启用存档服务器。</span><span class="sxs-lookup"><span data-stu-id="c4267-127">Select the **Associate Archiving Server** checkbox to enable an Archiving Server for this Front End Server or Front End pool.</span></span> <span data-ttu-id="c4267-128">选中该复选框后，从列表中选择现有存档服务器，或单击"新建"为新的存档服务器创建定义。</span><span class="sxs-lookup"><span data-stu-id="c4267-128">After selecting the check box, you select an existing Archiving Server from the list or click **New** to create the definitions for a new Archiving Server.</span></span>

- <span data-ttu-id="c4267-129">选中" **关联监控服务器** "复选框可为此前端服务器或前端池启用监控服务器。</span><span class="sxs-lookup"><span data-stu-id="c4267-129">Select the **Associate Monitoring Server** checkbox to enable a Monitoring Server for this Front End Server or Front End pool.</span></span> <span data-ttu-id="c4267-130">选中该复选框后，从列表中选择现有监控服务器，或单击"新建"为新的监控服务器创建定义。</span><span class="sxs-lookup"><span data-stu-id="c4267-130">After selecting the check box, you select an existing Monitoring Server from the list or click **New** to create the definitions for a new Monitoring Server.</span></span>

- <span data-ttu-id="c4267-131">选中" **将边缘池 (媒体组件关联"** 复选框，为此前端服务器或前端池启用边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="c4267-131">Select the **Associate Edge Pool (for media components** checkbox to enable an Edge Server for this Front End Server or Front End pool.</span></span> <span data-ttu-id="c4267-132">选中该复选框后，从列表中选择现有边缘服务器或池，或单击"新建"为新的边缘服务器或池创建定义。</span><span class="sxs-lookup"><span data-stu-id="c4267-132">After selecting the check box, you select an existing Edge Server or pool from the list or click **New** to create the definitions for a new Edge Server or pool.</span></span>

  <span data-ttu-id="c4267-133">**复原能力**</span><span class="sxs-lookup"><span data-stu-id="c4267-133">**Resiliency**</span></span>

- <span data-ttu-id="c4267-134">选中 **"** 关联的备份注册器池"复选框，从列表中选择一个前端服务器或前端池，该池将成为备份注册器 (，即当主注册器发生故障时指定为辅助注册器前端) </span><span class="sxs-lookup"><span data-stu-id="c4267-134">Select the **Associated backup Registrar pool** check box to select from the list a Front End Server or Front End pool that will be the backup Registrar ( that is, the Front End Server or Front End pool designated as a secondary registrar in the event that the primary fails)</span></span>

- <span data-ttu-id="c4267-135">如果选择了关联的备份注册器池并选择了备份注册器，则可以选中“语音的自动故障转移和故障回复”复选框。</span><span class="sxs-lookup"><span data-stu-id="c4267-135">If you selected Associated backup Registrar pool and have chosen a backup registrar, you can select the checkbox for **Automatic failover and failback for Voice**.</span></span> <span data-ttu-id="c4267-136">随后便可定义“语音故障转移检测间隔(秒)”和“语音故障回复间隔(秒)”的数字属性。</span><span class="sxs-lookup"><span data-stu-id="c4267-136">You can now define numerical properties for **Voice failover detection internal (sec)** and **Voice failback interval (sec)**.</span></span> <span data-ttu-id="c4267-137">有关详细信息，请参阅[Planning for Enterprise Voice Resiliency](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)</span><span class="sxs-lookup"><span data-stu-id="c4267-137">For details, see [Planning for Enterprise Voice Resiliency](https://technet.microsoft.com/library/ca116700-1055-4ca5-9b87-4c7f380c3655.aspx)</span></span>

  <span data-ttu-id="c4267-138">**Web 服务**</span><span class="sxs-lookup"><span data-stu-id="c4267-138">**Web services**</span></span>

- <span data-ttu-id="c4267-p114">若要配置“内部 Web 服务”，请为 **HTTP** 和 **HTTPS** 定义“侦听端口”。默认情况下，各自定义为 TCP 端口 80 和 TCP 端口 443。还为 **HTTP** 和 **HTTPS** 配置“已发布的端口”。默认情况下，各自配置为 TCP 端口 80 和 TCP 端口 443。根据内部 Web 服务配置和负载平衡器的使用（硬件负载平衡器和 DNS 负载平衡），调整端口值以定义侦听和发布端口。</span><span class="sxs-lookup"><span data-stu-id="c4267-p114">To configure **Internal web services**, you define **Listening ports** for **HTTP** and **HTTPS**. By default, these are TCP port 80 and TCP port 443, respectively. You also configure the **Published ports** for **HTTP** and **HTTPS**. By default, these are TCP port 80 and TCP port 443, respectively. Based on your internal web services configuration and use of load balancers (hardware load balancers and DNS load balancing), adjust the port values to define the listening and published ports.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="c4267-p115">内部 Web 服务和定义的侦听和发布的端口用于内部客户端和设备。外部客户端和设备使用外部 Web 服务侦听和发布的端口，以及定义的外部 Web 服务完全限定域名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="c4267-p115">Internal web services and the defined listening and published ports are for internal clients and devices. External clients and devices use the external web services listening and published ports, along with the defined external web services fully qualified domain name (FQDN).</span></span>

- <span data-ttu-id="c4267-p116">若要配置“外部 Web 服务”，请为 **HTTP** 和 **HTTPS** 定义“侦听端口”。默认情况下，各自定义为 TCP 端口 80 和 TCP 端口 443。还为 **HTTP** 和 **HTTPS** 配置“已发布的端口”。默认情况下，各自配置为 TCP 端口 80 和 TCP 端口 443。根据内部 Web 服务配置和负载平衡器的使用（硬件负载平衡器和 DNS 负载平衡），调整端口值以定义侦听和已发布的端口。</span><span class="sxs-lookup"><span data-stu-id="c4267-p116">To configure **External web services**, you define **Listening ports** for **HTTP** and **HTTPS**. By default, these are TCP port 80 and TCP port 443, respectively. You also configure the **Published ports** for **HTTP** and **HTTPS**. By default, these are TCP port 80 and TCP port 443, respectively. Based on your internal web services configuration and use of load balancers (hardware load balancers and DNS load balancing), adjust the port values to define the listening and published ports.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="c4267-151">外部 Web 服务及定义的侦听端口和已发布的端口都用于内部客户端和设备。</span><span class="sxs-lookup"><span data-stu-id="c4267-151">External web services and the defined listening and published ports are for external clients and devices.</span></span> <span data-ttu-id="c4267-152">外部客户端和设备使用外部 Web 服务侦听和已发布端口（通常由反向代理和定义的外部 Web 服务完全限定域名 (FQDN) 一起定义）。</span><span class="sxs-lookup"><span data-stu-id="c4267-152">External clients and devices use the external web services listening and published ports, typically defined by your reverse proxy along with the defined external web services fully qualified domain name (FQDN).</span></span> <span data-ttu-id="c4267-153">外部 Web 服务 FQDN 和简单 URL 的关系定义统一资源定位器 (URL) 地址，外部客户端可以使用该地址访问适用于外部用户和设备的服务。</span><span class="sxs-lookup"><span data-stu-id="c4267-153">The relationship of the external web services FQDN and the Simple URLs define the uniform resource locator (URL) addresses that external clients will use to access services available for external users and devices.</span></span> <span data-ttu-id="c4267-154">有关简单 URL 的更多详细信息，请参阅[Planning for Simple URLs](https://technet.microsoft.com/library/20e4f4b6-b7ff-4297-b00d-d1211ee800ac.aspx)。</span><span class="sxs-lookup"><span data-stu-id="c4267-154">For more details on Simple URLs, see [Planning for Simple URLs](https://technet.microsoft.com/library/20e4f4b6-b7ff-4297-b00d-d1211ee800ac.aspx).</span></span>

  <span data-ttu-id="c4267-155">**中介服务器**</span><span class="sxs-lookup"><span data-stu-id="c4267-155">**Mediation Server**</span></span>

- <span data-ttu-id="c4267-156">若要为 **并** 排的中介服务器 (（即部署在前端服务器或前端池) 上的中介服务器）配置中介服务器属性，请选择"启用并排中介服务器 **"。**</span><span class="sxs-lookup"><span data-stu-id="c4267-156">To configure **Mediation Server** properties for a collocated Mediation Server (that is, a Mediation Server deployed on the Front End Server or Front End pool), select **Collocated Mediation server enabled**.</span></span>

- <span data-ttu-id="c4267-157">若要 **为并并** 的中介服务器定义侦听端口，请键入并并的中介服务器正在侦听的 **TLS** 和 **TCP** 端口值。</span><span class="sxs-lookup"><span data-stu-id="c4267-157">To define the **Listening ports** for a collocated Mediation Server, you type the **TLS** and **TCP** port value that the collocated Mediation Server is listening on.</span></span> <span data-ttu-id="c4267-158">默认情况下，TLS 定义为 TCP 端口 5067。</span><span class="sxs-lookup"><span data-stu-id="c4267-158">By default, TLS is defined as TCP port 5067.</span></span>

- <span data-ttu-id="c4267-159">若要为中介服务器定义 TCP 端口值，请选中" **启用 TCP 端口** "复选框。</span><span class="sxs-lookup"><span data-stu-id="c4267-159">To define a TCP port value for the Mediation Server, you select the **Enable TCP port** check box.</span></span> <span data-ttu-id="c4267-160">默认情况下，中介服务器使用传输层安全性 (TCP 协议) 传输层安全性。</span><span class="sxs-lookup"><span data-stu-id="c4267-160">By default, the Mediation Server uses the transport layer security (TLS) over TCP protocol.</span></span> <span data-ttu-id="c4267-161">TCP 端口仅在“启用 TCP 端口”选项启用的情况下可用。</span><span class="sxs-lookup"><span data-stu-id="c4267-161">TCP ports are available only when the Enable TCP Port selection is enabled.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c4267-p120">这是一个可选设置，您应该参考网关或 PSTN 要求以确定是否需要此设置。默认情况下，TCP 端口值为 5068。</span><span class="sxs-lookup"><span data-stu-id="c4267-p120">This is an optional setting, and you should refer to the requirements of your gateway or PSTN to determine if you need this. By default, the TCP port value is 5068.</span></span>

- <span data-ttu-id="c4267-p121">定义与并置的中介服务器关联的中继。如果已定义了中继，则可以将它们与中介服务器关联。</span><span class="sxs-lookup"><span data-stu-id="c4267-p121">You define trunks that are associated with the collocated Mediation Server. If you have already defined trunks, they will be available to associate with the Mediation Server.</span></span>

    <span data-ttu-id="c4267-166">如果您具有多个与中介服务器关联的网关，则可以通过选择要设置为默认值的网关并单击"设置为默认值"来指定默认 **网关**。</span><span class="sxs-lookup"><span data-stu-id="c4267-166">If you have more than one gateway associated with a Mediation Server, you can specify the default gateway by selecting the gateway that you want to make the default, and clicking **Make Default**.</span></span> <span data-ttu-id="c4267-167">如果选择删除当前默认网关，请选择该网关并单击“取消设为默认值”。</span><span class="sxs-lookup"><span data-stu-id="c4267-167">If you choose to remove the current default gateway, select the gateway and click **Unmake Default**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c4267-168">如果对此对话框中的属性进行更改，则必须发布拓扑，并在所有受影响的服务器上运行 Skype for Business Server 部署向导。</span><span class="sxs-lookup"><span data-stu-id="c4267-168">If you make changes to the properties in this dialog, you must publish the topology and run the Skype for Business Server Deployment Wizard on all affected servers.</span></span> <span data-ttu-id="c4267-169">发布新拓扑后，会提供必须运行 Skype for Business Server 部署向导的受影响服务器列表，作为成功拓扑发布摘要屏幕上的链接。</span><span class="sxs-lookup"><span data-stu-id="c4267-169">After publishing the new topology, a list of affected servers where the Skype for Business Server Deployment Wizard must be run is provided for you as a link on the successful topology publishing summary screen.</span></span> <span data-ttu-id="c4267-170">有关发布更新拓扑的详细信息，请参阅[Publish the Topology](https://technet.microsoft.com/library/3b5a744b-b3a8-4538-a55e-e2e4f72dff47.aspx)。</span><span class="sxs-lookup"><span data-stu-id="c4267-170">For details on publishing the updated topology, see [Publish the Topology](https://technet.microsoft.com/library/3b5a744b-b3a8-4538-a55e-e2e4f72dff47.aspx).</span></span> <span data-ttu-id="c4267-171">有关 Skype for Business Server 部署向导的详细信息，请参阅 [Lync Server 管理工具](https://technet.microsoft.com/library/9b006f93-4f3d-461d-89b8-e80a34fdb3c5.aspx)。</span><span class="sxs-lookup"><span data-stu-id="c4267-171">For details on the Skype for Business Server Deployment Wizard , see [Lync Server Administrative Tools](https://technet.microsoft.com/library/9b006f93-4f3d-461d-89b8-e80a34fdb3c5.aspx).</span></span>

<span data-ttu-id="c4267-172">单击“确定”以保存并将更改应用到拓扑文档。</span><span class="sxs-lookup"><span data-stu-id="c4267-172">Click **OK** to save and commit your changes to the topology document.</span></span>

<span data-ttu-id="c4267-173">单击 **"** 取消"将放弃所做的更改并关闭前端服务器或前端池的"编辑属性"。</span><span class="sxs-lookup"><span data-stu-id="c4267-173">Click **Cancel** to discard your changes and close the **Edit Properties** for the Front End Server or Front End pool.</span></span>

<span data-ttu-id="c4267-174">单击“帮助”以阅读本帮助主题。</span><span class="sxs-lookup"><span data-stu-id="c4267-174">Click **Help** to read this help topic.</span></span>

## <a name="see-also"></a><span data-ttu-id="c4267-175">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c4267-175">See also</span></span>

[<span data-ttu-id="c4267-176">定义和配置前端池</span><span class="sxs-lookup"><span data-stu-id="c4267-176">Define and Configure a Front End Pool or Standard Edition Server</span></span>](https://technet.microsoft.com/library/713fc263-23dd-414a-b001-82932e4fe966.aspx)
