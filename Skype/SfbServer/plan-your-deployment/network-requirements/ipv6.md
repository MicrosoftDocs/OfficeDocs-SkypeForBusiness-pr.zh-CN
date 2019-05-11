---
title: 规划 Skype for Business 中的 IPv6
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 01f77196-38f4-4292-9480-2e2fbd57eabe
description: 摘要： 实现 IPv6 业务服务器安装 Skype 之前。
ms.openlocfilehash: fa00f769a277ae8ec1ecacae45560b4659082b21
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33905722"
---
# <a name="plan-for-ipv6-in-skype-for-business"></a>规划 Skype for Business 中的 IPv6
 
**摘要：** 在您安装 Skype 业务服务器之前，请实现 IPv6。
  
Skype 业务服务器包括对 IP 版本 6 (IPv6) 的支持地址，以及持续支持 ip 版本 4 (IPv4) 地址。 

IPv4 地址是 32 位地址，允许计算机通过 Internet 进行通信。 由于全球范围内的设备越来越多，可用的 IPv4 地址出完。因此，很多新设备移动到使用 IPv6 地址。 IPv6 地址执行与 IPv4 地址相同的功能（并另外增加了一些功能），只不过 IPv6 地址不是使用 32 位，而是使用 128 位。 这不仅提供了一组新的地址，而且数量远远超过原来的地址集。 

传统 IPv4 地址看起来类似于：192.0.2.235，而 IPv6 地址看起来类似于：2001:0db8:85a3:0000:0000:8a2e:0370:7334。 格式和使用 IPv6 地址的设备的功能更改业务服务器安装要求在您 Skype 的一些部署和配置注意事项。 

本主题包括以下部分：
  
