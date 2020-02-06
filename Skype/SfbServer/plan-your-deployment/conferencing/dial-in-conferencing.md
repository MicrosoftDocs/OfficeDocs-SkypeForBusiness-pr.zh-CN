---
title: 在 Skype for business 服务器中规划电话拨入式会议
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
ms.assetid: ea024a26-37b3-410e-961b-83ab85c07540
description: 摘要：阅读本主题，了解如何规划 Skype for Business 服务器中的电话拨入式会议。
ms.openlocfilehash: 90fe1ff1770d34b9fe0671de1a2fc0f9382acae5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815990"
---
# <a name="plan-for-dial-in-conferencing-in-skype-for-business-server"></a>在 Skype for business 服务器中规划电话拨入式会议
 
**摘要：** 阅读本主题，了解如何规划 Skype for Business 服务器中的电话拨入式会议。
  
电话拨入式会议是 Skype for Business 服务器的一项可选功能，允许与会者通过电话拨入会议的音频部分加入会议的音频部分。 电话拨入式会议是音频会议的子集，需要额外的配置。 本主题描述在为组织部署电话拨入式会议之前，需要考虑的事项。 
  
拨入式会议所需的一些组件特定于电话拨入式会议，而有些组件是企业语音组件。 虽然电话拨入式会议使用的某些组件与企业语音使用的组件相同，但是即使未部署企业语音，也可以部署电话拨入式会议。 本节介绍电话拨入式会议所需的组件。 有关规划完整的企业语音解决方案的详细信息，请参阅[在 Skype For Business 服务器中规划企业语音解决方案](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-solution.md)。
  
电话拨入式会议需要您部署中介服务器来提供与公用电话交换网 (PSTN) 的连接。 除了部署中介服务器外，还需要考虑以下几点来为组织实现电话拨入式会议：
  
- 连接公用电话交换网 (PSTN) 的规划
    
- 拨号计划、访问号码以及会议区域的规划
    
- 创建会议目录的规划
    
- 允许拨入访问的会议策略
    
- 支持企业用户和匿名用户
    
> [!NOTE]
> 如果你部署电话拨入式会议，则必须在部署 Skype for Business Server 会议的每个池中部署它。 无需在每个池中分配访问号码（参与者为加入会议而呼叫的号码），但必须在每个池中部署拨入功能。 当用户从一个池中调用访问号码以加入另一个池中的 Skype for Business Server 会议时，此要求支持录制的名称功能。 
  
## <a name="plan-for-pstn-connectivity"></a>规划 PSTN 连接

电话拨入式会议至少需要一台中介服务器和一个公用电话交换网 (PSTN) 网关。 
  
您可以在中央站点或分支站点部署中介服务器。 在中央站点，您可以在前端池或 Standard Edition Server 并置中介服务器，或者将其部署在独立服务器或池中。 在分支站点，您可以将中介服务器部署在独立服务器中或部署为 Survivable Branch Appliance 的组件。
  
您可以在中央站点或分支站点部署 PSTN 网关。在分支站点，PSTN 网关可以是独立的，也可以作为 Survivable Branch Appliance 的组件。
  
有关中介服务器和 PSTN 网关要求的详细信息，请参阅[skype For Business 服务器中的中介服务器组件](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md)、在[Skype for Business Server 的拓扑生成器中部署中介服务器](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md)和在[Skype For business 服务器的拓扑生成器中定义网关](../../deploy/deploy-enterprise-voice/define-a-gateway.md)。
  
## <a name="plan-for-dial-plans-access-numbers-and-conferencing-regions"></a>拨号计划、访问号码以及会议区域的规划

为了配置电话拨入式会议，要创建拨号计划和电话拨入式会议访问号码。还要指定将电话拨入式会议访问号码与其拨号计划相关联的拨入区域。更具体地说：
  
- 拨号计划是几组规范化规则，用来指定电话号码的数字和数字模式，并将电话号码转换为呼叫路由所必需的标准 E.164 格式。
    
- 电话拨入式会议访问号码是参与者为加入会议而呼叫的号码。
    
- 每个电话拨入式会议访问号码必须至少与一个拨号计划关联。 
    
- 每个拨号计划与一个会议区域关联。
    
创建拨号计划时，要指定适用于该拨号计划的电话拨入式会议区域。创建拨入访问号码时，要选择将访问号码与相应的拨号计划相关联的区域。
  
还要指定拨号计划的作用域：用户作用域、池作用域或站点作用域。会按照各用户适用的最小作用域为其分配拨号计划。例如，如果适用，则为用户分配用户级别的拨号计划。如果用户级别的拨号计划不适用，则为用户分配池级别的拨号计划。如果池级别的拨号计划不适用，则为用户分配站点级别的拨号计划。如果站点级别的拨号计划不适用，则为用户分配全局拨号计划。 
  
配置拨号计划之前，规划命名和使用区域的方式非常重要。对于电话拨入式会议区域，请注意下列事项：
  
- 区域通常是与某个办公室或一组办公室相关联的地理区域。
    
- 语言与拨入访问号码相关联。如果支持具有多种语言的地理区域，应该决定如何定义区域以便支持多种语言。例如，可以基于地理位置和语言的组合定义多个区域，或者基于地理位置定义一个区域，且每种语言拥有不同的拨入访问号码。
    
- 用户安排会议时，默认情况下会议将使用用户的拨号计划所指定的区域。
    
- 默认情况下，区域的所有拨入访问号码都会包含在会议邀请中。
    
