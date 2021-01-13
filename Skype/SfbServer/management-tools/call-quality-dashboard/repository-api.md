---
title: Skype for Business Server 中用于呼叫质量仪表板 (CQD) API
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d53e990f-1c5f-46d1-9eb1-8396782c2753
description: 摘要：了解用于通话质量仪表板的存储库 API。 通话质量仪表板是 Skype for Business Server 的工具。
ms.openlocfilehash: 982ec0932f0a57958e1929a6ae2413ada0b5c9fa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803122"
---
# <a name="repository-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>Skype for Business Server 中用于呼叫质量仪表板 (CQD) API
 
**摘要：** 了解用于通话质量仪表板的存储库 API。 通话质量仪表板是 Skype for Business Server 的工具。
  
存储库 API 为 Skype for Business Server 的呼叫质量仪表板提供编程访问。
  
## <a name="repository-api-for-call-quality-dashboard"></a>用于通话质量仪表板的存储库 API

存储库 API 提供存储库数据库的数据访问接口。 存储库允许将内容组织在树或图形结构中，以便用户可以按照对用户有意义的方式对内容进行分组。 存储库支持两种常规类型的用户：系统用户（表示存储库的内置用户）和代表存储库的授权用户的常规用户。
  
存储库 API 由三种常规服务组成： 
  
- [用于 CQD 的用户服务](user-service.md) - 用于访问用户。
    
- [呼叫质量仪表板项目服务 (CQD) ](item-service.md) - 用于访问项目和存储在项中的内容。
    
- [呼叫质量仪表板的用户设置服务 (CQD) ](user-settings-service.md) - 用于访问用户设置。
    
通话质量仪表板使用存储库 API 管理以下信息： 
  
- **用户** - 有权访问存储库的用户的表示形式。
    
- **Report** - 包含查询列表，以内容存储在存储库项中。
    
- **查询** - 用于从数据 API 检索数据，以内容存储在存储库项中。
    
- **用户设置** - 描述用户的可选应用程序行为。
    
  **跨源资源共享 (CORS) 存储库 API 支持**
  
存储库 API 支持跨源资源共享 (CORS) 。 CORS 是一项 HTTP 功能，它使运行在一个域下的 Web 应用程序能够访问另一个域中的资源。 Web 浏览器实现一种安全限制，称为 [同](https://www.w3.org/Security/wiki/Same_Origin_Policy) 源策略同源策略，可防止网页调用不同域中的 API。 CORS 提供了一种安全方法，允许一个 (源域) 调用另一个域中的 API。 有关 [CORS 的详细信息，请参阅 CORS](https://www.w3.org/TR/cors/) 规范。
  
 **为存储库 API 启用 CORS**
  
 下面摘录了存储库 API web.config，显示了 corsTrustedOrigin 应用程序设置中列出的两个域。 从这些服务器加载的脚本提出的所有请求都受存储库 API 信任。
  
请记住包含确切的协议、主机名和端口 (（如果有) ）。 请勿将 / (/) 放在末尾。 可以通过用逗号分隔来指定多个条目。
  
```xml
<repositoryConfiguration>
    <service corsTrustedOrigin="https://<trusted-server>,http://<another-trusted-domain>:8080"" />
    <diagnostics eventLevel="Verbose" systemLoggedEventLevel="Error">
      <traceLog enabled="true" fileName="repository_trace.log" />
    </diagnostics>
 </repositoryConfiguration>
```


