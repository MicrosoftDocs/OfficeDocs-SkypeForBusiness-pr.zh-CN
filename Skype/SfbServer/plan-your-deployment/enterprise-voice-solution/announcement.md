---
title: 在 Skype for Business 中规划通知应用程序
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2abee804-2599-48bb-90b2-15df0bae5e20
description: Planning for the announcement application in Skype for Business Server 企业语音， which configures what to do with phone calls to unassigned phone numbers in your organizations. 包括音频文件要求。
ms.openlocfilehash: e1309fe58942f3b9cd720b3643966ae9494bb0cb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51112708"
---
# <a name="plan-for-the-announcement-application-in-skype-for-business"></a>在 Skype for Business 中规划通知应用程序

Planning for the announcement application in Skype for Business Server 企业语音， which configures what to do with phone calls to unassigned phone numbers in your organizations. 包括音频文件要求。

Skype for Business Server Announcement 应用程序使您能够配置在拨打的号码对您的组织有效，但没有分配给用户或电话时对传入电话呼叫的处理。 可以将这些呼叫转换到预确定的目标（电话号码、SIP URI 或语音邮件）和/或播放音频通知。 该通知应用程序帮助您可以避免呼叫者拨错号并听到忙音或 SIP 客户端收到错误消息的情况。 本节包括特定于通知应用程序的规划信息

部署通知应用程序时，需要配置未分配号码表，该表确定在某人拨打未分配号码时要采取的操作。 未分配号码表包含对组织有效的电话号码范围，并指定哪个通知应用程序处理每个范围。 当呼叫者拨打对您的组织有效但没有分配给任何人的电话号码时，Skype for Business Server 会查找未分配号码路由表中的号码，标识该号码属于哪个范围，并将呼叫路由到为该范围指定的通知应用程序。 通知应用程序应答呼叫并播放音频消息 (如果将其配置为) 然后断开呼叫或将其转接到预先确定的目标（如接线员）。 Skype for Business Server 命令行管理程序 cmdlet 可用于配置多个音频消息或传输目标。

配置未分配号码表的方式取决于要使用该表的方式。如果您有不再使用的特定号码并且要播放为每个号码定制的消息，则可以输入未分配号码表中的那些特定号码。例如，如果已更改客户服务台的号码，则可以输入旧的客户服务号码并将其与提供新号码的通知相关联。如果要向呼叫未分配号码的任何人（例如已离开组织的员工）播放常规消息，则可以输入组织所有可用分机的范围。每当呼叫者拨打当前未分配的号码时，系统都会调用未分配号码表。

## <a name="deployment-and-requirements"></a>部署和要求

通知应用程序会自动随响应组应用程序一起安装。 通知和响应组应用程序是部署企业语音组件：在部署企业语音时，会自动部署这两个应用程序。

### <a name="software-requirements"></a>软件要求

运行通知应用程序的所有前端服务器或 Standard Edition Server 必须为运行 Windows Server 2008 R2 的服务器安装 Windows Media Format Runtime，或为运行 Windows Server 2012 R2 或 Windows Server 2012 R2 的服务器安装 Microsoft Media Foundation。 对于 Windows Server 2008 R2，Windows Media Format Runtime 作为 Windows 桌面体验的一部分进行安装。 通知应用程序播放通知和音乐的 Windows Media Audio (.wma) 需要 Windows Media Format Runtime 或 Microsoft Media Foundation。

### <a name="port-requirements"></a>端口要求

通知应用程序将 **端口 5071** 用于 SIP 侦听请求。

> [!NOTE]
> 此端口是默认设置，可以通过使用 **Set-CsApplicationServer** cmdlet 进行更改。 有关此 cmdlet 的详细信息，请参阅 Skype for Business Server 命令行管理程序文档。

### <a name="audio-file-requirements"></a>音频文件要求

通知应用程序支持 Wave (.wav) 文件格式和 Windows Media 音频 (.wma) 文件格式用于音乐和通知。 通知应用程序的音频文件要求与响应组应用程序的相同。 有关详细信息，请参阅[Technical Requirements for Response Groups](/previous-versions/office/lync-server-2013/lync-server-2013-technical-requirements-for-response-group)。