- [Overview of IP address types](ipv6.md#over)
    
- [Technical requirements for IPv6](ipv6.md#tech)
    
- [Migration and coexistence considerations for IPv6](ipv6.md#migration)
    
如果您确定您将使用 IPv6 地址，请参阅[Skype for Business 中的配置的 IP 地址类型](ip-address-types.md)文章。
  
## <a name="overview-of-ip-address-types"></a>IP 地址类型概述
<a name="over"> </a>

配置 IP 地址中 Skype 业务服务器时，您可以具有三个选项。 您可以配置的业务服务器支持仅 IP 版本 4 (IPv4)，仅 IP 版本 6 (IPv6) 的 Skype 或二者的组合 （称为双协议栈）。 对于每种类型的配置，都需要考虑一些问题：
  
- **仅使用 IPv4**创建 IPv6，因为世界不足 IPv4 地址。 最终，IPv6 将在全球范围内获得全面支持，但就目前而言，您的企业需要与之通信的很多公司和设备可能尚不支持 IPv6，并且在一段时间内可能也不会提供相应支持。 仅 IPv4 配置将有助于确保您的业务服务器实现 Skype 可以和大多数现有设备通信。
    
- **仅 IPv6**完全实现 IPv6 将相反，通信与许多现有设备。
    
- **双协议栈**双协议栈是的网络中启用 IPv4 和 IPv6 地址。 此配置是因为在大多数情况下从完全 IPv4 转换为完全 IPv6 将花费几年业务服务器 Skype 中支持的。
    
以下各节概述了各种 Skype 业务 Server 功能的三种配置之间的兼容性。
  
> [!NOTE]
> 仅 IPv6 的客户端或服务器配置只受选项卡或验证的支持。仅 IPv6 配置在生产部署中不受支持。 
  
### <a name="client-registration"></a>客户端注册
<a name="client"> </a>

|**客户端终结点网络**|**服务器网络**|
|:-----|:-----|
|IPv4  <br/> |IPv4  <br/> |
|IPv4  <br/> |双协议栈  <br/> |
|双协议栈  <br/> |IPv4  <br/> |
|双协议栈  <br/> |双协议栈  <br/> |
|双协议栈  <br/> |IPv6  <br/> |
|IPv6  <br/> |双协议栈  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="peer-to-peer-client"></a>对等客户端
<a name="peer"> </a>

对等通信包括音频、音频/视频、应用程序共享和文件传输。 两个客户端均注册成功后，将支持以下组合。
  
|**客户端终结点 1**|**客户端终结点 2**|
|:-----|:-----|
|IPv4  <br/> |IPv4  <br/> |
|IPv4  <br/> |双协议栈  <br/> |
|双协议栈  <br/> |双协议栈  <br/> |
|IPv6  <br/> |双协议栈  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="conferencing"></a>会议
<a name="conf"> </a>

会议包括音频/视频、应用程序共享和数据协作应用程序（比如白板和文件共享）。
  
|**客户端终结点网络**|**服务器网络**|
|:-----|:-----|
|IPv4  <br/> |IPv4  <br/> |
|IPv4  <br/> |双协议栈  <br/> |
|双协议栈  <br/> |IPv4  <br/> |
|双协议栈  <br/> |双协议栈  <br/> |
|双协议栈  <br/> |IPv6  <br/> |
|IPv6  <br/> |双协议栈  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="mediation-serverpstn"></a>中介服务器/PSTN
<a name="med"> </a>

Skype 业务服务器不支持媒体绕过公用电话交换网 (pstn) 呼叫流量是否通过 IPv6 接口。 如果需要媒体旁路，则我们建议将 PSTN 网关配置为 IPv4。 
  
|**主接口 1**|**PSTN 接口（位于中介服务器上）**|**PSTN 网关设置**|
|:-----|:-----|:-----|
|IPv4  <br/> |双协议栈  <br/> |IPv4  <br/> |
|双协议栈  <br/> |双协议栈  <br/> |IPv4  <br/> |
|双协议栈  <br/> |双协议栈  <br/> |IPv6  <br/> |
   
1. 主接口是与业务服务器组件的 Skype 进行通信的接口。
  
### <a name="remote-user-peer-to-peer-communications"></a>远程用户对等通信
<a name="remote"> </a>

与远程用户的对等通信包括即时消息、音频/视频、应用程序共享和文件传输。
  
|**远程用户网络**|**边缘服务器（外部边缘）**|
|:-----|:-----|
|IPv4  <br/> |IPv4  <br/> |
|双协议栈  <br/> |IPv4  <br/> |
|双协议栈  <br/> |双协议栈  <br/> |
|IPv6  <br/> |双协议栈  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="front-end-pool-and-edge-pool-configuration"></a>前端池和边缘池配置
<a name="FE_pool"> </a>

下表显示了前端服务器池和内部边缘服务器池之间的支持矩阵。
  
**前端池和边缘池（内部边缘）矩阵**

||**边缘池：IPv4** <br/> |**边缘池：双协议栈** <br/> |**边缘池：IPv6** <br/> |
|:-----|:-----|:-----|:-----|
|**前端池：IPv4** <br/> |是  <br/> |是  <br/> |否  <br/> |
|**前端池：双协议栈** <br/> |是  <br/> |是  <br/> |否  <br/> |
|**前端池：IPv6** <br/> |否  <br/> |否  <br/> |是\*  <br/> |
   
\*仅在实验室环境中使用此组合。
  
下表是内部和外部边缘接口支持的组合矩阵。
  
**边缘池（内部边缘）和边缘池（外部边缘）矩阵**

||**边缘池（外部边缘）：IPv4** <br/> |**边缘池（外部边缘）：双协议栈** <br/> |**边缘池（外部边缘）：IPv6** <br/> |
|:-----|:-----|:-----|:-----|
|**边缘池（内部边缘）：IPv4** <br/> |是  <br/> |是  <br/> |否  <br/> |
|**边缘池（内部边缘）：双协议栈** <br/> |否  <br/> |是  <br/> |否  <br/> |
|**边缘池（内部边缘）：IPv6** <br/> |否  <br/> |否  <br/> |是\*  <br/> |
   
\*仅在实验室环境中使用此组合。
  
### <a name="advanced-enterprise-voice-support-for-ipv6"></a>IPv6 的高级企业语音支持
<a name="Ent_V"> </a>

包括呼叫许可控制 (CAC)、增强型 9-1-1 (E9-1-1) 或媒体旁路的部署必须配置为仅 IPv4 或双协议栈实施。仅使用 IPv6 的终结点无法使用其中任何一项功能。
  
> [!NOTE]
> 在双协议栈部署中，即使 Skype Business Server 客户端连接到 Skype 业务服务器使用 IPv6，Skype 业务服务器将尽力映射相应的 IPv4 地址以支持 E9-1-1。 
  
不支持使用 IPv6 地址的位置信息服务。
  
Exchange 统一消息 (UM) 不支持 IPv6。对于 Exchange UM，请确保 DNS 解析不会返回 IPv6 地址。使用 IPv6 可能会在将呼叫发送至语音信箱时导致失败。 
  
### <a name="other-skype-for-business-server-feature-support-for-ipv6"></a>业务服务器功能支持 IPv6 的其他 Skype
<a name="Ent_V"> </a>

除了中的功能和组件前面提到的业务服务器的 Skype 对以下功能支持 IPv6:
  
- **持久聊天**
    
    使用拓扑生成器的持久聊天配置 IPv6。 有关配置持久聊天的详细信息，请参阅 Deploying Persistent Chat Server 文档。
    
- **用户体验质量 (QoE) 和呼叫详细信息记录 (CDR) 报告**
    
    监视报告将会包括 IP 地址，因为该地址存储在监视服务器数据库中（无论类型为 IPv4 还是 IPv6）。
    
## <a name="technical-requirements-for-ipv6"></a>IPv6 的技术要求
<a name="tech"> </a>

如果您计划配置 IPv6 的 Skype 业务服务器，请谨记以下要求：
  
- 若要对业务服务器与 Skype 使用 IPv6 地址，您需要创建域名系统 (DNS) 记录的记录，必须发现并解析为 IPv6 地址。 IPv6 DNS 使用主机 AAAA (4A) 记录。 如果在部署中同时使用 IPv4 和 IPv6，最好同时配置和维护 IPv4 的主机 A 记录和 IPv6 的主机 AAAA 记录。 即使将部署完全转换到 IPv6 后，仍可能需要 IPv4 DNS 主机记录以满足仍使用 IPv4 的用户。
    
    您可以在开始使用 IPv6 前部署 IPv6 DNS 主机记录。如果客户端或服务器不使用 IPv6，该记录不会被引用。切换技术将根据切换技术配置和策略决定使用哪条记录。
    
- 每个 IPv6 地址都有一个作用域。 您可以使用 IPv6 寻址的三个范围是 IPv6 全局地址 （类似于公共 IPv4 地址）、 IPv6 唯一本地地址 （类似于专用的 IPv4 地址范围） 和 IPv6 链接-本地地址 （类似于自动中的专用 IP 地址Windows Server ipv4)。 池内所有服务器都应该具有作用域相同的 IPv6 地址。 
    
> [!IMPORTANT]
> IPv6 是一个复杂的主题，需要仔细规划您的网络团队和 Internet 提供商，以帮助确保您分配了在 Windows Server 级别和业务服务器级别 Skype 的地址按预期方式工作。 请参阅本主题结尾处的链接，以了解有关 IPv6 寻址和规划的其他资源。 
  
## <a name="migration-and-coexistence-considerations-for-ipv6"></a>IPv6 的迁移和共存注意事项
<a name="migration"> </a>

Lync Server 2010 或 Office Communications Server 不支持 IP 版本 6 (IPv6)。 为了试用，您可以测试 Lync Server 2010 和 Skype Business Server 双协议栈共存。 建议的给定中央站点的所有池都升级到 Skype 业务服务器启用 IPv6 之前 （双协议栈网络） 的任何池。 如果您需要为池配置仅 IPv6，则建议您在实验室环境中设置仅 IPv6 以进行测试。
  
迁移和共存期间支持下列方案：
  
- Skype 的业务 Server、 Lync Server 2013 和 Lync Server 2010 池处于 IPv4 模式，与 Skype 共存的企业服务器，在双协议栈模式下。
    
- 在仅 IPv6 模式下，如果存储仅 IPv6 池业务服务器池的 Skype。
    
## <a name="see-also"></a>另请参阅
<a name="migration"> </a>

[Configure IP address types in Skype for Business](ip-address-types.md)

[IP 版本 6 寻址体系结构](https://tools.ietf.org/html/rfc4291)
  
[IPv6 全局单播地址格式](https://tools.ietf.org/html/rfc3587)
  
[唯一本地 IPv6 单播地址](https://tools.ietf.org/html/rfc4193)
