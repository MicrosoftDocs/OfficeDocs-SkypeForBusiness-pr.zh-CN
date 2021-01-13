---
title: 管理灾难恢复、高可用性和备份服务
ms.reviewer: ''
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 了解灾难恢复操作以及维护备份服务的过程，备份服务同步配对前端池中的数据。
ms.openlocfilehash: e486a71203b64b4fc351888869ac64a24689ba7b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817152"
---
# <a name="managing-skype-for-business-server-disaster-recovery-high-availability-and-backup-service"></a>管理 Skype for Business Server 灾难恢复、高可用性和备份服务

本节包含灾难恢复操作以及维护备份服务的过程，备份服务同步配对前端池中的数据。

灾难恢复过程（故障转移和故障回复）都是手动的。如果出现灾难，管理员必须手动调用故障转移过程。在修复池之后，此规则同样适用于故障回复。

本节中的灾难恢复过程假定以下内容：

  - 有一个部署，其中配对的前端池位于不同的站点，如规划高可用性和 [灾难恢复中所述](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。 这些配对池中一直运行备份服务，以使其保持同步。

  - 如果中央管理存储托管在任一池中，则它会在两个配对池上安装并运行，其中一个池托管活动主机，另一个池托管备用池。

> [!IMPORTANT]
> 在下面的过程中，*PoolFQDN* 参数表示受灾难影响的池而不是受影响的用户从中重定向的池的 FQDN。对于同一组受影响的用户，它在故障转移和故障回复 cmdlet 中表示同一个池（即，在故障转移之前先承载用户的池）。<BR><br>例如，假定这样一种情况，其中驻留在池 P1 中的所有用户都故障转移到备份池 P2。如果管理员要将当前由 P2 服务的所有用户都移动为由 P1 服务，则管理员必须执行以下步骤： 
> <OL>
> <LI>
> <P>使用故障回复 cmdlet 将最初驻留在 P1 上的所有用户从 P2 故障回复到 P1。在此情况下，*PoolFQDN* 为 P1 的 FQDN。</P>
> <LI>
> <P>使用故障转移 cmdlet 将最初驻留在 P2 上的所有用户故障转移到 P1。 在此情况下，PoolFQDN 为 P2 的 FQDN。</P>
> <LI>
> <P>如果稍后管理员要将这些 P2 用户故障回复到 P2，则 PoolFQDN 为 P2 的 FQDN。</P></LI></OL><br>请注意，上面的步骤 1 必须在步骤 2 之前执行，才能保留池完整性。如果在步骤 1 之前尝试步骤 2，则步骤 2 cmdlet 将失败。


## <a name="see-also"></a>另请参阅

[规划高可用性和灾难恢复](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) 
  
