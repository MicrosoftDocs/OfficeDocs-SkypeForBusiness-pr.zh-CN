---
title: 规划 Skype for Business Server 2015 移动性
ms.author: heidip
author: microsoftheidi
ms.date: 2/17/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7117eff5-6860-4673-b366-afe0756c4bb2
description: 对 Skype 的业务服务器 2015年的移动实现的计划。
ms.openlocfilehash: f0d822050055ea7255786128fcaecd144f91367a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-mobility-for-skype-for-business-server-2015"></a>规划 Skype for Business Server 2015 移动性
 
对 Skype 的业务服务器 2015年的移动实现的计划。
  
具有的业务服务器 2015年的 Skype，您可以部署为在移动设备上的业务服务器 2015年功能提供 Skype 的移动功能。 本文提供有关移动功能的详细信息，并可帮助您为您的部署计划。
  
Skype 的业务服务器 2015年的移动功能是能够支持 Skype 业务，为移动客户端以及回到 2010 Lync 客户端。 一旦部署，您的用户可以连接到您 Skype 为支持业务服务器 2015年部署使用 iOS 中，Android 和 Windows Phone 利用几个不同的功能，包括企业语音功能的移动设备。 我们提供了下面列出的部分，还可以检查[业务的 Skype 的桌面客户端功能比较](clients-and-devices/desktop-feature-comparison.md)，以获取详细信息：
  
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
    
所有这些功能均通过统一通信 Web API (UCWA) 实现。 UCWA 第一次引入 Lync Server 2013，和目前仍在使用上使用 Skype 业务服务器 2015年。 没有与 Lync 2010 的客户端进行通信的其他功能，这就是移动服务 (MCX)。 这些都是免费服务，允许 Lync Server 2010 2013年的客户端，以及业务客户端，成功访问了业务服务器部署 Skype 的 Skype。
  
> [!NOTE]
> 我们在这里也将 MCX 包括在内，但是需要阐明的是，尽管现在支持，但是我们计划在下一个版本中弃用此功能，你在进行规划时请注意这一点。 我们将继续使用 UCWA，并建议 Lync 2013 和 Skype 的业务客户可用于今后的最终公告 MCX 环境中。 
  
请务必注意，虽然已实现移动后，所有这些功能都可用，他们可能工作有点以不同的方式在某些设备上。 我们讨论了功能上何种设备，在[Skype 业务的移动客户端功能比较](clients-and-devices/mobile-feature-comparison.md)的工作网站。 我们还在[为客户端和设备计划](clients-and-devices/clients-and-devices.md)了一些很好的设备和操作系统信息。
  
移动利用自动发现功能，它允许客户端自动找到 Skype 业务服务器 web 服务而无需输入任何 Url （它们甚至不必知道它们） 中的用户。 如果你需要执行某些故障排除操作，仍支持手动输入 URL。
  
此外支持推式通知，当 Skype 的业务应用程序未运行在后台 （或不支持在后台运行的应用程序的移动设备）。 当设备或应用处于非活动状态时，向移动设备发送关于所发生事件的推送通知。 例如，当手机处于非活动状态而错过 IM 消息时，就会发送推送通知（采用 Toast 或通知的形式，就像应用在后台运行时那样）。 借助推送通知，用户就不会错过 IM 或语音呼叫。
  
有关详细信息，请参阅以下部分：
  
