---
title: 规划电话拨入式会议Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: ea024a26-37b3-410e-961b-83ab85c07540
description: 摘要：阅读本主题，了解如何在 Skype for Business Server 中规划电话拨入式Skype for Business Server。
ms.openlocfilehash: 84d034ba358213a0f79548df6cc1ca027098633b
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60841084"
---
# <a name="plan-for-dial-in-conferencing-in-skype-for-business-server"></a>规划电话拨入式会议Skype for Business Server
 
**摘要：** 阅读本主题，了解如何在 Skype for Business Server 中规划电话拨入式Skype for Business Server。
  
电话拨入式会议是电话拨入式会议的一项可选Skype for Business Server该功能允许与会者通过电话拨入会议来加入会议的音频部分。 电话拨入式会议是音频会议的一部分且需要其他配置。 本主题介绍在为组织部署电话拨入式会议之前您需要思考的内容。 
  
电话拨入式会议所需的某些组件特定于电话拨入式会议，有些组件企业语音组件。 尽管电话拨入式会议使用的一些组件企业语音，但即使未部署电话拨入式会议，也可以部署企业语音。 本节介绍电话拨入式会议所需的组件。 有关规划完整解决方案企业语音，请参阅在 Skype for Business Server 中规划企业语音[解决方案](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-solution.md)。
  
电话拨入式会议要求通过部署中介服务器 (PSTN) 公用电话交换网的连接。 除了部署中介服务器之外，还需要考虑以下事项，以允许组织进行电话拨入式会议：
  
- 您用于连接到 PSTN 公用电话交换网 (PSTN) 
    
- 拨号计划、访问号码和会议区域计划
    
- 创建会议目录的计划
    
- 允许拨入访问的会议策略
    
- 支持企业用户和匿名用户
    
> [!NOTE]
> 如果部署电话拨入式会议，则必须在部署电话拨入式会议Skype for Business Server部署电话拨入式会议。 无需为每个池中分配访问号码（参与者为加入会议而呼叫的号码），但必须在每个池中部署拨入功能。 当用户从一个池中呼叫访问号码以加入另一个池中Skype for Business Server会议时，此要求支持记录的名称功能。 
  
## <a name="plan-for-pstn-connectivity"></a>规划 PSTN 连接

电话拨入式会议需要 PSTN 网关中的至少一台中介服务器 (一) 电话交换网。 
  
可以在中央站点或分支站点部署中介服务器。 在中央站点中，可以将中介服务器并Standard Edition前端池或前端服务器上，也可以将其部署到独立服务器或池中。 在分支站点中，可以在独立服务器上部署中介服务器，也可以将中介服务器部署为 Survivable Branch Appliance 的组件。
  
您可以在中央站点或分支站点部署 PSTN 网关。 在分支站点中，PSTN 网关可以是独立网关，也可以作为 Survivable Branch Appliance 的组件。
  
有关中介服务器和 PSTN 网关要求的详细信息，请参阅[Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md)中的中介服务器组件、在 Skype for Business Server 拓扑生成器中部署中介服务器和在[Skype for Business Server](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md)拓扑生成器中定义[网关](../../deploy/deploy-enterprise-voice/define-a-gateway.md)。
  
## <a name="plan-for-dial-plans-access-numbers-and-conferencing-regions"></a>规划拨号计划、访问号码和会议区域

若要配置电话拨入式会议，请创建拨号计划和电话拨入式会议访问号码。 还可以指定将电话拨入式会议访问号码与拨号计划关联的拨入区域。 更具体地说：
  
- 拨号计划是一组规范化规则，用于指定电话号码中的数字和数字模式，以及将电话号码转换为呼叫路由所需的标准 E.164 格式。
    
- 电话拨入式会议访问号码是参与者为加入会议而呼叫的号码。
    
- 每个电话拨入式会议访问号码必须至少与一个拨号计划关联。 
    
- 每个拨号计划都与一个会议区域关联。
    
创建拨号计划时，指定适用于拨号计划的电话拨入式会议区域。 在创建拨入访问号码时，选择将该访问号码与相应拨号计划关联的区域。
  
还可以指定拨号计划的作用域：用户作用域、池作用域或站点作用域。 会按照各用户适用的最小作用域为其分配拨号计划。 例如，如果适用，则为用户分配用户级别的拨号计划。 如果用户级别的拨号计划不适用，则为用户分配池级别的拨号计划。 如果池级别的拨号计划不适用，则为用户分配站点级别的拨号计划。 如果站点级别的拨号计划不适用，则为用户分配全局拨号计划。 
  
配置拨号计划之前，规划命名和使用区域的方式非常重要。对于电话拨入式会议区域，请注意下列事项：
  
- 区域通常是与某个办公室或一组办公室相关联的地理区域。
    
- 语言与拨入访问号码相关联。如果支持具有多种语言的地理区域，应该决定如何定义区域以便支持多种语言。例如，可以基于地理位置和语言的组合定义多个区域，或者基于地理位置定义一个区域，且每种语言拥有不同的拨入访问号码。
    
- 用户安排会议时，默认情况下会议将使用用户的拨号计划所指定的区域。
    
- 默认情况下，区域的所有拨入访问号码都包含在会议邀请中。
    
- 命名区域非常重要，以便可以清楚地识别它们。 用户可以使用区域名称更改会议区域，以便邀请中包含不同的访问号码。  (用户使用 Outlook 安排会议时，用户使用联机会议外接程序Skype for Business更改区域) 。
    
