---
title: ErrorReport 视图
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ca873f7e-b18b-4eaf-8db0-5f9d5a9b60a1
description: ErrorReport 视图存储有关报告的错误的信息。 每条记录是一个错误发生。 这些错误由前端服务器上运行的 CDR 代理或从客户端发送的 CDR 捕获。 此视图已在 Microsoft Lync Server 2013 中引入。
ms.openlocfilehash: a95d3d1e99fc41727c10ecef7beaafddc213dd17
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296271"
---
# <a name="errorreport-view"></a>ErrorReport 视图
 
ErrorReport 视图存储有关报告的错误的信息。 每条记录是一个错误发生。 这些错误由前端服务器上运行的 CDR 代理或从客户端发送的 CDR 捕获。 此视图已在 Microsoft Lync Server 2013 中引入。
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |出现错误的时间。 与 ErrorReportSeq 结合使用以唯一标识错误。  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |标识错误的 ID 号。 与 ErrorTime 结合使用以唯一标识错误。  <br/> |
|**MsDiagId** <br/> |int  <br/> |错误报告的诊断 ID。  <br/> |
|**FromUri** <br/> |nvarchar (450)  <br/> |发出错误的用户的 URI。  <br/> |
|**FromUriType** <br/> |nvarchar(256)  <br/> |发出错误的用户的 URI 类型。 有关详细信息, 请参阅[UriTypes 表](uritypes.md)。 <br/> |
|**FromTenant** <br/> |nvarchar(256)  <br/> |发出错误的用户的租户。 有关详细信息, 请参阅[租户表](tenants.md)。 <br/> |
|**ToUri** <br/> |nvarchar (450)  <br/> |错误报告目标用户的 URI。  <br/> |
|**ToUriType** <br/> |nvarchar(256)  <br/> |错误报告目标用户的 URI 的类型。 有关详细信息, 请参阅 UriTypes 表。  <br/> |
|**ToTenant** <br/> |nvarchar(256)  <br/> |错误报告面向的用户的租户。 有关详细信息, 请参阅[租户表](tenants.md)。 <br/> |
|**ConferenceUri** <br/> |nvarchar (450)  <br/> |错误报告目标的会议的 URI。  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |错误报告目标的会议的 URI 类型。 有关详细信息, 请参阅[UriTypes 表](uritypes.md)。 <br/> |
|**SessionIdTime** <br/> |datetime  <br/> |发出错误报告的会话请求的时间。 与 SessionIdSeq 结合使用以唯一标识会话。 有关详细信息, 请参阅[Skype For Business Server 2015 中的对话框表](dialogs.md)。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |标识发出错误报告的会话请求的 ID 号。 与 SessionIdTime 结合使用以唯一标识会话。 有关详细信息, 请参阅[Skype For Business Server 2015 中的对话框表](dialogs.md)。 <br/> |
|**DialogId** <br/> |varstring (775)  <br/> |发出错误的会话的 SIP 对话框 ID。 格式为:  <br/> 对话框; 从-标签; 到-标记  <br/> 可以使用以下语法将此数据转换为文本格式:  <br/> cast (cast (ExternalId 为 varbinary (max)) 作为 varchar (max))  <br/> |
|**ClientVersion** <br/> |nvarchar(256)  <br/> |发出错误的用户使用的客户端版本。  <br/> |
|**ClientType** <br/> |int  <br/> |发出错误的用户所使用的客户端。 有关详细信息, 请参阅[UserAgentDef 表](useragentdef.md)。 <br/> |
|**ClientCategory** <br/> |nvarchar (64)  <br/> |发出错误的用户所使用的客户端类别的名称。  <br/> |
|**来源** <br/> |nvarchar(256)  <br/> |产生错误的服务器的名称 (如果报表是从服务器组件发送的)。  <br/> |
|**应用程序** <br/> |nvarchar(256)  <br/> |发出错误的应用程序的名称 (如果报表是从服务器组件发送的)。  <br/> |
|**ResponseCode** <br/> |int  <br/> |SIP 回复代码发送到包含错误报告的 SIP 邮件的会话。  <br/> |
|**RequestType** <br/> |varchar (max)  <br/> |失败的请求类型。  <br/> |
|**ContentType** <br/> |varchar (max)  <br/> |失败的请求的内容类型。  <br/> |
|**CallType** <br/> |nvarchar(256)  <br/> |会话类型。 有关详细信息, 请参阅[Skype For Business Server 2015 中的 CallType 表](calltype.md)。 <br/> |
|**TelemetryId** <br/> |标识符  <br/> |关联会议中涉及的不同组件的加入时间信息的唯一标识符。  <br/> |
|**SetupTime** <br/> |int  <br/> |特定组件加入会议所需的时间 (以毫秒为单位)。  <br/> |
|**IsCapturedByServer** <br/> |bit  <br/> |指示错误报告是由前端服务器上运行的 CDR 代理捕获的还是由客户端发送的。  <br/> |
|**旗** <br/> |smallint  <br/> |保留以供将来使用。  <br/> |
|**MsDiagHeader** <br/> |varchar (max)  <br/> |有关错误的其他信息。  <br/> |
|**FrontEnd** <br/> |nvarchar  <br/> |提交报表的前端服务器的完全限定的域名。  <br/> |
|**Pool** <br/> |nvarchar  <br/> |包含提交报表的前端服务器的池的完全限定的域名。  <br/> |
   

