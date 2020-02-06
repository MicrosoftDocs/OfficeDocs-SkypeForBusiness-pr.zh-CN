---
title: Skype for Business 服务器中的架构更改
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d760cb93-77d4-4d64-adb7-416b808f36f8
description: 在部署和操作 Skype for Business 服务器之前，必须通过扩展架构来准备 Active Directory 域服务。 架构扩展添加 Skype for Business 服务器所需的类和属性。
ms.openlocfilehash: 0c3765fe36b252cc03218a3fa4365c5cc36c7f48
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815480"
---
# <a name="schema-changes-in-skype-for-business-server"></a>Skype for Business 服务器中的架构更改
 
在部署和操作 Skype for Business 服务器之前，必须通过扩展架构来准备 Active Directory 域服务。 架构扩展添加 Skype for Business 服务器所需的类和属性。

> [!NOTE]
> 如果要从 Lync Server 2013 升级到 Skype for business Server 2015，则不会进行任何架构更改，因此本文不适用。
  
Skype for business 服务器需要多个新的类和属性，并修改一些现有的类和属性。 此外，Skype for business 服务器的许多配置信息存储在中央管理存储中，而不是在 AD DS 中，就像在以前的版本中一样。 以下信息仍存储在 Skype for business Server 的 AD DS 中：
  
- **架构扩展**：
    
  - 用户对象扩展
    
  - 用于维护与受支持的早期版本 Lync Server 的向后兼容性的类扩展。
    
- **数据**（存储在 Skype For business 服务器扩展架构和现有架构类中）：
    
  - 用户 SIP 统一资源标识符（URI）和其他用户设置
    
  - 响应组和会议助理等应用程序的联系人对象
    
  - 指向中央管理存储的指针
    
  - Kerberos 身份验证帐户（可选计算机对象）
    
本主题介绍了 Skype for Business 服务器所需的 Active Directory 架构更改。 它不会描述以前版本的 Office 通信服务器引入的架构更改。 有关类及其说明的列表，请参阅[Skype For Business 服务器中的架构类和说明](schema-classes-and-descriptions.md)。 有关属性及其说明的列表，请参阅[Skype For Business 服务器中的架构属性和说明](schema-attributes-and-descriptions.md)。 有关它们可能包含的属性的类的列表，请参阅[Skype For Business 服务器中按类列出的架构属性](schema-attributes-by-class.md)。
  
MsRTCSIP 前缀标识特定于 Skype for Business 服务器的类和属性。
  
## <a name="new-active-directory-attributes"></a>新的 Active Directory 属性

下表介绍了由 Skype for Business 服务器添加的 Active Directory 属性。
  
**Skype for Business 服务器添加的属性**

|**属性**|**说明**|
|:-----|:-----|
|msExchUserHoldPolicies  <br/> |此多值属性包含适用于用户的保留策略的标识符。 保留策略在保留期间保留用户的邮箱项目。 此属性是与 Exchange 2013 共享的。  <br/> |
|msRTCSIP-UserRoutingGroupId  <br/> |这是 SIP 路由组 ID。 同一组中的用户将注册到同一前端服务器。  <br/> |
|msRTCSIP-MirrorBackEndServer  <br/> |此属性用于存储前端池使用的镜像 SQL Server 后端。  <br/> |
   
## <a name="modified-active-directory-classes"></a>已修改的 Active Directory 类

下表介绍了由 Skype for Business Server 修改的 Active Directory 类。
  
**Skype for Business Server 修改的类**

|**种类**|**更改**|**类或属性**|
|:-----|:-----|:-----|
|用户  <br/> |add： mayContain  <br/> add： mayContain  <br/> |ProxyAddresses  <br/> msRTCSIP-UserRoutingGroupId  <br/> |
|联系人  <br/> |add： mayContain  <br/> add： mayContain  <br/> |ProxyAddresses  <br/> msRTCSIP-UserRoutingGroupId  <br/> |
|邮件-收件人  <br/> |add： mayContain  <br/> |msExchUserHoldPolicies  <br/> |
|msRTCSIP-GlobalTopologySetting  <br/> |add： mayContain  <br/> |msRTCSIP-MirrorBackEndServer  <br/> |
   

