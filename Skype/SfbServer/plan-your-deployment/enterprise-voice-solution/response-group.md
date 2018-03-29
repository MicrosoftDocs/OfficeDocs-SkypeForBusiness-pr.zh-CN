---
title: 在Skype for Business Server 2015 中规划响应组应用程序
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 6cc333e7-4029-4372-86b2-016040c415fb
description: 规划在 Skype 的响应组的业务服务器企业语音，它使您可以设置呼叫路由到用户组。 包括音频文件要求。
ms.openlocfilehash: 67b86d6dd15d6dece05261f216c114b377ea3f07
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-the-response-group-application-in-skype-for-business-server-2015"></a>在Skype for Business Server 2015 中规划响应组应用程序
 
规划在 Skype 的响应组的业务服务器企业语音，它使您可以设置呼叫路由到用户组。 包括音频文件要求。
  
如果您的组织具有的回答和管理某些类型的调用用户组，如客户服务、 内部帮助台或一个部门，对于一般的电话支持可以部署响应组应用程序来管理这些类型的调用。 应用程序路由，并排队传入呼叫响应组指定人员称为代理。 您可以通过响应组来增加电话支持服务的使用并降低运行这些服务的开销。
  
当呼叫者呼叫响应组时，呼叫会基于智能寻线或呼叫者对互动语音响应 (IVR) 问题的回答路由至代理。 响应组应用程序使用标准响应组路由方法将路由到下一个可用代理调用。 支持的呼叫路由方法包括串行、最长闲置、并行、循环以及助理路由（即每次传入呼叫时都将同时呼叫所有代理，无论其当前状态如何）。 
  
如果没有可用的代理，呼叫将保留在一个队列中，直到代理可用为止。在队列中时，呼叫者将听到音乐，直到可用代理接受呼叫为止。如果队列已满，或者呼叫在队列中已超时，则呼叫者可能会听到一则消息，然后呼叫将断开连接或转接到其他目标，例如其他电话号码或语音信箱。当代理接受呼叫时，呼叫者可能会（也可能不会）看到代理的身份，具体取决于管理员如何配置响应组。代理可以是正式的，这意味着他们必须登录到组，然后才能接受路由至该组的呼叫；也可以是非正式的，这意味着他们无需登录到组，在组外即可接受呼叫。
  
> [!NOTE]
> 仅本地用户可成为代理。 如果代理从内部移动到在线，响应组调用不会将路由到该代理。 
  
> [!NOTE]
> 响应组应用程序使用名为匹配进行，内部服务调用进行排队并查找可用的代理。 运行响应组应用程序的每台计算机运行的匹配进行服务，但只有一次-每个池中的一个匹配项进行服务活动是被动。 如果在计划外中断期间，活动 Match Making 服务变得不可用，则某一个非活动 Match Making 服务将变成活动状态。 应用程序响应组会尽全力确保该呼叫路由和队列继续不间断。 但是，当转换 Match Making 服务时，会丢失此时正在传输的所有呼叫。 例如，如果转换是由于前端服务器在不断减少，当前正在处理的活动上，匹配进行服务调用任何前端服务器也会丢失。 
  
## <a name="response-group-workflows"></a>响应组工作流

工作流定义了从电话响铃到有人接听电话这段时间内呼叫的行为。工作流指定用于保留呼叫的队列，并指定用于智能寻线的路由方法或用于互动响应组的问题和答案。工作流还定义了诸如欢迎消息、保持音乐、工作时间和假日等设置。
  
> [!NOTE]
> 必须先创建代理组和队列，然后再创建使用这些组和队列的工作流。 
  
## <a name="management-of-response-groups"></a>响应组的管理

在业务服务器的 Skype，两种管理角色是可用于管理响应组： 响应组经理并响应组管理员。 响应组管理员可以管理任何响应组的任何方面。 响应组管理员可以管理仅某些方面和他们拥有的仅用于响应的组。 经理角色可以帮助您降低管理成本，因为您可以委派特定响应组的所有用户启用了企业语音有限的责任。 注意，用户可以同时是响应组 Manager 和响应组 Administrator。 
  
为了适应经理角色，响应组的应用程序，请使用托管或非托管的**工作流类型**。 下表介绍了托管响应组和非托管响应组。
  
**托管和非托管响应组**

