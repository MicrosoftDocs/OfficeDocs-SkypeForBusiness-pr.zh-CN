---
title: 在 Skype 业务服务器的架构更改
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: 在部署和运行 Skype 业务服务器之前，您必须通过扩展架构准备 Active Directory 域服务。 架构扩展添加的类和属性所需的 Skype 业务服务器。
ms.openlocfilehash: 42b4417311c557323535aa03053ccb03d95cc840
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="schema-changes-in-skype-for-business-server"></a>在 Skype 业务服务器的架构更改
 
在部署和运行 Skype 业务服务器之前，您必须通过扩展架构准备 Active Directory 域服务。 架构扩展添加的类和属性所需的 Skype 业务服务器。 
  
Skype 业务服务器需要多个新类和属性和修改一些现有的类和属性。 此外，多为 Skype 业务服务器的配置信息存储在 AD DS 中而不是中央管理存储以前版本中。 以下信息仍在 Skype 在 AD DS 中存储业务服务器：
  
- **架构扩展**：
    
  - 用户对象扩展
    
  - 类维护向后兼容 Lync Server 支持以前版本的扩展。
    
- **数据**（存储在业务服务器扩展架构的 Skype 和现有架构类）：
    
  - 用户的 SIP 统一资源标识符 (URI) 和其他用户设置
    
  - 联系人对象的应用程序响应组和会议助理等
    
  - 一个指针，指向中央管理存储
    
  - Kerberos 身份验证帐户 （可选计算机对象）
    
本主题介绍通过 Skype 所需业务服务器的 Active Directory 架构变化。 它不描述引入的以前版本的 Office 通信服务器的架构更改。 类及其说明的列表，请参阅[架构类和 Skype 业务服务器中的说明](schema-classes-and-descriptions.md)。 有关属性及其说明的列表，请参阅[架构属性和 Skype 业务服务器中的说明](schema-attributes-and-descriptions.md)。 具有属性的类的列表，它们可能包含，请参阅[通过 Skype 业务服务器中类的架构属性](schema-attributes-by-class.md)。
  
MsRTCSIP 前缀标识类别和特定于 Skype 业务服务器的属性。
  
## <a name="new-active-directory-attributes"></a>新的活动目录属性

下表介绍了通过 Skype 来添加业务服务器的 Active Directory 特性。
  
**添加通过 Skype 业务服务器的属性**

|**属性**|**说明**|
|:-----|:-----|
|msExchUserHoldPolicies  <br/> |此多值属性包含标识符的保留适用于用户的策略。 保留策略的暂停的持续时间内保留该用户的邮箱项目。 此属性是与 Exchange 2013 共享。  <br/> |
|msRTCSIP UserRoutingGroupId  <br/> |这是 SIP 路由组 id。 同一组中的用户将注册到同一前端服务器。  <br/> |
|msRTCSIP MirrorBackEndServer  <br/> |此属性用于存储镜像的 SQL Server 后端前端池使用。  <br/> |
   
## <a name="modified-active-directory-classes"></a>修改后的 Active Directory 类

下表描述了通过 Skype 修改的业务服务器的 Active Directory 类。
  
**通过 Skype 修改的业务服务器的类**

|**类**|**更改**|**类或属性**|
|:-----|:-----|:-----|
|用户  <br/> |添加： mayContain  <br/> 添加： mayContain  <br/> |代理地址  <br/> msRTCSIP UserRoutingGroupId  <br/> |
|联系人  <br/> |添加： mayContain  <br/> 添加： mayContain  <br/> |代理地址  <br/> msRTCSIP UserRoutingGroupId  <br/> |
|邮件收件人  <br/> |添加： mayContain  <br/> |msExchUserHoldPolicies  <br/> |
|msRTCSIP GlobalTopologySetting  <br/> |添加： mayContain  <br/> |msRTCSIP MirrorBackEndServer  <br/> |
   

