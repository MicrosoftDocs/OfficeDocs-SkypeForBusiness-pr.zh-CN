---
title: 在响应组中规划响应组Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6cc333e7-4029-4372-86b2-016040c415fb
description: 规划呼叫Skype for Business Server 企业语音，从而使您能够设置到用户组的呼叫路由。 包括音频文件要求。
ms.openlocfilehash: 41decf3e61e32867dd6b1d726bb551f8c2ae38f0
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58631576"
---
# <a name="plan-for-the-response-group-application-in-skype-for-business-server"></a>在响应组中规划响应组Skype for Business Server

规划呼叫Skype for Business Server 企业语音，从而使您能够设置到用户组的呼叫路由。 包括音频文件要求。

如果您的组织具有一组应答和管理某些类型的呼叫（例如客户服务、内部技术支持或部门常规电话支持）的呼叫，您可以部署响应组应用程序来管理这些类型的呼叫。 响应组应用程序将传入呼叫路由到指定人员（称为代理）并排入队列。 您可以通过响应组来增加电话支持服务的使用并降低运行这些服务的开销。

当呼叫者呼叫响应组时，呼叫会基于智能寻线或呼叫者对互动语音响应 (IVR) 问题的回答路由至代理。 响应组应用程序使用标准响应组路由方法将呼叫路由到下一个可用的代理。 支持的呼叫路由方法包括串行、最长空闲、并行、循环和助理路由 (即，每个传入呼叫的所有代理都会同时调用，无论其当前状态) 。

如果没有可用的代理，呼叫将保留在一个队列中，直到代理可用为止。 在队列中时，呼叫者将听到音乐，直到可用代理接受呼叫为止。 如果队列已满，或者呼叫在队列中时出现中断，呼叫者可能会听到一条消息，然后断开连接或转接到其他目标，如不同的电话号码或语音邮件。 当代理接受呼叫时，呼叫者可能会（也可能不会）看到代理的身份，具体取决于管理员如何配置响应组。 代理可以是正式的，这意味着他们必须登录到组，然后才能接受路由至该组的呼叫；也可以是非正式的，这意味着他们无需登录到组，在组外即可接受呼叫。

> [!NOTE]
> 只有内部部署用户可以成为代理。如果代理从内部部署移动到联机状态，则不会将响应组呼叫路由到该代理。

> [!NOTE]
> 响应组应用程序使用名为 Match Making 的内部服务对呼叫进行排队并查找可用代理。 运行响应组应用程序的每台计算机都运行 Match Making 服务，但每个池一次只有一个 Match Making 服务处于活动状态，其他服务是被动的。 如果在计划外中断期间，活动 Match Making 服务变得不可用，则某一个非活动 Match Making 服务将变成活动状态。 响应组应用程序将尽最大努力确保呼叫路由和队列不会中断。 但是，当转换 Match Making 服务时，会丢失此时正在传输的所有呼叫。 例如，如果转换是由于前端服务器关闭，则当前由该前端服务器上活动的 Match Making 服务处理的任何呼叫也将丢失。

## <a name="response-group-workflows"></a>响应组工作流

工作流定义了从电话响铃到有人接听电话这段时间内呼叫的行为。工作流指定用于保留呼叫的队列，并指定用于智能寻线的路由方法或用于互动响应组的问题和答案。工作流还定义了诸如欢迎消息、保持音乐、工作时间和假日等设置。

> [!NOTE]
> 必须先创建代理组和队列，然后再创建使用这些组和队列的工作流。

## <a name="management-of-response-groups"></a>响应组的管理

在Skype for Business Server中，有两个管理角色可用于管理响应组：响应组管理员和响应组管理员。 响应组管理员可以管理任何响应组的各个方面。 响应组管理员只能管理某些方面，并且只能管理他们拥有的响应组。 Manager 角色可以帮助您降低管理成本，因为您可以将特定响应组的有限责任委派给启用了此角色企业语音。 请注意，用户可以是响应组管理员和响应组管理员。

为了适应 Manager 角色，响应组应用程序使用 **"** 托管"或"非托管"的工作流类型。 下表介绍了托管响应组和非托管响应组。

**托管响应组和非托管响应组**

|**响应组类型**|**说明**|
|:-----|:-----|
|非托管  <br/> | 非托管响应组未分配有 Manager。 只有响应组管理员可以配置这些响应组。 <br/>  多个非托管响应组可共享一个队列或代理组。 <br/>  将响应组从早期版本迁移到 Skype for Business Server时，类型设置为"非托管"。 <br/> |
|托管  <br/> | 响应组管理员可以配置托管响应组的任何方面。 <br/>  响应组管理员无法查看或修改未明确分配给他们的响应组。 <br/>  响应组管理员只能为显式分配给他们的响应组配置某些设置。 <br/>  托管响应组无法与任何其他响应组（托管或非托管）共享任何队列或代理组。 <br/> |

