---
title: 前端池中的Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 142caf34-0f20-47f3-9d32-ce25ab622fad
description: 对于灾难恢复，Skype for Business Server在一个池出现故障时提供与故障转移的池配对。
ms.openlocfilehash: fa63aa9d549f64508f32c32ede24f34592a88719
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60833318"
---
# <a name="front-end-pool-disaster-recovery-in-skype-for-business-server"></a>前端池中的Skype for Business Server
 
对于灾难恢复，Skype for Business Server在一个池出现故障时提供与故障转移的池配对。
  
为了在部署中实现最可靠的灾难恢复Skype for Business Server，请跨两个地理位置分散的站点部署前端池对。 每个站点都有一个前端池，该池与其他站点中的相应前端池配对。 这两个站点都处于活动状态，备份服务提供实时数据复制以保持池同步。 如果要[实现前端池](../../deploy/deploy-high-availability-and-disaster-recovery/front-end-pools-for-disaster-recovery.md)配对，请参阅在 Skype for Business Server 部署配对前端池进行灾难恢复。
  
![显示两个不同站点中相互配对的前端池。](../../media/f74533c0-a10e-4f18-85a8-b9a008497573.jpg)
  
如果一个站点中的池出现故障，您可以将用户从该池故障转移到另一个站点中的池，然后为两个池中的所有用户服务。 对于容量规划，应设计每个池，以便能够在发生灾难时处理两个池中所有用户的工作负荷。
  
包含相互配对的前端池的两个数据中心之间可以有任何距离。 建议您将同一世界地区的两个数据中心与它们之间的高速链接配对。 
  
可以跨世界区域拥有两个数据中心，但由于数据复制延迟，如果发生灾难，则可能导致更高的数据丢失。
  
在规划要配对的池时，必须记住，仅支持以下配对：
  
- Enterprise Edition 池仅能与其他 Enterprise Edition 池进行配对。同样，Standard Edition 池仅能与其他 Standard Edition 池进行配对。
    
- 物理池仅能与其他物理池配对。同样，虚拟池仅能与其他虚拟池配对。
    
- 配对在一起的池必须运行相同的基本操作系统。
    
拓扑生成器和拓扑验证都不会阻止以不遵循这些建议的方式对两个池进行配对。 例如，拓扑生成器允许您将 Enterprise Edition 池与 Standard Edition 池进行配对。 但是，不支持这些类型的配对。
  
## <a name="backup-registrar-relationships-and-survivable-branch-appliances"></a>备份注册器关系和 Survivable Branch 设备

除了提供灾难恢复功能外，两个配对的池彼此用作对方的备份注册器。 每个池只能是其他一个前端池的备份。
  
即使两个前端池之间的备份关系必须为 1：1 和对称，每个前端池仍可以是任意数目的 Survivable Branch Appliances 的备份注册器。
  
请注意，Skype for Business不会将灾难恢复支持扩展到 Survivable Branch Appliance 上的用户。 如果用作 Survivable Branch Appliance 的备份的前端池关闭，则登录到 Survivable Branch Appliance 的用户将进入恢复能力模式，即使位于前端池上的用户已故障排入备份前端池。
  
## <a name="recovery-time-for-pool-failover-and-pool-failback"></a>池故障转移和池故障回复的恢复时间

对于池故障转移和池故障回复，RTO (恢复) 目标为 15-20 分钟。 在管理员确定发生灾难并启动故障转移过程后，需要此时间才能进行故障转移。 此时间不包括管理员评估情况并作出决策所需的时间，也不包括用户在故障转移完成后再次登录所需的时间。
  
对于池故障转移和池故障回复，RPO 恢复点目标 (目标) 5 分钟。 这表示测量可能因灾难、因备份服务的复制延迟丢失的数据的时间。 例如，如果池在上午 10：00 下降，RPO 为 5 分钟，则写入池的数据在上午 9：55 之间。 和 10：00 A.M .可能尚未复制到备份池，并且将会丢失。
  
本文档中的所有 RTO 和 RPO 数字均假定两个数据中心位于同一在两个网站间具有高速度、低延迟传输的世界区域中。 这些数字针对具有 40，000 个并发活动用户和 200，000 个用户启用 Skype for Business 的预定义用户模型（其中数据复制没有积压工作）的池进行测量。 这些数字可能根据测试和验证性能发生改变。
  
## <a name="central-management-store-failover"></a>中央管理存储故障转移

