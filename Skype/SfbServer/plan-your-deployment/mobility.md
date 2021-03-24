---
title: Plan for Mobility for Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 2/17/2018
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7117eff5-6860-4673-b366-afe0756c4bb2
description: Plan for your implementation of Mobility for Skype for Business Server.
ms.openlocfilehash: 5c33c88d13dd3720d1526c1620f852fe176a9750
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096638"
---
# <a name="plan-for-mobility-for-skype-for-business-server"></a>Plan for Mobility for Skype for Business Server
 
Plan for your implementation of Mobility for Skype for Business Server.
  
使用 Skype for Business Server，可以部署移动功能以在移动设备上提供 Skype for Business Server 功能。 本文提供有关移动功能的详细信息，并帮助您规划部署。
  
Skype for Business Server 的移动功能支持 Skype for Business 的移动客户端，以及可返回到 2010 的 Lync 客户端。 部署后，你的用户可以使用受支持的 iOS、Android 和 Windows Phone 移动设备连接到 Skype for Business Server 部署，以利用几种不同的功能，包括企业语音功能。 我们在下面包含了部分列表，还可以查看 [Skype for Business](clients-and-devices/desktop-feature-comparison.md) 的桌面客户端功能比较，了解详细信息：
  
- 发送和接收邮件
    
- 查看状态
    
- 查看联系人
    
- 单击以加入会议
    
- 通过工作电话呼叫
    
- 单一号码范围
    
- 语音邮件
    
- 未接来电通知
    
- IP 电话 (VoIP)
    
- H.264 (与会者视频) 
    
- 查看 PowerPoint (桌面/应用程序共享功能的会议) 
    
所有这些操作都是通过统一通信 Web API 或 UCWA 完成的。 UCWA 在 Lync Server 2013 中首次引入，现在仍用于 Skype for Business Server。 此外，还有一项与 Lync 2010 客户端进行通信的附加功能，即 Mobility Service (MCX) 。 这些服务是免费服务，允许 Lync Server 2010 和 2013 客户端以及 Skype for Business 客户端成功访问 Skype for Business Server 部署。
  
> [!NOTE]
> Skype for Business Server 2019 (MCX) Mobility Service 不再提供对旧版移动客户端的支持。 所有当前的 Skype for Business 移动客户端已使用统一通信 Web API (UCWA) 来支持即时消息 (IM) 、状态和联系人。 使用 MCX 的旧客户端的用户将需要升级到当前客户端。
  
值得注意的是，虽然这些功能一经实现就可用，但在某些设备上可能有点不同。 我们在 Mobile client feature comparison for Skype for Business [（Skype for Business](clients-and-devices/mobile-feature-comparison.md)的移动客户端功能比较）上获取了一个网站，讨论哪些功能适用于哪些设备。 我们还在 Plan for clients and devices 中提供一 [些出色的设备和操作系统信息](clients-and-devices/clients-and-devices.md)。
  
移动性利用自动发现功能，该功能允许客户端自动找到 Skype for Business Server Web 服务，而无需输入任何 URL (他们甚至无需知道这些 url) 。 如果需要执行一些故障排除，仍支持手动输入 URL。
  
推送通知也受支持，当 Skype for Business 应用未在后台 (中运行时，或者对于不支持在后台运行应用程序的移动设备) 。 当设备或应用处于非活动状态时，会向移动设备发送有关所发生事件的推送通知。 一个很好的示例是在手机不活动时缺少 IM 消息，这可能会导致推送通知被发送 (这将显示为 toast 或通知，就像应用在后台) 中运行时一样。 使用推送通知，用户不会错过 IM 或语音呼叫。
  
有关详细信息，我们包含以下部分：
  
