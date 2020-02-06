---
title: Skype for Business Server 中的呼叫质量仪表板（CQD）的知识库 API
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d53e990f-1c5f-46d1-9eb1-8396782c2753
description: 摘要：了解呼叫质量仪表板的知识库 API。 通话质量仪表板是 Skype for business 服务器的工具。
ms.openlocfilehash: a027cc7402bad7524343391f9bf7039dd077a46c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816691"
---
# <a name="repository-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>Skype for Business Server 中的呼叫质量仪表板（CQD）的知识库 API
 
**摘要：** 了解 "呼叫质量" 仪表板的知识库 API。 通话质量仪表板是 Skype for business 服务器的工具。
  
存储库 API 提供对 Skype for Business 服务器的呼叫质量仪表板的编程访问。
  
## <a name="repository-api-for-call-quality-dashboard"></a>呼叫质量仪表板的知识库 API

知识库 API 为知识库数据库提供数据访问接口。 存储库允许内容按树或图形结构进行组织，以便用户可以按照对用户有意义的方式对其进行分组。 存储库支持两种常规类型的用户：系统用户（即表示存储库的内置用户），以及表示存储库的授权用户的常规用户。
  
存储库 API 包括三个常规服务： 
  
- [CQD 用户服务](user-service.md)-用于访问用户。
    
- [通话质量仪表板（CQD）的项目服务](item-service.md)-用于访问项目和存储在项目中的内容。
    
- [呼叫质量仪表板（CQD）的用户设置服务](user-settings-service.md)-用于访问用户设置。
    
通话质量仪表板使用知识库 API 管理以下信息： 
  
- **用户**可访问存储库的用户的表示形式。
    
- **报表**-包含查询的列表，该列表存储为存储库项目中的内容。
    
- **查询**-用于从数据 API 检索数据，这些数据存储为存储库项目中的内容。
    
- **用户设置**-描述用户的可选应用程序行为。
    
  **存储库 API 的跨源资源共享（CORS）支持**
  
存储库 API 支持跨源资源共享（CORS）。 CORS 是一种 HTTP 功能，可使在一个域下运行的 web 应用程序访问其他域中的资源。 Web 浏览器实现了一个称为[相同源策略](https://www.w3.org/Security/wiki/Same_Origin_Policy)的安全限制，该策略可防止网页调用其他域中的 api。 CORS 提供一种安全的方法，允许一个域（原始域）调用另一个域中的 Api。 有关 CORS 的详细信息，请参阅[cors 规范](https://www.w3.org/TR/cors/)。
  
 **为存储库 API 启用 CORS**
  
 下面是知识库 API web.config 的节选内容，显示了 corsTrustedOrigin 应用程序设置中列出的两个域。 从这些服务器加载的脚本发出的所有请求均受存储库 API 的信任。
  
切记要包括确切的协议、主机名和端口（如果有）。 不要在结尾处放置任何正斜杠字符（/）。 可以通过使用逗号分隔来指定多个条目。
  
```
<repositoryConfiguration>
    <service corsTrustedOrigin="https://<trusted-server>,http://<another-trusted-domain>:8080"" />
    <diagnostics eventLevel="Verbose" systemLoggedEventLevel="Error">
      <traceLog enabled="true" fileName="repository_trace.log" />
    </diagnostics>
 </repositoryConfiguration>
```