|**响应组类型**|**说明**|
|:-----|:-----|
|非托管  <br/> | 非托管响应组未分配有 Manager。 只有响应组管理员可以配置这些响应组。 <br/>  多个非托管响应组可共享一个队列或代理组。 <br/>  迁移时响应组从以前版本到 Skype 业务服务器，则将类型设置为非托管。 <br/> |
|托管  <br/> | 响应组管理员可以配置托管的响应任何的组方面。 <br/>  响应组管理员无法查看或修改未向其明确分派的响应组。 <br/>  响应组管理员可以配置为向其明确分派响应组的某些设置。 <br/>  托管响应组无法与任何其他响应组（托管或非托管）共享任何队列或代理组。 <br/> |
   
下表描述响应组经理可以和不能对分配给它们的响应组执行的操作。
  
**响应组管理器功能**

|**可以配置：**|**可以创建、 删除或配置：**|**不能：**|
|:-----|:-----|:-----|
| 代理 <br/>  欢迎消息 <br/>  响应组名称 <br/>  说明 <br/>  显示号码 <br/>  工作时间 <br/>  保持音乐 <br/>  状态（活动/非活动） <br/>  智能寻线工作流和互动语音响应 (IVR) 工作流 <br/> | 代理组 <br/>  队列 <br/>  假日集 <br/> | 创建或删除任意类型的工作流 <br/>  修改核心响应组设置，如：“**SIP URI**”、“**电话号码**”或“**工作流类型**”。  <br/> |
   
响应组管理员可以使用以下工具来管理其指定的响应组。 
  
- Skype for Business Server 控制面板
    
    > [!NOTE]
    > 响应组管理员只能管理响应组设置使用此工具。 其他 Skype 业务服务器设置不是对经理可用。 
  
- 响应组配置工具
    
- Skype for Business Server 管理程序
    
