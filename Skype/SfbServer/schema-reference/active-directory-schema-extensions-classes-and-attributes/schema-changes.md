---
title: 架构中的架构Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: 在部署和运行 Skype for Business Server，必须通过扩展架构来准备 Active Directory 域服务。 架构扩展添加用户所需的类和Skype for Business Server。
ms.openlocfilehash: 16f71b80864fae8fc97b87eda22ad2a9594c3987
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58626534"
---
# <a name="schema-changes-in-skype-for-business-server"></a>架构中的架构Skype for Business Server
 
在部署和运行 Skype for Business Server，必须通过扩展架构来准备 Active Directory 域服务。 架构扩展添加用户所需的类和Skype for Business Server。

> [!NOTE]
> 如果要从 Lync Server 2013 升级到 Skype for Business Server 2015，将不会进行架构更改，因此本文不适用。
  
Skype for Business Server需要几个新的类和属性，并修改一些现有的类和属性。 此外，与以前版本一样，Skype for Business Server管理存储（而不是 AD DS）中存储有关该策略的很多配置信息。 以下信息仍存储在 AD DS 中的 Skype for Business Server：
  
- **架构扩展**：
    
  - 用户对象扩展
    
  - 用于保持与支持的以前版本的 Lync Server 的向后兼容性的类扩展。
    
- **存储在** (扩展架构Skype for Business Server现有架构类中存储的数据) ：
    
  - 用户 SIP 统一资源标识符 (URI) 和其他用户设置
    
  - 应用程序（如响应组和会议助理）的联系人对象
    
  - 指向中央管理存储的指针
    
  - Kerberos 身份验证帐户（可选计算机对象）
    
本主题介绍 Active Directory 架构更改Skype for Business Server。 它不介绍早期版本的 Communications Server 引入的Office更改。 有关类及其说明的列表，请参阅架构类和[Skype for Business Server。](schema-classes-and-descriptions.md) 有关属性及其说明的列表，请参阅架构[属性和Skype for Business Server。](schema-attributes-and-descriptions.md) 有关包含其可能包含的属性的类的列表，请参阅 Schema [attributes by class in Skype for Business Server](schema-attributes-by-class.md)。
  
msRTCSIP 前缀标识特定于 Skype for Business Server 的类和Skype for Business Server。
  
## <a name="new-active-directory-attributes"></a>新增 Active Directory 属性

下表介绍了由 Skype for Business Server 添加的 Active Directory 属性。
  
**由 Skype for Business Server**

|**属性**|**说明**|
|:-----|:-----|
|msExchUserHoldPolicies  <br/> |此多值属性可保存应用于用户的保留策略的标识符。 保留策略会在保留持续时间内保留用户的邮箱项目。 此属性与 Exchange 2013 共享。  <br/> |
|msRTCSIP-UserRoutingGroupId  <br/> |这是 SIP 路由组 ID。同一组中的用户将注册到同一前端服务器。  <br/> |
|msRTCSIP-MirrorBackEndServer  <br/> |此属性用于存储前端池SQL Server镜像的后端。  <br/> |
   
## <a name="modified-active-directory-classes"></a>修改的 Active Directory 类

下表介绍了由 Skype for Business Server 修改的 Active Directory 类。
  
**由用户修改Skype for Business Server**

|**类**|**更改**|**类或属性**|
|:-----|:-----|:-----|
|用户  <br/> |add:mayContain  <br/> add:mayContain  <br/> |ProxyAddresses  <br/> msRTCSIP-UserRoutingGroupId  <br/> |
|联系人  <br/> |add:mayContain  <br/> add:mayContain  <br/> |ProxyAddresses  <br/> msRTCSIP-UserRoutingGroupId  <br/> |
|Mail-Recipient  <br/> |add:mayContain  <br/> |msExchUserHoldPolicies  <br/> |
|msRTCSIP-GlobalTopologySetting  <br/> |add:mayContain  <br/> |msRTCSIP-MirrorBackEndServer  <br/> |
   

