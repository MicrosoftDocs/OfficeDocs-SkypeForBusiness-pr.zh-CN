---
title: 在 Skype for Business 服务器中规划响应组应用程序
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6cc333e7-4029-4372-86b2-016040c415fb
description: 在 Skype for Business Server Enterprise Voice 中规划响应组, 这使你可以设置到用户组的呼叫路由。 包括音频文件要求。
ms.openlocfilehash: b1c8a2ab1a7dc42fd290df4bdc1ccf69b52db43a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276466"
---
# <a name="plan-for-the-response-group-application-in-skype-for-business-server"></a>在 Skype for Business 服务器中规划响应组应用程序

在 Skype for Business Server Enterprise Voice 中规划响应组, 这使你可以设置到用户组的呼叫路由。 包括音频文件要求。

如果您的组织有多个用户组, 他们可以回答和管理某些类型的呼叫 (例如客户服务、内部技术支持或部门的常规电话支持), 则可以部署响应组应用程序来管理这些类型的呼叫。 响应组应用程序将传入呼叫路由和排队给称为代理的指定人员。 您可以通过响应组来增加电话支持服务的使用并降低运行这些服务的开销。

当呼叫者呼叫响应组时，呼叫会基于智能寻线或呼叫者对互动语音响应 (IVR) 问题的回答路由至代理。 "响应组" 应用程序使用标准响应组路由方法将呼叫路由到下一个可用的代理。 支持的呼叫路由方法包括串行、最长闲置、并行、循环以及助理路由（即每次传入呼叫时都将同时呼叫所有代理，无论其当前状态如何）。

如果没有可用的代理，呼叫将保留在一个队列中，直到代理可用为止。在队列中时，呼叫者将听到音乐，直到可用代理接受呼叫为止。如果队列已满，或者呼叫在队列中已超时，则呼叫者可能会听到一则消息，然后呼叫将断开连接或转接到其他目标，例如其他电话号码或语音信箱。当代理接受呼叫时，呼叫者可能会（也可能不会）看到代理的身份，具体取决于管理员如何配置响应组。代理可以是正式的，这意味着他们必须登录到组，然后才能接受路由至该组的呼叫；也可以是非正式的，这意味着他们无需登录到组，在组外即可接受呼叫。

> [!NOTE]
> 仅本地用户可成为代理。 如果代理从本地移动到联机, 则响应组调用将不会路由到该代理。

> [!NOTE]
> 响应组应用程序使用名为 "匹配" 的内部服务对呼叫进行排队和查找可用的代理。 运行响应组应用程序的每台计算机运行的是 "匹配" 服务, 但每个池的服务一次仅有一个匹配项, 而另一个是被动。 如果在计划外中断期间，活动 Match Making 服务变得不可用，则某一个非活动 Match Making 服务将变成活动状态。 响应组应用程序最适合确保呼叫路由和队列继续不间断。 但是，当转换 Match Making 服务时，会丢失此时正在传输的所有呼叫。 例如, 如果由于前端服务器出现故障而导致的转换, 则当前由活动的匹配进行的任何通话将在该前端服务器上提供服务也将丢失。

## <a name="response-group-workflows"></a>响应组工作流

工作流定义了从电话响铃到有人接听电话这段时间内呼叫的行为。工作流指定用于保留呼叫的队列，并指定用于智能寻线的路由方法或用于互动响应组的问题和答案。工作流还定义了诸如欢迎消息、保持音乐、工作时间和假日等设置。

> [!NOTE]
> 必须先创建代理组和队列，然后再创建使用这些组和队列的工作流。

## <a name="management-of-response-groups"></a>响应组的管理

在 Skype for Business 服务器中, 有两个管理角色可用于管理响应组: "响应组管理器" 和 "响应组管理员"。 响应组管理员可以管理任何响应组的任何方面。 响应组管理器只能管理某些方面, 并且仅可管理其拥有的响应组。 经理角色可帮助您减少管理费用, 因为您可以将有限的特定响应组的责任委派给任何已启用企业语音的用户。 注意，用户可以同时是响应组 Manager 和响应组 Administrator。

为了适应经理角色, 响应组应用程序使用托管或非托管的**工作流类型**。 下表介绍了托管响应组和非托管响应组。

**托管响应组和非托管响应组**

|**响应组类型**|**说明**|
|:-----|:-----|
|非托管  <br/> | 非托管响应组未分配有 Manager。 只有响应组管理员可以配置这些响应组。 <br/>  多个非托管响应组可共享一个队列或代理组。 <br/>  将响应组从以前的版本迁移到 Skype for business 服务器时, 类型将设置为 "未管理"。 <br/> |
|托管  <br/> | 响应组管理员可以配置托管响应组的任何方面。 <br/>  响应组管理器无法查看或修改未明确分配给它们的响应组。 <br/>  响应组管理器只能为显式分配给它们的响应组配置某些设置。 <br/>  托管响应组无法与任何其他响应组（托管或非托管）共享任何队列或代理组。 <br/> |

