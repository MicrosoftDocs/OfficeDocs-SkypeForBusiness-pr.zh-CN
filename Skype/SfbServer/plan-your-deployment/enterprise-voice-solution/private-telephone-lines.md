---
title: 在 Skype for Business Server 2015 中规划专用电话线路
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 9cc4f9e1-7b7a-4699-bd05-f16669ef2d21
description: 在 Skype 的专用 （辅助） 电话线路规划的业务服务器企业语音。
ms.openlocfilehash: ae1d992890d2faa1db9de097a519d363b9e1c228
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-private-telephone-lines-with-skype-for-business-2015"></a>在 Skype for Business Server 2015 中规划专用电话线路
 
在 Skype 的专用 （辅助） 电话线路规划的业务服务器企业语音。
  
Skype 业务服务器可以为用户提供其主要电话线路以及第二个的专用电话线路。 专用电话线路通常分配给需要一个未列出的电话号码以便他人直接与其取得联系的高管和其他人员。
  
私人电话线路只可以用 Skype 业务服务器管理外壳程序的配置。 用于业务服务器控件面板，不能用 Skype 配置专用电话线路。 仅在部署中的 Skype 业务服务器而不是混合部署，应配置专用电话线路。
  
## <a name="characteristics-of-private-telephone-lines"></a>专用电话线路的特征

虽然从根本上简单概念的第二个专用的电话线，就必须了解专线和它们是类似于方法的特性和不同用户的主要电话线路。
  
### <a name="general-characteristics-of-private-telephone-lines"></a>专用电话线路的常规特征

- 每个用户只能有一条专用电话线路。
    
- 具有专用电话线路的用户只有一个语音邮箱，并且只使用一个电子邮件地址接收错过的呼叫通知。
    
- 具有专用电话线路的用户没有第二个 SIP 地址，并且第二条专用电话线路不会在网络上为用户提供第二个状态（如第二个即时消息身份）。 
    
- 为只在内部部署提供了专用电话线路。 这些选项不可用的 Skype 业务服务器的承载部署。
    
### <a name="how-private-telephone-lines-differ-from-primary-telephone-lines"></a>专用电话线路与主要电话线路的不同之处

- 专用电话线路的电话号码不会显示在派生自 Active Directory 域服务的电话簿或联系人列表中。
    
- 专用电话线路不具备以下功能：呼叫转接、团队呼叫、委派、小组电话、组内呼叫应答和响应组应用程序。
    
- 对专用电话线路的呼叫有特殊的响铃，呼叫的系统通知会告知用户传入呼叫位于其专用线路上。
    
- 对专用电话线路的呼叫始终会发出响铃。它们不会遵循“请勿打扰”规则。
    
- 专用电话线路仅限于入站呼叫，不能用于进行传出呼叫。 当具有专用电话线路的用户的调用时，调用来自用户的主要电话线路和不会隐藏用户的名称或用户的主要电话号码的呼叫的人。
    
### <a name="how-private-telephone-lines-are-similar-to-primary-telephone-lines"></a>专用电话线路与主要电话线路的相似之处

- 专用电话线路上的未接听呼叫将路由到与主要电话线路相同的语音邮件收件箱（如果已启用语音邮件）。
    
- 挂断电话，并与用户的主要电话线路一样以相同的方式调用专用电话线路使用的分拣工作。
    
- 当用户的主要电话线路上启用并发响铃时，它也被启用专用电话线路上。
    
- 专用电话线路的电话号码呼叫详细记录中记录用户的主要电话线路，但使用表明，它是一个专用电话号码的电话号码的方式相同。
    
- 在用户回答对专用电话线路，电话是被同等对待用户的主要电话线路的电话。 例如，如果收到专用电话线路的电话用户转发呼叫或邀请其他人到会议呼叫，用户的名称显示在 Skype 的业务，而用户的主要电话线路的电话号码出现在调用方标识。
    
- 用户可以转接来自于专用电话线路的呼叫（应答前，将呼叫重定向到其他目标，如移动电话或家庭电话），方式与主要电话线路相同。 
    
    > [!NOTE]
    > 专用线路的呼叫路由到备用电话号码后，专用电话线路的电话号码将提供给备用电话号码，并可以显示在该号码的日志中。 
  
    > [!NOTE]
    > 从会议对专用电话线路的调用将不具有*专用线路*指示中传入的系统通知。
  
## <a name="administering-private-telephone-lines"></a>管理专用电话线路

除创建和管理专用电话线路的技术方面外，还需要为其建立管理过程。这包括确定组织中谁可以使用专线的策略，创建和维护人员及其电话号码的列表，还可能要为高管创建专用电话簿，安排用户培训和相关任务。
  
> [!NOTE]
> 专用电话线路将在 Active Directory 中作为用户对象的 msRTCSIP-PrivateLine 属性存储。默认情况下，Authenticated Users 组的任何成员对此属性具有读取访问权限。 
  
### <a name="assigning-telephone-numbers"></a>分配电话号码

 需要专用电话线路的新用户帐户创建帐户，而无需专用电话线路，使用 Skype 业务服务器的控制面板或 Skype 业务服务器管理外壳程序的方式相同。
  
使用中的业务服务器管理外壳 Skype**集 CsUser** cmdlet 将电话号码分配给专用电话线路的用户，例如，**组 CsUser-标识"sip:joe@contoso.com"-PrivateLine"电话： +14255551212"**。
  
对专用电话线路的电话号码可以是长度在 3 到 15 号之间和前面必须加上"TEL:"前缀。 这些号码可以具有任何区号和国家/地区代码，前提是您的组织有该区号和国家/地区代码的外线直拨分机。 
  
Cmdlet 和 Skype 业务服务器管理程序的详细信息，请参阅有关业务服务器管理外壳程序文档 Skype。
  
### <a name="private-telephone-lines-in-mixed-deployments"></a>混合部署中的专用电话线路

应仅对 Skype 的业务服务器或 Lync Server 2013 的部署配置专用电话线路。 在部署中存在一些运行较早版本的 Lync Server 中，当用户在早期版本的服务器尝试调用专用电话线路中，路由调用的失败，因为服务器不能执行反向号码查询专用电话线路上。
  