很好地适应部门响应组扩展或工作组环境 （有关详细信息，请参阅[响应组的容量计划](http://technet.microsoft.com/library/a2459a69-1f45-4f2f-bca5-d4f442708e44.aspx)） 和可以部署在全新安装中电话服务。 它支持从企业语音部署和本地运营商网络的传入呼叫。 代理可以使用 Skype 业务、 Lync 2013，Lync 2010，Lync 2010 助理，或 Lync 电话版才能调用传递给他们。
  
## <a name="deployment-and-requirements"></a>部署和要求

在部署企业语音时，会自动启用响应组应用程序。
  
### <a name="hardware-and-software-requirements"></a>硬件和软件要求

响应组应用程序作为前端服务器具有相同的硬件要求、 系统要求和必备软件。 
  
如果您使用 Windows Media 音频 (.wma) 文件响应组音乐和公告，运行响应组应用程序的所有前端服务器或标准版服务器必须运行 Windows 的服务器上安装的 Windows 媒体格式运行时Server 2008 R2 或运行 Windows Server 2012 或 Windows Server 2012 R2 的服务器的 Microsoft 媒体基础。 对于 Windows Server 2008 R2，Windows 媒体格式运行时安装作为 Windows 桌面体验的一部分。
  
响应组使用**语言包**支持文本到语音转换和语音识别。 配置消息（例如欢迎消息以及其他提示、互动语音响应 (IVR) 问题和答案）时，会使用这些语音技术。 默认情况下，26 支持的语言包安装业务服务器部署 Skype 时。
  
### <a name="port-requirements"></a>端口要求

该响应组应用程序使用以下端口：
  
- SIP 侦听请求的**端口 5071**
    
- 用于服务器间通信的**端口 8404**
    
    > [!NOTE]
    > 此端口用于匹配进行服务，在有多个前端服务器的池中部署响应组应用程序时需要。 
  
   > [!NOTE]
   > 这些端口是通过**设置 CsApplicationServer** cmdlet 可以更改的默认设置。 此 cmdlet 的详细信息，请参阅有关业务服务器管理外壳程序文档 Skype。
  
### <a name="audio-file-requirements"></a>音频文件要求

响应组应用程序支持波形 (.wav) 文件格式和 Windows Media 音频 (.wma) 文件格式的邮件响应分组、 暂挂音乐或交互式语音响应 (IVR) 问题。
  
Windows Media 音频文件格式要求前端服务器运行 Windows Server 2008 R2 和 Windows Server 2008 上安装了 Windows 媒体格式运行时。 有关详细信息，请参阅上文中的“软件要求”。
  
#### <a name="supported-wave-file-formats"></a>支持的 Wave 文件格式

所有 wave 文件必须符合以下要求：
  
- 8 位或 16 位文件
    
- 线性脉冲编码调制 (LPCM)，A-Law 或 mu-Law 格式
    
- 单声道或立体声
    
- 4 MB 或更小
    
为获得 wave 文件的最佳性能，建议使用 16 kHz、单声道、16 位的 wave 文件。 
  
#### <a name="supported-windows-media-audio-file-formats"></a>支持的 Windows Media 音频文件格式

如果使用 Windows Media 音频文件，请考虑使用较低的比特率，并验证负载下的系统性能。
  
您可以使用 Microsoft Expression Encoder 4 将文件转换为 Windows Media 音频格式。 若要下载表达式编码器 4，请参阅[https://go.microsoft.com/fwlink/p/?linkId=202843](https://go.microsoft.com/fwlink/p/?linkId=202843)。
  
### <a name="response-group-configuration-tool-requirements"></a>响应组配置工具要求

响应组配置工具支持操作系统和下表中描述的 web 浏览器的组合。
  
> [!NOTE]
> 支持 32 位或 64 位版本的操作系统。仅支持 32 位版本的 Internet Explorer。 
  
**支持的操作系统和 Web 浏览器**

|**操作系统**|**Web 浏览器**|
|:-----|:-----|
|Windows Vista Service Pack (SP) 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8（本机模式）  <br/> Internet Explorer 9（本机模式）  <br/> |
|Windows 7  <br/> Windows 7 Service Pack 1  <br/> |Internet Explorer 8（本机模式）  <br/> Internet Explorer 9（本机模式）  <br/> |
|Windows Server 2008 Service Pack 2  <br/> |Internet Explorer 7  <br/> Internet Explorer 8（本机模式）  <br/> Internet Explorer 9（本机模式）  <br/> |
|Windows Server 2008 R2  <br/> Windows Server 2008 R2 Service Pack 1  <br/> |Internet Explorer 8（本机模式）  <br/> Internet Explorer 9（本机模式）  <br/> |
|Windows Server 2012  <br/> ||
|Windows Server 2012 R2  <br/> ||
|||
   
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

该响应组应用程序支持下列客户端：
  
- Skype 业务桌面客户端
    
- Lync 2013 桌面客户端
    
- Lync 2010 桌面客户端
    
- Lync 2010 Attendant
    
- Office Communications Server 2007 R2 Attendant
    
- Lync Phone Edition
    
> [!NOTE]
> Lync 移动客户端不支持响应组应用程序。 
  
特定的客户端，您可以使用取决于您的响应组用户的类型： 
  
- **呼叫者**可使用前面列出的任何客户端和公用电话交换网 (PSTN) 上的标准电话来呼叫响应组。
    
- **非正式的代理**（不要对签名和他们组接受调用代理） 可以通过使用助理、 Lync 或 Lync 电话版接受呼叫。 当他们登录 Skype 业务服务器使用这些客户端之一时，自动签名非正式代理其分组。
    
- **正式代理**通过使用 Skype 业务和访问代理控制台菜单项，或通过使用助理并访问代理控制台直接从 Internet Explorer （必须签署其组进出接受调用代理） 可以接受呼叫。
    
## <a name="capacity-planning"></a>容量规划

下表介绍了可用作容量规划需求基础的响应组用户模型。
  
> [!NOTE]
> 下表中的数值假定所有响应组音频文件使用的是 16 kHz、单声道、16 位的 Wave (.wav) 文件。如果使用其他文件格式（如 Windows Media 音频 (.wma)），则数值可能会有所不同。 
  
> [!IMPORTANT]
> 请记住，对于灾难恢复容量规划，一对池中的每一个池都应能处理这两个池中的所有响应组的工作负荷。 
  
**响应组的用户模型**

|**跃点计数**|**每个企业版池<br/>（与 8 前端服务器）**|**每个标准版服务器**|
|:-----|:-----|:-----|
|每秒传入的呼叫数  <br/> |16  <br/> |2  <br/> |
|连接到 IVR 或 MoH 的并发呼叫数  <br/> |480  <br/> |60  <br/> |
|并发的匿名会话数（无 IM）  <br/> |224  <br/> |28  <br/> |
|并发的匿名会话数（具有 IM）  <br/> |64  <br/> |8  <br/> |
|活动代理数（正式和非正式）  <br/> |2400  <br/> |2400  <br/> |
|智能寻线数  <br/> |800  <br/> |800  <br/> |
|IVR 组数（使用语音识别）  <br/> |400  <br/> |400  <br/> |
   

