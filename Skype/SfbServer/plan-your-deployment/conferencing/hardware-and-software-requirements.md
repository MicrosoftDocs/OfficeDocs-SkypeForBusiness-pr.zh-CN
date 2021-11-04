---
title: 会议中的硬件和软件Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: bfa31b24-a02f-410f-a8ec-206ca4d5b620
description: 摘要：阅读本主题，了解 Skype for Business Server 中的会议硬件和软件要求。
ms.openlocfilehash: 16f5d44258474657e901933cdbf9bb66c178b5e0
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60754469"
---
# <a name="hardware-and-software-requirements-for-conferencing-in-skype-for-business-server"></a>会议中的硬件和软件Skype for Business Server

**摘要：** 阅读本主题，了解会议中的硬件和软件Skype for Business Server。

本节介绍 Web 会议、音频和视频 (A/V) 会议、电话拨入式会议和即时消息 (IM) 会议等的硬件和软件要求。 所有会议功能在前端服务器上运行;不同类型的会议有其他要求，如下图所示。

例如，如果要允许电话拨入式会议，则需要部署中介服务器和网关以连接到 PSTN 电话交换 (PSTN) 。 如果要允许 Web 会议，则需要确保Skype for Business Server Web Apps Server Office Web Apps Server。 如果要允许外部用户参加会议，则需要部署边缘服务器。

**会议功能和要求**

![会议组件。](../../media/9359b98b-b3ab-46a1-acf0-93c7bab6fc67.png)

 有关拓扑注意事项详细信息，请参阅 Plan [your conferencing topology for Skype for Business Server](conferencing-topology.md)。

## <a name="hardware-and-software-requirements-for-front-end-servers"></a>前端服务器的硬件和软件要求

由于 Web 会议、A/V 会议、电话拨入式会议和 IM 会议均与前端服务器并排，因此服务器硬件和软件要求与前端服务器的要求相同。 有关这些要求的详细信息，请参阅[server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)和 Environmental requirements for Skype for Business Server [2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)或[Server requirements for Skype for Business Server 2019。](../../../SfBServer2019/plan/system-requirements.md)

## <a name="requirements-for-web-conferencing"></a>Web 会议的要求

如果您已选择启用 Web 会议，则需计划以下事项：

- 访问文件存储，文件存储用于存储 Web 会议内容。

- 与 Office Web Apps Server 集成，这是在会议期间共享PowerPoint文件所必需的。

### <a name="file-store"></a>文件存储

Skype for Business Server Web 会议服务将会议期间共享的内容存储在文件存储中。 作为部署的一部分，您必须指定一个文件共享，以用作前端Standard Edition或Enterprise Edition的文件存储。 可以将现有的文件共享用作文件存储，也可以通过指定文件共享所在的文件服务器的完全限定域名 (FQDN) 和新文件共享的文件夹名称来指定新的文件共享。 有关详细信息，请参阅 Create [a file share in Skype for Business Server](../../deploy/install/create-a-file-share.md)。 Web 会议服务先对内容进行加密，然后再将内容存储在文件存储中。

Skype for Business Server 支持在直接附加存储 (DAS) 或存储区域网络 (SAN) （包括分布式文件系统 (DFS) ）和文件存储的独立磁盘冗余阵列 (RAID) 上使用文件共享。 在Skype for Business Server向导定义文件共享的位置后，Skype for Business Server在文件共享内创建一个文件夹结构，类似于：

- 1-ApplicationServer-1

- 1-CentralMgmt-1

- 1-WebServices-1

  - CollabContent

  - CollabMetadata

  - DataConf

然后，Web 会议服务在位于 WebServices 文件夹中的 CollabContent 和 CollabMetadata 文件夹中存储诸如 PowerPoint 幻灯片、白板、投票表决和附件之类的内容。

### <a name="office-web-apps-server"></a>Office Web Apps Server

若要使用 Web 会议功能，必须安装 Office Web Apps Server，Skype for Business Server Web Apps Server Office通信。

OfficeWeb Apps Server 应安装在未运行 Skype for Business Server、SQL Server或其他任何服务器应用程序独立计算机上。  (不得在计算机上安装任何版本的 Office。) 任何用于运行 Office Web Apps Server 的计算机还必须安装一组特定的软件 (包括 .NET Framework 4.5 和 Windows PowerShell 3.0) 。 这些要求以及有关配置证书和 IIS Internet Information Services (的信息) Web [Apps 部署Microsoft Office详细讨论。](/webappsserver/deploy-the-infrastructure-office-web-apps-server)

