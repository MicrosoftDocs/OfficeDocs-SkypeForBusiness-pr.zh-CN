---
title: 池中池故障期间Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: b224b0d0-87e3-4cac-ae87-f45f54fabb49
description: 了解前端池在 Skype for Business Server 中的灾难恢复期间发生故障或故障Skype for Business Server。
ms.openlocfilehash: 19533d855c8aeee453808873746609e2508b0b2f
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62390004"
---
# <a name="user-experience-during-pool-failure-in-skype-for-business-server"></a>池中池故障期间Skype for Business Server
 
了解前端池在 Skype for Business Server 中的灾难恢复期间发生故障或故障Skype for Business Server。
  
如果对池进行故障管理，将强制受影响池中的所有用户注销，然后登录到备份池。 登录到备份池的用户在短时间内可能会处于恢复能力模式。 在恢复能力模式下，用户无法执行将导致在用户上发生永久性Skype for Business Server的任务，例如添加联系人。 故障转移完成后，所有用户均可从备份池获得所有服务。
  
池出现故障时，用户拥有的任何呼叫、会议或对话将中断，并且用户必须在故障转移后重新建立这些会话，以继续。
  
故障转移或故障回复期间，不能重新连接用户。 位于失败的池上的用户将由备份池临时提供服务。 还原主池后，管理员可以故障回复这些用户，以便由原始池（仍位于其原来的池）提供服务。
  
请注意，不会将位置信息服务器数据库复制到备份池。 作为最佳做法，管理员应定期备份 LIS 数据库，并在故障转移后使用最新备份副本在备份池中还原 LIS 数据库。
  
## <a name="user-experience-during-failover"></a>故障转移期间用户体验

当用户位于失败的池中时，该用户将注销。用户参与的任何对等会话将结束，该用户组织的会议也结束。 在注册器恢复能力计时器过期或管理员启动故障转移过程之前（以先发生的为准），该用户将无法重新登录。 当用户重新登录时，将会登录到备份池。 如果他们在故障转移完成前登录，则在故障转移完成前，他们将一直处于恢复能力模式。 只有在那时，用户才能建立新会话或重新建立以前的会话。
  
## <a name="user-experience-during-failback"></a>故障回复期间用户体验

当受影响的用户登录到备份池时，可能会发生池故障回复，用户在故障回复期间将保持登录并正常运行。 请注意，故障回复过程需要几分钟时间才能完成。 作为参考，对于用户数为 20,000 的池而言，预期最多需要 60 分钟。
  
下表显示了有关故障回复期间和之后用户如何受到影响的更多详细信息，以及其他池中的用户如何查看正在故障回复的池中的用户并与之交互。 
  
术语受影响用户 指从主池进行故障转移并由备份池提供服务的用户。 最初位于备份池上的用户不是受影响用户。
  
**受影响用户在故障回复池中的用户体验**

|**用户状态或任务**|**故障回复期间**|**故障回复完成后**|
|:-----|:-----|:-----|
|已登录用户的用户状态  <br/> |用户仍登录并连接到备份池。有时，用户将注销，然后在恢复能力模式下登录回原始主池。  <br/> |用户仍然保持登录并转到常规模式。  <br/> |
|用户新登录  <br/> |用户可在恢复能力模式下登录主池。  <br/> |用户可在常规模式下登录原始主池。  <br/> |
|受影响用户组织的正在进行的会议  <br/> |将终止所有形式的会议。将显示“重新加入”按钮，但在受影响用户处于恢复能力模式时任何用户均无法重新加入。  <br/> |所有形式的会议现在可以正常进行。每个参与者需要单击才能重新加入会议。  <br/> |
|不受影响用户组织的正在进行的会议  <br/> |会议将继续，受影响用户可留在会议中。受影响用户将被限制为仅可执行其在恢复能力模式下可执行的操作。  <br/> |会议将继续，受影响用户可留在会议中，所有形式的会议可在用户退出恢复能力模式后正常进行。  <br/> |
|安排或修改计划的会议，创建临时会议  <br/> |当用户处于恢复能力模式时无法实现。  <br/> |所有形式的会议均可实现。  <br/> |
|同一池中的其他用户可看见的状态  <br/> |当用户在恢复能力模式期间登录备份池时状态未知。  <br/> |显示用户设置的最后状态，并且现在将会反映状态更改。  <br/> |
|联系人列表和通讯簿服务可用性  <br/> |不可用  <br/> |可用  <br/> |
|所有对等会话和形式  <br/> |可用  <br/> |可用  <br/> |
   
**在其他池的故障回复期间位于不受影响池的用户的用户体验**

|**用户任务**|**故障回复期间**|**故障回复完成后**|
|:-----|:-----|:-----|
|查看受影响用户的状态  <br/> |显示受影响用户设置的最后状态。  <br/> |正常工作。不受影响的用户可看到受影响用户进行的更新。  <br/> |
|受影响用户组织的正在进行的会议  <br/> |将终止所有形式的会议。  <br/> |所有形式的会议现在可以正常进行。每个参与者需要单击才能重新加入会议。  <br/> |
|不受影响用户组织的正在进行的会议  <br/> |会议将继续，并且受影响用户可留在会议中，所有形式的会议都将正常进行。  <br/> |会议将继续，并且受影响用户可留在会议中，所有形式的会议都将正常进行。  <br/> |
|所有对等会话和形式  <br/> |可用  <br/> |可用  <br/> |
   

