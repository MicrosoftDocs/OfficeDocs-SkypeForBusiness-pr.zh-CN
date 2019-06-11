---
title: Lync Server 2013：前端池配对数据安全
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Front End pool pairing data security
ms:assetid: edb852b8-ea86-4948-b756-60fe6ee876d2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721930(v=OCS.15)
ms:contentKeyID: 49733865
ms.date: 10/07/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: db1a408aecedc14162271d5def1adc2bcebdfd82
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830141"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="front-end-pool-pairing-data-security-in-lync-server-2013"></a>Lync Server 2013 中的前端池配对数据安全

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2014-10-07_

备份服务是 Lync Server 2013 中引入的一种数据复制机制, 可在两个数据中心之间连续传输两个已配对前端池的用户数据和会议内容, 以便进行灾难恢复。 用户数据包含用户 SIP Uri 以及联系人列表和设置。 会议内容包括 Microsoft PowerPoint 2010 上传以及在会议中使用的白板。 从源池中, 用户数据和会议内容从已压缩的本地存储导出到目标池, 并将其解压缩并导入到本地存储。 备份服务假定两个数据中心之间的通讯链路位于公司网络内部，并且具有 Internet 保护。 它不会在两个数据中心之间加密已传输的数据, 也不会在本地封装在安全协议 (如 HTTPS) 中。 因此, 来自公司网络内部人员的中间人攻击是可能的。

<div>

## <a name="evaluating-security-risks"></a>评估安全风险

跨多个数据中心部署 Lync Server 2013 并使用灾难恢复功能的任何企业必须确保跨数据中心流量受其公司 Intranet 的保护。 负责内部攻击防护的企业必须保护数据中心之间的通信链接。

假设企业的数据中心受保护在公司 Intranet 的下方是标准的。 在这些数据中心中传输了许多其他类型的公司敏感数据。 如果这些跨数据中心链接不受保护, 企业的 IT 基础结构将面临可怕风险。

当公司网络内存在中间人攻击的风险时，比较而言，它相当于包含将流量公开到 Internet。 尤其是, 由备份服务 (如 SIP Uri) 公开的用户数据通常可通过其他方式 (如 Exchange 或其他目录软件的全球通讯簿) 供公司内的所有员工使用。 因此, 当使用备份服务在两个配对的池之间复制数据时, 重点应在保护两个数据中心之间的 WAN。

</div>

<div>

## <a name="mitigating-security-risks"></a>减少安全风险

有多种方法可增强备份服务流量的安全保护, 范围从限制对数据中心的访问, 到保护两个数据中心之间的 WAN 传输。 在大多数情况下, 部署 Lync Server 2013 的企业可能已经有了所需的安全基础结构。 对于寻求指导的企业, Microsoft 提供解决方案作为如何构建安全 IT 基础结构的示例。 但是, 这并不意味着它是唯一的解决方案, 也不意味着它是 Lync Server 的首选解决方案。 我们建议, 企业客户根据其 IT 安全基础结构和要求选择解决方案满足其特定需求。Microsoft 解决方案示例使用 IPSec 和组策略进行服务器和域隔离。 有关详细信息, [http://go.microsoft.com/fwlink/p/?LinkId=268544](http://go.microsoft.com/fwlink/p/?linkid=268544)请参阅。 有关问题和评论, 请联系 secwish@microsoft.com。

另一个可能的解决方案是仅使用 IPSec 来帮助保护由备份服务本身发送的数据。 如果选择此方法，您应该为以下服务器配置 SMB 协议的 IPSec 规则，其中，池 A 和池 B 是两个配对前端池。

  - SMB 服务 (TCP/445) 从池 A 中的每个前端服务器到由池 B 使用的文件存储。

  - SMB 服务 (TCP/445) 从池 B 中的每个前端服务器到由池 A 使用的文件存储。

<div>


> [!WARNING]  
> IPsec 不专门用于代替应用程序级别的安全，例如，SSL/TLS。 使用 IPsec 的一个优势是，可为现有应用程序提供网络流量安全，但无需更改它们。 只想在两个数据中心之间提供传输保护的企业应该咨询其相应的网络硬件供应商，以了解有关通过使用供应商的设备建立安全 WAN 连接的方法。



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