- 应该对区域加以设计，以便想要拨入会议的被邀请者可以在会议邀请中看到本地访问号码。
    
- 通过使用 Skype for Business Server 命令行管理程序 cmdlet，可以配置区域内访问号码在电话拨入式会议 设置 (上的显示顺序 (以及这些号码在会议邀请) 中的显示顺序。
    
- 任何位置的任何用户均可拨打拨入访问号码来加入会议。
    
有关创建拨号计划的信息，请参阅 Create [or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md) and Create or modify a normalization rule in [Skype for Business](../../deploy/deploy-enterprise-voice/normalization-rules.md)。 
  
## <a name="plan-for-conference-directories"></a>规划会议目录

会议目录维护使用 Skype for Business 时参与者用于加入会议的字母数字会议 ID 与电话拨入式会议参与者加入会议时使用的仅数字会议 ID 之间的映射。 会议 ID 的格式如下：
  

\<housekeeping digit (1 digit)\>\<conference directory (usually 1-2 digits)\>\<conference number (variable number of digits\>\<check digit (1 digit)\>


创建多个会议目录将确保会议 ID 将短暂停留，直到创建了大量会议。 在每个用户需要参与典型数量会议的组织中，建议您为池中的每 999 个用户创建一个会议目录。 使用此指南，会议 ID 通常可以保持较小。 但是，一旦会议目录的数目（在池中）超过 9，则会议 ID 号将增大以支持其他会议。
  
## <a name="plan-for-a-conferencing-policy-that-allows-dial-in-access"></a>规划允许拨入访问的会议策略

配置会议策略时，必须为会议启用拨入访问。 默认情况下，允许拨入访问的会议会在会议邀请中包括以下信息：
  
- 用于标识会议的数字会议 ID
    
- 一个或多个 PSTN 访问号码
    
- 指向电话拨入式会议设置页面的链接，其中包含使用其关联语言的访问号码的完整列表;创建、重置或取消阻止个人标识号 (PIN) ;以及其他信息，例如双音多频 (DTMF) 控件
    
有关会议策略详细信息，请参阅在 Skype for Business Server[](../../deploy/deploy-conferencing/dial-in-conferencing.md)中配置电话拨入式会议[Skype for Business Server。](../../manage/conferencing/conferencing-policies.md)  

## <a name="support-for-enterprise-and-anonymous-users"></a>支持企业用户和匿名用户

电话拨入式会议支持企业用户和匿名用户。 Enterprise用户拥有 Active Directory 域服务凭据，Skype for Business Server拥有其组织内部的帐户。 匿名用户在组织内不具有企业凭据。 在电话拨入式会议上下文中，联盟伙伴组织中使用 PSTN 连接到会议的用户被视为匿名用户。 对于电话拨入式会议（不同于其他环境），联盟用户都未经过身份验证。
  
参加允许拨入访问会议的企业用户或会议主持人拨打一个会议访问号码后，系统会提示他们输入会议 ID。 如果主持人尚未参加会议，则用户可以输入其统一通信 (UC) 分机号（或完整电话号码）和 PIN，或者等待主持人准许其参加会议。 通过只输入其 PIN，会议组织者就可以以主持人身份参加会议。 前端服务器使用完整电话号码或分机号以及 PIN 的组合来唯一地将企业用户映射到其 Active Directory 凭据。 因此，在会议中是按名称对企业用户进行身份验证和标识的。 企业用户还可以担任由组织者预定义的会议角色。
  
> [!NOTE]
> Enterprise从 Office IP 电话或 Skype for Business Server Attendant 拨入的用户不会提示输入其电话号码，因为他们已经过身份验证。 
  
要参加电话拨入式会议的匿名用户拨打一个会议接入号码后，系统会提示他们输入会议 ID。还会提示未经身份验证的匿名用户记录其名称。记录的名称用于在会议中标识未经身份验证的用户。除非至少一个主持人或经过身份验证的用户已参加会议，否则不允许匿名用户参加会议，且无法向其分配预定义角色。
  
> [!NOTE]
> 选择不输入其电话号码和 PIN 的企业用户未经过身份验证。系统会提示他们记录其名称，并在会议中将他们视为匿名用户。 
  
安排会议时，会议组织者可以选择通过关闭或锁定会议来限制对会议的访问。 在这种情况下，将请求拨入用户进行身份验证。 
  
- 如果拨入用户失败或选择不进行身份验证，他们将被转移到会议厅，直到领导接受或拒绝他们，或者他们退出并断开连接。
    
- 在允许他们参加会议后，电话拨入用户可以参与会议的音频部分，并且可以使用电话小键盘执行双音多频 (DTMF) 命令。
    
- 拨入领导可以练习 DTMF 命令，使参与者能够打开或关闭静音、锁定或解锁会议、允许会议厅中的人员加入，以及打开或关闭进入和退出通知。
    
- 领导还可使用 DTMF 命令允许会议厅中的每个人加入会议，这将更改会议权限以允许随后加入的任何人。 
    
- 所有拨入参与者都可以练习 DTMF 命令来收听帮助、收听会议名单和将自己静音。
    
- 电话拨入参与者 (，即是否从 PSTN) 在会议期间听到个人通知，例如是否已静音或取消静音、是否录制会议，或者是否有人正在会议厅中等待。
    
    > [!NOTE]
    > 通过单击链接（而不是电话拨入）参加会议的与会者不会听到个人通知。 
  

