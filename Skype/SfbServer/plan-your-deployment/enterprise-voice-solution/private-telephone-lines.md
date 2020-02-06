---
title: 通过 Skype for Business 规划私人电话线
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9cc4f9e1-7b7a-4699-bd05-f16669ef2d21
description: 在 Skype for Business Server Enterprise Voice 中规划专用（辅助）电话线路。
ms.openlocfilehash: 001a83e4bd81f0f47546f51f1d4993c6b1cec4bf
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802562"
---
# <a name="plan-for-private-telephone-lines-with-skype-for-business"></a>通过 Skype for Business 规划私人电话线
 
在 Skype for Business Server Enterprise Voice 中规划专用（辅助）电话线路。
  
Skype for business 服务器使您可以除主要电话线之外为用户提供第二条专用电话线路。 专用电话线路通常分配给需要一个未列出的电话号码以便他人直接与其取得联系的高管和其他人员。
  
专用电话线只能通过 Skype for Business 服务器命令行管理程序来配置。 您不能通过 Skype for business 服务器控制面板配置私人电话线。 专用电话线应仅在部署 Skype for Business 服务器而不是在混合部署中配置。
  
## <a name="characteristics-of-private-telephone-lines"></a>专用电话线路的特征

虽然第二条专用电话线的概念基本很简单，但重要的是了解专用线路的特性以及它们与用户的主要电话线有类似的方式和不同之处。
  
### <a name="general-characteristics-of-private-telephone-lines"></a>专用电话线路的常规特征

- 每个用户只能有一条专用电话线路。
    
- 具有专用电话线路的用户只有一个语音邮箱，并且只使用一个电子邮件地址接收错过的呼叫通知。
    
- 具有专用电话线路的用户没有第二个 SIP 地址，并且第二条专用电话线路不会在网络上为用户提供第二个状态（如第二个即时消息身份）。 
    
- 专用电话线路仅适用于本地部署。 它们不适用于 Skype for Business Server 的托管部署。
    
### <a name="how-private-telephone-lines-differ-from-primary-telephone-lines"></a>专用电话线路与主要电话线路的不同之处

- 专用电话线路的电话号码不会显示在派生自 Active Directory 域服务的电话簿或联系人列表中。
    
- 专用电话线路不具备以下功能：呼叫转接、团队呼叫、委派、小组电话、组内呼叫应答和响应组应用程序。
    
- 对专用电话线路的呼叫有特殊的响铃，呼叫的系统通知会告知用户传入呼叫位于其专用线路上。
    
- 对专用电话线路的呼叫始终会发出响铃。它们不会遵循“请勿打扰”规则。
    
- 专用电话线路仅限于入站呼叫，不能用于进行传出呼叫。 当具有专用电话线的用户进行呼叫时，该呼叫来自用户的主电话线，并且不会隐藏用户的姓名或用户的主要电话号码（来自呼叫者）。
    
### <a name="how-private-telephone-lines-are-similar-to-primary-telephone-lines"></a>专用电话线路与主要电话线路的相似之处

- 专用电话线路上的未接听呼叫将路由到与主要电话线路相同的语音邮件收件箱（如果已启用语音邮件）。
    
- 呼叫寄存和呼叫装货使用专用电话线的方式与使用用户的主要电话线完全相同。
    
- 在用户的主电话线上启用同时拨打时，它也会在专用电话线上启用。
    
- 专用电话线的电话号码以与用户的主要电话线的电话号码相同的方式记录在呼叫详细记录中，但表明它是专用电话号码。
    
- 用户使用专用电话线应答呼叫后，呼叫将被视为用户的主电话线上的呼叫。 例如，如果通过专用电话线接收呼叫的用户转发呼叫或邀请其他人加入电话会议，则用户名将显示在 Skype for Business 中，用户的主电话线的电话号码将显示在 "来电显示" 中。
    
- 用户可以转接来自于专用电话线路的呼叫（应答前，将呼叫重定向到其他目标，如移动电话或家庭电话），方式与主要电话线路相同。 
    
    > [!NOTE]
    > 专用线路的呼叫路由到备用电话号码后，专用电话线路的电话号码将提供给备用电话号码，并可以显示在该号码的日志中。 
  
    > [!NOTE]
    > 从电话会议到专用电话线的通话在传入系统通知中不会有*私钥*指示。
  
## <a name="administering-private-telephone-lines"></a>管理专用电话线路

除创建和管理专用电话线路的技术方面外，还需要为其建立管理过程。这包括确定组织中谁可以使用专线的策略，创建和维护人员及其电话号码的列表，还可能要为高管创建专用电话簿，安排用户培训和相关任务。
  
> [!NOTE]
> 专用电话线路将在 Active Directory 中作为用户对象的 msRTCSIP-PrivateLine 属性存储。默认情况下，Authenticated Users 组的任何成员对此属性具有读取访问权限。 
  
### <a name="assigning-telephone-numbers"></a>分配电话号码

 对于需要私人电话线的新用户，其帐户的创建方式与没有私人电话线的帐户相同，使用 Skype for Business 服务器控制面板或 Skype for business Server 命令行管理程序。
  
使用 Skype for Business Server Management Shell 中的**move-csuser** cmdlet 为用户将电话号码分配给专用电话线，例如， **move-csuser-Identity "Sip:joe@contoso.com"-PrivateLine "电话： + 14255551212"**。
  
专用电话线的电话号码长度可以介于3到15个号码之间，并且前面必须带有 "电话：" 前缀。 这些号码可以具有任何区号和国家/地区代码，前提是您的组织有该区号和国家/地区代码的外线直拨分机。 
  
有关 cmdlet 和 Skype for business Server 命令行管理程序的详细信息，请参阅 Skype for Business 服务器管理外壳文档。
  
### <a name="private-telephone-lines-in-mixed-deployments"></a>混合部署中的专用电话线路

专用电话线应仅针对 Skype for business Server 或 Lync Server 2013 的部署进行配置。 在其中有运行早期版本的 Lync Server 的服务器的部署中，当较早版本的用户尝试呼叫专用电话线时，呼叫路由失败的原因是服务器无法在专用电话线上执行反向号码查找。
  

