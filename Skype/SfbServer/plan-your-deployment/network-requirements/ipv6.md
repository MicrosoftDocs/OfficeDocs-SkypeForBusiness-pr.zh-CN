---
title: 规划 IPv6 Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 01f77196-38f4-4292-9480-2e2fbd57eabe
description: 摘要：在安装 IPv6 之前实现Skype for Business Server。
ms.openlocfilehash: ff58da4a4064c91949446e9107d0f3ff07b720e1
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58593506"
---
# <a name="plan-for-ipv6-in-skype-for-business"></a>规划 IPv6 Skype for Business
 
**摘要：** 在安装 IPv6 之前实现Skype for Business Server。
  
Skype for Business Server支持 IP 版本 6 (IPv6) 地址，并继续支持 IP 版本 4 (IPv4) 地址。 

IPv4 地址是 32 位地址，允许计算机通过 Internet 进行通信。 由于全球设备数量不断增加，可用 IPv4 地址已用完。因此，许多新设备都迁移到使用 IPv6 地址。 IPv6 地址执行与 IPv4 地址相同的功能（另外还有一些附加功能），但 IPv6 地址不仅使用 32 位，而且还使用 128 位。 这不仅提供了一组新的地址，而且数量远远超过原来的地址集。 

传统 IPv4 地址看起来类似于：192.0.2.235，而 IPv6 地址看起来类似于：2001:0db8:85a3:0000:0000:8a2e:0370:7334。 使用 IPv6 地址的设备的格式和功能更改要求在安装时考虑Skype for Business Server注意事项。 

本主题包括以下部分：
  
