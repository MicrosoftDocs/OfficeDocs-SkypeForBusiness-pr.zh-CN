---
title: Skype 业务服务器中的架构更改
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: 在部署和操作 Skype 业务服务器之前，您必须通过扩展架构准备 Active Directory 域服务。 架构扩展添加的类和 Skype 业务服务器所需的属性。
ms.openlocfilehash: 8594ff3a25c7af7ef8c57468a8900d3abbb7f790
ms.sourcegitcommit: 1ad4120af98240f1b54c0ca18286598b289a97f1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2018
ms.locfileid: "27240915"
---
# <a name="schema-changes-in-skype-for-business-server"></a>Skype 业务服务器中的架构更改
 
在部署和操作 Skype 业务服务器之前，您必须通过扩展架构准备 Active Directory 域服务。 架构扩展添加的类和 Skype 业务服务器所需的属性。

> [!NOTE]
> 如果您要为业务服务器 2015年来升级到 Skype 从 Lync Server 2013，不架构更改，因此这篇文章不适用于。
  
Skype 业务服务器需要多个新类和属性，并修改某些现有类和属性。 此外，多的 Skype 业务服务器的配置信息存储在 AD DS 中而不是中央管理存储中早期版本中。 以下信息仍 Skype 中的 AD DS 中存储的业务服务器：
  
- **架构扩展**：
    
  - 用户对象扩展
    
  - 用于维护与支持的 Lync Server 的早期版本向后兼容的类的扩展。
    
- **数据**（存储在 Skype Business Server 扩展架构和现有架构类中）：
    
  - 用户 SIP 统一资源标识符 (URI) 和其他用户设置
    
  - 例如，响应组和会议助理应用程序的联系对象
    
  - 指向中央管理存储的指针
    
  - Kerberos 身份验证帐户 （可选计算机对象）
    
本主题介绍 Skype 业务服务器所需的 Active Directory 架构更改。 它不介绍引入由早期版本的 Office Communications Server 的架构更改。 类及其说明的列表，请参阅[架构类和 Skype 业务服务器中的说明](schema-classes-and-descriptions.md)。 有关属性及其说明的列表，请参阅[架构属性和 Skype 业务服务器中的说明](schema-attributes-and-descriptions.md)。 类的属性的列表，它们可能包含，请参阅[Skype 业务服务器中的类的架构属性](schema-attributes-by-class.md)。
  
MsRTCSIP 前缀标识类和特定于 Skype 业务服务器的属性。
  
## <a name="new-active-directory-attributes"></a>新的 Active Directory 属性

下表介绍由 Skype 业务服务器添加的 Active Directory 属性。
  
**由 Skype 添加业务服务器的属性**

|**属性**|**说明**|
|:-----|:-----|
|msExchUserHoldPolicies  <br/> |此多值属性包含标识符保留应用于用户的策略。 保留策略保留的持续时间内保留用户的邮箱项目。 此属性与 Exchange 2013 共享。  <br/> |
|msRTCSIP UserRoutingGroupId  <br/> |这是 SIP 路由组 id。 同一组中的用户将注册到同一个前端服务器。  <br/> |
|msRTCSIP MirrorBackEndServer  <br/> |此属性用于存储的前端池使用的镜像的 SQL Server 后端。  <br/> |
   
## <a name="modified-active-directory-classes"></a>已修改的 Active Directory 类

下表介绍由 Skype 修改业务服务器的 Active Directory 类。
  
**为业务 Server 由 Skype 修改的类**

|**类**|**更改**|**类或属性**|
|:-----|:-----|:-----|
|用户  <br/> |添加： mayContain  <br/> 添加： mayContain  <br/> |ProxyAddresses  <br/> msRTCSIP UserRoutingGroupId  <br/> |
|联系人  <br/> |添加： mayContain  <br/> 添加： mayContain  <br/> |ProxyAddresses  <br/> msRTCSIP UserRoutingGroupId  <br/> |
|邮件收件人  <br/> |添加： mayContain  <br/> |msExchUserHoldPolicies  <br/> |
|msRTCSIP GlobalTopologySetting  <br/> |添加： mayContain  <br/> |msRTCSIP MirrorBackEndServer  <br/> |
   

