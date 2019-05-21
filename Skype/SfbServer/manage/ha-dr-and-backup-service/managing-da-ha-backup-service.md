---
title: 管理灾难恢复、高可用性和备份服务
ms.reviewer: ''
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 了解灾难恢复操作的过程, 以及维护备份服务, 该过程将同步成对前端池内的数据。
ms.openlocfilehash: 9664a7d9d48ca084232e2a0473a15d29d970cea6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303896"
---
# <a name="managing-skype-for-business-server-disaster-recovery-high-availability-and-backup-service"></a>管理 Skype for Business Server 灾难恢复、高可用性和备份服务

本部分包含灾难恢复操作的过程, 以及用于维护备份服务的过程, 该过程将同步成对前端池内的数据。

灾难恢复过程 (故障转移和回切) 是手动的。 如果发生灾难, 管理员必须手动调用故障转移过程。 修复完池后, 故障回复也同样适用。

本部分中的灾难恢复过程假定以下情况:

  - 你的部署具有成对的前端池, 位于不同的网站中, 如[高可用性和灾难恢复计划](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)中所述。 备份服务已在这些配对的池上运行, 以使其保持同步。

  - 如果中央管理存储托管在任一池中, 则会在这两个配对的池上安装和运行它, 其中一个托管活动主机的池和另一个托管备用池的池。

> [!IMPORTANT]
> 在以下过程中, *PoolFQDN*参数是指受灾难影响的池的 FQDN, 而不是对受影响的用户进行重定向的池的 FQDN。 对于同一组受影响的用户, 它指的是故障转移和故障回复 cmdlet 中的同一池 (即, 在故障转移之前首先驻留用户的池)。<BR><br>例如, 假设驻留在池 P1 上的所有用户都已故障转移到备份池 P2 的情况。 如果管理员想要移动当前由 P2 服务的所有用户以供 P1 处理, 管理员必须执行以下步骤: 
> <OL>
> <LI>
> <P>使用故障回复 cmdlet, 将原来位于 P1 中的所有用户从 P2 切换回 P1。 在此情况下, *PoolFQDN*为 P1's FQDN。</P>
> <LI>
> <P>使用故障转移 cmdlet, 将所有最初驻留在 P2 上的用户故障转移到 P1。 在此情况下, PoolFQDN 为 P2's FQDN。</P>
> <LI>
> <P>如果管理员稍后希望将这些 P2 用户故障回复回 P2, 则 PoolFQDN 为 P2's FQDN。</P></LI></OL><br>请注意, 上面的步骤1必须在步骤2之前执行, 以保留池完整性。 如果你在步骤1之前尝试步骤 2, 则步骤 2 cmdlet 将失败。


## <a name="see-also"></a>另请参阅

[规划高可用性和灾难恢复](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) 
  