若要了解如何配置 Skype for Business Server 以使用 Office Web Apps Server，请参阅在 Skype for Business Server 中配置与[Office Web Apps Server 的Skype for Business Server。](../../deploy/deploy-conferencing/office-web-app-server.md)

## <a name="requirements-for-audio-and-video-conferencing"></a>音频和视频会议的要求

要规划 A/V 会议，需了解组织所需会议媒体类型要求的网络带宽。 这可能包括音频、视频和全景视频。 如果网络带宽不足，用户体验可能会严重下降。

有关会议的音频和视频容量规划的信息，请参阅 Plan network [requirements for Skype for Business](../../plan-your-deployment/network-requirements/network-requirements.md)。

可以使用呼叫允许控制 (CAC) A/V 会议使用的网络带宽。 这一点对于受限网络很重要，例如中央站点和分支站点之间的有限带宽链路。 有关详细信息，请参阅 Plan [for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)。

如果在网络中部署音频会议，用户将需要音频设备（如耳机）参与音频会议。 如果部署视频会议，则需要为用户部署视频设备，如网络摄像机。 对于音频和视频设备，设备部署和用户培训是要考虑的重要步骤。 有关详细信息，请参阅规划 [客户端和设备](../../plan-your-deployment/clients-and-devices/clients-and-devices.md)。 Microsoft 建议在所有设备类型 (Microsoft 认证的) UC 设备上使用统一通信，以确保获得最佳用户体验。 有关 UC 认证设备的详细信息，请参阅电话和设备[for Skype for Business。](../../../SfbPartnerCertification/certification/devices-ip-phones.md)

## <a name="requirements-for-dial-in-conferencing"></a>电话拨入式会议的要求

电话拨入式会议是电话拨入式Skype for Business Server的可选功能，包括各种组件。 一些组件是特定于电话拨入式会议的，一些组件是企业语音组件。 本节介绍电话拨入式会议所需的组件要求。 有关中介服务器和公用电话交换网 (PSTN) 网关要求的详细信息，请参阅 Skype for Business Server 中的中介[服务器](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md)组件和 Skype for Business Server 中的在拓扑生成器中[部署中介服务器](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md)。

### <a name="required-components"></a>所需组件

配置电话拨入式会议Skype for Business Server安装以下组件：

- 统一通信应用程序服务 (UCAS)（称为“应用程序服务”）

- 会议助理应用程序

- 会议通知应用程序

- 电话拨入式会议设置网页

- 至少一台中介服务器和至少一个 PSTN 网关

