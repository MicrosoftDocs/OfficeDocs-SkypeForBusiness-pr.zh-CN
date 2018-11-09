---
title: 呼叫质量仪表板 (CQD) 中的业务服务器 Skype 的库 API
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d53e990f-1c5f-46d1-9eb1-8396782c2753
description: 摘要： 了解呼叫质量仪表板的存储库 API。 呼叫质量仪表板是用于业务服务器 Skype 的工具。
ms.openlocfilehash: de933063e5768b12af5ae8dc678ec7aa2da5f168
ms.sourcegitcommit: b680505c5dad435d98fbd0b235e0e7c67b9d8c9c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2018
ms.locfileid: "26035553"
---
# <a name="repository-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>呼叫质量仪表板 (CQD) 中的业务服务器 Skype 的库 API
 
**摘要：** 对于呼叫质量的仪表板，请了解库 API。 呼叫质量仪表板是用于业务服务器 Skype 的工具。
  
存储库 API 提供编程访问呼叫质量仪表板的 Skype 业务服务器。
  
## <a name="repository-api-for-call-quality-dashboard"></a>呼叫质量仪表板的库 API

存储库 API 提供了一个数据访问接口到存储库数据库。 存储库中允许的内容，以便用户可以将它们组合中对用户有意义的方式来组织树或图结构中。 存储库支持两种常规用户： 系统的用户，即表示存储库，内置用户与表示存储库的授权的用户的常规用户。
  
存储库 API 包含三个常规服务： 
  
- [用户服务 CQD](user-service.md) -用于访问用户。
    
- [项服务的呼叫质量仪表板 (CQD)](item-service.md) -用于访问项目和存储在项目中的内容。
    
- [用户设置服务的呼叫质量仪表板 (CQD)](user-settings-service.md) -用于访问用户设置。
    
呼叫质量仪表板使用存储库 API 来管理的以下信息： 
  
- **用户**-表示形式到存储库具有访问权的用户。
    
- **报表**-包含查询，作为存储库项目中的内容存储的列表。
    
- **查询**-用于检索数据 API，作为存储库项目中的内容存储中的数据。
    
- **用户设置**-介绍用户可选的应用程序行为。
    
  **跨源资源共享 (CORS) 库 API 支持**
  
存储库 API 支持跨源资源共享 (CORS)。 CORS 是 HTTP 功能，使运行下一个域的 web 应用程序以访问其他域中的资源。 Web 浏览器实现称为阻止从不同域中的调用 Api 网页的[同源策略](https://www.w3.org/Security/wiki/Same_Origin_Policy)同源策略的安全限制。 CORS 提供安全的方式，以允许一个域 （原点而言的） 来调用其他域中的 Api。 请参阅 CORS [CORS 规范](https://www.w3.org/TR/cors/)的详细信息。
  
 **启用库 API 的 CORS**
  
 下面是摘录存储库 API web.config，显示 corsTrustedOrigin 应用程序设置中列出的两个域。 通过从这些服务器中加载脚本所做的所有请求都受信任库 API。
  
请记住要包含的确切协议、 主机名和端口 （如果有）。 不将任何反斜杠 （/） 字符末尾。 通过用逗号分隔，可以指定多个条目。
  
```
<repositoryConfiguration>
    <service corsTrustedOrigin="https://<trusted-server>,http://<another-trusted-domain>:8080"" />
    <diagnostics eventLevel="Verbose" systemLoggedEventLevel="Error">
      <traceLog enabled="true" fileName="repository_trace.log" />
    </diagnostics>
 </repositoryConfiguration>
```


