---
title: 前端池高可用性和管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 965041b7-3136-49f2-89c1-8b30417cb8ea
description: 了解 Skype for Business 服务器中的前端池管理，包括管理池、仲裁损失以及仅有两个前端服务器的池的特殊步骤。
ms.openlocfilehash: 731284d6df761b7fb023c92c656cae5cd6d0ed77
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815910"
---
# <a name="front-end-pool-high-availability-and-management"></a>前端池高可用性和管理
 
了解 Skype for Business 服务器中的前端池管理，包括管理池、仲裁损失以及仅有两个前端服务器的池的特殊步骤。
  
在 Skype for Business 服务器中，前端池的体系结构使用分布式系统模型，其中每个用户的数据都保存在池中的多个前端服务器上。 我们建议你的所有企业版前端池至少包括三个前端服务器。 
  
## <a name="planning-for-the-management-of-front-end-pools"></a>规划前端池的管理

 Skype for business 服务器使用基于 Windows Fabric 的分布式系统模型。 在此模型中，每个用户和会议的重要数据存储在前端池中的三个前端服务器上。 这三个服务器存储一组特定的数据是 calledreplicas。
  
使用分布式模型的前端池，必须运行特定数量的池服务器才能使池正常工作。 池有两种丢失模式。
  
- 路由组级别仲裁丢失，是由于特定路由组的副本服务器不足引起的。 路由组是指驻留在池中的一组用户。 每个路由组在池中都有三个副本：一个主要副本和两个辅助副本。
    
- 池级别仲裁丢失，当池中运行的种子服务器不足时导致的。 
    
### <a name="routing-group-level-quorum-loss"></a>路由组级别仲裁丢失

当您首次启动新的前端池时，务必确保有 85% 的服务器已启动且正在运行，如下表所示。如果正在运行的服务器数目较少，则服务可能会滞留在启动状态，而池可能无法启动。
  
|池中服务器的总数  <br/> |使池第一次启动所必须运行的服务器的数量  <br/> |
|:-----|:-----|
|ppls-2  <br/> |1  <br/> |
|3  <br/> |3  <br/> |
|4  <br/> |3  <br/> |
|5  <br/> |4  <br/> |
|6  <br/> |5  <br/> |
|7  <br/> |5  <br/> |
|个  <br/> |6  <br/> |
|db-9  <br/> |7  <br/> |
|10  <br/> |个  <br/> |
|11  <br/> |db-9  <br/> |
|至  <br/> |10  <br/> |
|**适用于 Skype for Business Server 2019 的**16 <br/> |至  <br/> |


   
以后每次启动池时，都应启动 85% 的服务器（如上表所示）。 如果此数目的服务器无法启动（但可以启动足够的服务器，因此你不在池级别的仲裁丢失），则可以使用`Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery` cmdlet 使池能够从该路由组级别仲裁丢失恢复并进行操作。 有关如何使用此 cmdlet 的详细信息，请参阅[Reset-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/reset-cspoolregistrarstate?view=skype-ps)。 
  
> [!NOTE]
> 在具有偶数个服务器的池中，Skype for business 服务器使用主 SQL 数据库作为见证。 在此类池内，如果关闭主数据库并切换到镜像副本，并关闭足够的前端服务器，以便根据上表中的表运行时，整个池将会停止运行。 有关详细信息，请参阅[数据库镜像见证](https://go.microsoft.com/fwlink/?LinkId=393672)。 
  
#### <a name="pool-level-quorum-loss"></a>池级别仲裁丢失

要使前端池完全正常工作，它不能处于池级别仲裁损失。 如果正在运行的服务器数量低于下表所示的正常运作级别，则池中的其余服务器将停止所有 Skype for Business Server 服务。 请注意，下表中的数字假定池中的后端服务器正在运行。
  
|池中的前端服务器总数  <br/> |使池发挥作用所必须运行的服务器的数量  <br/> |
|:-----|:-----|
|ppls-2  <br/> |1  <br/> |
|3-4  <br/> |任意 2 台  <br/> |
|5-6  <br/> |任意 3 台  <br/> |
|7  <br/> |任意 4 台  <br/> |
|8-9  <br/> |前 7 台服务器中的任意 4 台  <br/> |
|10-12  <br/> |前 9 台服务器中的任意 5 台  <br/> |
|**适用于 Skype for Business Server 2019 的**12-16  <br/> |前12个服务器中的任何7个  <br/> |
   
在上表中，"第一台服务器" 是第一次启动池时的服务器。 若要确定这些服务器，可以将`Get-CsComputer` cmdlet 与`-PoolFqdn`选项结合使用。 此 cmdlet 将按服务器在池中的出现顺序显示服务器，列表最上方的服务器就是前几台服务器。
  
> [!IMPORTANT]
> [Skype For Business Server 2019](https://docs.microsoft.com/skypeforbusiness/plan/user-model-2019)中的最大前端服务器数已增加到16
> 
#### <a name="additional-steps-to-ensure-pools-are-functional"></a>确保池正常工作的其他步骤

您应注意其他几项因素，以确保您的前端池仍正常工作。
  
- 首次将用户移动到池时，请确保至少有三个前端服务器正在运行。
    
- 如果您为灾难恢复的目的建立此池和另一池之间的一对关系，那么在建立此关系后，必须确保在某些时候此池具有三个同时运行的前端服务器以正确将数据与备份池同步。 有关池配对和灾难恢复功能的详细信息，请参阅[在 Skype For Business 服务器中规划高可用性和灾难恢复](high-availability-and-disaster-recovery.md)。 
    
## <a name="front-end-pool-with-two-front-end-servers"></a>带有两个前端服务器的前端池

我们不建议部署仅包含两个前端服务器的前端池。 这种小型池无法像更大的池一样提供强大的高可用性解决方案，同时还需要花费额外精力进行管理。 此外，如果两个服务器池的后端服务器出现故障，则整个池本身可能也会很快停止。 如果要仅部署一个或两个运行 Skype for Business Server 的服务器，建议将它们部署为标准版服务器。
  
如果你需要部署具有两个前端服务器的池，请遵循以下指南：
  
- 如果这两个前端服务器之一出现故障，您应尽可能快地尝试让故障服务器恢复正常状态。 同样，如果需要升级两台服务器之一，升级完成后将其尽快联机。
    
- 如果因某些原因需要将两台服务器同时停机，当该池停机后执行下列操作：
    
  - 最佳做法是同时重新启动这两个前端服务器。 
    
  - 如果无法同时重新启动两台服务器，则应该按其停机时的相反顺序来启动它们。
    
  - 如果不能按该顺序恢复它们，请在重新启动池之前使用以下 cmdlet：`Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`
    
## <a name="front-end-pool-configuration-failures-and-changes"></a>前端池配置失败和更改

如果前端服务器失败，且在近期不可能替换，则从拓扑删除该服务器。当再次可用时向该拓扑添加新的前端服务器。
  
在您对前端池作出配置更改时（比如添加或删除服务器），您必须遵守以下准则：
  
- 发布新拓扑后，必须在池中重新启动每个前端池。一次重新启动一个。
    
- 如果在配置更改期间整个池已停机，则在发布新拓扑后运行以下 cmdlet：`Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`
    

