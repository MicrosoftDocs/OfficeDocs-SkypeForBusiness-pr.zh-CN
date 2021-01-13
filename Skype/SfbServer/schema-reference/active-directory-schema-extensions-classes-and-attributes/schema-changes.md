---
title: Skype for Business Server 中的架构更改
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
localization_priority: Normal
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: 在部署和运行 Skype for Business Server 之前，必须通过扩展架构来准备 Active Directory 域服务。 架构扩展将添加 Skype for Business Server 所需的类和属性。
ms.openlocfilehash: 4ca18b0ccfde6b247f1c29e140004804462d0f56
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813572"
---
# <a name="schema-changes-in-skype-for-business-server"></a>Skype for Business Server 中的架构更改
 
在部署和运行 Skype for Business Server 之前，必须通过扩展架构来准备 Active Directory 域服务。 架构扩展将添加 Skype for Business Server 所需的类和属性。

> [!NOTE]
> 如果要从 Lync Server 2013 升级到 Skype for Business Server 2015，则不进行架构更改，因此本文不适用。
  
Skype for Business Server 需要几个新的类和属性，并修改一些现有的类和属性。 此外，Skype for Business Server 的很多配置信息都存储在中央管理存储中，而不是像以前版本一样存储在 AD DS 中。 以下信息仍存储在 Skype for Business Server 中的 AD DS 中：
  
- **架构扩展**：
    
  - 用户对象扩展
    
  - 用于维护与受支持的早期版本的 Lync Server 的向后兼容性的类扩展。
    
- **数据存储** (Skype for Business Server 扩展架构和现有架构类) ：
    
  - 用户 SIP 统一资源标识符 (URI) 和其他用户设置
    
  - 应用程序（如响应组和会议助理）的联系人对象
    
  - 指向中央管理存储的指针
    
  - Kerberos 身份验证帐户（可选计算机对象）
    
本主题介绍 Skype for Business Server 所需的 Active Directory 架构更改。 它未介绍 Office Communications Server 早期版本引入的架构更改。 有关类及其说明的列表，请参阅 Skype for Business Server 中的架构 [类和说明](schema-classes-and-descriptions.md)。 有关属性及其说明的列表，请参阅 Skype for Business Server 中的架构属性 [和说明](schema-attributes-and-descriptions.md)。 有关包含其可能包含的属性的类的列表，请参阅 Skype for Business Server 中按 [类分类的架构属性](schema-attributes-by-class.md)。
  
msRTCSIP 前缀标识特定于 Skype for Business Server 的类和属性。
  
## <a name="new-active-directory-attributes"></a>新增 Active Directory 属性

下表介绍了由 Skype for Business Server 添加的 Active Directory 属性。
  
**由 Skype for Business Server 添加的属性**

|**属性**|**说明**|
|:-----|:-----|
|msExchUserHoldPolicies  <br/> |此多值属性可保存应用于用户的保留策略的标识符。 保留策略会在保留持续时间内保留用户的邮箱项目。 此属性与 Exchange 2013 共享。  <br/> |
|msRTCSIP-UserRoutingGroupId  <br/> |这是 SIP 路由组 ID。同一组中的用户将注册到同一前端服务器。  <br/> |
|msRTCSIP-MirrorBackEndServer  <br/> |此属性用于存储前端池SQL Server后端的镜像池。  <br/> |
   
## <a name="modified-active-directory-classes"></a>修改的 Active Directory 类

下表介绍了由 Skype for Business Server 修改的 Active Directory 类。
  
**由 Skype for Business Server 修改的类**

|**类**|**更改**|**类或属性**|
|:-----|:-----|:-----|
|用户  <br/> |add:mayContain  <br/> add:mayContain  <br/> |ProxyAddresses  <br/> msRTCSIP-UserRoutingGroupId  <br/> |
|Contact  <br/> |add:mayContain  <br/> add:mayContain  <br/> |ProxyAddresses  <br/> msRTCSIP-UserRoutingGroupId  <br/> |
|Mail-Recipient  <br/> |add:mayContain  <br/> |msExchUserHoldPolicies  <br/> |
|msRTCSIP-GlobalTopologySetting  <br/> |add:mayContain  <br/> |msRTCSIP-MirrorBackEndServer  <br/> |
   

