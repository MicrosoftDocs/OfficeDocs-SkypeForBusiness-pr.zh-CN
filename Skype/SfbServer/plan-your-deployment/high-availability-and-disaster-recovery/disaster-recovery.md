---
title: 为业务 Server 前端中 Skype 的最终池灾难恢复
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 142caf34-0f20-47f3-9d32-ce25ab622fad
description: 对于灾难恢复 Skype 业务服务器提供池配对与故障转移，以防一个池不可用。
ms.openlocfilehash: 4f7be2c41155c25984a3a4892fdabe982384756a
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20979889"
---
# <a name="front-end-pool-disaster-recovery-in-skype-for-business-server"></a>为业务 Server 前端中 Skype 的最终池灾难恢复
 
对于灾难恢复 Skype 业务服务器提供池配对与故障转移，以防一个池不可用。
  
最强大灾难恢复选项的 Skype 中的业务服务器，跨两个地理上分散的站点部署成对的前端池。 每个站点包含一个前端池，该池与另一个站点中的相应前端池配对。 这两个站点都处于活动状态，并且备份服务提供了实时数据复制以保持池同步。 如果您想要实现前端池配对，请参阅[部署配对前端池 Skype 业务服务器中的灾难恢复](../../deploy/deploy-high-availability-and-disaster-recovery/front-end-pools-for-disaster-recovery.md)。
  
![显示两个不同网站中相互配对的前端池](../../media/f74533c0-a10e-4f18-85a8-b9a008497573.jpg)
  
如果某个站点中的池出现故障，则您可以将用户从该前端池故障转移到另一个站点中的池，然后可向两个池中的所有用户提供服务。出于容量规划目的，每个池应设计为在发生灾难时处理两个池中所有用户的工作负荷。
  
包括互相配对的前端池的两个数据中心之间没有距离限制。建议使用位于相同世界区域的两个数据中心，并在两者之间建立高速链接。 
  
将两个数据中心设立在不同世界区域也是可行的，但一旦发生灾难，可能会因为数据复制延迟而导致丢失较多数据。
  
当您计划对池进行配对时，必须谨记仅支持以下配对法：
  
- Enterprise Edition 池仅能与其他 Enterprise Edition 池进行配对。同样，Standard Edition 池仅能与其他 Standard Edition 池进行配对。
    
- 物理池仅能与其他物理池配对。同样，虚拟池仅能与其他虚拟池配对。
    
- 配对的池必须运行相同的基本操作系统。
    
拓扑生成器和拓扑验证都不会阻止以不遵循这些建议的方式对两个池进行配对。例如，拓扑生成器允许您将 Enterprise Edition 池与 Standard Edition 池进行配对。但是，不支持进行这些类型的配对。
  
## <a name="backup-registrar-relationships-and-survivable-branch-appliances"></a>备份注册表关系和 Survivable Branch Appliance

除了提供灾难恢复功能外，两个配对的池彼此用作对方的备份注册器。 每个池可以是其他只有一个前端池的备份。
  
即使两个前端池之间的备份关系必须为 1:1 和对称，每个前端池仍可作为任意数量的 Survivable Branch Appliance 的备份注册器。
  
请注意，Skype for Business 不将灾难恢复支持扩展到驻留在 Survivable Branch Appliance 上的用户。如果用作 Survivable Branch Appliance 备份的前端池关闭，那么即使在驻留在前端池上的用户故障转移到备份前端池之后，登录 Survivable Branch Appliance 的用户也会进入恢复能力模式。
  
## <a name="recovery-time-for-pool-failover-and-pool-failback"></a>池故障转移和池故障回复的恢复时间

对于池故障转移和池故障回复，恢复时间目标 (RTO) 的工程目标为 15-20 分钟。这是管理员确定存在灾难并启动故障转移过程之后，故障转移发生所需的时间。此时间不包括管理员评估情况并作出决策所需的时间，也不包括用户在故障转移完成后再次登录所需的时间。
  
对于池故障转移和池故障回复，恢复点目标 (RPO) 的工程目标为 5 分钟。 这表示测量可能因灾难、因备份服务的复制延迟丢失的数据的时间。 例如，如果池关闭上午 10:00 和 RPO 为 5 分钟，数据写入到的池之间上午 9:55 和 10:00 至.might 没有复制到备份池，并将会丢失。
  
本文档中的所有 RTO 和 RPO 数字均假定两个数据中心位于同一在两个网站间具有高速度、低延迟传输的世界区域中。这些数字是针对具有 40,000 个同时活动的用户和 200,000 个已启用有关预定义的用户模型（在该模型中，数据复制没有备份日志）的 Lync 的用户的池测量而来的。这些数字可能根据测试和验证性能发生改变。
  