对于电话拨入式会议，应用程序服务、会议助理应用程序 和 会议公告应用程序 具有与前端服务器相同的操作系统要求。 有关详细信息，请参阅[Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。

会议助理应用程序会议公告应用程序要求Windows前端服务器上安装媒体格式运行时。 Windows需要媒体格式运行时才能Windows媒体音频 (WMA) 用于保持音乐、录制的名称和提示的文件。 如果要在 Windows Server 2012 或 Windows Server 2012 R2 (（我们建议) ，则需要安装 Microsoft Media Foundation 才能Windows Media Format Runtime。 如果要在 Windows 2012 之前的任何 Windows Server 版本上安装，则需要确保安装了 Windows 桌面体验，才能获得 Windows Media Format Runtime。

### <a name="audio-file-requirements-for-dial-in-conferencing"></a>电话拨入式会议音频文件要求

Skype for Business Server不支持为电话拨入式会议自定义语音提示和音乐。 但是，如果您有强大的业务需求，需要您更改默认音频文件，请参阅 Microsoft 知识库文章 961177 如何为电话拨入式音频会议自定义语音提示或音乐 [文件](https://go.microsoft.com/fwlink/p/?linkid=3052&amp;kbid=961177)。

会议助理应用程序会议公告应用程序对保持音乐、录制的名称和音频提示文件有以下要求：

- Windows Media 音频 (WMA) 文件格式

- 16 位单声道

- 48 kbps 2-pass CBR（恒定比特率）

- 语音级别 - 24DB

### <a name="user-requirements-for-dial-in-conferencing"></a>电话拨入式会议的用户要求

电话拨入式会议用户必须为其帐户分配唯一的电话号码或分机。 该要求支持在电话拨入式会议期间进行身份验证。 Enterprise用户 (，即组织中具有 Active Directory 域服务凭据和 Skype for Business Server 帐户的用户) 输入其电话号码 (或分机) 和个人标识号 (PIN) 以经过身份验证的用户身份拨入会议。

## <a name="port-requirements-for-conferencing"></a>会议端口要求

为了使用会议功能，Skype for Business Server某些端口是打开的。 下表列出了会议端口要求。 有关所有端口要求的详细信息，请参阅 [Port and protocol requirements for servers](../../plan-your-deployment/network-requirements/ports-and-protocols.md)。

**所需的服务器端口**


|**服务器角色**|**服务名称**|**Port**|**协议**|**备注**|
|:-----|:-----|:-----|:-----|:-----|
|前端服务器  <br/> |Skype for Business ServerIM 会议服务  <br/> |5062  <br/> |TCP  <br/> |用于即时消息 (IM) 会议的传入 SIP 请求。  <br/> |
|前端服务器  <br/> |Skype for Business ServerWeb 会议服务  <br/> |8057  <br/> |TCP (TLS)  <br/> |用于侦听来自客户端的持续性共享对象模型 (PSOM) 连接。  <br/> |
|前端服务器  <br/> |Skype for Business ServerWeb 会议兼容性服务  <br/> |8058  <br/> |TCP (TLS)  <br/> |用于侦听 PSOM 中的持久共享 (模型) Live Meeting 客户端和早期版本的 SKYPE FOR BUSINESS SERVER。  <br/> |
|前端服务器  <br/> |Skype for Business Server音频/视频会议服务  <br/> |5063  <br/> |TCP  <br/> |用于音频/视频 (A/V) 会议的传入 SIP 请求。  <br/> |
|前端服务器  <br/> |Skype for Business Server音频/视频会议服务  <br/> |57501-65535  <br/> |TCP/UDP  <br/> |用于视频会议的媒体端口范围。  <br/> |
|前端服务器  <br/> |Skype for Business Server 会议助理电话 (会议服务)   <br/> |5064  <br/> |TCP  <br/> |用于电话拨入式会议的传入 SIP 请求。  <br/> |
|前端服务器  <br/> |Skype for Business Server 会议助理电话 (会议服务)   <br/> |5072  <br/> |TCP  <br/> |用于助理电话拨入式会议 (传入 SIP) 。  <br/> |
|前端服务器  <br/> |Skype for Business Server应用程序共享服务  <br/> |5065  <br/> |TCP  <br/> |用于应用程序共享的传入 SIP 侦听请求。  <br/> |
|前端服务器  <br/> |Skype for Business Server应用程序共享服务  <br/> |49152-65535  <br/> |TCP  <br/> |用于应用程序共享的媒体端口范围。  <br/> |
|前端服务器  <br/> |Skype for Business Server 会议公告服务  <br/> |5073  <br/> |TCP  <br/> |用于电话拨入式会议Skype for Business Server 会议公告服务的 (SIP 请求) 。  <br/> |
|所有内部服务器  <br/> |各种  <br/> |49152-57500  <br/> |TCP/UDP  <br/> |用于所有内部服务器上的音频会议的媒体端口范围。 由终止音频的所有服务器使用：前端服务器 (用于 Skype for Business Server 会议助理 服务Skype for Business Server 会议公告服务，Skype for Business Server音频/视频会议服务) 和中介服务器。  <br/> |
|OfficeWeb Apps 服务器  <br/> ||443  <br/> ||Used by Skype for Business Server to connect to Office Web Apps Server.  <br/> |

**所需的客户端端口**


|**Port**|**协议**|**备注**|
|:-----|:-----|:-----|
|443  <br/> |TCP (PSOM/TLS)  <br/> |用于外部用户访问 Web 会议会话。  <br/> |
|443  <br/> |TCP (STUN/MSTURN)  <br/> |用于外部用户访问 A/V 会话和媒体 (TCP)  <br/> |
|3478  <br/> |UDP (STUN/MSTURN)  <br/> |用于外部用户访问 A/V 会话和 UDP (媒体)   <br/> |
|1024-65535 \*  <br/> |TCP/UDP  <br/> |音频端口范围（最少需要 20 个端口）  <br/> |
|1024-65535 \*  <br/> |TCP/UDP  <br/> |视频端口范围（最少需要 20 个端口）。  <br/> |
|1024-65535 \*  <br/> |TCP  <br/> |应用程序共享。  <br/> |