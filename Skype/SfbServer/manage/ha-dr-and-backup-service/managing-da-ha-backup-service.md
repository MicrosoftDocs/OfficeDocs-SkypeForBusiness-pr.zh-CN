---
title: 管理灾难恢复、 高可用性和备份服务
ms.reviewer: ''
author: heidip
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 了解有关灾难恢复操作以及维护同步配对前端池中数据备份服务的过程。
ms.openlocfilehash: 103e0aa274e40fd997981bd6de595ceca089b710
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892411"
---
# <a name="managing-skype-for-business-server-disaster-recovery-high-availability-and-backup-service"></a>管理 Skype 的业务 Server 灾难恢复、 高可用性和备份服务

本节包含灾难恢复操作以及维护同步配对前端池中数据备份服务的过程。

灾难恢复过程，故障转移和故障回复，是手动。 如果没有灾难，管理员必须手动调用故障转移过程。 这同样适用于故障回复后修复池。

本节中的灾难恢复过程假定以下几点：

  - 您必须部署已配对前端池，位于不同网站[规划高可用性和灾难恢复](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)中所述。 备份服务已在这些配对的池，以使它们保持同步运行。

  - 如果在任一池中承载中央管理存储，它是两者之一的承载活动主控形状这些池和承载备用的其他池配对池上安装和运行。

> [!IMPORTANT]
> 在下面的过程中， *PoolFQDN*参数是指受灾难的池的 FQDN，从正在重定向不受影响用户的池。 为一组相同的受影响的用户，它引用到相同的池故障转移和故障回复 cmdlet （即，首先驻留故障转移前的用户的池） 中。<BR><br>例如，假定所有用户都驻留在 P1 已故障转移到备份池，P2 池中案例。 如果管理员希望将当前 P2 P1 中处理由提供服务的所有用户都移动，管理员必须执行以下步骤： 
> <OL>
> <LI>
> <P>失败备份所有用户最初驻留在从 P2 到 P1 P1 使用故障回复 cmdlet。 在这种情况下，则*PoolFQDN*为 P1 的 FQDN。</P>
> <LI>
> <P>故障转移所有用户最初驻留在 P2 到 P1 使用故障转移 cmdlet。 在这种情况下，则 PoolFQDN 为 P2 的 FQDN。</P>
> <LI>
> <P>如果更高版本，管理员希望故障回复这些 P2 用户回复到 P2，则 PoolFQDN 为 P2 的 FQDN。</P></LI></OL><br>请注意步骤 2 以保持池完整性之前必须执行的步骤 1 上面。 如果您尝试步骤 2 之前步骤 1，则第 2 步 cmdlet 将失败。


## <a name="see-also"></a>另请参阅

[规划高可用性和灾难恢复](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md) 
  
