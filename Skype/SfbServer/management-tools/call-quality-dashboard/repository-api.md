---
title: 通话质量仪表板 (CQD) API Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: d53e990f-1c5f-46d1-9eb1-8396782c2753
description: 摘要：了解通话质量仪表板的存储库 API。 通话质量仪表板是一种用于Skype for Business Server。
ms.openlocfilehash: 21765c4766e7fc729988f2b8ba23241175a96584
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60759694"
---
# <a name="repository-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>通话质量仪表板 (CQD) API Skype for Business Server
 
**摘要：** 了解通话质量仪表板存储库 API。 通话质量仪表板是一种用于Skype for Business Server。
  
存储库 API 为呼叫质量仪表板提供了对呼叫质量仪表板的编程Skype for Business Server。
  
## <a name="repository-api-for-call-quality-dashboard"></a>通话质量仪表板存储库 API

存储库 API 提供存储库数据库的数据访问接口。 存储库允许内容在树或图形结构中进行组织，以便用户可以按用户有意义的方式进行分组。 存储库支持两种常规类型的用户：系统用户（表示存储库的内置用户）和代表存储库授权用户的常规用户。
  
存储库 API 包含三个常规服务： 
  
- [用于 CQD 的用户服务](user-service.md) - 用于访问用户。
    
- [呼叫质量仪表板项目服务 (CQD) ](item-service.md) - 用于访问项目和存储于"项目"中的内容。
    
- [通话设置仪表板的用户服务 (CQD](user-settings-service.md)) - 用于访问设置。
    
通话质量仪表板使用存储库 API 管理以下信息： 
  
- **User** - 有权访问存储库的用户的表示形式。
    
- **Report** - 包含查询列表，以内容存储在存储库项中。
    
- **Query** - 用于从数据 API 检索数据，以内容存储在存储库项中。
    
- **用户设置** - 描述用户的可选应用程序行为。
    
  **跨源资源共享 (CORS) 存储库 API 支持**
  
存储库 API 支持跨源资源共享 (CORS) 。 CORS 是一项 HTTP 功能，它使在一个域下运行的 Web 应用程序可以访问另一个域中的资源。 Web 浏览器实现一个称为同源 [策略](https://www.w3.org/Security/wiki/Same_Origin_Policy) 同源策略的安全限制，阻止网页调用其他域中的 API。 CORS 提供了一种安全的方法，允许源域 (一个) 域中调用 API。 有关 [CORS 的详细信息，请参阅 CORS](https://www.w3.org/TR/cors/) 规范。
  
 **为存储库 API 启用 CORS**
  
 下面摘录了存储库 API 应用程序，web.config corsTrustedOrigin 应用程序设置中列出的两个域。 从这些服务器加载的脚本提出的所有请求都受存储库 API 信任。
  
请记住包含确切的协议、主机名和端口 (（如果有) ）。 不要将任何正斜杠字符 (/) 末尾。 可以通过用逗号分隔来指定多个条目。
  
```xml
<repositoryConfiguration>
    <service corsTrustedOrigin="https://<trusted-server>,http://<another-trusted-domain>:8080"" />
    <diagnostics eventLevel="Verbose" systemLoggedEventLevel="Error">
      <traceLog enabled="true" fileName="repository_trace.log" />
    </diagnostics>
 </repositoryConfiguration>
```


