---
title: Plan for Mobility for Skype 业务服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 2/17/2018
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7117eff5-6860-4673-b366-afe0756c4bb2
description: Plan for Business 服务器的 Skype 移动的实现。
ms.openlocfilehash: e981f7d9ac22739dc38bc48e574d96670536594b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33907197"
---
# <a name="plan-for-mobility-for-skype-for-business-server"></a>Plan for Mobility for Skype 业务服务器
 
Plan for Business 服务器的 Skype 移动的实现。
  
与 Skype 的业务服务器，您可以部署移动功能，以提供用于在移动设备上的业务服务器功能的 Skype。 本文提供有关移动功能，详细信息，并帮助您规划您的部署。
  
能够支持的业务的 Skype 的移动客户端以及 Lync 客户端返回转到 2010年的业务服务器 Skype 的移动功能。 为业务服务器部署使用支持的 iOS，它为部署之后，用户可以连接您 Skype Android 和 Windows Phone 移动设备利用几个不同的功能，包括企业语音功能。 我们提供了下面的部分列表，您还可以检查[的 Skype for Business 的桌面客户端功能比较](clients-and-devices/desktop-feature-comparison.md)的详细信息：
  
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
    
所有这些功能均通过统一通信 Web API (UCWA) 实现。 UCWA 中首次引入 Lync Server 2013 和仍在使用 Skype 业务服务器。 Lync 2010 客户端与进行通信的其他功能，并位于 Mobility Service (MCX)。 这些是互补服务允许 Lync Server 2010 和 2013年客户端，以及为业务客户端，成功访问业务服务器部署 Skype Skype。
  
> [!NOTE]
> MCX (Mobility Service) 支持旧的移动客户端的不再可用的业务服务器 2019 Skype 中。 业务移动客户端的所有当前 Skype 已使用统一通信 Web API (UCWA) 来支持即时消息 (IM)、 状态和联系人。 与使用 MCX 的旧客户端的用户需要升级到当前客户端。
  
请务必注意时已实现移动功能后，所有这些功能均可用，它们可能按有点不同某些设备上。 我们讨论功能从事哪些设备，在[移动客户端功能比较的 Skype for Business](clients-and-devices/mobile-feature-comparison.md)的网站。 我们还在[规划客户端和设备](clients-and-devices/clients-and-devices.md)了一些出色的设备和操作系统信息。
  
移动利用自动发现功能，允许客户端自动找到 Skype 业务服务器 web 服务而无需输入任何 （它们不会甚至需要了解这些） 的 Url 中的用户。 如果你需要执行某些故障排除操作，仍支持手动输入 URL。
  
此外支持推送通知，当业务应用程序 Skype 不在后台运行 （或不支持在后台运行的应用程序的移动设备）。 当设备或应用处于非活动状态时，向移动设备发送关于所发生事件的推送通知。 例如，当手机处于非活动状态而错过 IM 消息时，就会发送推送通知（采用 Toast 或通知的形式，就像应用在后台运行时那样）。 借助推送通知，用户就不会错过 IM 或语音呼叫。
  
有关详细信息，请参阅以下部分：
  
