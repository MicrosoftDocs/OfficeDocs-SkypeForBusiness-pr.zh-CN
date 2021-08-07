---
title: 前端池高可用性和管理
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 965041b7-3136-49f2-89c1-8b30417cb8ea
description: 了解池中的前端池Skype for Business Server包括管理池、仲裁丢失和仅包含两台前端服务器的池的特殊步骤。
ms.openlocfilehash: 697cebf352d4fa0e2f245f50395107477ac3bae712346302e94746f173ce4d39
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54276617"
---
# <a name="front-end-pool-high-availability-and-management"></a>前端池高可用性和管理
 
了解池中的前端池Skype for Business Server包括管理池、仲裁丢失和仅包含两台前端服务器的池的特殊步骤。
  
在Skype for Business Server中，前端池的体系结构使用分布式系统模型，每个用户的数据在池中的三个前端服务器上保留。 建议您的所有前端Enterprise Edition都至少包含三台前端服务器。

> [!NOTE]
> Skype for Business Server 2019 不支持Enterprise Edition两台前端服务器的前端池，并且不允许在该方案中发布拓扑。
  
## <a name="planning-for-the-management-of-front-end-pools"></a>规划前端池的管理

 Skype for Business Server基于分布式系统模型Windows Fabric。 在此模型中，每个用户和会议的重要数据存储在前端池中的三台前端服务器上。 这三个存储特定数据集的服务器称为replicas。
  
使用前端池的分布式模型，必须运行一定数量的池服务器，池正常运行。 池有两种丢失模式。
  
- 路由组级别仲裁丢失，由特定路由组的副本服务器不足导致。 路由组是池中的一组用户。 每个路由组在池中有三个副本：一个主要副本和两个辅助副本。
    
- 池级别仲裁丢失，在池中运行种子服务器不足时导致。 
    
### <a name="routing-group-level-quorum-loss"></a>路由组级别仲裁丢失

首次启动新的前端池时，85% 的服务器必须启动并运行，如下表所示。 如果正在运行的服务器较少，则服务可能卡在启动状态，并且池可能无法启动。
  
|池中的服务器总数  <br/> |首次启动池时必须运行的服务器数  <br/> |
|:-----|:-----|
|2  <br/> |1  <br/> |
|3  <br/> |3  <br/> |
|4   <br/> |3  <br/> |
|5   <br/> |4   <br/> |
|6   <br/> |5   <br/> |
|7   <br/> |5   <br/> |
|8   <br/> |6   <br/> |
|9   <br/> |7   <br/> |
|10   <br/> |8   <br/> |
|11  <br/> |9   <br/> |
|12   <br/> |10   <br/> |
|16 **For Skype for Business Server 2019** <br/> |12   <br/> |


   
每次启动池时，都应启动 85% 的服务器 (如上表所示) 。 如果无法启动此数量的服务器 (但可以启动足够的服务器，以便不处于池级别的仲裁丢失) ，您可以使用 cmdlet 使池从此路由组级别仲裁丢失中恢复并推进。 `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery` 有关如何使用此 cmdlet 的信息，请参阅 [Reset-CsPoolRegistrarState](/powershell/module/skype/reset-cspoolregistrarstate?view=skype-ps)。 
  
> [!NOTE]
> 在服务器数量为等数的池中，Skype for Business Server主SQL数据库作为见证。 在此类池中，如果关闭主数据库并切换到镜像副本，并关闭足够的前端服务器，以便根据上表运行不足，整个池将停机。 有关详细信息，请参阅数据库 [镜像见证](/sql/database-engine/database-mirroring/database-mirroring-witness)。 
  
#### <a name="pool-level-quorum-loss"></a>池级别仲裁丢失

前端池可以正常工作，它不能处于池级别仲裁丢失状态。 如果正在运行的服务器数量低于下表中所示的功能级别，则池中的其余服务器将停止所有Skype for Business Server服务。 请注意，下表中的数字假定池中的后端服务器正在运行。
  
|池中的前端服务器总数  <br/> |要使池正常工作所必须运行的服务器的数目  <br/> |
|:-----|:-----|
|2  <br/> |1  <br/> |
|3-4  <br/> |任意 2 个  <br/> |
|5-6  <br/> |任意 3 个  <br/> |
|7   <br/> |任意 4 个  <br/> |
|8-9  <br/> |前 7 台服务器中的任意 4 台  <br/> |
|10-12  <br/> |前 9 台服务器中的任意 5 台  <br/> |
|12-16 **For Skype for Business Server 2019**  <br/> |前 12 台服务器中的任意 7 台  <br/> |
   
在上表中，"第一台服务器"是首次启动池时按时间顺序首先启动的服务器。 若要确定这些服务器，可以将  `Get-CsComputer` cmdlet 与 `-PoolFqdn` 选项一同使用。 此 cmdlet 将按服务器在拓扑中的显示顺序显示服务器，列表顶部的服务器是第一批服务器。
  
> [!IMPORTANT]
> 2019 年，前端服务器的最大数量已增加到[16 Skype for Business Server 16](../../../SfBServer2019/plan/user-model-2019.md)
> 
#### <a name="additional-steps-to-ensure-pools-are-functional"></a>确保池正常工作的其他步骤

应留意一些其他因素，以确保前端池继续正常工作。
  
- 当第一次将用户移动到池时，确保至少运行三个前端服务器。
    
- 如果出于灾难恢复目的在此池与其他池之间建立了配对关系，则建立此关系后，必须确保该池有三个前端服务器同时运行，以便正确将数据与备份池同步。 有关池配对和灾难恢复功能的信息，请参阅 Plan [for high availability and disaster recovery in Skype for Business Server](high-availability-and-disaster-recovery.md)。 
    
## <a name="front-end-pool-with-two-front-end-servers"></a>具有两台前端服务器的前端池

建议不要部署仅包含两台前端服务器的前端池。 此小型池不会像大型池那样提供可靠的高可用性解决方案，并且需要额外注意管理。 此外，如果双服务器池的后端服务器关闭，则整个池本身可能很快也会关闭。 如果要仅部署一台或两台运行 Skype for Business Server，建议将它们部署为Standard Edition服务器。
  
如果您曾经需要部署具有两台前端服务器的池，请遵循以下指南：
  
- 如果两个前端服务器之一停机，您应尝试将该失败的服务器尽快恢复运行。同样，如果需要升级两台服务器之一，升级完成后将其尽快联机。
    
- 如果因某些原因需要将两台服务器同时停机，当该池停机后执行下列操作：
    
  - 最佳做法是同时重新启动两台前端服务器。 
    
  - 如果无法同时重新启动两台服务器，则应该按其停机时的相反顺序来启动它们。
    
  - 如果无法按此顺序进行备份，则先使用以下 cmdlet，然后再备份池：  `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`
    
## <a name="front-end-pool-configuration-failures-and-changes"></a>前端池配置失败和更改

如果前端服务器出现故障，且在几天或几天内不太可能替换，请从拓扑中删除该服务器。 当新的前端服务器再次可用时，将新前端服务器添加到拓扑中。
  
每当对前端池进行配置更改（如添加或删除服务器）时，都必须遵循以下准则：
  
- 发布新拓扑后，必须重新启动池中的每个前端服务器。 一次重新启动一个。
    
- 如果在配置更改期间整个池已关闭，则发布新拓扑后运行以下 cmdlet：  `Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`
