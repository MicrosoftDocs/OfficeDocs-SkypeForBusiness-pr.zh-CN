---
title: 前端池高可用性和管理
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 965041b7-3136-49f2-89c1-8b30417cb8ea
description: 了解业务服务器，包括管理池、 仲裁丢失和特殊的步骤，只有两个前端服务器与池的前端池管理 Skype 中。
ms.openlocfilehash: 43c8e3fffb010bf268f94970b5cca25ecee7cd58
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214073"
---
# <a name="front-end-pool-high-availability-and-management"></a>前端池高可用性和管理
 
了解业务服务器，包括管理池、 仲裁丢失和特殊的步骤，只有两个前端服务器与池的前端池管理 Skype 中。
  
Skype 业务服务器，在前端池的体系结构与每个用户的数据保留在池中的三个前端服务器上使用分布式的系统模型。 我们建议您的所有 Enterprise Edition 前端池都包括至少使用三个前端服务器。 
  
## <a name="planning-for-the-management-of-front-end-pools"></a>规划前端池的管理

 Skype 业务服务器使用基于 Windows Fabric 的分布式的系统模型。 该模型中，为每个用户和会议的重要数据存储三个前端服务器上的前端池。 这些存储特定的数据集的三个服务器是 calledreplicas。
  
与前端池的分布式模型，某些号码的池的服务器必须运行该池的函数。 有两种丢失模式的池。
  
- 路由组级别仲裁丢失，是由于特定路由组的副本服务器不足引起的。 路由组是指驻留在池中的一组用户。 每个路由组在池中都有三个副本：一个主要副本和两个辅助副本。
    
- 池级别仲裁丢失，当池中运行的种子服务器不足时导致的。 
    
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
   
以后每次启动池时，都应启动 85% 的服务器（如上表所示）。 如果无法启动此服务器的数量 （但可以启动足够的服务器，以便不在池级别仲裁丢失），则可以使用`Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery`cmdlet 来启用要恢复此路由组级别仲裁丢失，并使进度的池。 有关如何使用此 cmdlet 的详细信息，请参阅<link Reset-CsPoolRegistrarState>。
  
> [!NOTE]
> 在服务器为偶数的池，Skype 业务服务器使用作为见证主 SQL 数据库。 在类似池中，如果关闭主数据库和切换到镜像副本，并关闭足够的前端服务器，以便根据前面的表中，运行没有足够的整个池就会降低。 有关详细信息，请参阅[数据库镜像见证](https://go.microsoft.com/fwlink/?LinkId=393672)。 
  
#### <a name="pool-level-quorum-loss"></a>池级别仲裁丢失

对于在所有运行的前端池，它不能在池级别仲裁丢失。 如果正在运行的服务器数量低于下表所示的正常运作级别，则池中的其余服务器将停止所有 Skype for Business Server 服务。 请注意下表中的数字假定运行后端服务器池中。
  
|池中前端服务器的总数  <br/> |使池发挥作用所必须运行的服务器的数量  <br/> |
|:-----|:-----|
|2  <br/> |1  <br/> |
|3-4  <br/> |任意 2 台  <br/> |
|5-6  <br/> |任意 3 台  <br/> |
|7  <br/> |任意 4 台  <br/> |
|8-9  <br/> |前 7 台服务器中的任意 4 台  <br/> |
|10-12  <br/> |前 9 台服务器中的任意 5 台  <br/> |
   
在前面的表中，"第一个服务器"是其已提出第一次、 排序，首次启动池时的服务器。 若要确定这些服务器，您可以使用`Get-CsComputer`cmdlet 与` -PoolFqdn`选项。 此 cmdlet 将按服务器在池中的出现顺序显示服务器，列表最上方的服务器就是前几台服务器。
  
#### <a name="additional-steps-to-ensure-pools-are-functional"></a>确保池正常工作的其他步骤

您应注意其他几项因素，以确保您的前端池仍正常工作。
  
- 当您在首次向池中移动用户时，请确保至少运行三个前端服务器。
    
- 如果您为灾难恢复的目的建立此池和另一池之间的一对关系，那么在建立此关系后，必须确保在某些时候此池具有三个同时运行的前端服务器以正确将数据与备份池同步。 有关池配对和灾难恢复功能的详细信息，请参阅[规划高可用性和灾难恢复 Skype 业务服务器中](high-availability-and-disaster-recovery.md)。 
    
## <a name="front-end-pool-with-two-front-end-servers"></a>带有两个前端服务器的前端池

建议不要部署包含只有两个前端服务器的前端池。 这种小型池无法像更大的池一样提供强大的高可用性解决方案，同时还需要花费额外精力进行管理。 此外，如果两个服务器池的后端服务器发生故障，整个池本身可能很快会向下以及。 如果您想要部署运行 Business Server Skype 的只是一个或两个服务器，我们建议您将其部署为 Standard Edition server。
  
如果您的确需要部署具有两个前端服务器池，请遵循以下准则：
  
- 如果一个两个前端服务器不可用，应尝试只要您可以备份使服务器出现故障。 同样，如果需要升级两台服务器之一，升级完成后将其尽快联机。
    
- 如果因某些原因需要将两台服务器同时停机，当该池停机后执行下列操作：
    
  - 最佳做法是同时重新启动两个前端服务器。 
    
  - 如果无法同时重新启动两台服务器，则应该按其停机时的相反顺序来启动它们。
    
  - 如果您无法备份使它们的顺序，然后将备份池前使用以下 cmdlet:`Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`
    
## <a name="front-end-pool-configuration-failures-and-changes"></a>前端池配置失败和更改

如果前端服务器失败，且在近期不可能替换，则从拓扑删除该服务器。当再次可用时向该拓扑添加新的前端服务器。
  
在您对前端池作出配置更改时（比如添加或删除服务器），您必须遵守以下准则：
  
- 发布新拓扑后，必须在池中重新启动每个前端池。一次重新启动一个。
    
- 如果在配置更改期间，整个池已关闭，然后发布新拓扑后运行以下 cmdlet:`Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`
    

