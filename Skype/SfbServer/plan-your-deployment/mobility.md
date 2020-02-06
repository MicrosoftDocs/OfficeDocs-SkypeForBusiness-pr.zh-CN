---
title: 适用于 Skype for business 服务器的移动性计划
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 对 Skype for business 服务器的移动性进行规划。
ms.openlocfilehash: dd57da19a935ce1a8713cc856d553b81f4f7cd6b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815850"
---
# <a name="plan-for-mobility-for-skype-for-business-server"></a>适用于 Skype for business 服务器的移动性计划
 
对 Skype for business 服务器的移动性进行规划。
  
通过 Skype for Business 服务器，你可以部署移动功能，以便在移动设备上提供 Skype for business 服务器功能。 本文提供有关移动功能的详细信息，并帮助你规划部署。
  
Skype for business 服务器的移动功能能够支持 Skype for business 的移动客户端，以及要返回到2010的 Lync 客户端。 部署后，用户可以使用支持的 iOS、Android 和 Windows Phone 移动设备连接到 Skype for Business 服务器部署，以利用多种不同的功能，包括企业语音功能。 我们已包含下面的部分列表，你也可以查看[Skype For business 的桌面客户端功能比较](clients-and-devices/desktop-feature-comparison.md)，了解详细信息：
  
- 发送和接收消息
    
- 查看状态
    
- 查看联系人
    
- 单击加入会议
    
- 通过工号拨号
    
- 一号通
    
- 语音邮件
    
- 未接电话通知
    
- IP 语音 (VoIP)
    
- 与会者视频 (H.264)
    
- 查看会议内容（PowerPoint 和桌面/应用程序共享）
    
所有这些功能均通过统一通信 Web API (UCWA) 实现。 UCWA 是 Lync Server 2013 中第一次引入的，它仍用于 Skype for business 服务器。 还有另一种与 Lync 2010 客户端进行通信的功能，以及它的移动服务（MCX）。 这些是免费服务，允许 Lync Server 2010 和2013客户端以及 Skype for business 客户端成功访问 Skype for business 服务器部署。
  
> [!NOTE]
> 在 Skype for Business Server 2019 中，MCX （移动服务）对旧式移动客户端的支持不再可用。 所有当前 Skype for business 移动客户端都已使用统一通信 Web API （UCWA）来支持即时消息（IM）、状态和联系人。 具有使用 MCX 的旧客户端的用户将需要升级到当前客户端。
  
请务必注意，虽然所有这些功能在实现移动性后均可使用，但它们在某些设备上的工作方式可能稍有不同。 我们在[Skype for business 的移动客户端功能比较](clients-and-devices/mobile-feature-comparison.md)中提供了一个网站，讨论哪些功能适用于哪些设备。 我们还[为客户和设备计划](clients-and-devices/clients-and-devices.md)提供了一些出色的设备和操作系统信息。
  
移动利用自动发现功能，使客户能够自动找到 Skype for Business 服务器 web 服务，而无需用户输入任何 Url （甚至不需要知道它们）。 如果你需要执行某些故障排除操作，仍支持手动输入 URL。
  
如果 Skype for Business 应用未在后台运行（或不支持后台运行的应用程序的移动设备），则还支持推送通知。 当设备或应用处于非活动状态时，向移动设备发送关于所发生事件的推送通知。 例如，当手机处于非活动状态而错过 IM 消息时，就会发送推送通知（采用 Toast 或通知的形式，就像应用在后台运行时那样）。 借助推送通知，用户就不会错过 IM 或语音呼叫。
  
有关详细信息，请参阅以下部分：
  