下表介绍了对于分配给他们的响应组, 响应组管理器可以执行和不能执行的操作。

**响应组 Manager 功能**

|**可以配置：**|**可以创建、删除或配置：**|**无法：**|
|:-----|:-----|:-----|
| 代理 <br/>  欢迎消息 <br/>  响应组名称 <br/>  说明 <br/>  显示号码 <br/>  工作时间 <br/>  保持音乐 <br/>  状态（活动/非活动） <br/>  智能寻线工作流和互动语音响应 (IVR) 工作流 <br/> | 代理组 <br/>  队列 <br/>  假日集 <br/> | 创建或删除任意类型的工作流 <br/>  修改核心响应组设置，如：“**SIP URI**”、“**电话号码**”或“**工作流类型**”。  <br/> |

响应组管理员可以使用以下工具管理其指定的响应组。

- Skype for Business Server 控制面板

    > [!NOTE]
    > 响应组管理器仅可通过此工具管理响应组设置。 其他 Skype for Business 服务器设置对经理不可用。

- 响应组配置工具

- Skype for Business Server 管理程序

响应组可以很好地扩展到部门或工作组环境 (有关详细信息, 请参阅针对[响应组的容量规划](https://technet.microsoft.com/library/a2459a69-1f45-4f2f-bca5-d4f442708e44.aspx)), 并且可以在全新的电话安装中部署。 它支持来自企业语音部署和本地运营商网络的传入呼叫。 工程师可以使用 Skype for Business、Lync 2013、Lync 2010、Lync 2010 助理或 Lync Phone Edition 将呼叫传送给他们。

## <a name="deployment-and-requirements"></a>部署和要求

部署企业语音时, 将自动启用响应组应用程序。

### <a name="hardware-and-software-requirements"></a>硬件和软件要求

响应组应用程序具有与前端服务器相同的硬件要求、操作系统要求和软件先决条件。

如果将 Windows Media 音频 (.wma) 文件用于响应组音乐和通知, 则所有前端服务器或运行响应组应用程序的标准版服务器必须为运行 Windows 的服务器安装 Windows Media 格式运行时服务器 2008 R2 或 Microsoft Media Foundation for 运行 Windows Server 2012 或 Windows Server 2012 R2 的服务器。 对于 Windows Server 2008 R2, Windows Media 格式运行时作为 Windows 桌面体验的一部分进行安装。

响应组使用**语言包**支持文本到语音转换和语音识别。 配置消息（例如欢迎消息以及其他提示、互动语音响应 (IVR) 问题和答案）时，会使用这些语音技术。 默认情况下, 在部署 Skype for Business 服务器时会安装26个受支持的语言包。

### <a name="port-requirements"></a>端口要求

响应组应用程序使用以下端口:

- 用于 SIP 侦听请求的**端口 5071**

- 用于 interserver 通信的**端口 8404**

    > [!NOTE]
    > 此端口用于匹配 "正在进行" 服务, 并且当响应组应用程序部署在具有多个前端服务器的池中时, 此端口是必需的。

   > [!NOTE]
   > 这些端口是默认设置，您可以使用 **Set-CsApplicationServer** cmdlet 更改。 有关此 cmdlet 的详细信息, 请参阅 Skype for Business 服务器管理外壳文档。

### <a name="audio-file-requirements"></a>音频文件要求

响应组应用程序支持波形 (.wav) 文件格式和 Windows Media 音频 (.wma) 文件格式, 用于响应组消息、保留音乐或交互式语音响应 (IVR) 问题。

Windows Media 音频文件格式要求 Windows Media 格式运行时安装在运行 Windows Server 2008 R2 和 Windows Server 2008 的前端服务器上。 有关详细信息，请参阅上文中的“软件要求”。

#### <a name="supported-wave-file-formats"></a>支持的 Wave 文件格式

所有 wave 文件必须符合以下要求：

- 8 位或 16 位文件

- 线性脉冲编码调制 (LPCM)，A-Law 或 mu-Law 格式

- 单声道或立体声

- 4 MB 或更小

为获得 wave 文件的最佳性能，建议使用 16 kHz、单声道、16 位的 wave 文件。

#### <a name="supported-windows-media-audio-file-formats"></a>支持的 Windows Media 音频文件格式

如果使用 Windows Media 音频文件，请考虑使用较低的比特率，并验证负载下的系统性能。

您可以使用 Microsoft Expression Encoder 4 将文件转换为 Windows Media 音频格式。 若要下载表达式编码器 4, [https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkId=202843)请参阅。

### <a name="response-group-configuration-tool-requirements"></a>响应组配置工具要求

"响应组配置" 工具支持下表中所述的操作系统和 web 浏览器的组合。

> [!NOTE]
> 支持 32 位或 64 位版本的操作系统。 仅支持 32 位版本的 Internet Explorer。

**支持的操作系统和 Web 浏览器**

|**操作系统**|**Web 浏览器**|
|:-----|:-----|
|Windows Vista Service Pack (SP) 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8（本机模式）  <br/> Internet Explorer 9（本机模式）  <br/> |
|Windows 7  <br/> Windows 7 Service Pack 1  <br/> |Internet Explorer 8（本机模式）  <br/> Internet Explorer 9（本机模式）  <br/> |
|Windows Server 2008 Service Pack 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8（本机模式）  <br/> Internet Explorer 9（本机模式）  <br/> |
|Windows Server 2008 R2  <br/> Windows Server 2008 R2 Service Pack 1  <br/> |Internet Explorer 8（本机模式）  <br/> Internet Explorer 9（本机模式）  <br/> |
|Windows Server 2012  <br/> ||
|Windows Server 2012 R2  <br/> ||

### <a name="response-group-agent-console"></a>响应组代理控制台

此代理控制台支持下表所述的操作系统和 Web 浏览器的组合。

> [!NOTE]
> 支持 32 位或 64 位版本的操作系统。仅支持 32 位版本的 Internet Explorer。

**支持的操作系统和 Web 浏览器**

|**操作系统**|**Web 浏览器**|
|:-----|:-----|
|Windows Vista Service Pack (SP) 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8（本机模式）  <br/> Internet Explorer 9（本机模式）  <br/> |
|Windows 7  <br/> Windows 7 Service Pack 1  <br/> |Internet Explorer 8（本机模式）  <br/> Internet Explorer 9（本机模式）  <br/> Firefox 10.0  <br/> Chrome 18.0  <br/> |
|Windows Server 2008 Service Pack 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8（本机模式）  <br/> Internet Explorer 9（本机模式）  <br/> |
|Windows Server 2008 R2  <br/> Windows Server 2008 R2 Service Pack 1  <br/> |Internet Explorer 8（本机模式）  <br/> Internet Explorer 9（本机模式）  <br/> Firefox 10.0  <br/> Chrome 18.0  <br/> |
|Windows Server 2012  <br/> |
|Windows Server 2012 R2  <br/> |

## <a name="client-support"></a>客户端支持

响应组应用程序支持下列客户端:

- Skype for Business 桌面客户端

- Lync 2013 桌面客户端

- Lync 2010 桌面客户端

- Lync 2010 Attendant

- Office Communications Server 2007 R2 Attendant

- Lync Phone Edition

> [!NOTE]
> Lync 移动客户端不支持响应组应用程序。

你可以使用的特定客户端取决于你所使用的响应组用户的类型:

- **呼叫者**可使用前面列出的任何客户端和公用电话交换网 (PSTN) 上的标准电话来呼叫响应组。

- **非正式代理**(未登录和注销其组以接受呼叫的代理) 可通过使用助理、Lync 或 Lync Phone Edition 接受呼叫。 当使用其中一个客户端登录到 Skype for business 服务器时, 非正式代理会自动登录其组。

- **正式代理**(必须登录和注销其组才能接受呼叫) 的代理可以使用 Skype for Business 接受呼叫, 并从菜单项访问代理控制台, 或者使用助理直接从 Internet Explorer 访问代理控制台。

## <a name="capacity-planning"></a>容量规划

下表介绍了可用作容量计划要求基础的 "响应组" 用户模型。

> [!NOTE]
> 下表中的数值假定所有响应组音频文件使用的是 16 kHz、单声道、16 位的 Wave (.wav) 文件。如果使用其他文件格式（如 Windows Media 音频 (.wma)），则数值可能会有所不同。

> [!IMPORTANT]
> 请记住，对于灾难恢复容量规划，一对池中的每一个池都应能处理这两个池中的所有响应组的工作负荷。

**响应组用户模型**

|**指标**|**每个企业版<br/>池 (具有8个前端服务器)**|**每台 Standard Edition Server**|
|:-----|:-----|:-----|
|每秒传入的呼叫数  <br/> |utf-16  <br/> |2  <br/> |
|连接到 IVR 或 MoH 的并发呼叫数  <br/> |480  <br/> |60  <br/> |
|并发的匿名会话数（无 IM）  <br/> |224  <br/> |28  <br/> |
|并发的匿名会话数（具有 IM）  <br/> |64  <br/> |个  <br/> |
|活动代理数（正式和非正式）  <br/> |2400  <br/> |2400  <br/> |
|智能寻线数  <br/> |800  <br/> |800  <br/> |
|IVR 组数（使用语音识别）  <br/> |400  <br/> |400  <br/> |


