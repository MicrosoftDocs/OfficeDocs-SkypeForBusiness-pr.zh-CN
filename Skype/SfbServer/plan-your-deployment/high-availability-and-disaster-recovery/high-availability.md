---
title: 前端池高可用性和管理
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 965041b7-3136-49f2-89c1-8b30417cb8ea
description: 了解如何在 Skype 业务服务器，包括管理池、 仲裁丢失和特殊的步骤只有两个前端服务器与池的前端池管理。
ms.openlocfilehash: f348fcc4fee6a48a41265da88fe432d9e4550b6c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="front-end-pool-high-availability-and-management"></a>前端池高可用性和管理
 
了解如何在 Skype 业务服务器，包括管理池、 仲裁丢失和特殊的步骤只有两个前端服务器与池的前端池管理。
  
在 Skype 业务服务器，前端池的体系结构与每个用户的数据保留在池中的三个前端服务器上使用的分布式的系统模型。 我们建议所有的前端企业版池包括至少三个前端服务器。 
  
## <a name="planning-for-the-management-of-front-end-pools"></a>规划前端池的管理

 Skype 业务服务器使用基于 Windows 结构的分布式的系统模型。 在此模型中，每个用户和会议的重要数据存储在三个前端服务器前端池中。 这些存储特定的数据集的三个服务器是 calledreplicas。
  
与前端池的分布式模型，某些数字的池的服务器必须运行池函数。 有两个池损失模式。
  
- 路由组级别仲裁丢失，由特定的路由组没有足够副本服务器。 路由组是指驻留在池中的一组用户。 每个路由组在池中都有三个副本：一个主要副本和两个辅助副本。
    
- 池级仲裁丢失，导致没有足够的种子服务器都运行在池中。 
    
### <a name="routing-group-level-quorum-loss"></a>路由组级别仲裁丢失

当您首次启动新的前端池时，务必确保有 85% 的服务器已启动且正在运行，如下表所示。如果正在运行的服务器数目较少，则服务可能会滞留在启动状态，而池可能无法启动。
  
|池中服务器的总数  <br/> |使池第一次启动所必须运行的服务器的数量  <br/> |
|:-----|:-----|
|2  <br/> |1  <br/> |
|3  <br/> |3  <br/> |
|4  <br/> |3  <br/> |
|5  <br/> |4  <br/> |
|6  <br/> |5  <br/> |
|7  <br/> |5  <br/> |
|8  <br/> |6  <br/> |
|9  <br/> |7  <br/> |
|10  <br/> |8  <br/> |
|11  <br/> |9  <br/> |
|12  <br/> |10  <br/> |
   
以后每次启动池时，都应启动 85% 的服务器（如上表所示）。 如果不能启动此数目的服务器 （但足够的服务器可以启动，这样您就不在池级仲裁丢失），则可以使用`Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery`cmdlet 以启用池从该路由组级仲裁丢失恢复并取得进展。 有关如何使用此 cmdlet 的详细信息，请参阅<link Reset-CsPoolRegistrarState>。
  
> [!NOTE]
> 在有偶数个服务器池，Skype 业务服务器使用作为见证主 SQL 数据库。 在此池中，如果关闭主数据库并切换到镜像副本中，并且关闭足够的前端服务器，以便运行按照上表中，没有足够的整个池就会降低。 有关详细信息，请参阅[数据库镜像见证](https://go.microsoft.com/fwlink/?LinkId=393672)。 
  
#### <a name="pool-level-quorum-loss"></a>池级别仲裁丢失

函数在所有前端池，它不能在池级仲裁丢失。 如果正在运行的服务器数量低于下表所示的正常运作级别，则池中的其余服务器将停止所有 Skype for Business Server 服务。 注意下表中的数字假定在池中的后端服务器正在运行。
  
|前端服务器的池中的总数  <br/> |使池发挥作用所必须运行的服务器的数量  <br/> |
|:-----|:-----|
|2  <br/> |1  <br/> |
|3-4  <br/> |任意 2 台  <br/> |
|5-6  <br/> |任意 3 台  <br/> |
|7  <br/> |任意 4 台  <br/> |
|8-9  <br/> |前 7 台服务器中的任意 4 台  <br/> |
|10-12  <br/> |前 9 台服务器中的任意 5 台  <br/> |
   
在前面的表中，"第一个服务器"是其已提出第一次，按时间顺序，第一次启动时该池的服务器。 若要确定这些服务器，可以使用`Get-CsComputer`使用的 cmdlet` -PoolFqdn`选项。 此 cmdlet 将按服务器在池中的出现顺序显示服务器，列表最上方的服务器就是前几台服务器。
  
#### <a name="additional-steps-to-ensure-pools-are-functional"></a>确保池正常工作的其他步骤

您应注意其他几项因素，以确保您的前端池仍正常工作。
  
- 当您在第一次到池中移动用户时，请确保至少三个前端服务器正在运行。
    
- 如果您为灾难恢复的目的建立此池和另一池之间的一对关系，那么在建立此关系后，必须确保在某些时候此池具有三个同时运行的前端服务器以正确将数据与备份池同步。 池的配对和灾难恢复功能的详细信息，请参阅[规划高可用性和灾难恢复业务服务器 2015年的 Skype](high-availability-and-disaster-recovery.md)。 
    
## <a name="front-end-pool-with-two-front-end-servers"></a>带有两个前端服务器的前端池

我们不建议部署包含只有两个前端服务器的前端池。 这种小型池无法像更大的池一样提供强大的高可用性解决方案，同时还需要花费额外精力进行管理。 此外，如果两台服务器池的后端服务器发生故障，整个池本身很可能不久要向下也。 如果您要部署的业务服务器运行 Skype 的只是一个或两个服务器，我们建议将其部署为标准版服务器。
  
如果您以往任何时候都需要部署两个前端服务器的池中，请遵循以下准则：
  
- 如果一个两个前端服务器出现故障时，您应尝试备份将发生故障的服务器，就可以。 同样，如果需要升级两台服务器之一，升级完成后将其尽快联机。
    
- 如果因某些原因需要将两台服务器同时停机，当该池停机后执行下列操作：
    
  - 最好的做法是同时重新启动两个前端服务器。 
    
  - 如果无法同时重新启动两台服务器，则应该按其停机时的相反顺序来启动它们。
    
  - 如果您不能备份使它们按顺序，然后使用以下 cmdlet 之前将备份的池：`Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`
    
## <a name="front-end-pool-configuration-failures-and-changes"></a>前端池配置失败和更改

如果前端服务器失败，且在近期不可能替换，则从拓扑删除该服务器。当再次可用时向该拓扑添加新的前端服务器。
  
在您对前端池作出配置更改时（比如添加或删除服务器），您必须遵守以下准则：
  
- 发布新拓扑后，必须在池中重新启动每个前端池。一次重新启动一个。
    
- 如果在更改配置过程中，整个池已关闭，然后运行以下 cmdlet 后发布新的拓扑：`Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`
    