- [移动组件](mobility.md#MobilityComponents)
    
- [受支持的拓扑](mobility.md#SupportedTopos)
    
- [技术要求](mobility.md#TechRequirements)
    
- [定义移动需求](mobility.md#MobilityNeeds)
    
## <a name="mobility-components"></a>移动组件
<a name="MobilityComponents"> </a>

Skype for Business Server 移动性包含四种服务：
  
- **统一通信 Web API (UCWA)**
    
    为 Skype for Business Server 的移动和 Web 客户端提供实时通信服务。 部署 Skype for Business Server 时，UCWA 虚拟目录在内部和外部 Web 服务中创建。 此虚拟目录中的一个虚拟组件，用于接受来自启用 UCWA 的客户端的呼叫。 客户端应用通过表述性状态传输 (REST) 接口进行通信，用于：
    
  - 状态
    
  - contacts
    
  - 即时消息 (IM) 
    
  - VoIP
    
  - 视频会议
    
  - 协作
    
    UCWA 使用基于 P-GET 的通道将事件（如传入呼叫、传入 IM 或消息）发送到客户端应用程序。
    
- **Mobility service (MCX)**
    
    支持移动设备上的 Skype for Business Server 功能，例如 IM、状态和联系人。 Mobility Service 安装在每个池中的每台前端服务器上，旨在支持移动设备上的 Skype for Business Server 功能。 安装 Skype for Business Server 2015 时，在前端服务器的内部和外部网站下 (Mcx) 将创建一个新的虚拟目录。
    
    > [!NOTE]
    > Skype for Business Server 2019 (MCX) Mobility Service 不再提供对旧版移动客户端的支持。 所有当前的 Skype for Business 移动客户端已使用统一通信 Web API (UCWA) 来支持即时消息 (IM) 、状态和联系人。 使用 MCX 的旧客户端的用户将需要升级到当前客户端。
  
- **自动发现服务**
    
    标识用户的位置，并允许移动设备和其他 Skype for Business 客户端查找资源 (如 Skype for Business Server Web 服务的内部和外部 URL、Mcx URL 或 UCWA URL) 而不考虑网络位置。 自动发现对网络 (lyncdiscoverinternal、lyncdiscover for users outside the network) 和用户的 SIP 域使用硬编码主机名。 它支持使用 HTTP 或 HTTPS 的客户端连接。 
    
    自动发现服务安装在每台前端服务器和每个池中的控制器上，旨在支持移动设备上的 Skype for Business Server 功能。 安装该服务时，将 (前端服务器和) 上的内部和外部网站下创建一个新的自动发现虚拟目录。
    
- **推送通知服务**
    
    位于 Skype for Business Online 数据中心的基于云的服务。 在未在后台运行 Skype for Business 客户端的手机上，当发生新事件时，会向移动设备发送名为 (推送通知) 未接事件的通知。 Mobility Service 向 MPNS (推送通知服务) ，然后向移动设备发送通知。 然后，用户可以在移动设备上响应通知以激活应用。 此功能需要边缘服务器。
    
## <a name="supported-topologies"></a>受支持的拓扑
<a name="SupportedTopos"> </a>

我们的拓扑规划支持以下 Skype for Business Server 应用程序：
  
- Mobility Standard Edition
    
- Mobility Enterprise Edition
    
你应该能够将此功能与 Skype for Business Server 边缘服务器或 Lync Server 2013 边缘服务器一同使用。
  
与中介服务器角色并排在一起（具有两个网络接口）时，前端服务器支持 Mobility Service，但您需要采取适当步骤来配置这些接口。 您需要将 IP 地址分配给将作为中介服务器进行通信的特定接口，以及将作为前端服务器通信的网络 IP 接口。 可以在拓扑生成器中为此选择每个服务的正确 IP 地址，而不是使用默认的"使用所有已配置的 **IP 地址"** 选项。
  
## <a name="technical-requirements"></a>技术要求
<a name="TechRequirements"> </a>

规划移动用户可能会遇到的各种移动应用程序方案非常重要。 例如，某人可能通过 3G 网络进行连接，开始在工作之外使用移动应用，然后在工作Wi-Fi公司网络。 他们离开大楼时可能会切换到 4G。 现在，规划将允许你支持这些网络转换，并保证一致的用户体验。
  
### <a name="dns-configuration"></a>DNS 配置

Mobility Services Mcx 和 UCWA 以相同方式使用 DNS。 通过自动发现，移动设备可使用 DNS 查找资源。 在 DNS 查找过程中，将尝试连接到与 lyncdiscoverinternal 中的内部 DNS 记录关联的 FQDN (DNS。[内部域名]) 。 如果内部 DNS 记录不能用于建立该连接，则尝试进行第二次连接，这次连接到 lyncdiscover (DNS 记录。[sipdomain]) 。 那么，为什么有两个？ 网络内部的移动设备将能够使用内部自动发现 URL。 外部移动设备将使用外部自动发现 URL。 在任一情况下，自动发现服务都会返回用户主池的所有 Web 服务 URL，其中包括 Mobility service (Mcx 和 UCWA) 。
  
预计外部自动发现请求将经过你为 Skype for Business Server 配置的反向代理。 但是，内部 Mobility Service URL 和外部 Mobility Service URL 都与外部 Web 服务 FQDN 关联。 因此，无论移动设备是网络内部设备还是外部设备，该设备始终通过反向代理从外部连接到 Skype for Business Server Mobility Service。
  
> [!NOTE]
> 正如我们刚才指出的，内部和外部 (所有 mobility service) 流量都将通过反向代理。 但有时，当内部流量通过接口离开时，只有在同一接口上尝试返回时，才出现问题。 这可能会违反你的欺骗 (，正式称为 TCP 数据包欺骗) 安全规则。 你需要允许发夹 **具有** 移动功能。
  
> [!NOTE]
> 如果你已准备好这样做，还可以选择使用独立于防火墙 (的反向代理用于安全目的，欺骗防护应始终在防火墙) 。 这样，发夹可以在反向代理的外部接口（而不是防火墙的外部接口）上发生。 这允许你在防火墙上正确检测欺骗，同时在反向代理上放宽规则，并获取移动功能。 
  
> [!NOTE]
> 如果转到此路由，请务必使用 DNS 主机或 CNAME 记录为发夹行为定义反向代理， (防火墙) （如果可能）。 
  
需要配置一些内容以支持企业网络内外的用户。
  
以下为内部和外部 Web FQDN 的规则：
  
- 新的 CNAME 或 A (主机（如果 IPv6，则 AAAA) DNS 记录）进行自动发现。
    
- 新防火墙规则，如果要通过你的防火墙网络支持推送通知Wi-Fi规则。
    
- 内部服务器证书和反向代理证书上的备用主题名称，用于自动发现。
    
- 前端服务器硬件负载平衡配置会更改源相关性。
    
这些是支持 Mobility Service 和自动发现服务所需的拓扑要求：
  
- 前端池内部 Web FQDN 必须与前端池外部 Web FQDN 不同。
    
- 内部 Web FQDN 只能解析为企业网络内部，并且可从企业网络内部访问。
    
- 外部 Web FQDN 只能解析为 Internet，并且可从 Internet 访问。
    
- 对于企业网络内部的用户，必须将 Mobility Service URL 寻址到外部 Web FQDN。 此要求适用于 Mobility Service，仅适用于此 URL。
    
- 对于企业网络外部的用户，请求必须转到前端池或控制器的外部 Web FQDN。
    
如果支持自动发现，则需要针对每个 SIP 域创建以下 DNS 记录：
  
- 用于支持从组织网络内部进行连接的移动用户的内部 DNS 记录。
    
- 用于支持从 Internet 连接的移动用户的外部（或公共）DNS 记录。
    
不应从内部网络外部对内部自动发现 URL 进行地址处理。 不应从网络内对外部自动发现 URL 进行地址处理。 但是，如果外部 URL 无法这样做，您的移动客户端功能可能不会受到影响，因为始终会先尝试内部 URL。
  
### <a name="port-and-firewall-requirements"></a>端口和防火墙要求

我们已在其他文档中介绍大部分内容，但专门针对移动性，如果你有任何用户位于 Survivable Branch Appliance (SBA 上，你将希望让企业 Wi-Fi 网络打开以下) 端口：
  
- UcwaSipExternalListeningPort 需要 5088。
    
- UcwaSipPrimaryListeningPort 需要 5089。
    
### <a name="certificate-requirements"></a>证书要求

如果对 Skype for Business 移动客户端使用自动发现，则需要修改证书上的 SAN (主题备用名称) 列表，以支持来自移动客户端的安全连接。 如果已有证书就地，则需要请求并分配包含此处所述的 SAN 条目的新证书。 如果环境中运行的是自动发现服务 (前端服务器和控制器) 需要执行这一操作。 我们还建议修改反向代理证书上的 SAN 列表，为组织中添加每个 SIP 域的 SAN 条目。
  
如果要从内部 CA (证书颁发机构) 请求新证书，这应该是一个简单的过程，但公共证书更为复杂，而且重新请求的成本可能更高，更不用提将大量 SIP 域添加到新的公共证书的成本。在这种情况下，有一种方法受支持，但不 **推荐使用**。 您可以将反向代理配置为通过端口 80（将使用 HTTP，而不是端口 443，即 HTTPS (）提出初始自动发现服务请求，443 是默认配置) 。 该传入请求将重定向到前端池或控制器上的端口 8080。 通过执行此操作，无需进行任何证书更改，因为此流量不会对请求使用 HTTPS。 但同样，我们不建议这样做，尽管它适合你。
  
### <a name="windows-and-iis-requirements"></a>Windows 和 IIS 要求

你应该具有 Skype for Business Server 环境支持的 Windows Server 版本。 因此，您还应具有 IIS 8 或 IIS 8.5 以满足您的移动需求。 需要对默认策略设置进行一些 ASP.NET，但 Mobility Service 安装程序会自动执行这些更改。
  
### <a name="hlb-requirements"></a>HLB 要求

如果使用的 Skype for Business Server 拓扑包括前端池 (该拓扑可能是包括多个前端服务器) 的任何拓扑，则需要为源配置用于 Web 服务流量的外部 Web 服务虚拟 IP () 。 源相关性有助于确保将来自单个客户端的多个连接发送到同一服务器以保持会话状态。
  
如果计划仅通过内部 Wi-Fi 网络支持 Skype for Business 移动客户端，应为源配置内部 Web 服务 IP，如外部 Web 服务 ISP 所述。 在这种情况下，您应对 HLB 上的source_addr (WEB) 使用 TCP 或 TCP 关联。
  
有关所有这些的详细信息，请查看 [Skype for Business 的](network-requirements/load-balancing.md) 负载平衡要求文档。
  
### <a name="reverse-proxy-requirements"></a>反向代理要求

为了支持 Skype for Business 移动客户端的自动发现，你需要更新当前发布规则，如下所示：
  
- 如果您决定更新反向代理证书上的 SAN 列表，并且对初始自动发现服务请求使用 HTTPS，则需要更新 lyncdiscover 的 Web 发布规则 \<sipdomain\> 。 这通常与前端池上的外部 Web 服务 URL 的发布源结合使用。
    
- 如果您决定对初始自动发现服务请求使用 HTTP，以避免必须更新反向代理证书 (我们不建议使用) 的 SAN 列表，则需要为端口 HTTP/TCP 80 创建新的 Web 发布规则（如果尚未更新）。 如果该规则存在，请更新该规则以包含 lyncdiscover。\<sipdomain\> 条目。
    
## <a name="defining-your-mobility-needs"></a>定义移动需求
<a name="MobilityNeeds"> </a>

既然我们已经查看了拓扑、组件和技术要求，让我们看一下贵组织在移动性实现方面可能需要哪些内容。
  
### <a name="do-you-want-to-use-automatic-discovery-for-skype-for-business-mobile-clients"></a>是否要对 Skype for Business 移动客户端使用自动发现？

我们强烈建议你使用自动发现。 这将需要新建内部和外部 DNS 记录，如上面的"技术要求"部分所述。 通过自动发现，Skype for Business 客户端可以从任何位置自动找到 Skype for Business Server Web 服务，而无需手动输入 URL。
  
如果需要，可以使用手动设置。 用户需要将以下 URL 输入到其移动设备上：
  
- **https:// \<ExtPoolFQDN\> /Autodiscover/autodiscoverservice.svc/Root** 进行外部访问。
    
- **https:// \<IntPoolFQDN\> /Autodiscover/autodiscoverservice.svc/Root** 进行内部访问。
    
同样，我们建议使用自动发现。 您可能会发现手动设置对疑难解答很有用。
  
### <a name="are-you-going-to-support-push-notifications"></a>是否支持推送通知？

推送通知用于支持此功能的移动应用程序，以在应用不活动时通知用户事件。 边缘服务器需要与基于云的 Skype for Business Server 推送通知服务（位于 Skype for Business Online 数据中心）建立联盟关系。 需要运行 cmdlet 才能启用推送通知。
  
> [!NOTE]
> 如果有任何人仍在使用 Lync Server 2010 客户端，他们需要 TCP 端口 5223 在企业 WiFi 网络上开放出站。 
  
### <a name="do-you-want-all-your-users-accessing-all-mobility-features-or-do-you-want-to-specify-the-users-who-can-access-these-features-instead"></a>您是否希望所有用户都访问所有移动功能，或者是否希望指定可以访问这些功能的用户？

我们提供了一个表，可帮助处理所有用户可用的一些功能，以及默认情况下是否按此方式设置这些功能。 有关完整列表，请查看[New-CsMobilityPolicy。](/powershell/module/skype/new-csmobilitypolicy?view=skype-ps)
  
> [!NOTE]
> 所有这些功能的作用域是 Global/Site/User。 
  
|**功能**|**参数名**|**描述**|**默认设置**|
|:-----|:-----|:-----|:-----|
|启用移动性  <br/> |EnableMobility  <br/> |控制给定范围内安装了 Skype for Business 移动客户端的用户。 如果策略设置为 False，用户将无法使用其客户端登录。  <br/> |True  <br/> |
|外部语音  <br/> |EnableOutsideVoice  <br/> |使用户能够使用通过工号呼叫功能，这使用户可以使用其工作号码而不是其移动电话号码发送和接收呼叫。 如果设置为 False，用户在使用工作电话号码时将无法通过移动电话拨打或接听电话。  <br/> |True  <br/> |
|启用 IP 音频和视频  <br/> |EnableIPAudioVideo  <br/> |设置为默认值，允许用户使用 VoIP 在移动设备上拨打或接听电话或视频呼叫。 设置为 False 时，用户将无法使用其移动设备执行上述任一操作。  <br/> |True  <br/> |
|IP 音频需要 WiFi  <br/> |RequireWiFiForIPAudio  <br/> |定义客户端是否需要通过 WiFi 而不是手机数据网络通过 VoIP 拨打和接听电话。 如果设置为 True，则用户只有在通过 WiFi 连接时才能拨打和接听 VoIP 呼叫。  <br/> |False  <br/> |
|IP 视频需要 WiFi  <br/> |RequireWiFiForIPVideo  <br/> |定义客户端是否需要在 WiFi（而不是手机数据网络）上拨打和接听视频呼叫。 如果设置为 True，则用户只有在通过 WiFi 连接时才能拨打和接听 VoIP 呼叫。  <br/> |False  <br/> |
   
### <a name="should-users-who-arent-enabled-for-enterprise-voice-be-able-to-use-click-to-join-to-join-conferences"></a>未启用此功能的用户企业语音单击以加入会议吗？

若要使用户可以访问移动功能和通过工位呼叫功能，需要为用户启用企业语音。 但是，即使未启用它们，他们仍然可以通过单击其移动设备上的链接来加入会议，但只有在他们分配了相应的语音策略时才能加入会议。 您可以：
  
- 为这些用户分配特定语音策略，或者
    
- 确保全局策略或站点级别的策略存在并应用于它们。
    
无论使用哪种方式，你分配的语音策略都需要有公用电话交换网 (PSTN) 用法记录和路由，这些记录和路由将定义你的用户能够拨出加入会议的地方。
  
> [!NOTE]
> 想要使用"单击以加入"的移动用户需要语音策略以及相关的 PSTN 用法记录和语音路由，因为当他们在移动设备上单击该链接时，将会产生来自 Skype for Business Server 的出站呼叫。 
