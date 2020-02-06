---
title: 规划 Skype for Business 中的 IPv6
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 01f77196-38f4-4292-9480-2e2fbd57eabe
description: 摘要：安装 Skype for Business 服务器之前，请先实施 IPv6。
ms.openlocfilehash: 5fe8cd186d152d368ac89c1d6bc9c07cebb7bfe7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802072"
---
# <a name="plan-for-ipv6-in-skype-for-business"></a>规划 Skype for Business 中的 IPv6
 
**摘要：** 在安装 Skype for Business 服务器之前实施 IPv6。
  
Skype for business 服务器包括对 ip 版本6（IPv6）地址的支持，以及对 IP 版本4（IPv4）地址的连续支持。 

IPv4 地址是 32 位地址，允许计算机通过 Internet 进行通信。 由于世界各地的设备数量不断增加，可用的 IPv4 地址已用尽。因此，许多新设备将移动到使用 IPv6 地址。 IPv6 地址执行与 IPv4 地址相同的功能（并另外增加了一些功能），只不过 IPv6 地址不是使用 32 位，而是使用 128 位。 这不仅提供了一组新的地址，而且数量远远超过原来的地址集。 

传统 IPv4 地址看起来类似于：192.0.2.235，而 IPv6 地址看起来类似于：2001:0db8:85a3:0000:0000:8a2e:0370:7334。 对于使用 IPv6 地址的设备的格式设置和功能的更改，需要在 Skype for Business 服务器安装中执行一些部署和配置注意事项。 

本主题包括以下部分：
  
