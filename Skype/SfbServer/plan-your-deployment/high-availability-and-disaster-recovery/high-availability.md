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
description: 了解 Skype for Business Server 中的前端池管理，包括管理池、仲裁丢失以及仅有两个前端服务器的池的特殊步骤。
ms.openlocfilehash: 2982e2da0e7a103b5b598019baa7403a73da826d
ms.sourcegitcommit: 397c4840fb053238de24b8b24ae75588b33b693d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2020
ms.locfileid: "45098430"
---
# <a name="front-end-pool-high-availability-and-management"></a>前端池高可用性和管理
 
了解 Skype for Business Server 中的前端池管理，包括管理池、仲裁丢失以及仅有两个前端服务器的池的特殊步骤。
  
在 Skype for Business Server 中，前端池的体系结构使用分布式系统模型，每个用户的数据在池中的多个前端服务器上保留为多达三台的前端服务器。 我们建议您的所有 Enterprise Edition 前端池至少包含三台前端服务器。

> [!NOTE]
> Skype for Business Server 2019 不支持使用两台前端服务器的 Enterprise Edition 前端池，并且不允许在该方案中发布拓扑。
  
## <a name="planning-for-the-management-of-front-end-pools"></a>规划前端池的管理

 Skype for Business Server 使用基于 Windows Fabric 的分布式系统模型。 在此模型中，每个用户和会议的重要数据存储在前端池中的三台前端服务器上。 这三个服务器存储一组特定的数据是 calledreplicas。
  
对于前端池的分布式模型，池服务器的一定数量的服务器必须运行，以便池能够正常工作。 池有两种丢失模式。
  
- 路由组级别仲裁丢失，因特定路由组的副本服务器不足而导致。 路由组是驻留在池中的一组用户。 每个路由组在池中都有三个副本：一个主副本和两个辅助副本。
    
- 池级别仲裁丢失，在池中没有足够的种子服务器运行时导致。 
    
### <a name="routing-group-level-quorum-loss"></a>路由组级别仲裁丢失

首次启动新的前端池时，有85% 的服务器已启动并且正在运行，这一点非常重要，如下表所示。 如果运行较少的服务器，服务可能会处于 "启动" 状态，并且池可能无法启动。
  
|池中的服务器总数  <br/> |在首次启动池时必须运行的服务器的数量  <br/> |
|:-----|:-----|
|2   <br/> |1   <br/> |
|3   <br/> |3   <br/> |
|4   <br/> |3   <br/> |
|5   <br/> |4   <br/> |
|6   <br/> |5   <br/> |
|7   <br/> |5   <br/> |
|8   <br/> |6   <br/> |
|9   <br/> |7   <br/> |
|10   <br/> |8   <br/> |
|11   <br/> |9   <br/> |
|12   <br/> |10   <br/> |
|16 **（适用于 Skype for Business Server 2019** ） <br/> |12   <br/> |


   
每次启动池时，应启动85% 的服务器 (，如上表中所示) 。 如果无法启动此数量的服务器 (但可以启动足够的服务器，以便不会) 池级别的仲裁丢失，则可以使用 `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery` cmdlet 使池能够从该路由组级别仲裁丢失恢复并进行操作。 有关如何使用此 cmdlet 的详细信息，请参阅[Reset-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/reset-cspoolregistrarstate?view=skype-ps)。 
  
> [!NOTE]
> 在具有偶数台服务器的池中，Skype for Business Server 使用主 SQL 数据库作为见证。 在这种情况下，如果关闭主数据库并切换到镜像副本，并关闭足够的前端服务器，以便根据前面的表运行，则整个池将会停止运行。 有关详细信息，请参阅[数据库镜像见证](https://go.microsoft.com/fwlink/?LinkId=393672)。 
  
#### <a name="pool-level-quorum-loss"></a>池级别仲裁丢失

为了让前端池能够正常运行，它不能处于池级别仲裁丢失。 如果运行的服务器数低于功能级别，如下表所示，池中的其余服务器将停止所有 Skype for Business Server 服务。 请注意，下表中的数字假定池中的后端服务器正在运行。
  
|池中的前端服务器总数  <br/> |要使池正常工作所必须运行的服务器的数目  <br/> |
|:-----|:-----|
|2   <br/> |1   <br/> |
|3-4  <br/> |任意2  <br/> |
|5-6  <br/> |任意3  <br/> |
|7   <br/> |任意4  <br/> |
|8-9  <br/> |前7台服务器中的任意4个  <br/> |
|10-12  <br/> |前9个服务器中的任何5个  <br/> |
|**适用于 Skype For Business Server 2019 的**12-16  <br/> |前12个服务器中的任何7个  <br/> |
   
在上表中，"第一台服务器" 是第一次启动池时的服务器。 若要确定这些服务器，可以将 `Get-CsComputer` cmdlet 与选项一起使用 `-PoolFqdn` 。 此 cmdlet 将按其在拓扑中出现的顺序显示服务器，列表顶部的服务器是第一台服务器。
  
> [!IMPORTANT]
> [Skype For Business Server 2019](https://docs.microsoft.com/skypeforbusiness/plan/user-model-2019)中已将最大前端服务器数增加到16个
> 
#### <a name="additional-steps-to-ensure-pools-are-functional"></a>确保池正常运行的其他步骤

您应观看几个其他因素，以确保前端池保持正常运行。
  
- 当第一次将用户移动到池时，确保至少运行三个前端服务器。
    
- 如果在此池与另一个池之间建立了配对关系以用于灾难恢复目的，则必须确保该池在一段时间内同时运行三台前端服务器，以便正确地将数据与备份池同步。 有关池配对和灾难恢复功能的详细信息，请参阅[在 Skype For Business Server 中规划高可用性和灾难恢复](high-availability-and-disaster-recovery.md)。 
    
## <a name="front-end-pool-with-two-front-end-servers"></a>具有两个前端服务器的前端池

建议不要部署仅包含两台前端服务器的前端池。 此小型池不会提供强大的高可用性解决方案，如更大的池，并且在管理时需要格外小心。 此外，如果两个服务器池的后端服务器停止运行，则整个池本身可能也会发生故障。 如果要仅部署一个或两个运行 Skype for Business Server 的服务器，建议将它们作为 Standard Edition 服务器进行部署。
  
如果您需要部署两台前端服务器的池，请遵循以下准则：
  
- 如果两个前端服务器之一停机，您应尝试将该失败的服务器尽快恢复运行。同样，如果需要升级两台服务器之一，升级完成后将其尽快联机。
    
- 如果因某些原因需要将两台服务器同时停机，当该池停机后执行下列操作：
    
  - 最佳做法是同时重新启动这两个前端服务器。 
    
  - 如果无法同时重新启动两台服务器，则应该按其停机时的相反顺序来启动它们。
    
  - 如果不能按该顺序备份，请使用以下 cmdlet，然后再使池恢复：`Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`
    
## <a name="front-end-pool-configuration-failures-and-changes"></a>前端池配置失败和更改

如果前端服务器出现故障且不太可能被替换几天或更多时间，请从拓扑中删除该服务器。 将新的前端服务器添加到拓扑中（当它再次可用时）。
  
无论何时对前端池进行配置更改（如添加或删除服务器），都必须遵循以下准则：
  
- 发布新拓扑后，必须重新启动池中的每台前端服务器。 一次重新启动一个。
    
- 如果在配置更改过程中整个池已关闭，则在发布新拓扑后，请运行以下 cmdlet：`Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`
    

