---
title: 在 Skype for Business 中规划发布应用程序
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 在 Skype for Business Server 企业语音中规划公告应用程序，该应用程序配置对组织中未分配的电话号码进行电话呼叫的操作。 包括音频文件要求。
ms.openlocfilehash: d160878030fad30dd3e91b78f54ffcdab722299f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803262"
---
# <a name="plan-for-the-announcement-application-in-skype-for-business"></a>在 Skype for Business 中规划发布应用程序

在 Skype for Business Server 企业语音中规划公告应用程序，该应用程序配置对组织中未分配的电话号码进行电话呼叫的操作。 包括音频文件要求。

使用 Skype for Business 服务器公告应用程序，你可以配置当已拨电话号码对你的组织有效，但未分配给用户或电话时对传入电话呼叫的处理。 可以将这些呼叫转换到预确定的目标（电话号码、SIP URI 或语音邮件）和/或播放音频通知。 该通知应用程序帮助您可以避免呼叫者拨错号并听到忙音或 SIP 客户端收到错误消息的情况。 本部分包含特定于公告应用程序的规划信息

部署公告应用程序时，需要配置一个未分配的数字表，用于确定当某人拨打未分配的号码时要执行的操作。 "未分配的号码" 表包含对组织有效的电话号码范围，并指定哪个公告应用程序处理每个范围。 当呼叫者拨打对您的组织有效但未分配给任何人的电话号码时，Skype for Business 服务器将在未分配的号码路由表中查找该号码，确定该号码属于哪个范围，并将呼叫路由到为该范围指定的公告应用程序。 "通知" 应用程序将应答呼叫并播放音频消息（如果将其配置为执行此操作），然后断开通话或将其转移到预先确定的目标，如 "操作员"。 你可以使用 Skype for Business Server Management Shell cmdlet 配置多条音频消息或传输目标。

配置未分配号码表的方式取决于要使用该表的方式。如果您有不再使用的特定号码并且要播放为每个号码定制的消息，则可以输入未分配号码表中的那些特定号码。例如，如果已更改客户服务台的号码，则可以输入旧的客户服务号码并将其与提供新号码的通知相关联。如果要向呼叫未分配号码的任何人（例如已离开组织的员工）播放常规消息，则可以输入组织所有可用分机的范围。每当呼叫者拨打当前未分配的号码时，系统都会调用未分配号码表。

## <a name="deployment-and-requirements"></a>部署和要求

公告应用程序将随响应组应用程序一起自动安装。 "通知" 和 "响应" 组应用程序是企业语音部署的标准组件：当部署企业语音时，将自动部署这两个应用程序。

### <a name="software-requirements"></a>软件要求

运行公告应用程序的所有前端服务器或标准版服务器必须为运行 Windows Server 2008 R2 的服务器安装 Windows Media Format Runtime，或者为运行 Windows Server 2012 的服务器安装 Microsoft Media Foundation。Windows Server 2012 R2。 对于 Windows Server 2008 R2，Windows Media 格式运行时作为 Windows 桌面体验的一部分进行安装。 对于发布应用程序为通知和音乐播放的 Windows Media 音频（.wma）文件，需要 windows Media 格式运行时或 Microsoft Media Foundation。

### <a name="port-requirements"></a>端口要求

公告应用程序使用**端口 5071**进行 SIP 侦听请求。

> [!NOTE]
> 此端口是默认设置，可以通过使用 **Set-CsApplicationServer** cmdlet 进行更改。 有关此 cmdlet 的详细信息，请参阅 Skype for Business 服务器管理外壳文档。

### <a name="audio-file-requirements"></a>音频文件要求

"通知" 应用程序支持波形（.wav）文件格式和 Windows Media 音频（.wma）文件格式的音乐和公告。 公告应用程序的音频文件要求与响应组应用程序的音频文件相同。 有关详细信息，请参阅 [Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)。


