---
title: Skype for Business 服务器中的前端池灾难恢复
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 142caf34-0f20-47f3-9d32-ce25ab622fad
description: 对于灾难恢复, Skype for business 服务器在一个池停机时提供池配对和故障转移。
ms.openlocfilehash: 15df85790cd7959b88126c5e6bb0e7fd99b836e1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297503"
---
# <a name="front-end-pool-disaster-recovery-in-skype-for-business-server"></a>Skype for Business 服务器中的前端池灾难恢复
 
对于灾难恢复, Skype for business 服务器在一个池停机时提供池配对和故障转移。
  
对于 Skype for Business Server 中最强健的灾难恢复选项, 请跨两个地理位置分散的网站部署前端池对。 每个站点包含一个前端池，该池与另一个站点中的相应前端池配对。 这两个站点都处于活动状态，并且备份服务提供了实时数据复制以保持池同步。 如果要实现前端池配对, 请参阅[在 Skype for Business 服务器中部署用于灾难恢复的配对的前端池](../../deploy/deploy-high-availability-and-disaster-recovery/front-end-pools-for-disaster-recovery.md)。
  
![显示两个不同网站中相互配对的前端池](../../media/f74533c0-a10e-4f18-85a8-b9a008497573.jpg)
  
如果某个站点中的池出现故障，则您可以将用户从该前端池故障转移到另一个站点中的池，然后可向两个池中的所有用户提供服务。 出于容量规划目的，每个池应设计为在发生灾难时处理两个池中所有用户的工作负荷。
  
包括互相配对的前端池的两个数据中心之间没有距离限制。建议使用位于相同世界区域的两个数据中心，并在两者之间建立高速链接。 
  
将两个数据中心设立在不同世界区域也是可行的，但一旦发生灾难，可能会因为数据复制延迟而导致丢失较多数据。
  
当您计划对池进行配对时，必须谨记仅支持以下配对法：
  
- Enterprise Edition 池仅能与其他 Enterprise Edition 池进行配对。 同样，Standard Edition 池仅能与其他 Standard Edition 池进行配对。
    
- 物理池仅能与其他物理池配对。 同样，虚拟池仅能与其他虚拟池配对。
    
- 配对的池必须运行相同的基本操作系统。
    
拓扑生成器和拓扑验证都不会阻止以不遵循这些建议的方式对两个池进行配对。例如，拓扑生成器允许您将 Enterprise Edition 池与 Standard Edition 池进行配对。但是，不支持进行这些类型的配对。
  
## <a name="backup-registrar-relationships-and-survivable-branch-appliances"></a>备份注册机构关系和 Survivable 分支装置

除了提供灾难恢复功能外，两个配对的池彼此用作对方的备份注册器。 每个池只能是一个其他前端池的备份。
  
即使两个前端池之间的备份关系必须为 1:1 和对称，每个前端池仍可作为任意数量的 Survivable Branch Appliance 的备份注册器。
  
请注意，Skype for Business 不将灾难恢复支持扩展到驻留在 Survivable Branch Appliance 上的用户。 如果用作 Survivable Branch Appliance 备份的前端池关闭，那么即使在驻留在前端池上的用户故障转移到备份前端池之后，登录 Survivable Branch Appliance 的用户也会进入恢复能力模式。
  
## <a name="recovery-time-for-pool-failover-and-pool-failback"></a>池故障转移和池故障回复的恢复时间

对于池故障转移和池故障回复，恢复时间目标 (RTO) 的工程目标为 15-20 分钟。 这是管理员确定存在灾难并启动故障转移过程之后，故障转移发生所需的时间。 此时间不包括管理员评估情况并作出决策所需的时间，也不包括用户在故障转移完成后再次登录所需的时间。
  
对于池故障转移和池故障回复，恢复点目标 (RPO) 的工程目标为 5 分钟。 这表示测量可能因灾难、因备份服务的复制延迟丢失的数据的时间。 例如, 如果池在 10:00 A.M. 停止, RPO 为5分钟, 则在 9:55 A.M. 之间写入到池中的数据 和 10:00 (可能尚未复制到备份池), 将丢失。
  
本文档中的所有 RTO 和 RPO 数字均假定两个数据中心位于同一在两个网站间具有高速度、低延迟传输的世界区域中。 这些数字是针对具有 40,000 个同时活动的用户和 200,000 个已启用有关预定义的用户模型（在该模型中，数据复制没有备份日志）的 Lync 的用户的池测量而来的。 这些数字可能根据测试和验证性能发生改变。
  
## <a name="central-management-store-failover"></a>中央管理存储故障转移

