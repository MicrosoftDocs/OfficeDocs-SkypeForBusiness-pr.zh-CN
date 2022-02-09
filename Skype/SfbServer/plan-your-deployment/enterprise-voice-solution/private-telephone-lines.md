---
title: 规划专用电话线路与Skype for Business
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9cc4f9e1-7b7a-4699-bd05-f16669ef2d21
description: 规划专用 (专用) 电话线路Skype for Business Server 企业语音。
ms.openlocfilehash: 0e438615219dd92300390873278132000edd8112
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62397576"
---
# <a name="plan-for-private-telephone-lines-with-skype-for-business"></a>规划专用电话线路与Skype for Business
 
规划专用 (专用) 电话线路Skype for Business Server 企业语音。
  
Skype for Business Server用户的主要电话线路之外，您还可以为用户提供第二条专用电话线路。 专用电话线路通常分配给需要一个未列出的电话号码以便他人直接与其取得联系的高管和其他人员。
  
专用电话线路只能使用命令行管理程序Skype for Business Server配置。 不能使用控制面板配置专用Skype for Business Server线路。 专用电话线路只能在专用电话Skype for Business Server混合部署中配置。
  
## <a name="characteristics-of-private-telephone-lines"></a>专用电话线路的特征

尽管第二条专用电话线路的概念基本上很简单，但了解专用线路的特征以及这些线路与用户的主要电话线路的相似和不同方式很重要。
  
### <a name="general-characteristics-of-private-telephone-lines"></a>专用电话线路的常规特征

- 每个用户只能有一条专用电话线路。
    
- 具有专用电话线路的用户只有一个语音邮箱，并且只使用一个电子邮件地址接收错过的呼叫通知。
    
- 具有专用电话线路的用户没有第二个 SIP 地址，并且第二条专用电话线路不会在网络上为用户提供第二个状态（如第二个即时消息身份）。 
    
- 专用电话线路仅适用于本地部署。 它们不适用于托管部署Skype for Business Server。
    
### <a name="how-private-telephone-lines-differ-from-primary-telephone-lines"></a>专用电话线路与主要电话线路的不同之处

- 专用电话线路的电话号码不会显示在派生自 Active Directory 域服务的电话簿或联系人列表中。
    
- 专用电话线路没有以下功能可用：呼叫转发、团队呼叫、委派、团队响铃、组内呼叫应答和响应组应用程序。
    
- 对专用电话线路的呼叫有特殊的响铃，呼叫的系统通知会告知用户传入呼叫位于其专用线路上。
    
- 对专用电话线路的呼叫始终会发出响铃。它们不会遵循“请勿打扰”规则。
    
- 专用电话线路仅限于入站呼叫，不能用于进行传出呼叫。 当具有专用电话线路的用户发起呼叫时，该呼叫源自该用户的主要电话线路，并且不会向被叫人员隐藏该用户的姓名或用户的主要电话号码。
    
### <a name="how-private-telephone-lines-are-similar-to-primary-telephone-lines"></a>专用电话线路与主要电话线路的相似之处

- 专用电话线路上的未接听呼叫将路由到与主要电话线路相同的语音邮件收件箱（如果已启用语音邮件）。
    
- 呼叫安排和呼叫接听使用专用电话线路的方式与使用用户的主要电话线路的方式完全相同。
    
- 在用户的主要电话线路上启用同时响铃时，也会在专用电话线路上启用此功能。
    
- 专用电话线路的电话号码记录在呼叫详细信息记录中的方式与用户的主要电话线路的电话号码相同，但指示这是专用电话号码。
    
- 在用户应答专用电话线路上的呼叫后，该呼叫被视为与该用户的主要电话线路上的呼叫相同。 例如，如果在专用电话线路上收到呼叫的用户转发该呼叫或邀请其他人加入电话会议，该用户的名称将显示在 Skype for Business 中，并且该用户的主要电话线路的电话号码将显示在呼叫者 ID 中。
    
- 用户可以转接来自于专用电话线路的呼叫（应答前，将呼叫重定向到其他目标，如移动电话或家庭电话），方式与主要电话线路相同。 
    
    > [!NOTE]
    > 专用线路的呼叫路由到备用电话号码后，专用电话线路的电话号码将提供给备用电话号码，并可以显示在该号码的日志中。 
  
    > [!NOTE]
    > 从会议到专用电话线路的呼叫  *在传入系统*  通知中不会显示专线指示。
  
## <a name="administering-private-telephone-lines"></a>管理专用电话线路

除创建和管理专用电话线路的技术方面外，还需要为其建立管理过程。这包括确定组织中谁可以使用专线的策略，创建和维护人员及其电话号码的列表，还可能要为高管创建专用电话簿，安排用户培训和相关任务。
  
> [!NOTE]
> 专用电话线路将在 Active Directory 中作为用户对象的 msRTCSIP-PrivateLine 属性存储。默认情况下，Authenticated Users 组的任何成员对此属性具有读取访问权限。 
  
### <a name="assigning-telephone-numbers"></a>分配电话号码

 需要专用电话线路的新用户的帐户创建方式与没有专用电话线路的帐户相同，Skype for Business Server控制面板或 Skype for Business Server命令行管理程序。
  
使用 Skype for Business Server 命令行管理程序 中的 **Set-CsUser** cmdlet 将电话号码分配给用户的专用电话线路，例如 **Set-CsUser -Identity "sip:joe@contoso.com" -PrivateLine "Tel：+14255551212"**。
  
专用电话线路的电话号码长度介于 3 到 15 位之间，且必须以"TEL："前缀开头。 这些号码可以具有任何区号和国家/地区代码，前提是您的组织有该区号和国家/地区代码的外线直拨分机。 
  
有关 cmdlet 和命令行管理Skype for Business Server的详细信息，请参阅命令行Skype for Business Server命令行管理程序文档。
  
### <a name="private-telephone-lines-in-mixed-deployments"></a>混合部署中的专用电话线路

专用电话线路应仅为部署 Skype for Business Server Lync Server 2013 而配置。 在有些服务器运行早期版本的 Lync Server 的部署中，当早期版本上的用户尝试呼叫专用电话线路时，呼叫路由将失败，因为服务器无法在专用电话线路上执行反向号码查找。
  