- [IP 地址类型概述](ipv6.md#over)
    
- [IPv6 的技术要求](ipv6.md#tech)
    
- [IPv6 的迁移和共存注意事项](ipv6.md#migration)
    
如果您确定您将使用 IPv6 地址，请参阅本文中的配置[IP 地址Skype for Business](ip-address-types.md)文章。
  
## <a name="overview-of-ip-address-types"></a>IP 地址类型概述
<a name="over"> </a>

在服务器中配置 IP 地址时，有三Skype for Business Server。 您可以将 Skype for Business Server 配置为仅支持 IP 版本 4 (IPv4) 、仅支持 IP 版本 6 (IPv6) ，或支持两者的组合（称为双协议栈 () ）。 对于每种类型的配置，都需要考虑一些问题：
  
- **仅 IPv4** 创建 IPv6 是因为世界上的 IPv4 地址已用不上。 最终，IPv6 将会在世界范围内得到完全支持，但现在有很多您的企业可能需要与之通信的公司和设备尚不支持 IPv6，并且在一段时间内可能也不会支持。 仅 IPv4 配置有助于确保你的 Skype for Business Server 实现可以与大多数现有设备通信。
    
- **仅 IPv6** 相反，完整的 IPv6 实现将排除与许多现有设备的通信。
    
- **双协议栈** 双协议栈是同时启用 IPv4 和 IPv6 地址的网络。 此配置在 Skype for Business Server因为在大多数情况下，从完全 IPv4 转换到完全 IPv6 需要若干年。
    
以下各节概述了这三种配置之间对各种功能Skype for Business Server兼容性。
  
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

对等通信包括音频、音频/视频、应用程序共享和文件传输。两个客户端均注册成功后，将支持以下组合。
  
|**客户端终结点 1**|**客户端终结点 2**|
|:-----|:-----|
|IPv4  <br/> |IPv4  <br/> |
|IPv4  <br/> |双协议栈  <br/> |
|双协议栈  <br/> |双协议栈  <br/> |
|IPv6  <br/> |双协议栈  <br/> |
|IPv6  <br/> |IPv6  <br/> |
   
### <a name="conferencing"></a>会议
<a name="conf"> </a>

会议包括音频/视频、应用程序共享和数据协作应用程序，如白板和文件共享。
  
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

Skype for Business Server如果流量通过 IPv6 接口 (PSTN) ，则不支持公用电话交换网或 PSTN 呼叫的媒体旁路。 如果需要媒体旁路，则我们建议将 PSTN 网关配置为 IPv4。 
  
|**主接口 1**|**PSTN 接口（位于中介服务器上）**|**PSTN 网关设置**|
|:-----|:-----|:-----|
|IPv4  <br/> |双协议栈  <br/> |IPv4  <br/> |
|双协议栈  <br/> |双协议栈  <br/> |IPv4  <br/> |
|双协议栈  <br/> |双协议栈  <br/> |IPv6  <br/> |
   
1. 主接口是一个接口，用于与Skype for Business Server组件通信。
  
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
   
\* 仅在实验室环境中使用此组合。
  
下表是内部和外部边缘接口支持的组合矩阵。
  
**边缘池（内部边缘）和边缘池（外部边缘）矩阵**

||**边缘池（外部边缘）：IPv4** <br/> |**边缘池（外部边缘）：双协议栈** <br/> |**边缘池（外部边缘）：IPv6** <br/> |
|:-----|:-----|:-----|:-----|
|**边缘池（内部边缘）：IPv4** <br/> |是  <br/> |是  <br/> |否  <br/> |
|**边缘池（内部边缘）：双协议栈** <br/> |否  <br/> |是  <br/> |否  <br/> |
|**边缘池（内部边缘）：IPv6** <br/> |否  <br/> |否  <br/> |是\*  <br/> |
   
\* 仅在实验室环境中使用此组合。
  
### <a name="advanced-enterprise-voice-support-for-ipv6"></a>IPv6 的高级企业语音支持
<a name="Ent_V"> </a>

包括呼叫许可控制 (CAC)、增强型 9-1-1 (E9-1-1) 或媒体旁路的部署必须配置为仅 IPv4 或双协议栈实现。 仅使用 IPv6 的终结点无法使用其中任何功能。
  
> [!NOTE]
> 在双协议栈部署中，即使 Skype for Business Server 客户端使用 IPv6 连接到 Skype for Business Server，Skype for Business Server 也会尽力映射相应的 IPv4 地址以支持 E9-1-1。 
  
不支持具有 IPv6 地址的位置信息服务。
  
Exchange 统一消息 (UM) 不支持 IPv6。对于 Exchange UM，请确保 DNS 解析不会返回 IPv6 地址。使用 IPv6 可能会在将呼叫发送至语音信箱时导致失败。 
  
### <a name="other-skype-for-business-server-feature-support-for-ipv6"></a>IPv6 的其他 Skype for Business Server 功能支持
<a name="Ent_V"> </a>

除了前面提到的功能和组件，Skype for Business Server以下功能支持 IPv6：
  
- **持久聊天**
    
    使用拓扑生成器为持久聊天配置 IPv6。 有关配置持久聊天的详细信息，请参阅部署持久聊天服务器文档。
    
- **用户体验质量 (QoE) 和呼叫详细信息记录 (CDR) 报告**
    
    监视报告将会包括 IP 地址，因为该地址存储在监视服务器数据库中（无论类型为 IPv4 还是 IPv6）。
    
## <a name="technical-requirements-for-ipv6"></a>IPv6 的技术要求
<a name="tech"> </a>

如果计划为 IPv6 Skype for Business Server配置 IPv6，请牢记以下要求：
  
- 若要将 IPv6 地址与Skype for Business Server，您需要为必须发现并解析为 IPv6 地址的记录创建域名系统 (DNS) 记录。 IPv6 DNS 使用主机 AAAA (4A) 记录。 如果在部署中同时使用 IPv4 和 IPv6，最好同时配置和维护 IPv4 的主机 A 记录和 IPv6 的主机 AAAA 记录。 即使将部署完全转换到 IPv6 后，仍可能需要 IPv4 DNS 主机记录以满足仍使用 IPv4 的用户。
    
    您可以在开始使用 IPv6 前部署 IPv6 DNS 主机记录。 如果客户端或服务器不使用 IPv6，该记录不会被引用。 切换技术将根据切换技术配置和策略决定使用哪条记录。
    
- 每个 IPv6 地址都有一个作用域。 可用于 IPv6 寻址的三个范围是 IPv6 全局地址 (类似于公共 IPv4 地址) 、IPv6 唯一本地地址 (类似于专用 IPv4 地址范围) 和 IPv6 链接本地地址 (类似于 Windows Server for IPv4) 中的自动专用 IP 地址。 池内所有服务器都应该具有作用域相同的 IPv6 地址。 
    
> [!IMPORTANT]
> IPv6 是一个复杂的主题，需要网络团队和 Internet 提供商进行仔细规划，以帮助确保在 Windows Server 级别和 Skype for Business Server 级别分配的地址能够正常工作。 请参阅本主题结尾处的链接，以了解有关 IPv6 寻址和规划的其他资源。 
  
## <a name="migration-and-coexistence-considerations-for-ipv6"></a>IPv6 的迁移和共存注意事项
<a name="migration"> </a>

Lync Server 2010 (Communications Server 不支持 IP 版本 6) IPv6 Office IPv6 版本。 出于试点目的，您可以测试 Lync Server 2010 和 Skype for Business Server双协议栈共存。 建议先将给定中央站点的所有池升级到 Skype for Business Server，然后再为任意池 (IPv6) 双协议栈网络。 如果您需要为池配置仅 IPv6，则建议您在实验室环境中设置仅 IPv6 以进行测试。
  
迁移和共存期间支持下列方案：
  
- Skype for Business Server IPv4 模式下运行 Lync Server 2013 和 Lync Server 2010 池，Skype for Business Server双协议栈模式共存。
    
- Skype for Business Server仅 IPv6 池为孤立池，则以仅 IPv6 模式访问池。
    
## <a name="see-also"></a>另请参阅
<a name="migration"> </a>

[配置 IP 地址类型Skype for Business](ip-address-types.md)

[IP 版本 6 寻址体系结构](https://tools.ietf.org/html/rfc4291)
  
[IPv6 全局单播地址格式](https://tools.ietf.org/html/rfc3587)
  
[唯一本地 IPv6 单播地址](https://tools.ietf.org/html/rfc4193)
