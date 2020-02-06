---
title: Skype for Business Server 2015 中的 ErrorReport 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
description: ErrorReport 表存储发生的错误的相关信息。 每条记录是一个错误发生。 这些错误由前端服务器上运行的 CDR 代理或从客户端发送的 CDR 捕获。
ms.openlocfilehash: de103c61f74b50297f9c012ae7f4c6e1586e87d7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815220"
---
# <a name="errorreport-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的 ErrorReport 表
 
ErrorReport 表存储发生的错误的相关信息。 每条记录是一个错误发生。 这些错误由前端服务器上运行的 CDR 代理或从客户端发送的 CDR 捕获。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ErrorTime** <br/> |datetime  <br/> |Primary  <br/> |出现错误的日期和时间。  <br/> |
|**ErrorReportSeq** <br/> |int  <br/> |Primary  <br/> |标识错误报告的 ID 号。 与**ErrorTime**结合使用以唯一标识错误报告。 <br/> |
|**ErrorId** <br/> |int  <br/> |外表  <br/> |错误类型的唯一 ID。 有关详细信息，请参阅[Skype For Business Server 2015 中的 ErrorDef 表](errordef.md)。 <br/> |
|**FromUserId** <br/> |int  <br/> |外表  <br/> |发出导致错误的请求的用户。 有关详细信息，请参阅[用户表](users.md)。 <br/> |
|**ToUserId** <br/> |int  <br/> |外表  <br/> |导致错误的请求的目标用户。 有关详细信息，请参阅[用户表](users.md)。 <br/> |
|**ConferenceUriId** <br/> |int  <br/> |外表  <br/> |与该错误相关的会议 URI。 有关详细信息，请参阅[Skype For Business Server 2015 中的 ConferenceUris 表](conferenceuris.md)。 通常情况下，如果 ConferenceUriId 不为 null，则 FromUserId 或 ToUserId 将为 null。 <br/> |
|**SessionIdTime** <br/> |datetime  <br/> |外表  <br/> |与**SessionIdSeq**结合使用以唯一标识会话。 有关详细信息，请参阅[Skype For Business Server 2015 中的对话框表](dialogs.md)。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |外表  <br/> |标识会话的 ID 号。 与**SessionIdTime**结合使用以唯一标识会话。 有关详细信息，请参阅[Skype For Business Server 2015 中的对话框表](dialogs.md)。 <br/> |
|**SourceId** <br/> |int  <br/> |外表  <br/> |发送错误报告的服务器（如果正在从服务器组件发送报表）。 有关详细信息，请参阅[服务器表](servers.md)。 <br/> 此字段是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**ApplicationId** <br/> |int  <br/> |外表  <br/> |发送错误报告的服务器（如果正在从服务器组件发送报表）。 有关详细信息，请参阅[Skype For Business Server 2015 中的应用程序表](application.md)。 <br/> 此字段是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**MsDiagHeader** <br/> |图像  <br/> | <br/> |有关错误的详细信息。  <br/> 可以使用以下语法将此数据转换为文本格式：  <br/>  `cast(cast(Detail as varbinary(max)) as varchar(max))` <br/> |
|**ClientVersionId** <br/> |int  <br/> |外表  <br/> |发送错误报告的终结点的客户端版本。 有关详细信息，请参阅[Skype For Business Server 2015 中的 ClientVersions 表](clientversions.md)。 <br/> |
|**IsCapturedByServer** <br/> |bit  <br/> ||由前端服务器上运行的 CDR 代理捕获的错误报告，或由客户端发送的错误报告。  <br/> |
|**旗** <br/> |smallint  <br/> ||保留以供将来使用。  <br/> |
|**TelemetryId** <br/> |标识符  <br/> ||关联会议中涉及的不同组件的加入时间信息的唯一标识符。  <br/> 此字段是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**SessionSetupTime** <br/> |int  <br/> ||特定组件加入会议所需的时间（以毫秒为单位）。  <br/> 此字段是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**ServerId** <br/> |int  <br/> |外表  <br/> |表示生成错误报告的服务器的完全限定的域名。  <br/> |
|**PoolId** <br/> |int  <br/> |外表  <br/> |表示生成错误报告的池的完全限定的域名。  <br/> |
|**LastModifiedTime** <br/> |从中  <br/> ||供监视服务内部使用。  <br/> 此字段是在 Skype for Business Server 2015 中引入的。  <br/> |
   