- [Overview of IP address types](ipv6.md#over)
    
- [Technical requirements for IPv6](ipv6.md#tech)
    
- [Migration and coexistence considerations for IPv6](ipv6.md#migration)
    
如果确定你将使用 IPv6 地址，请参阅[Skype For business 文章中的 "配置 IP 地址类型](ip-address-types.md)"。
  
## <a name="overview-of-ip-address-types"></a>IP 地址类型概述
<a name="over"> </a>

在 Skype for Business 服务器中配置 IP 地址时，有三个选项。 你可以将 Skype for business 服务器配置为仅支持 IP 版本4（IPv4）、仅限 IP 版本6（IPv6）或二者（称为双重堆栈）的组合。 对于每种类型的配置，都需要考虑一些问题：
  
- **仅限 IPv4**由于全球 IPv4 地址不足，因此已创建 IPv6。 最终，IPv6 将在全球范围内获得全面支持，但就目前而言，您的企业需要与之通信的很多公司和设备可能尚不支持 IPv6，并且在一段时间内可能也不会提供相应支持。 仅 IPv4 配置将有助于确保 Skype for Business 服务器实现可以与大多数现有设备进行通信。
    
- **仅限 IPv6**相反，完整的 IPv6 实现将排除与许多现有设备的通信。
    
- **双栈**双堆栈是启用 IPv4 和 IPv6 地址的网络。 Skype for Business Server 支持此配置，因为在大多数情况下，从完整 IPv4 到完整 IPv6 的转换将需要几年。
    
以下部分概述了各种 Skype for Business 服务器功能的这三种配置之间的兼容性。
  
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

如果流量通过 IPv6 接口，则 Skype for business 服务器不支持公共交换电话网络（PSTN）呼叫的媒体旁路。 如果需要媒体旁路，则我们建议将 PSTN 网关配置为 IPv4。 
  
|**主接口1**|**PSTN 接口（位于中介服务器上）**|**PSTN 网关设置**|
|:-----|:-----|:-----|
|IPv4  <br/> |双协议栈  <br/> |IPv4  <br/> |
|双协议栈  <br/> |双协议栈  <br/> |IPv4  <br/> |
|双协议栈  <br/> |双协议栈  <br/> |IPv6  <br/> |
   
1. 主界面是与 Skype for Business 服务器组件进行通信的接口。
  
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

下表显示了前端服务器池和内部边缘服务器池之间的支持列表。
  
**前端池和边缘池（内部边缘）矩阵**

||**边缘池：IPv4** <br/> |**边缘池：双协议栈** <br/> |**边缘池：IPv6** <br/> |
|:-----|:-----|:-----|:-----|
|**前端池：IPv4** <br/> |必需  <br/> |是  <br/> |否  <br/> |
|**前端池：双协议栈** <br/> |必需  <br/> |是  <br/> |否  <br/> |
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
> 在双堆栈部署中，即使 Skype for Business 服务器客户端通过使用 IPv6 连接到 Skype for business 服务器，Skype for business 服务器也能更好地映射合适的 IPv4 地址以支持 E9-1。 
  
不支持具有 IPv6 地址的位置信息服务。
  
Exchange 统一消息 (UM) 不支持 IPv6。对于 Exchange UM，请确保 DNS 解析不会返回 IPv6 地址。使用 IPv6 可能会在将呼叫发送至语音信箱时导致失败。 
  
### <a name="other-skype-for-business-server-feature-support-for-ipv6"></a>适用于 IPv6 的其他 Skype for Business 服务器功能支持
<a name="Ent_V"> </a>

除了之前提到的功能和组件，Skype for business 服务器还支持针对以下功能的 IPv6：
  
- **持久聊天**
    
    可使用拓扑生成器为持久聊天配置 IPv6。 有关配置持久聊天的详细信息，请参阅部署持久聊天服务器文档。
    
- **用户体验质量 (QoE) 和呼叫详细信息记录 (CDR) 报告**
    
    监视报告将会包括 IP 地址，因为该地址存储在监视服务器数据库中（无论类型为 IPv4 还是 IPv6）。
    
## <a name="technical-requirements-for-ipv6"></a>IPv6 的技术要求
<a name="tech"> </a>

如果您计划为 IPv6 配置 Skype for business Server，请记住以下要求：
  
- 若要将 IPv6 地址用于 Skype for Business 服务器，你需要为必须发现和解析为 IPv6 地址的记录创建域名系统（DNS）记录。 IPv6 DNS 使用主机 AAAA (4A) 记录。 如果在部署中同时使用 IPv4 和 IPv6，最好同时配置和维护 IPv4 的主机 A 记录和 IPv6 的主机 AAAA 记录。 即使将部署完全转换到 IPv6 后，仍可能需要 IPv4 DNS 主机记录以满足仍使用 IPv4 的用户。
    
    您可以在开始使用 IPv6 前部署 IPv6 DNS 主机记录。如果客户端或服务器不使用 IPv6，该记录不会被引用。切换技术将根据切换技术配置和策略决定使用哪条记录。
    
- 每个 IPv6 地址都有一个作用域。 可用于 IPv6 寻址的三个作用域是 IPv6 全局地址（类似于公用 IPv4 地址）、IPv6 唯一本地地址（类似于专用 IPv4 地址范围）和 IPv6 链接本地地址（类似于中的自动专用 IP 地址）Windows Server for IPv4）。 池内所有服务器都应该具有作用域相同的 IPv6 地址。 
    
> [!IMPORTANT]
> IPv6 是一个复杂的主题，需要仔细规划网络团队和 Internet 提供商，以帮助确保你在 Windows Server 级别和 Skype for Business 服务器级别分配的地址按预期工作。 请参阅本主题结尾处的链接，以了解有关 IPv6 寻址和规划的其他资源。 
  
## <a name="migration-and-coexistence-considerations-for-ipv6"></a>IPv6 的迁移和共存注意事项
<a name="migration"> </a>

Lync Server 2010 或 Office 通信服务器不支持 IP 版本6（IPv6）。 出于试验目的，你可以测试 Lync Server 2010 和 Skype for business 服务器双栈共存。 我们建议先将给定中心网站的所有池升级到 Skype for business 服务器，然后再为任何池启用 IPv6 （双堆栈网络）。 如果您需要为池配置仅 IPv6，则建议您在实验室环境中设置仅 IPv6 以进行测试。
  
迁移和共存期间支持下列方案：
  
- 在双堆栈模式下与 Skype for business Server 共存的 IPv4 模式下的 skype for business 服务器、Lync Server 2013 和 Lync Server 2010 池。
    
- 仅限 IPv6 模式的 Skype for business 服务器池（如果仅限 IPv6 的池是孤立的池）。
    
## <a name="see-also"></a>另请参阅
<a name="migration"> </a>

[Configure IP address types in Skype for Business](ip-address-types.md)

[IP 版本6寻址体系结构](https://tools.ietf.org/html/rfc4291)
  
[IPv6 全局单播地址格式](https://tools.ietf.org/html/rfc3587)
  
[唯一本地 IPv6 单播地址](https://tools.ietf.org/html/rfc4193)