## <a name="central-management-store-failover"></a>中央管理存储故障转移

中央管理存储包含有关部署中的服务器和服务的配置数据。 对于业务服务器部署的每个 Skype 包括一个中央管理存储，由一个前端池的后端服务器承载。
  
如果对承载中央管理存储的池进行配对，备份池中将会设置一个备份中央管理存储数据库。在任意时刻，两个中央管理存储数据库中总有一个处于活动状态，另一个处于备用状态。备份服务会将内容从主动数据库复制到备用数据库。
  
![显示两个前端池，一个包含主动 CMS 存储，另一个包含被动备份 CMS 存储](../../media/aa479398-eb56-4854-8d50-1eff39c58a56.jpg)
  
在包含承载中央管理存储的池故障转移期间，您必须先对中央管理存储进行故障转移，然后再对前端池进行故障转移。
  
修复灾难后，无需对中央管理存储进行故障回复。中央管理存储可以保留在作为故障转移目标的池中。
  
中央管理存储故障转移的恢复时间目标 (RTO) 和恢复点目标 (RPO) 的工程目标均为 5 分钟。
  
## <a name="front-end-pool-pairing-data-security"></a>前端池配对数据安全

备份服务会在两个成对的前端池之间连续传输用户数据和会议内容。用户数据包含用户 SIP URI 以及会议安排、联系人列表和设置。会议内容包括 Microsoft PowerPoint 上载文件以及会议中使用的白板。
  
在资源池中，此数据将会从本地存储导出、提取并传输到目标池，在这里进行解压并导入到本地存储。 备份服务假定两个数据中心之间的通讯链路位于公司网络内部，并且具有 Internet 保护。 它不会加密在两个数据中心之间传输的数据，也不会在安全协议（如 HTTPS）内进行本地数据封装。 因此，可能会从内部企业网络内部的人员的中间中中间人攻击。
  
任何企业的 Skype 业务服务器部署在多个数据中心，并使用灾难恢复功能必须确保数据中心之间的流量受到其公司的 Intranet。 关注内部攻击保护的企业必须保护数据中心之间的通讯链路。 这是一种标准要求，同样有助于保护数据中心之间传输的其他类型的企业敏感数据。
  
当公司网络内存在中间人攻击的风险时，比较而言，它相当于包含将流量公开到 Internet。尤其是，通过备份服务（如，SIP URI）公开的用户数据通过其他方法（例如，全局通讯簿或其他目录软件）通常可用于公司内的所有员工。因此，当将备份服务用于复制两个成对池之间的数据时，重点应该是保护两个数据中心之间的 WAN。
  
### <a name="mitigating-security-risks"></a>减轻安全风险

可以使用多种方法来增强的备份服务通信的安全保护。 从限制到到保护 WAN 数据中心的访问，该范围在两个数据中心之间的传输。 在大多数情况下，部署 for Business Server Skype 的企业可能已经就地拥有所需的安全基础结构。 企业版查找的指南，Microsoft 提供的举例说明如何构建安全的 IT 基础结构的解决方案。 有关详细信息，请参阅[https://go.microsoft.com/fwlink/p/?LinkId=268544](https://go.microsoft.com/fwlink/p/?LinkId=268544)。 
  
我们并不意味着，它是唯一的解决方案，也不执行意味着它是业务服务器 Skype 的首选的解决方案。 我们建议企业客户根据其 IT 安全基础结构和要求选择适合其特定需要的解决方案套件。 例如，Microsoft 解决方案将 IPSec 和组策略应用于服务器和域隔离。
  
另一个可能的解决方案是仅使用 IPSec 来帮助保护由备份服务本身发送的数据。如果选择此方法，您应该为以下服务器配置 SMB 协议的 IPSec 规则，其中，池 A 和池 B 是两个配对前端池。
  
- SMB 服务 (TCP/445) 从池 A 中的每个前端服务器到由池 B 使用的文件存储。
    
- SMB 服务 (TCP/445) 从池 B 中的每个前端服务器到由池 A 使用的文件存储。
    
> [!CAUTION]
>  IPsec 不专门用于代替应用程序级别的安全，例如，SSL/TLS。 使用 IPsec 的一个优势是，可为现有应用程序提供网络流量安全，但无需更改它们。 要只是安全的两个数据中心之间传输的企业应咨询其各自网络硬件供应商了解使用供应商的设备设置安全的 WAN 连接的方式。
  
## <a name="see-also"></a>另请参阅

[为业务服务器部署已配对的前端池 Skype 中的灾难恢复](../../deploy/deploy-high-availability-and-disaster-recovery/front-end-pools-for-disaster-recovery.md)