- [移动组件](mobility.md#MobilityComponents)
    
- [支持的拓扑](mobility.md#SupportedTopos)
    
- [技术要求](mobility.md#TechRequirements)
    
- [定义你的移动性需求](mobility.md#MobilityNeeds)
    
## <a name="mobility-components"></a>移动组件
<a name="MobilityComponents"> </a>

适用于 Skype for business 服务器的移动有四种服务：
  
- **统一通信 Web API (UCWA)**
    
    提供与 Skype for business 服务器的移动和 web 客户端进行实时通信的服务。 部署 Skype for Business 服务器时，在内部和外部 web 服务中创建的 UCWA 虚拟目录。 此虚拟目录中的虚拟组件接受支持 UCWA 的客户端发出的呼叫。 客户端应用程序通过表述性状态转移 (REST) 接口进行通信，用于：
    
  - presence － 状态
    
  - 联系人
    
  - 即时消息 (IM)
    
  - VoIP
    
  - 视频会议
    
  - 协作
    
    UCWA 使用基于 P-GET 的通道发送事件，例如来电、传入的 IM 或者发送到客户端应用的消息。
    
- **移动性服务 (MCX)**
    
    支持移动设备上的 Skype for business 服务器功能，如 IM、联机状态和联系人。 移动服务在每个池中的每个前端服务器上安装，用于在移动设备上支持 Skype for business Server 功能。 安装 Skype for Business Server 2015 时，将在前端服务器上的内部和外部网站下创建新的虚拟目录（Mcx）。
    
    > [!NOTE]
    > 在 Skype for Business Server 2019 中，MCX （移动服务）对旧式移动客户端的支持不再可用。 所有当前 Skype for business 移动客户端都已使用统一通信 Web API （UCWA）来支持即时消息（IM）、状态和联系人。 具有使用 MCX 的旧客户端的用户将需要升级到当前客户端。
  
- **自动发现服务**
    
    标识用户的位置，并允许移动设备和其他 Skype for business 客户端查找资源（如 Skype for business Server Web 服务的内部和外部 URL、Mcx URL 或 UCWA URL），无论网络位置如何。 自动发现功能使用硬编码的主机名（对于网络内部用户，为 lyncdiscoverinternal；对于网络外部用户，为 lyncdiscover）和用户的 SIP 域。 它支持使用 HTTP 或 HTTPS 的客户端连接。 
    
    自动发现服务在每个前端服务器和每个池中的每个控制器上安装，用于在移动设备上支持 Skype for business Server 功能。 安装该服务时，将在前端服务器和控制器上的内部和外部网站下创建新的虚拟目录（自动发现）。
    
- **推送通知服务**
    
    位于 Skype for Business Online 数据中心的基于云的服务。 在没有在后台运行 Skype for Business 客户端的手机上，当发生新事件时，错过事件的通知（称为推送通知）将改为发送到移动设备。 移动服务向推送通知服务（MPNS）发送通知，然后将其发送到移动设备。 然后，用户可以在其移动设备上响应此通知，以激活应用。 此功能需要边缘服务器。
    
## <a name="supported-topologies"></a>支持的拓扑
<a name="SupportedTopos"> </a>

我们有以下受支持的 Skype for business 服务器应用程序用于你的拓扑规划：
  
- 移动标准版
    
- 移动企业版
    
你应该能够将此功能与 Skype for Business 服务器边缘服务器或 Lync Server 2013 Edge 服务器配合使用。
  
当 collocated 使用中介服务器角色（具有两个网络接口）时，移动服务在前端服务器上受支持，但你需要采取相应的步骤来配置这些接口。 你需要将 IP 地址分配给将作为中介服务器通信的特定接口，以及将作为前端服务器通信的网络 IP 接口。 你可以在拓扑生成器中执行此操作，方法是为每个服务选择正确的 IP 地址，而不是使用默认**使用所有配置的 IP 地址**选择。
  
## <a name="technical-requirements"></a>技术要求
<a name="TechRequirements"> </a>

针对移动用户可能遇到的各种移动应用程序方案做好规划非常重要。 例如，有些人可能在工作之余通过连接到 3G 网络使用移动应用，然后在工作时切换到公司 Wi-Fi 网络。 他们在离开建筑物时可能会切换到4G。 现在进行规划有助于为这些网络转换提供支持并保证一致的用户体验。
  
### <a name="dns-configuration"></a>DNS 配置

移动服务 Mcx 和 UCWA 以同样的方式使用 DNS。 利用自动发现，移动设备使用 DNS 定位资源。 在 DNS 查找期间，尝试连接到与内部 DNS 记录关联的 FQDN (lyncdiscoverinternal.[内部域名])。 如果无法使用内部 DNS 记录实现连接，将尝试进行第二次连接，这次将连接到外部 DNS 记录 (lyncdiscover.[sipdomain])。 为什么会有两个呢？ 位于网络内部的移动设备可以使用内部自动发现 URL。 外部移动设备将使用外部自动发现 URL。 在任何一种情况下，自动发现服务都将返回用户的主池的所有 Web 服务 Url，其中包括移动服务（Mcx 和 UCWA）。
  
预计外部自动发现请求将经历您为 Skype for business 服务器配置的反向代理。 但是，内部移动服务 URL 和外部移动服务 URL 均与外部 Web 服务 FQDN 相关联。 因此，无论移动设备是网络的内部还是外部设备，设备都将始终通过反向代理连接到外部的 Skype for business 服务器移动服务。
  
> [!NOTE]
> 正如我们刚刚说过的，所有移动服务流量（内部和外部）都将通过您的反向代理。 但是，当内部通信通过某个接口离开，然后又只能返回到相同的接口时，偶尔会发生问题。 这可能会违反欺骗（之前称为 TCP 数据包欺骗）安全规则。 您需要允许**头发钉住**有移动功能。
  
> [!NOTE]
> 如果你已准备好执行此操作，你也可以选择使用独立于防火墙的反向代理（出于安全考虑，应始终在防火墙上强制使用欺骗防护）。 这样，hairpin 可能会在反向代理的外部接口（而不是防火墙的外部接口）上发生。 这使你可以在你的反向代理上放宽规则的同时在你的防火墙上检测欺骗，并且你可以获得移动功能。 
  
> [!NOTE]
> 如果你转到此路线，请确保使用 DNS 主机或 CNAME 记录来定义 hairpin 行为（而非防火墙）的反向代理（如有可能）。 
  
要支持企业网络内部和外部的用户，你需要执行几项配置操作。
  
这些是用于内部和外部 Web FQDN 的规则：
  
- 新的 CNAME 或 A（主机，如果是 IPv6，则为 AAAA）DNS 记录（用于自动发现）。
    
- 新防火墙规则（如果希望通过 Wi-Fi 网络支持推送通知）。
    
- 内部服务器证书上的使用者备用名称和反向代理证书，用于自动发现。
    
- 前端服务器硬件负载平衡配置更改源关联。
    
以下是支持移动服务和自动发现服务所需的拓扑要求：
  
- 前端池内部 web FQDN 必须与前端池外部 web FQDN 不同。
    
- 内部 Web FQDN 必须仅解析为企业网络地址且仅能从企业网络内部进行访问。
    
- 外部 Web FQDN 必须仅解析为 Internet 地址且仅能从 Internet 进行访问。
    
- 对于企业网络内的用户，移动服务 URL 必须寻址到外部 web FQDN。 此要求适用于移动服务，并且仅适用于此 URL。
    
- 对于公司网络外部的用户，请求必须转到前端池或控制器的外部 web FQDN。
    
如果你支持自动发现，则需要为每个 SIP 域创建以下 DNS 记录：
  
- 内部 DNS 记录，用于支持从组织网络内部进行连接的移动用户。
    
- 外部或公共 DNS 记录，用于支持从 Internet 进行连接的移动用户。
    
应无法从内部网络外部对内部自动发现 URL 进行寻址。应无法从网络内部对外部自动发现 URL 进行寻址。但是，如果无法满足外部 URL 的此要求，可能也不会影响移动客户端的功能，因为始终会先尝试内部 URL。
  
### <a name="port-and-firewall-requirements"></a>端口和防火墙要求

我们在其他文档中介绍了大部分内容，但特别是对于移动性，如果你有任何用户驻留在 Survivable 分支设备（SBA）上，你将希望在企业 Wi-fi 网络上打开以下端口：
  
- UcwaSipExternalListeningPort 需要 5088。
    
- UcwaSipPrimaryListeningPort 需要 5089。
    
### <a name="certificate-requirements"></a>证书要求

如果你使用的是 Skype for Business 移动客户端的自动发现，则需要修改你的证书上的 SAN （使用者备用名称）列表，以支持来自移动客户端的安全连接。 如果已将证书准备就绪，则需要请求并分配包含此处所述 SAN 条目的新证书。 需要针对运行自动发现服务的每个前端服务器和控制器（如果在你的环境中）执行此操作。 我们还建议在反向代理证书上修改 SAN 列表，并为组织中的每个 SIP 域添加 SAN 条目。
  
如果你向内部 CA （证书颁发机构）请求新证书，但公共证书更复杂，并且可能需要更昂贵的重新请求，则这应该是一个简单的过程，而不是提及在新的公共证书中添加大量 SIP 域可能会花费大量费用。在这种情况下，有一种受支持的方法，但**不建议这样做**。 你可以将反向代理配置为通过端口80发出初始自动发现服务请求，该请求将使用 HTTP，而不是端口443，后者是 HTTPS （和443是默认配置）。 该传入请求将被重定向到您的前端池或控制器上的端口8080。 通过执行此操作，无需再更改任何证书，因为此通信为请求使用的不是 HTTPS。 再次说明，尽管你可以使用此方法，但我们不建议这样做。
  
### <a name="windows-and-iis-requirements"></a>Windows 和 IIS 要求

您的 Skype for business 服务器环境应具有受支持的 Windows Server 版本。 因此，你还需要具有 IIS 8 或 IIS 8.5 才能满足你的移动性需求。 将需要对默认 ASP.NET 设置进行一些更改，但移动服务安装程序将自动执行此操作。
  
### <a name="hlb-requirements"></a>HLB 要求

如果你使用的是 Skype for Business 服务器的拓扑，并且该服务器包含 HLB 前端池的一个拓扑（这将是包括多个前端服务器的任何拓扑），则需要为 Web 服务流量配置外部 Web 服务虚拟 IPs （Vip）适用于源。 源关联有助于确保将单个客户端的多个连接发送给同一台服务器以保持会话状态。
  
如果你计划仅在内部 Wlan 网络上支持 Skype for Business 移动客户端，你应该为源配置内部 Web 服务 Vip，如外部 Web 服务 Vip 所述。 在这种情况下，你应该对 HLB 上的内部 Web 服务 Vip 使用 source_addr （或 TCP）关联。
  
有关所有详细信息，请参阅 [Load balancing requirements for Skype for Business](network-requirements/load-balancing.md)文档。
  
### <a name="reverse-proxy-requirements"></a>反向代理要求

为了支持 Skype for business 移动客户端的自动发现，你需要更新当前发布规则，如下所示：
  
- 如果你决定更新反向代理证书上的 SAN 列表，并且你对初始自动发现服务请求使用 HTTPS，则需要更新 lyncdiscover 的 web 发布规则。\<sipdomain\>。 这通常与前端池中的外部 Web 服务 URL 的发布 rul 结合。
    
- 如果你已决定将 HTTP 用于初始自动发现服务请求，以避免更新反向代理证书的 SAN 列表（我们不推荐使用），则需要为端口 HTTP/TCP 80 创建新的 web 发布规则（如果尚未有的话）。 如果存在该规则，请将其更新为包含 lyncdiscover。\<sipdomain\>条目。
    
## <a name="defining-your-mobility-needs"></a>定义你的移动性需求
<a name="MobilityNeeds"> </a>

我们已经查看了拓扑、组件和技术要求，让我们来看看你的组织在移动实施方面可能需要的内容。
  
### <a name="do-you-want-to-use-automatic-discovery-for-skype-for-business-mobile-clients"></a>是否要为 Skype for Business 移动客户端使用自动发现功能？

强烈建议你使用自动发现。 如上面的“技术要求”部分所述，这需要创建新的内部和外部 DNS 记录。 使用自动发现，Skype for Business 客户端可以自动从任何位置找到 Skype for business Server Web 服务，无需手动输入 URL。
  
如果需要，你也可以使用手动设置。 用户需要将以下 URL 输入到其移动设备中：
  
- **Https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root** ，用于外部访问。
    
- **Https://\<IntPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root** ，用于内部访问。
    
再次强调一下，我们建议使用自动发现。你会发现手动设置对于故障排除很有用。
  
### <a name="are-you-going-to-support-push-notifications"></a>你是否打算支持推送通知？

推送通知用于支持此功能的移动应用程序，可以在应用处于非活动状态时将事件通知给用户。 边缘服务器需要与基于云的 Skype for business 服务器推送通知服务（在 Skype for business Online 数据中心中）进行联合身份验证关系。 你需要运行 cmdlet 以启用推送通知。
  
> [!NOTE]
> 如果您的任何人仍在使用 Lync Server 2010 客户端，他们将需要在您的企业 WiFi 网络上打开 TCP 端口5223。 
  
### <a name="do-you-want-all-your-users-accessing-all-mobility-features-or-do-you-want-to-specify-the-users-who-can-access-these-features-instead"></a>您是否希望所有用户都能访问所有移动功能，或者是否希望指定可以访问这些功能的用户？

我们有一个表，可帮助所有用户使用某些功能，以及默认情况下是否设置了这些功能。 有关完整列表，请参阅 [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps)。
  
> [!NOTE]
> 所有这些功能的适用范围为全局/站点/用户。 
  
|**功能**|**参数名称**|**说明**|**默认设置**|
|:-----|:-----|:-----|:-----|
|支持移动性  <br/> |EnableMobility  <br/> |控制已安装 Skype for business mobile 客户端的给定范围内的用户。 如果该策略设置为 False，用户将无法登录其客户端。  <br/> |True  <br/> |
|外部语音  <br/> |EnableOutsideVoice  <br/> |使用户可以使用“通过工号拨号”功能，该功能允许用户使用其工作号码而不是自己的移动号码来拨打和接听电话。如果设置为 False，用户在使用其工作电话号码时，将无法在其移动电话上拨打或接听电话。  <br/> |True  <br/> |
|支持 IP 音频和视频  <br/> |EnableIPAudioVideo  <br/> |设置为默认值，允许用户在其移动设备上使用 VoIP 拨打或接听电话或视频电话。如果设置为 False，用户将无法使用其移动设备执行这些操作。  <br/> |True  <br/> |
|IP 音频需要 WiFi  <br/> |RequireWiFiForIPAudio  <br/> |定义客户端是否需要通过 WiFi 而不是手机数据网络拨打和接听 VoIP 电话。如果设置为 True，则用户仅在连接到 WiFi 网络时才能拨打和接听 VoIP 电话。  <br/> |False  <br/> |
|IP 视频需要 WiFi  <br/> |RequireWiFiForIPVideo  <br/> |定义客户端是否需要通过 WiFi 而不是手机数据网络拨打和接听视频电话。如果设置为 True，则用户仅在连接到 WiFi 网络时才能拨打和接听 VoIP 电话。  <br/> |False  <br/> |
   
### <a name="should-users-who-arent-enabled-for-enterprise-voice-be-able-to-use-click-to-join-to-join-conferences"></a>未启用企业语音的用户能否使用“单击以加入”来加入会议？

为了让用户能够访问移动功能并通过工作进行呼叫，他们需要为企业语音启用。 不过，即使没有为他们启用此功能，他们仍可以通过单击其移动设备上的链接来加入会议，但前提是为其分配了适当的语音策略。 你可以：
  
- 向这些用户分配特定的语音策略，或者
    
- 确保全局策略或站点级别的策略存在并且应用于这些用户。
    
不管使用哪种方法，你分配的语音策略必须具有公用电话交换网 (PSTN) 用法记录和定义用户为加入会议而将拨出到的区域的路由。
  
> [!NOTE]
> 希望使用 "单击以加入" 的移动用户以及相关的 PSTN 使用记录和语音路由，因为当他们在其移动设备上单击该链接时，将产生来自 Skype for Business 服务器的出站呼叫。 
  