下表介绍了响应组管理员可以/不能为分配给这些响应组的响应组执行的操作。

**响应组 Manager 功能**

|**可以配置：**|**可以创建、删除或配置：**|**不能：**|
|:-----|:-----|:-----|
| Agents <br/>  欢迎消息 <br/>  响应组名称 <br/>  说明 <br/>  显示号码 <br/>  工作时间 <br/>  保持音乐 <br/>  状态（活动/非活动） <br/>  智能寻线工作流和互动语音响应 (IVR) 工作流 <br/> | 代理组 <br/>  队列 <br/>  假日集 <br/> | 创建或删除任意类型的工作流 <br/>  修改核心响应组设置，如：“SIP URI”、“电话号码”或“工作流类型”。  <br/> |

响应组管理员可使用以下工具来管理其指定的响应组。

- Skype for Business Server 控制面板

    > [!NOTE]
    > 响应组管理员只能使用此工具管理响应组设置。 其他Skype for Business Server管理员不可用。

- 响应组配置工具

- Skype for Business Server 命令行管理程序

响应组可很好地扩展到部门或工作组 (，有关详细信息，请参阅 Capacity [Planning for Response Group](/previous-versions/office/lync-server-2013/lync-server-2013-capacity-planning-for-response-group)) and can be deployed in entirely new telephony installations。 它支持来自 企业语音 和本地运营商网络的传入呼叫。 代理可以使用 Skype for Business、Lync 2013、Lync 2010、Lync 2010 Attendant 或 Lync 电话 Edition 将呼叫路由到这些代理。

## <a name="deployment-and-requirements"></a>部署和要求

部署响应组应用程序时，将自动启用企业语音。

### <a name="hardware-and-software-requirements"></a>硬件和软件要求

响应组应用程序具有与前端服务器相同的硬件要求、操作系统要求和必备软件。

如果将 Windows Media Audio (.wma) 文件用于响应组音乐和通知，则运行响应组应用程序的所有前端服务器或 Standard EditionS 服务器必须为运行 Windows Server 2008 R2 的服务器安装 Windows Media Format Runtime，或者为运行 Windows Server 2012 或 Windows Server 2012 R2 的服务器安装 Microsoft Media Foundation。 对于 Windows Server 2008 R2，Windows Media Format Runtime 作为桌面体验的一Windows安装。

响应组 **使用语言包** 支持文本到语音和语音识别。 在配置消息（如欢迎邮件和其他提示）以及 IVR 的交互式语音响应 (IVR) 和答案时，会使用这些语音技术。 默认情况下，在部署语言包时，会安装 26 Skype for Business Server。

### <a name="port-requirements"></a>端口要求

响应组应用程序使用下列端口：

- SIP 侦听请求的端口 **5071**

- 用于服务器间通信的端口 **8404**

    > [!NOTE]
    > 此端口用于 Match Making 服务，在具有多个前端服务器的池中部署响应组应用程序时需要此端口。

   > [!NOTE]
   > 这些端口是默认设置，您可以使用 **Set-CsApplicationServer** cmdlet 更改。 有关此 cmdlet 的详细信息，请参阅 Skype for Business Server 命令行管理程序文档。

### <a name="audio-file-requirements"></a>音频文件要求

响应组应用程序支持 wave (.wav) 文件格式和 Windows Media 音频 (.wma) 文件格式处理响应组消息、保持音乐或互动语音响应 (IVR) 问题。

Windows Media 音频文件格式要求在运行 Windows Server 2008 R2 和 Windows Server 2008 的前端服务器上安装 Windows Media Format Runtime。 有关详细信息，请参阅本节前面介绍的"软件要求"。

#### <a name="supported-wave-file-formats"></a>支持的 Wave 文件格式

所有 wave 文件必须符合以下要求：

- 8 位或 16 位文件

- 线性脉冲编码调制 (LPCM)，A-Law 或 mu-Law 格式

- 单声道或立体声

- 4 MB 或更小

为获得 wave 文件的最佳性能，建议使用 16 kHz、单声道、16 位的 wave 文件。

#### <a name="supported-windows-media-audio-file-formats"></a>支持的 Windows Media 音频文件格式

如果使用 Windows 音频文件，请考虑使用低比特率，并验证负载下的系统性能。

您可以使用 Microsoft Expression Encoder 4 将文件转换为 Windows Media 音频格式。 若要下载 Expression Encoder 4，请参阅 [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkId=202843) 。

### <a name="response-group-configuration-tool-requirements"></a>响应组配置工具要求

响应组配置工具支持下表中描述的操作系统和 Web 浏览器的组合。