- [移动组件](mobility.md#MobilityComponents)
    
- [支持的拓扑](mobility.md#SupportedTopos)
    
- [技术要求](mobility.md#TechRequirements)
    
- [定义你的移动性需求](mobility.md#MobilityNeeds)
    
## <a name="mobility-components"></a>移动组件
<a name="MobilityComponents"> </a>

有四种服务组成移动的 Skype 业务服务器：
  
- **统一通信 Web API (UCWA)**
    
    提供了 mobile 进行实时通信的服务和 web 客户端的 Skype 业务服务器。 Skype 业务服务器部署时，内部和外部 web 服务中创建一个 UCWA 虚拟目录的。 此虚拟目录中的虚拟组件接受支持 UCWA 的客户端发出的呼叫。 客户端应用程序通过表述性状态转移 (REST) 接口进行通信，用于：
    
  - presence － 状态
    
  - 联系人
    
  - 即时消息 (IM)
    
  - VoIP
    
  - 视频会议
    
  - 协作
    
    UCWA 使用基于 P-GET 的通道发送事件，例如来电、传入的 IM 或者发送到客户端应用的消息。
    
- **移动性服务 (MCX)**
    
    支持的业务服务器功能，例如，IM、 状态和联系人，移动设备上的 Skype。 已用来支持的移动设备上的业务服务器功能的 Skype 每个池中每台前端服务器上安装 Mobility service。 为业务服务器 2015年安装 Skype 时在前端服务器上内部和外部网站下创建一个新的虚拟目录 (Mcx)。
    
    > [!NOTE]
    > MCX (Mobility Service) 支持旧的移动客户端的不再可用的业务服务器 2019 Skype 中。 业务移动客户端的所有当前 Skype 已使用统一通信 Web API (UCWA) 来支持即时消息 (IM)、 状态和联系人。 与使用 MCX 的旧客户端的用户需要升级到当前客户端。
  
- **自动发现服务**
    
    标识用户的位置并在无论网络位置启用移动设备和其他 Skype 的业务客户端定位资源 （如业务服务器 Web 服务、 Mcx URL 或 UCWA URL 的 Skype 的内部和外部 URL)。 自动发现功能使用硬编码的主机名（对于网络内部用户，为 lyncdiscoverinternal；对于网络外部用户，为 lyncdiscover）和用户的 SIP 域。 它支持使用 HTTP 或 HTTPS 的客户端连接。 
    
    每个前端服务器上和在已用于在移动设备上的业务服务器功能支持 Skype 每个池中的每个控制器上安装的自动发现服务。 当您安装服务时，在前端服务器和控制器上内部和外部网站下创建一个新的虚拟目录 (Autodiscover)。
    
- **推送通知服务**
    
    位于您的业务 Online 数据中心的 Skype 的基于云的服务。 没有 Skype 业务客户端在后台运行的电话上的新事件发生时，向移动设备改为获取发送 （称为推送通知） 的已错过事件通知。 Mobility service 到然后将其发送到移动设备的推送通知服务 (MPNS) 发送通知。 然后，用户可以在其移动设备上响应此通知，以激活应用。 此功能需要边缘服务器。
    
## <a name="supported-topologies"></a>支持的拓扑
<a name="SupportedTopos"> </a>

我们有业务服务器应用程序的拓扑规划以下支持的 Skype:
  
- 移动 Standard Edition
    
- 移动企业版
    
您应该能够与 Skype 业务 Server 边缘服务器或 Lync Server 2013 边缘服务器使用此功能。
  
前端服务器并置中介服务器角色，有两个网络接口上, 支持 Mobility service，但您需要采取相应的步骤配置这些接口。 您需要分配给为中介服务器中，将会进行通信的特定接口和将作为前端服务器进行通信的网络 IP 接口的 IP 地址。 您可以这样做拓扑生成器中通过选择每个服务，而不是使用默认**使用所有已配置的 IP 地址**选择正确的 IP 地址。
  
## <a name="technical-requirements"></a>技术要求
<a name="TechRequirements"> </a>

针对移动用户可能遇到的各种移动应用程序方案做好规划非常重要。 例如，有些人可能在工作之余通过连接到 3G 网络使用移动应用，然后在工作时切换到公司 Wi-Fi 网络。 离开其构建时，他们可以切换到 4 G。 现在进行规划有助于为这些网络转换提供支持并保证一致的用户体验。
  
### <a name="dns-configuration"></a>DNS 配置

Mobility service Mcx 和 UCWA 相同的方式使用 DNS。 利用自动发现，移动设备使用 DNS 定位资源。 在 DNS 查找期间，尝试连接到与内部 DNS 记录关联的 FQDN (lyncdiscoverinternal.[内部域名])。 如果无法使用内部 DNS 记录实现连接，将尝试进行第二次连接，这次将连接到外部 DNS 记录 (lyncdiscover.[sipdomain])。 为什么会有两个呢？ 位于网络内部的移动设备可以使用内部自动发现 URL。 外部移动设备将使用外部自动发现 URL。 在任一情况下，自动发现服务将返回用户的主池，其中包括 Mobility service （Mcx 和 UCWA） 的所有 Web 服务 Url。
  
预计的外部自动发现请求将通过反向代理配置的 Skype 业务服务器。 但是，内部 Mobility service URL 和外部 Mobility service URL 是与外部 Web 服务 FQDN 关联。 因此，无论是否移动设备，内部或外部到您的网络设备始终连接到外部业务服务器 Mobility service 的 Skype 通过反向代理。
  
> [!NOTE]
> 正如我们只需说，所有 Mobility service 流量 （内部和外部） 将都通过反向代理。 但是，当内部通信通过某个接口离开，然后又只能返回到相同的接口时，偶尔会发生问题。 这可能会违反欺骗（之前称为 TCP 数据包欺骗）安全规则。 您需要允许**字形驻留**具有移动函数。
  
> [!NOTE]
> 如果您已准备好执行此操作，您还可以选择使用反向代理的独立于您的防火墙 （对于安全目的，欺骗防护应始终会在防火墙上实施）。 这种方式，发夹可以发生在您的反向代理的外部接口，而不是防火墙的外部接口。 这样，您可以检测欺骗正确在防火墙时在反向代理，放宽规则，并获取您的移动功能。 
  
> [!NOTE]
> 如果您转此路由，请务必使用 DNS 主机或 CNAME 记录定义反向代理为发夹行为 （不防火墙），如果可能。 
  
要支持企业网络内部和外部的用户，你需要执行几项配置操作。
  
这些是用于内部和外部 Web FQDN 的规则：
  
- 新的 CNAME 或 A（主机，如果是 IPv6，则为 AAAA）DNS 记录（用于自动发现）。
    
- 新防火墙规则（如果希望通过 Wi-Fi 网络支持推送通知）。
    
- 主题备用名称内部服务器证书和反向代理证书上的自动发现。
    
- 前端服务器硬件负载平衡配置更改源关联。
    
以下是支持 Mobility Service 和自动发现服务所需的拓扑要求：
  
- 前端池的内部 web FQDN 必须是前端池的外部 web FQDN 不同。
    
- 内部 Web FQDN 必须仅解析为企业网络地址且仅能从企业网络内部进行访问。
    
- 外部 Web FQDN 必须仅解析为 Internet 地址且仅能从 Internet 进行访问。
    
- 在企业网络内部用户，Mobility service URL 必须发往外部 web FQDN。 这一要求为 Mobility service，并且仅适用于此 URL。
    
- 企业网络外部的用户，此请求必须转到的外部 web 前端池或控制器的 FQDN。
    
如果你支持自动发现，则需要为每个 SIP 域创建以下 DNS 记录：
  
- 内部 DNS 记录，用于支持从组织网络内部进行连接的移动用户。
    
- 外部或公共 DNS 记录，用于支持从 Internet 进行连接的移动用户。
    
应无法从内部网络外部对内部自动发现 URL 进行寻址。应无法从网络内部对外部自动发现 URL 进行寻址。但是，如果无法满足外部 URL 的此要求，可能也不会影响移动客户端的功能，因为始终会先尝试内部 URL。
  
### <a name="port-and-firewall-requirements"></a>端口和防火墙要求

我们在我们其他文档中，介绍大部分这但专门以实现移动功能，您将需要以下端口上企业 Wi-fi 网络如果您有打开任何用户驻留在 Survivable Branch Appliance (SBA):
  
- UcwaSipExternalListeningPort 需要 5088。
    
- UcwaSipPrimaryListeningPort 需要 5089。
    
### <a name="certificate-requirements"></a>证书要求

如果您为您 Skype 业务移动客户端使用自动发现，您需要修改证书以支持从移动客户端的安全连接的 SAN （使用者替代名称） 列表。 如果已将证书准备就绪，则需要请求并分配包含此处所述 SAN 条目的新证书。 这将需要为每个前端服务器和控制器 （如果环境中完成您） 运行自动发现服务。 我们还建议修改 SAN 上的列表反向代理证书，您的组织中添加的每个 SIP 域的 SAN 条目。
  
这应该是一个简单的过程，如果您正在请求新证书关闭内部 CA （证书颁发机构），但公共证书是更复杂，和重新请求，不必说可能、 添加大量 SIP 可能更高域到新的公共证书。在这种情况下，没有一种受支持，但**不是建议使用**。 您可以配置反向代理进行的初始自动发现服务请求，通过端口 80，它将使用 HTTP，而不是端口 443，这是 HTTPS （和 443 是默认配置）。 该传入请求将被重定向到您的前端池或控制器上的端口 8080。 通过执行此操作，无需再更改任何证书，因为此通信为请求使用的不是 HTTPS。 再次说明，尽管你可以使用此方法，但我们不建议这样做。
  
### <a name="windows-and-iis-requirements"></a>Windows 和 IIS 要求

您应该是受支持的 Windows Server 版本的业务服务器环境您 Skype。 因此，你还需要具有 IIS 8 或 IIS 8.5 才能满足你的移动性需求。 那里需要来进行某些更改默认 ASP.NET 设置，但 Mobility service 安装程序将自动执行的。
  
### <a name="hlb-requirements"></a>HLB 要求

如果您正在使用的拓扑的 Skype 业务服务器包含前端池 （其中将为任何拓扑包含多台前端服务器） HLB，需要配置外部 Web 服务虚拟 Ip (Vip) 的 Web Services 通信源。 源关联有助于确保将单个客户端的多个连接发送给同一台服务器以保持会话状态。
  
如果您计划仅对内部 Wi-fi 网络支持的业务移动客户端的 Skype，您应为外部 Web 服务 Vip 所述配置源您内部 Web 服务 Vip。 在这种情况下，您应使用 source_addr （或 TCP） 的内部 Web 服务 Vip 上 HLB 的相关性。
  
有关所有详细信息，请参阅 [Load balancing requirements for Skype for Business](network-requirements/load-balancing.md)文档。
  
### <a name="reverse-proxy-requirements"></a>反向代理要求

为了对业务移动客户端 Skype 支持自动发现，您需要更新当前发布规则，如下所示：
  
- 如果您决定要更新您的反向代理证书上的 SAN 列表和您将 HTTPS 用于初始自动发现服务请求，您需要更新 lyncdiscover 的 web 发布规则。\<sipdomain\>。 这通常与结合发布 rul 的前端池上的外部 Web 服务 URL。
    
- 如果您决定要使用 HTTP 用于初始自动发现服务请求可避免更新 SAN 列表的反向代理证书 （其不建议） 中，您将需要创建新的 web 发布规则为端口 HTTP/TCP 80，如果没有已。 如果存在该规则，对其进行更新以包括 lyncdiscover。\<sipdomain\>条目。
    
## <a name="defining-your-mobility-needs"></a>定义你的移动性需求
<a name="MobilityNeeds"> </a>

现在，我们已审阅的拓扑、 组件和技术要求，让我们看您的组织可能需要方面的移动性实现。
  
### <a name="do-you-want-to-use-automatic-discovery-for-skype-for-business-mobile-clients"></a>是否要为 Skype for Business 移动客户端使用自动发现功能？

强烈建议你使用自动发现。 如上面的“技术要求”部分所述，这需要创建新的内部和外部 DNS 记录。 使用自动发现，业务客户端的 Skype 可以自动找到 Skype 业务服务器 Web 服务从任何位置，而无需手动输入 URL。
  
如果需要，你也可以使用手动设置。 用户需要将以下 URL 输入到其移动设备中：
  
- **https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root**外部访问。
    
- **https://\<IntPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root**供内部访问。
    
再次强调一下，我们建议使用自动发现。你会发现手动设置对于故障排除很有用。
  
### <a name="are-you-going-to-support-push-notifications"></a>你是否打算支持推送通知？

推送通知用于支持此功能的移动应用程序，可以在应用处于非活动状态时将事件通知给用户。 边缘服务器将需要对业务服务器推送通知服务，它位于业务 Online 数据中心的 Skype 拥有与您的基于云的 Skype 联合身份验证关系。 你需要运行 cmdlet 以启用推送通知。
  
> [!NOTE]
> 如果您有任何人仍在使用 Lync Server 2010 客户端，他们将需要 TCP 端口 5223 打开出站企业 WiFi 网络上。 
  
### <a name="do-you-want-all-your-users-accessing-all-mobility-features-or-do-you-want-to-specify-the-users-who-can-access-these-features-instead"></a>要指定可以改为访问这些功能的用户或您希望访问所有移动功能，所有用户？

我们有一个表来帮助的一些功能可供所有用户，并是否他们正在方式或不通过设置的默认值。 有关完整列表，请参阅 [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/new-csmobilitypolicy?view=skype-ps)。
  
> [!NOTE]
> 所有这些功能的适用范围为全局/站点/用户。 
  
|**功能**|**参数名称**|**说明**|**默认设置**|
|:-----|:-----|:-----|:-----|
|支持移动性  <br/> |EnableMobility  <br/> |控制给定范围内拥有 Skype 业务移动客户端安装的用户。 如果该策略设置为 False，用户将无法登录其客户端。  <br/> |True  <br/> |
|外部语音  <br/> |EnableOutsideVoice  <br/> |使用户可以使用“通过工号拨号”功能，该功能允许用户使用其工作号码而不是自己的移动号码来拨打和接听电话。如果设置为 False，用户在使用其工作电话号码时，将无法在其移动电话上拨打或接听电话。  <br/> |True  <br/> |
|支持 IP 音频和视频  <br/> |EnableIPAudioVideo  <br/> |设置为默认值，允许用户在其移动设备上使用 VoIP 拨打或接听电话或视频电话。如果设置为 False，用户将无法使用其移动设备执行这些操作。  <br/> |True  <br/> |
|IP 音频需要 WiFi  <br/> |RequireWiFiForIPAudio  <br/> |定义客户端是否需要通过 WiFi 而不是手机数据网络拨打和接听 VoIP 电话。如果设置为 True，则用户仅在连接到 WiFi 网络时才能拨打和接听 VoIP 电话。  <br/> |False  <br/> |
|IP 视频需要 WiFi  <br/> |RequireWiFiForIPVideo  <br/> |定义客户端是否需要通过 WiFi 而不是手机数据网络拨打和接听视频电话。如果设置为 True，则用户仅在连接到 WiFi 网络时才能拨打和接听 VoIP 电话。  <br/> |False  <br/> |
   
### <a name="should-users-who-arent-enabled-for-enterprise-voice-be-able-to-use-click-to-join-to-join-conferences"></a>未启用企业语音的用户能否使用“单击以加入”来加入会议？

对于用户有权访问移动功能和单位电话呼叫，它们需要为启用企业语音。 不过，即使没有为他们启用此功能，他们仍可以通过单击其移动设备上的链接来加入会议，但前提是为其分配了适当的语音策略。 你可以：
  
- 向这些用户分配特定的语音策略，或者
    
- 确保全局策略或站点级别的策略存在并且应用于这些用户。
    
不管使用哪种方法，你分配的语音策略必须具有公用电话交换网 (PSTN) 用法记录和定义用户为加入会议而将拨出到的区域的路由。
  
> [!NOTE]
> 移动用户要加入到使用单击需要语音策略，以及相关的 PSTN 用法记录和语音路由，因为当他们单击其移动设备上的链接时，会导致从 Skype 业务服务器出站呼叫。 
  