中央管理存储包含有关部署中的服务器和服务的配置数据。 每个Skype for Business Server都包括一个中央管理存储，该存储由一个前端池的后端服务器承载。
  
如果将承载中央管理存储的池配对，备份池中将设置备份中央管理存储数据库。 在任意时间点，两个中央管理存储数据库之一处于活动状态，另一个处于备用状态。 备份服务将内容从活动数据库复制到备用数据库。
  
![显示两个前端池，一个池具有活动 CMS 存储，另一个使用被动备份 CMS 存储。](../../media/aa479398-eb56-4854-8d50-1eff39c58a56.jpg)
  
在涉及承载中央管理存储的池的池故障转移期间，必须先对中央管理存储进行故障转移，然后才能对前端池进行故障转移。
  
修复灾难后，不需要对中央管理存储进行故障回复。 中央管理存储可以保留在您进行其故障的池中。
  
中央管理存储故障转移的恢复时间目标 (RTO 故障转移的工程目标为 5 分钟) 5 分钟用于恢复点目标 (RPO) 。
  
## <a name="front-end-pool-pairing-data-security"></a>前端池配对数据安全性

备份服务在两个配对的前端池之间连续传输用户数据和会议内容。 用户数据包含用户 SIP URI 以及会议计划、联系人列表和设置。 会议内容包括 Microsoft PowerPoint上载以及会议中使用的白板。
  
从源池中，此数据从本地存储导出、压缩，然后传输到目标池，在此池中解压缩并导入到本地存储。 备份服务假定两个数据中心之间的通讯链路位于公司网络内部，受 Internet 保护。 它不会加密两个数据中心之间传输的数据，也不会在安全协议（如 HTTPS）中本地封装数据。 因此，可能会受到企业网络内内部人员的中间人攻击。
  
跨多个数据中心部署Skype for Business Server并使用灾难恢复功能的企业必须确保数据中心之间的流量受其公司 Intranet 保护。 关注内部攻击保护的企业必须保护数据中心之间的通信链接。 这是一个标准要求，还有助于保护数据中心之间传输的许多其他类型的公司敏感数据。
  
当公司网络内存在中间人攻击的风险时，比较而言，它相当于包含将流量公开到 Internet。 具体而言，备份服务 (（如 SIP URI) ）公开的用户数据通常可通过其他方式（如全局通讯簿或其他目录软件）提供给公司内的所有员工。 因此，当使用备份服务在两个成对池之间复制数据时，重点应该是保护两个数据中心之间的 WAN。
  
### <a name="mitigating-security-risks"></a>缓解安全风险

您有许多方法可以增强对备份服务流量的安全保护。 这一范围从限制对数据中心的访问到保护两个数据中心之间的 WAN 传输。 在大多数情况下，部署 Skype for Business Server可能已有所需的安全基础结构。 对于寻求指南的企业，Microsoft 提供了一个解决方案，作为如何构建安全的 IT 基础结构的示例。 有关详细信息，请参阅 [https://go.microsoft.com/fwlink/p/?LinkId=268544](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc725770(v=ws.10)) 。 
  
我们并不暗示这是唯一的解决方案，也不表示它是解决方案的首选Skype for Business Server。 建议企业客户根据 IT 安全基础结构和要求选择适合其特定需求的解决方案。 示例 Microsoft 解决方案将 IPSec 和组策略用于服务器和域隔离。
  
另一个可能的解决方案是使用 IPSec 来帮助保护备份服务本身发送的数据。 如果选择此方法，应为以下服务器配置 SMB 协议的 IPSec 规则，其中池 A 和池 B 是两个配对的前端池。
  
- SMB 服务 (TCP/445) 池 A 中的每台前端服务器到池 B 使用的文件存储。
    
- SMB 服务 (TCP/445) 从池 B 中的每台前端服务器到池 A 使用的文件存储。
    
> [!CAUTION]
>  IPsec 不用作应用程序级别安全性（如 SSL/TLS）的替换。 使用 IPsec 的一个优点是，它可以为现有应用程序提供网络流量安全，而无需更改它们。 只想保护两个数据中心之间的传输的企业应咨询其各自的网络硬件供应商，以了解使用供应商设备设置安全 WAN 连接的方法。
  
## <a name="see-also"></a>另请参阅

[部署配对的前端池，以在 Skype for Business Server](../../deploy/deploy-high-availability-and-disaster-recovery/front-end-pools-for-disaster-recovery.md)