中央管理存储包含有关部署中的服务器和服务的配置数据。 每个 Skype for business 服务器部署都包含一个中央管理存储, 该存储由一个前端池的后端服务器托管。
  
如果对承载中央管理存储的池进行配对，备份池中将会设置一个备份中央管理存储数据库。 在任意时刻，两个中央管理存储数据库中总有一个处于活动状态，另一个处于备用状态。 备份服务会将内容从主动数据库复制到备用数据库。
  
![显示两个前端池，一个包含主动 CMS 存储，另一个包含被动备份 CMS 存储](../../media/aa479398-eb56-4854-8d50-1eff39c58a56.jpg)
  
在包含承载中央管理存储的池故障转移期间，您必须先对中央管理存储进行故障转移，然后再对前端池进行故障转移。
  
修复灾难后，无需对中央管理存储进行故障回复。 中央管理存储可以保留在作为故障转移目标的池中。
  
中央管理存储故障转移的恢复时间目标 (RTO) 和恢复点目标 (RPO) 的工程目标均为 5 分钟。
  
## <a name="front-end-pool-pairing-data-security"></a>前端池配对数据安全

备份服务会在两个成对的前端池之间连续传输用户数据和会议内容。 用户数据包含用户 SIP URI 以及会议安排、联系人列表和设置。 会议内容包括 Microsoft PowerPoint 上载文件以及会议中使用的白板。
  
在资源池中，此数据将会从本地存储导出、提取并传输到目标池，在这里进行解压并导入到本地存储。 备份服务假定两个数据中心之间的通讯链路位于公司网络内部，并且具有 Internet 保护。 它不会加密在两个数据中心之间传输的数据，也不会在安全协议（如 HTTPS）内进行本地数据封装。 因此, 来自公司网络内部人员的中间人攻击是可能的。
  
任何在多个数据中心部署 Skype for Business 服务器并使用灾难恢复功能的企业必须确保数据中心之间的流量受其公司 Intranet 的保护。 关注内部攻击保护的企业必须保护数据中心之间的通讯链路。 这是一种标准要求，同样有助于保护数据中心之间传输的其他类型的企业敏感数据。
  
当公司网络内存在中间人攻击的风险时，比较而言，它相当于包含将流量公开到 Internet。 尤其是，通过备份服务（如，SIP URI）公开的用户数据通过其他方法（例如，全局通讯簿或其他目录软件）通常可用于公司内的所有员工。 因此，当将备份服务用于复制两个成对池之间的数据时，重点应该是保护两个数据中心之间的 WAN。
  
### <a name="mitigating-security-risks"></a>减轻安全风险

你可以通过多种方式增强对备份服务流量的安全保护。 这包括限制对数据中心的访问, 以保护两个数据中心之间的 WAN 传输。 在大多数情况下, 部署 Skype for Business 服务器的企业可能已经具备所需的安全基础结构。 对于寻求指导的企业, Microsoft 提供了一个解决方案作为如何构建安全 IT 基础结构的示例。 有关详细信息, [https://go.microsoft.com/fwlink/p/?LinkId=268544](https://go.microsoft.com/fwlink/p/?LinkId=268544)请参阅。 
  
我们不暗示它是唯一的解决方案, 也不意味着它是 Skype for business 服务器的首选解决方案。 我们建议企业客户根据其 IT 安全基础结构和要求选择适合其特定需要的解决方案套件。 例如，Microsoft 解决方案将 IPSec 和组策略应用于服务器和域隔离。
  
另一个可能的解决方案是仅使用 IPSec 来帮助保护由备份服务本身发送的数据。 如果选择此方法，您应该为以下服务器配置 SMB 协议的 IPSec 规则，其中，池 A 和池 B 是两个配对前端池。
  
- SMB 服务 (TCP/445) 从池 A 中的每个前端服务器到由池 B 使用的文件存储。
    
- SMB 服务 (TCP/445) 从池 B 中的每个前端服务器到由池 A 使用的文件存储。
    
> [!CAUTION]
>  IPsec 不专门用于代替应用程序级别的安全，例如，SSL/TLS。 使用 IPsec 的一个优势是，可为现有应用程序提供网络流量安全，但无需更改它们。 希望仅保护两个数据中心之间传输安全的企业应咨询其各自的网络硬件供应商, 了解如何使用供应商的设备设置安全的 WAN 连接。
  
## <a name="see-also"></a>另请参阅

[在 Skype for business Server 中部署用于灾难恢复的配对的前端池](../../deploy/deploy-high-availability-and-disaster-recovery/front-end-pools-for-disaster-recovery.md)
