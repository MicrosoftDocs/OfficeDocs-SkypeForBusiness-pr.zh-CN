---
title: 知识库 API 呼叫质量仪表板 (CQD) 在 Skype 业务服务器 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d53e990f-1c5f-46d1-9eb1-8396782c2753
description: 摘要： 了解关于存储库 API 呼叫质量仪表板。 通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。
ms.openlocfilehash: 0f84e3967bd4f78f8852dbcfed8ce5d59cbe4e8c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="repository-api-for-call-quality-dashboard-cqd-in-skype-for-business-server-2015"></a>知识库 API 呼叫质量仪表板 (CQD) 在 Skype 业务服务器 2015
 
**摘要：**请查阅知识库 API 呼叫质量仪表板。 通话质量仪表板是用于业务服务器 2015年的 Skype 的工具。
  
知识库 API 提供编程访问调用质量仪表板为 Skype 业务服务器 2015年个。
  
## <a name="repository-api-for-call-quality-dashboard"></a>知识库 API 呼叫质量仪表板

知识库 API 提供对知识库数据库的数据访问接口。 存储库可以树或图结构中，使用户可以将它们分组到对用户有意义的方式组织内容。 存储库中支持两种一般类型的用户： 系统用户，它是内置用户表示存储库中，并表示存储库中的授权的用户的一般用户。
  
知识库 API 包含三个常规服务： 
  
- [CQD 的用户服务](user-service.md)的访问用户。
    
- [项目服务呼叫质量仪表板 (CQD)](item-service.md) -用于访问项目和项中存储的内容。
    
- [用户设置服务呼叫质量仪表板 (CQD)](user-settings-service.md) -用于访问用户设置。
    
通话质量仪表板使用知识库 API 来管理以下信息： 
  
- **用户**-用户有权访问存储库的表示形式。
    
- **报告**-列出查询、 存储为存储库项目中的内容。
    
- **查询**-用于从数据 API，作为一个内容存储库项目中存储中检索数据。
    
- **用户设置**的描述用户可选的应用程序的行为。
    
 **跨原始资源共享知识库 API (CORS) 支持**
  
知识库 API 支持跨原始资源共享 (CORS)。 CORS 是 HTTP 功能，可以将 web 应用程序运行在一个域访问另一个域中的资源。 Web 浏览器实现称为[同源策略](https://www.w3.org/Security/wiki/Same_Origin_Policy)同源策略使 web 页从另一个域中调用的 Api 的安全限制。 CORS 提供一种安全的方法，以允许一个域 （原始域） 另一个域中调用的 Api。 请参阅 CORS [CORS 技术指标](https://www.w3.org/TR/cors/)的详细信息。
  
 **启用对存储库 API CORS**
  
 以下是摘录的知识库 API web.config 文件中，显示在 corsTrustedOrigin 应用程序设置中列出的两个域。 从这些服务器加载的脚本所做的所有请求都受信任存储库 API。
  
请务必包括具体协议、 主机名称和端口 （如果有的话）。 不要不将任何反斜杠字符 （/） 结尾。 通过用逗号分隔，可以指定多个条目。
  
```
<repositoryConfiguration>
    <service corsTrustedOrigin="https://<trusted-server>,http://<another-trusted-domain>:8080"" />
    <diagnostics eventLevel="Verbose" systemLoggedEventLevel="Error">
      <traceLog enabled="true" fileName="repository_trace.log" />
    </diagnostics>
 </repositoryConfiguration>

```


