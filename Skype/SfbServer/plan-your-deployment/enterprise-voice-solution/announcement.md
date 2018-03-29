---
title: 在 Skype for Business 2015 中规划通知应用程序
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 2abee804-2599-48bb-90b2-15df0bae5e20
description: 该规划业务服务器企业语音在 Skype 的发布应用程序，配置如何向您组织中未指定的电话号码的电话。 包括音频文件要求。
ms.openlocfilehash: c7ed700c749f1d5692b78c931e225fee5d0497be
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-the-announcement-application-in-skype-for-business-2015"></a>在 Skype for Business 2015 中规划通知应用程序
 
该规划业务服务器企业语音在 Skype 的发布应用程序，配置如何向您组织中未指定的电话号码的电话。 包括音频文件要求。
  
Skype 业务服务器发布应用程序使您能够配置传入电话呼叫处理时拨叫的号码为您的组织有效但未分配给一个用户或一部电话。 可以将这些呼叫转换到预确定的目标（电话号码、SIP URI 或语音邮件）和/或播放音频通知。 该通知应用程序帮助您可以避免呼叫者拨错号并听到忙音或 SIP 客户端收到错误消息的情况。 本部分包括规划特定于产品发布应用程序的信息
  
在部署时通知应用程序，您需要配置确定有人拨打未分配的号码时要采取的操作未分配数字表。 未分配的数字表包含区域组织有效的电话号码和指定的发布应用程序处理每个范围。 当呼叫者拨叫的电话号码，为您的组织有效，但不是授予任何人时，Skype 的业务服务器查找中未分配的数字路由表，数字标识哪些范围数落中，并将路由到该调用为该范围指定的发布应用程序。 发布应用程序应答呼叫和播放的音频消息 （如果您配置它来做到这一点的） 然后断开与呼叫的连接或将其传送到一个预先确定的目标，如对运算符。 要配置多个音频邮件或者转移目标，可以使用业务服务器管理外壳 cmdlet 的 Skype。
  
配置未分配号码表的方式取决于要使用该表的方式。如果您有不再使用的特定号码并且要播放为每个号码定制的消息，则可以输入未分配号码表中的那些特定号码。例如，如果已更改客户服务台的号码，则可以输入旧的客户服务号码并将其与提供新号码的通知相关联。如果要向呼叫未分配号码的任何人（例如已离开组织的员工）播放常规消息，则可以输入组织所有可用分机的范围。每当呼叫者拨打当前未分配的号码时，系统都会调用未分配号码表。
  
## <a name="deployment-and-requirements"></a>部署和要求

Tthe 发布应用程序会自动安装与响应组应用程序。 通知和响应组的应用程序的标准组件的企业语音部署： 部署企业语音时，这两个应用程序会自动部署。 
  
### <a name="software-requirements"></a>软件要求

运行发布应用程序的所有前端服务器或标准版服务器必须运行 Windows Server 2012 的服务器中运行 Windows Server 2008 R2 或 Microsoft 媒体基础的服务器安装的 Windows 媒体格式运行时或Windows Server 2012 R2。 对于 Windows Server 2008 R2，Windows 媒体格式运行时安装作为 Windows 桌面体验的一部分。 Windows 媒体格式运行时或 Microsoft 媒体基础是公告和音乐发布应用程序播放的 Windows Media 音频 (.wma) 文件需要。 
  
### <a name="port-requirements"></a>端口要求

发布应用程序使用 SIP 侦听请求的**端口 5071** 。
    
> [!NOTE]
> 此端口是默认设置，您可以通过**设置 CsApplicationServer** cmdlet 更改。 此 cmdlet 的详细信息，请参阅有关业务服务器管理外壳程序文档 Skype。
  
### <a name="audio-file-requirements"></a>音频文件要求

发布应用程序支持波形 (.wav) 文件格式以及 Windows Media 音频 (.wma) 音乐和公告的文件格式。 发布应用程序的音频文件要求都响应组应用程序一样。 有关详细信息，请参阅[响应组的技术要求](http://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)。
  