> [!NOTE]
> 支持 32 位或 64 位版本的操作系统。 仅支持 32 位Internet Explorer版本。

**支持的操作系统和 Web 浏览器**

|**操作系统**|**Web 浏览器**|
|:-----|:-----|
|WindowsVista Service Pack (SP) 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 (本机模式)   <br/> Internet Explorer 9 (本机模式)   <br/> |
|Windows 7  <br/> Windows 7 Service Pack 1  <br/> |Internet Explorer 8 (本机模式)   <br/> Internet Explorer 9 (本机模式)   <br/> |
|WindowsServer 2008 Service Pack 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 (本机模式)   <br/> Internet Explorer 9 (本机模式)   <br/> |
|Windows Server 2008 R2  <br/> WindowsServer 2008 R2 Service Pack 1  <br/> |Internet Explorer 8 (本机模式)   <br/> Internet Explorer 9 (本机模式)   <br/> |
|Windows Server 2012  <br/> ||
|Windows Server 2012 R2  <br/> ||

### <a name="response-group-agent-console"></a>响应组代理控制台

代理控制台支持下表中描述的操作系统和 Web 浏览器的组合。

> [!NOTE]
> 支持 32 位或 64 位版本的操作系统。 仅支持 32 位Internet Explorer版本。

**支持的操作系统和 Web 浏览器**

|**操作系统**|**Web 浏览器**|
|:-----|:-----|
|WindowsVista Service Pack (SP) 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 (本机模式)   <br/> Internet Explorer 9 (本机模式)   <br/> |
|Windows 7  <br/> Windows 7 Service Pack 1  <br/> |Internet Explorer 8 (本机模式)   <br/> Internet Explorer 9 (本机模式)   <br/> Firefox 10.0  <br/> Chrome 18.0  <br/> |
|WindowsServer 2008 Service Pack 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8 (本机模式)   <br/> Internet Explorer 9 (本机模式)   <br/> |
|Windows Server 2008 R2  <br/> WindowsServer 2008 R2 Service Pack 1  <br/> |Internet Explorer 8 (本机模式)   <br/> Internet Explorer 9 (本机模式)   <br/> Firefox 10.0  <br/> Chrome 18.0  <br/> |
|Windows Server 2012  <br/> |
|Windows Server 2012 R2  <br/> |

## <a name="client-support"></a>客户端支持

响应组应用程序支持以下客户端：

- Skype for Business桌面客户端

- Lync 2013 桌面客户端

- Lync 2010 桌面客户端

- Lync 2010 Attendant

- Office Communications Server 2007 R2 Attendant

- Lync Phone Edition

> [!NOTE]
> Lync 移动客户端不支持响应组应用程序。

可以使用的特定客户端取决于您是以下用户的响应组用户类型：

- **呼叫者** 可使用前面列出的任何客户端和公用电话交换网 (PSTN) 上的标准电话来呼叫响应组。

- **非正式代理** (组登录和注销的代理接受呼叫，) Attendant、Lync 或 Lync 电话 Edition 接受呼叫。 非正式代理在使用这些客户端之一登录Skype for Business Server自动登录到其组。

- 正式 **代理 (** 必须登录到组和从组注销才能接受呼叫的代理) 可以通过使用 Skype for Business 和从菜单项访问代理控制台，或者通过使用 Attendant 并直接从 Internet Explorer 访问代理控制台来接受呼叫。

## <a name="capacity-planning"></a>容量规划

下表介绍了可用于作为容量规划要求基础的响应组用户模型。

> [!NOTE]
> 下表中的数值假定所有响应组音频文件使用的是 16 kHz、单声道、16 位的 Wave (.wav) 文件。如果使用其他文件格式（如 Windows Media 音频 (.wma)），则数值可能会有所不同。

> [!IMPORTANT]
> 请记住，对于灾难恢复容量规划，一对池中的每一个池都应能处理这两个池中的所有响应组的工作负荷。

**响应组用户模型**

|**跃点数**|**每个Enterprise Edition池 <br/> (8 台前端服务器)**|**每台 Standard Edition Server**|
|:-----|:-----|:-----|
|每秒传入的呼叫数  <br/> |16   <br/> |2   <br/> |
|连接到 IVR 或 MoH 的并发呼叫数  <br/> |480  <br/> |60  <br/> |
|并发的匿名会话数（无 IM）  <br/> |224  <br/> |28  <br/> |
|并发的匿名会话数（具有 IM）  <br/> |64  <br/> |8   <br/> |
|活动代理数（正式和非正式）  <br/> |2400  <br/> |2400  <br/> |
|智能寻线数  <br/> |800  <br/> |800  <br/> |
|IVR 组数（使用语音识别）  <br/> |400  <br/> |400  <br/> |