- [移动组件](mobility.md#MobilityComponents)
    
- [支持的拓扑](mobility.md#SupportedTopos)
    
- [技术要求](mobility.md#TechRequirements)
    
- [定义你的移动性需求](mobility.md#MobilityNeeds)
    
## <a name="mobility-components"></a>移动组件
<a name="MobilityComponents"> </a>

有的业务服务器 2015年的 Skype 组成移动的四种服务：
  
- **统一通信 Web API (UCWA)**
    
    提供了实时通信与移动有关的服务和业务服务器 2015年的 Skype 的 web 客户端。 Skype 业务服务器部署时，UCWA 虚拟目录创建内部和外部 web 服务中。 此虚拟目录中的虚拟组件接受支持 UCWA 的客户端发出的呼叫。 客户端应用程序通过表述性状态转移 (REST) 接口进行通信，用于：
    
  - presence － 状态
    
  - 联系人
    
  - 即时消息 (IM)
    
  - VoIP
    
  - 视频会议
    
  - 协作
    
    UCWA 使用基于 P-GET 的通道发送事件，例如来电、传入的 IM 或者发送到客户端应用的消息。
    
- **移动性服务 (MCX)**
    
    获取业务服务器功能，例如即时消息、 在线状态以及在移动设备上的联系人，支持 Skype。 在每个池中已用于支持 Skype 业务服务器的功能，在移动设备上的每个前端服务器上安装了移动服务。 您为业务服务器 2015年安装 Skype 时您前端服务器在内部和外部网站下创建新的虚拟目录 (Mcx)。
    
    > [!NOTE]
    > 如上所述，MCX 将在产品的下一个版本中弃用。 
  
- **自动发现服务**
    
    标识用户的位置，并使移动设备与其他 Skype 业务客户端定位资源 （如 Skype 业务服务器 2015 Web 服务、 Mcx URL 或 UCWA URL 的内部和外部 URL) 的任何网络位置。 自动发现功能使用硬编码的主机名（对于网络内部用户，为 lyncdiscoverinternal；对于网络外部用户，为 lyncdiscover）和用户的 SIP 域。 它支持使用 HTTP 或 HTTPS 的客户端连接。 
    
    和每个控制器具有用于支持 Skype 业务服务器的功能，在移动设备上的每个池中每个前端服务器上安装了自动发现服务。 当您安装该服务时，在前端服务器和控制器内部和外部网站下创建新的虚拟目录 （自动发现）。
    
- **推送通知服务**
    
    位于您的在线业务数据中心的 Skype 基于云的服务。 业务客户端运行在后台，没有 Skype 的电话上时，将发生新的事件，（称为推式通知） 的丢失事件通知发送到移动设备改为。 移动服务发送推式通知服务 (MPNS)，然后将其发送到移动设备的通知。 然后，用户可以在其移动设备上响应此通知，以激活应用。 边缘服务器时需要此功能。
    
## <a name="supported-topologies"></a>支持的拓扑
<a name="SupportedTopos"> </a>

我们有下面的支持的 Skype 为拓扑结构规划的业务服务器应用程序：
  
- 移动性标准版
    
- 移动企业版
    
您应该能够使用 Skype 对业务服务器边缘服务器或 Lync Server 2013 边缘服务器使用此功能。
  
在前端服务器时搭配与中介服务器角色，有两个网络接口，支持移动服务，但需要采取适当的步骤来配置这些接口。 您将需要为特定的接口将通信作为中介服务器，并将作为前端服务器进行通信的网络 IP 接口分配 IP 地址。 你可以在拓扑生成器中通过选择对每个服务，而不是使用默认**使用已配置的所有 IP 地址**选择正确的 IP 地址。
  
## <a name="technical-requirements"></a>技术要求
<a name="TechRequirements"> </a>

针对移动用户可能遇到的各种移动应用程序方案做好规划非常重要。 例如，有些人可能在工作之余通过连接到 3G 网络使用移动应用，然后在工作时切换到公司 Wi-Fi 网络。 离开他们的建筑时，他们可能转用 4g。 现在进行规划有助于为这些网络转换提供支持并保证一致的用户体验。
  
### <a name="dns-configuration"></a>DNS 配置

Mcx 和 UCWA 的移动服务使用 DNS 以相同的方式。 利用自动发现，移动设备使用 DNS 定位资源。 在 DNS 查找期间，尝试连接到与内部 DNS 记录关联的 FQDN (lyncdiscoverinternal.[内部域名])。 如果无法使用内部 DNS 记录实现连接，将尝试进行第二次连接，这次将连接到外部 DNS 记录 (lyncdiscover.[sipdomain])。 为什么会有两个呢？ 位于网络内部的移动设备可以使用内部自动发现 URL。 外部移动设备将使用外部自动发现 URL。 在任一情况下，自动发现服务将返回所有用户的主池，包括移动服务 （Mcx 和 UCWA） 的 Web 服务 Url。
  
预计外部自动发现请求会通过反向代理服务器配置为 Skype 业务服务器 2015年。 但是，内部移动服务 URL 和外部移动服务 URL 是与外部 Web 服务 FQDN。 因此，不管移动设备是内置或外置网络，设备始终连接到外部业务服务器 2015年移动服务 Skype 通过反向代理。
  
> [!NOTE]
> 如我们刚才所述，所有移动服务通信 （内部的和外部的） 将都经过您的反向代理服务器。 但是，当内部通信通过某个接口离开，然后又只能返回到相同的接口时，偶尔会发生问题。 这可能会违反欺骗（之前称为 TCP 数据包欺骗）安全规则。 您需要允许**头发固定**其具有移动功能。
  
> [!NOTE]
> 如果您已经准备好要这样做，也可以选择使用反向代理服务器独立于您的防火墙 （对于欺骗预防的目的，应始终会在防火墙处实施的安全）。 这种方式，hairpin 可能会发生在反向代理服务器的外部接口，而不是防火墙的外部接口。 这允许您检测到欺骗正确的防火墙处而放宽规则在您的反向代理服务器，并获得移动功能。 
  
> [!NOTE]
> 走这条，如果一定要使用的 DNS 主机名或 CNAME 记录定义反向代理 hairpin 行为 （没有防火墙），如果可能的话。 
  
要支持企业网络内部和外部的用户，你需要执行几项配置操作。
  
这些是用于内部和外部 Web FQDN 的规则：
  
- 新的 CNAME 或 A（主机，如果是 IPv6，则为 AAAA）DNS 记录（用于自动发现）。
    
- 新防火墙规则（如果希望通过 Wi-Fi 网络支持推送通知）。
    
- 主题备用名称在内部服务器证书和反向代理，用于自动发现。
    
- 前结束服务器硬件负载平衡配置更改源关系。
    
以下是支持的移动服务和自动发现服务所需的拓扑要求：
  
- 前端池内部 web FQDN 必须不同于前端池外部 web FQDN。
    
- 内部 Web FQDN 必须仅解析为企业网络地址且仅能从企业网络内部进行访问。
    
- 外部 Web FQDN 必须仅解析为 Internet 地址且仅能从 Internet 进行访问。
    
- 为了在企业网络内部的用户，移动服务 URL 必须发送到外部 web FQDN。 这一要求是移动服务，并且仅适用于此 URL。
    
- 对于公司网络外部的用户，该请求必须转到外部 web 前端池或控制器的 FQDN。
    
如果你支持自动发现，则需要为每个 SIP 域创建以下 DNS 记录：
  
- 内部 DNS 记录，用于支持从组织网络内部进行连接的移动用户。
    
- 外部或公共 DNS 记录，用于支持从 Internet 进行连接的移动用户。
    
应无法从内部网络外部对内部自动发现 URL 进行寻址。应无法从网络内部对外部自动发现 URL 进行寻址。但是，如果无法满足外部 URL 的此要求，可能也不会影响移动客户端的功能，因为始终会先尝试内部 URL。
  
### <a name="port-and-firewall-requirements"></a>端口和防火墙要求

我们已经介绍了我们其他文档中的大部分，但专门为移动，您将需要以下端口打开企业 Wi-Fi 网络如果您有任何用户驻留在高存活力分支装置 (SBA):
  
- UcwaSipExternalListeningPort 需要 5088。
    
- UcwaSipPrimaryListeningPort 需要 5089。
    
### <a name="certificate-requirements"></a>证书要求

如果您正在使用自动发现您 Skype 为业务移动客户端，您需要修改您的证书，以支持从移动客户端的安全连接的 SAN （主题备用名称） 列表。 如果已将证书准备就绪，则需要请求并分配包含此处所述 SAN 条目的新证书。 这将需要进行为每个前端服务器和 Director （如果您的环境中） 运行自动发现服务。 我们还建议修改 SAN 上的列表反向代理服务器的证书，您的组织中添加的每个 SIP 域的 SAN 项。
  
如果您正在请求新关闭内部 CA （证书颁发机构） 证书，但公共证书更复杂，并可能要重新申请，更不必说它可能代价高昂，要添加大量更加昂贵，这应该是 SIP 的一个简单的过程新的公用证书域。在这种情况下，没有一种支持，但**不是建议这样做**。 您可以配置您反向代理服务器进行初始的自动发现服务请求通过使用 HTTP，端口 80，而不是端口 443，即 HTTPS （和 443 是默认配置）。 该传入请求将被重定向到您的前端池或控制器上的端口 8080。 通过执行此操作，无需再更改任何证书，因为此通信为请求使用的不是 HTTPS。 再次说明，尽管你可以使用此方法，但我们不建议这样做。
  
### <a name="windows-and-iis-requirements"></a>Windows 和 IIS 要求

在我们的主所述[业务服务器 2015年的 Skype 的服务要求](requirements-for-your-environment/server-requirements.md)的文章中，您应为您的企业服务器环境的 Skype 有 Windows Server 2012 或 Windows Server 2012 R2。 因此，你还需要具有 IIS 8 或 IIS 8.5 才能满足你的移动性需求。 那里需要进行一些更改默认 ASP.NET 设置，但移动服务安装程序将自动执行的。
  
### <a name="hlb-requirements"></a>HLB 要求

如果您正在使用一个拓扑为 Skype 为包括前端池 （它可以包含多个前端服务器的任何拓扑） HLB 的业务服务器 2015年，外部 Web 服务虚拟 IPs (VIPs) 的 Web 服务通信需要为源配置。 源关联有助于确保将单个客户端的多个连接发送给同一台服务器以保持会话状态。
  
如果您打算只对内部 Wi-Fi 网络业务移动客户端支持 Skype，您应该配置源您内部 Web 服务 Vip 中描述的外部 Web 服务 Vip。 在这种情况下，应使用 source_addr （或 TCP） 内部 Web 服务 Vip HLB 上的相似性。
  
在这所有的详细信息，请查看文档，[负载平衡的 Skype 的业务要求](network-requirements/load-balancing.md)。
  
### <a name="reverse-proxy-requirements"></a>反向代理要求

为了支持自动发现的 Skype 业务移动客户端，您将需要更新当前的发布规则，如下所示：
  
- 如果您决定更新 SAN 列出在反向代理服务器的证书，和您的初始的自动发现服务请求使用 HTTPS，您需要更新 lyncdiscover 的 web 发布规则。\<sipdomain\>。 这通常与结合发布 rul 前端池上的外部 Web 服务 url。
    
- 如果您已经决定使用 HTTP 初始的自动发现服务请求，以避免必须更新 SAN 列出有关您的反向代理服务器证书 （这我们不建议使用），您将需要创建新的 HTTP/TCP 80 端口的 web 发布规则如果没有已经。 如果存在该规则，对其进行更新以包括 lyncdiscover。\<sipdomain\>项。
    
## <a name="defining-your-mobility-needs"></a>定义你的移动性需求
<a name="MobilityNeeds"> </a>

现在，我们已经讨论了拓扑结构、 组件和技术要求，一下在您的组织可能需要在移动性实现方面。
  
### <a name="do-you-want-to-use-automatic-discovery-for-skype-for-business-mobile-clients"></a>是否要为 Skype for Business 移动客户端使用自动发现功能？

强烈建议你使用自动发现。 如上面的“技术要求”部分所述，这需要创建新的内部和外部 DNS 记录。 使用自动发现，Skype 业务客户端可以自动找到 Skype 业务服务器 2015 Web 服务从任何位置，而无需手动输入中的 URL。
  
如果需要，你也可以使用手动设置。用户需要将以下 URL 输入到其移动设备中：
  
- **https://\<ExtPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root**进行外部访问。
    
- **https://\<IntPoolFQDN\>/Autodiscover/autodiscoverservice.svc/Root**用于内部访问。
    
再次强调一下，我们建议使用自动发现。你会发现手动设置对于故障排除很有用。
  
### <a name="are-you-going-to-support-push-notifications"></a>你是否打算支持推送通知？

推送通知用于支持此功能的移动应用程序，可以在应用处于非活动状态时将事件通知给用户。 边缘服务器将需要具有业务服务器推送通知服务，该服务在在线业务数据中心的 Skype 找到与您的基于云的 Skype 的联盟关系。 你需要运行 cmdlet 以启用推送通知。
  
> [!NOTE]
> 如果您仍在使用 Lync Server 2010 中的客户端的任何人，他们将需要 TCP 端口 5223 打开企业 WiFi 网络上的出站。 
  
### <a name="do-you-want-all-your-users-accessing-all-mobility-features-or-do-you-want-to-specify-the-users-who-can-access-these-features-instead"></a>是否所有用户访问所有的移动功能，或者您都想要指定的用户可以改为访问这些功能？

我们有一个表来帮助解决的一些功能可供所有用户，并是否他们正在妨碍或不按设置的默认值。 有关完整列表，请查看[新建 CsMobilityPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/new-csmobilitypolicy?view=skype-ps)。
  
> [!NOTE]
> 所有这些功能的适用范围为全局/站点/用户。 
  
|**功能**|**参数名称**|**说明**|**默认设置**|
|:-----|:-----|:-----|:-----|
|支持移动性  <br/> |EnableMobility  <br/> |控制用户在给定的范围内拥有业务移动客户端安装 Skype。 如果该策略设置为 False，用户将无法登录其客户端。  <br/> |True  <br/> |
|外部语音  <br/> |EnableOutsideVoice  <br/> |使用户可以使用“通过工号拨号”功能，该功能允许用户使用其工作号码而不是自己的移动号码来拨打和接听电话。如果设置为 False，用户在使用其工作电话号码时，将无法在其移动电话上拨打或接听电话。  <br/> |True  <br/> |
|支持 IP 音频和视频  <br/> |EnableIPAudioVideo  <br/> |设置为默认值，允许用户在其移动设备上使用 VoIP 拨打或接听电话或视频电话。如果设置为 False，用户将无法使用其移动设备执行这些操作。  <br/> |True  <br/> |
|IP 音频需要 WiFi  <br/> |RequireWiFiForIPAudio  <br/> |定义客户端是否需要通过 WiFi 而不是手机数据网络拨打和接听 VoIP 电话。如果设置为 True，则用户仅在连接到 WiFi 网络时才能拨打和接听 VoIP 电话。  <br/> |False  <br/> |
|IP 视频需要 WiFi  <br/> |RequireWiFiForIPVideo  <br/> |定义客户端是否需要通过 WiFi 而不是手机数据网络拨打和接听视频电话。如果设置为 True，则用户仅在连接到 WiFi 网络时才能拨打和接听 VoIP 电话。  <br/> |False  <br/> |
   
### <a name="should-users-who-arent-enabled-for-enterprise-voice-be-able-to-use-click-to-join-to-join-conferences"></a>未启用企业语音的用户能否使用“单击以加入”来加入会议？

对于移动功能和工作通过调用访问的用户，他们需要能够使用企业语音。 不过，即使没有为他们启用此功能，他们仍可以通过单击其移动设备上的链接来加入会议，但前提是为其分配了适当的语音策略。 你可以：
  
- 向这些用户分配特定的语音策略，或者
    
- 确保全局策略或站点级别的策略存在并且应用于这些用户。
    
不管使用哪种方法，你分配的语音策略必须具有公用电话交换网 (PSTN) 用法记录和定义用户为加入会议而将拨出到的区域的路由。
  
> [!NOTE]
> 那些想要加入使用单击移动用户需要语音策略，以及相关的 PSTN 使用记录和语音路由，因为当他们单击该链接在其移动设备上，会导致来自业务服务器 2015年的 Skype 的出站呼叫。 
  

