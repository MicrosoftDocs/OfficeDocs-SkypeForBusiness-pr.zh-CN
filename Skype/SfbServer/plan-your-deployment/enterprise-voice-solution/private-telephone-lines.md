---
title: 在 Skype for Business Server 2015 中规划专用电话线路
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9cc4f9e1-7b7a-4699-bd05-f16669ef2d21
description: 规划业务 Server 企业语音中 Skype 的专用 （辅） 电话线路。
ms.openlocfilehash: 67be5d65be7d97399309934aff52eadf1869cc50
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="plan-for-private-telephone-lines-with-skype-for-business-2015"></a>在 Skype for Business Server 2015 中规划专用电话线路
 
规划业务 Server 企业语音中 Skype 的专用 （辅） 电话线路。
  
Skype 业务服务器，您可以为用户提供其主要电话线路除了第二个、 专用电话线路。 专用电话线路通常分配给需要一个未列出的电话号码以便他人直接与其取得联系的高管和其他人员。
  
专用电话线路仅可以与 Skype 的业务 Server 命令行管理程序配置。 为业务 Server Control Panel，不能与 Skype 配置专用电话线路。 仅在的 Skype 业务服务器的部署和混合部署中不应配置专用电话线路。
  
## <a name="characteristics-of-private-telephone-lines"></a>专用电话线路的特征

虽然发生根本性简单第二个、 专用电话线路的概念，就必须了解专线和它们是类似的方法的特征和不同于用户的主要电话线路。
  
### <a name="general-characteristics-of-private-telephone-lines"></a>专用电话线路的常规特征

- 每个用户只能有一条专用电话线路。
    
- 具有专用电话线路的用户只有一个语音邮箱，并且只使用一个电子邮件地址接收错过的呼叫通知。
    
- 具有专用电话线路的用户没有第二个 SIP 地址，并且第二条专用电话线路不会在网络上为用户提供第二个状态（如第二个即时消息身份）。 
    
- 专用电话线路供仅限本地部署。 他们不可用的 Skype 业务服务器承载的部署。
    
### <a name="how-private-telephone-lines-differ-from-primary-telephone-lines"></a>专用电话线路与主要电话线路的不同之处

- 专用电话线路的电话号码不会显示在派生自 Active Directory 域服务的电话簿或联系人列表中。
    
- 专用电话线路不具备以下功能：呼叫转接、团队呼叫、委派、小组电话、组内呼叫应答和响应组应用程序。
    
- 对专用电话线路的呼叫有特殊的响铃，呼叫的系统通知会告知用户传入呼叫位于其专用线路上。
    
- 对专用电话线路的呼叫始终会发出响铃。它们不会遵循“请勿打扰”规则。
    
- 专用电话线路仅限于入站呼叫，不能用于进行传出呼叫。 当具有专用电话线路的用户进行呼叫时，呼叫来自用户的主要电话线路，并不隐藏用户的名称或从呼叫的人的用户的主要电话号码。
    
### <a name="how-private-telephone-lines-are-similar-to-primary-telephone-lines"></a>专用电话线路与主要电话线路的相似之处

- 专用电话线路上的未接听呼叫将路由到与主要电话线路相同的语音邮件收件箱（如果已启用语音邮件）。
    
- 呼叫寄存和呼叫中方式完全相同的分拣使用专用电话线路与用户的主要电话线路一样。
    
- 在用户的主要电话线路上启用同时响铃后，它还专用电话线路上启用。
    
- 专用电话线路的电话号码呼叫详细信息记录在记录在相同的方式的用户的主要电话线路，但是有指示它是专用电话号码的电话号码。
    
- 在用户 answers 上的专用电话线路，呼叫的呼叫被视为相同用户的主要电话线路上的呼叫。 例如，如果收到专用电话线路上的呼叫的用户转发呼叫或邀请其他人加入电话会议，用户的名称将出现在 for Business，Skype 和用户的主要电话线路的电话号码显示在呼叫者 id。
    
- 用户可以转接来自于专用电话线路的呼叫（应答前，将呼叫重定向到其他目标，如移动电话或家庭电话），方式与主要电话线路相同。 
    
    > [!NOTE]
    > 专用线路的呼叫路由到备用电话号码后，专用电话线路的电话号码将提供给备用电话号码，并可以显示在该号码的日志中。 
  
    > [!NOTE]
    > 从会议向专用电话线路的呼叫将不具有*专线*中，传入系统通知。
  
## <a name="administering-private-telephone-lines"></a>管理专用电话线路

除创建和管理专用电话线路的技术方面外，还需要为其建立管理过程。这包括确定组织中谁可以使用专线的策略，创建和维护人员及其电话号码的列表，还可能要为高管创建专用电话簿，安排用户培训和相关任务。
  
> [!NOTE]
> 专用电话线路将在 Active Directory 中作为用户对象的 msRTCSIP-PrivateLine 属性存储。默认情况下，Authenticated Users 组的任何成员对此属性具有读取访问权限。 
  
### <a name="assigning-telephone-numbers"></a>分配电话号码

 需要专用电话线路的新用户帐户创建方式与没有专用电话线路，业务 Server Control Panel 或 Skype Skype 用于业务 Server 命令行管理程序帐户相同。
  
使用中的业务 Server 命令行管理程序 Skype **Set-csuser** cmdlet 将电话号码分配给用户，例如，专用电话线路**Set-csuser-Identity"sip:joe@contoso.com"-PrivateLine"Tel: +14255551212"**。
  
专用电话线路的电话号码可以是在长度 3 至 15 个数字之间，并且必须前面带有"TEL:"前缀。 这些号码可以具有任何区号和国家/地区代码，前提是您的组织有该区号和国家/地区代码的外线直拨分机。 
  
有关 cmdlet 和 Skype 的业务 Server 命令行管理程序的详细信息，请参阅 Business Server Management Shell 文档 Skype。
  
### <a name="private-telephone-lines-in-mixed-deployments"></a>混合部署中的专用电话线路

专用电话线路应仅配置的 Skype 业务服务器或 Lync Server 2013 的部署。 在部署中在其中有服务器运行早期版本的 Lync Server，当早期版本上的用户尝试调用专用电话线路，路由的呼叫失败，因为服务器不能在专用电话线路上执行反向号码查找。
  