- 命名区域非常重要，这样就可以清楚地识别这些区域。 用户可以使用区域的名称更改会议的区域，以便邀请中包含不同的访问号码。 （当用户使用 Outlook 安排会议时，用户使用 Skype for business 的联机会议加载项更改区域）。
    
- 应该对区域加以设计，以便想要拨入会议的被邀请者可以在会议邀请中看到本地访问号码。
    
- 你可以通过使用 Skype for Business Server Management Shell cmdlet 来配置区域内的访问号码在 "电话拨入式会议设置" 页面上显示的顺序（并因此而显示在会议邀请中的顺序）。
    
- 任何位置的任何用户均可拨打拨入访问号码来加入会议。
    
有关创建拨号计划的详细信息，请参阅[在 skype For Business 服务器中创建或修改拨号计划](../../deploy/deploy-enterprise-voice/dial-plans.md)，并[在 skype For business 中创建或修改规范化规则](../../deploy/deploy-enterprise-voice/normalization-rules.md)。 
  
## <a name="plan-for-conference-directories"></a>规划会议目录

会议目录在使用 Skype for Business 时，在参与者用于加入会议的字母数字会议 ID 之间保留一个映射，以及电话拨入式会议参与者用于加入会议的仅限数字的会议 ID。 会议 ID 的格式如下：
  
```
<housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>
```

创建多个会议目录将确保会议 ID 将短暂停留，直到创建了大量会议。在每个用户需要参与典型数量会议的组织中，建议您为池中的每 999 个用户创建一个会议目录。使用此指南，通常可使会议 ID 保持较小数目。但是，一旦会议目录的数目（在池中）超过 9，则会议 ID 号将增大以支持其他会议。
  
## <a name="plan-for-a-conferencing-policy-that-allows-dial-in-access"></a>允许拨入访问的会议策略的规划

在配置会议策略时，必须为拨入访问启用会议。 默认情况下，允许拨入访问的会议会在会议邀请中包括以下信息：
  
- 用于标识会议的数字会议 ID
    
- 一个或多个 PSTN 访问号码
    
- 指向“电话拨入式会议设置”页的链接，其中包含有其关联语言的访问号码完整列表；创建、重置或解锁个人标识号 (PIN) 的位置；以及其他信息，例如，双音多频 (DTMF) 控制
    
有关会议策略的详细信息，请参阅在 skype for [Business 服务器中配置拨入式会议](../../deploy/deploy-conferencing/dial-in-conferencing.md)和[管理 Skype for business 服务器中的会议策略](../../manage/conferencing/conferencing-policies.md)。  

## <a name="support-for-enterprise-and-anonymous-users"></a>支持企业用户和匿名用户

电话拨入式会议支持企业用户和匿名用户。 企业用户在其组织内具有 Active Directory 域服务凭据和 Skype for business 服务器帐户。 匿名用户在组织内不具有企业凭据。 在拨入式会议环境中，联盟伙伴的组织中使用 PSTN 连接到会议的用户被视为匿名用户。 对于电话拨入式会议（不同于其他环境），联盟用户都未经过身份验证。
  
参加允许拨入访问会议的企业用户或会议主持人拨打一个会议访问号码后，系统会提示他们输入会议 ID。如果主持人尚未参加会议，则用户可以输入其统一通信 (UC) 分机号（或完整电话号码）和 PIN，或者等待主持人准许其参加会议。通过只输入其 PIN，会议组织者就可以以主持人身份参加会议。前端服务器使用完整电话号码或分机号与 PIN 的组合唯一地将企业用户映射到其 Active Directory 凭据。因此，在会议中是按名称对企业用户进行身份验证和标识的。企业用户还可以担任由组织者预定义的会议角色。
  
> [!NOTE]
> 通过 office IP 手机或 Skype for Business 服务器助理拨入的企业用户将不会收到其电话号码的提示，因为他们已经过身份验证。 
  
要参加电话拨入式会议的匿名用户拨打一个会议接入号码后，系统会提示他们输入会议 ID。还会提示未经身份验证的匿名用户记录其名称。记录的名称用于在会议中标识未经身份验证的用户。除非至少一个主持人或经过身份验证的用户已参加会议，否则不允许匿名用户参加会议，且无法向其分配预定义角色。
  
> [!NOTE]
> 选择不输入其电话号码和 PIN 的企业用户未经过身份验证。系统会提示他们记录其名称，并在会议中将他们视为匿名用户。 
  
安排会议时，会议组织者可选择关闭或锁定会议来限制访问会议。这种情况下，会请求拨入用户进行身份验证。 
  
- 如果拨入用户身份验证失败或选择不进行身份验证，他们会被转移到会议厅中等待，直到主持人接受或拒绝他们，或者连接超时并断开连接。
    
- 一旦被允许加入会议，电话拨入用户就可以参与会议的音频部分，并可使用电话键盘执行双音多频 (DTMF) 命令。
    
- 电话拨入主持人可以使用 DTMF 命令打开或关闭参与者的取消静音功能、锁定或解锁会议、允许会议厅中的人加入会议、打开或关闭进入和退出通知。
    
- 主持人还可以使用 DTMF 命令允许会议厅中的每个人加入会议，从而更改会议的权限以允许随后的任何人加入会议。 
    
- 所有电话拨入参与者都可以使用 DTMF 命令收听帮助，收听会议名单，以及使自己静音。
    
- 电话拨入参与者（即，无论他们是否从 PSTN 拨号）在会议期间收听个人通知，例如，是否已将其静音或取消静音，是否记录会议，或者是否有人在会议厅中等待。
    
    > [!NOTE]
    > 通过单击链接（而不是电话拨入）参加会议的与会者不会听到个人通知。 
  

