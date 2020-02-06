---
title: Skype for business 中的电话寄存计划
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
ms.assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
description: 在 Skype for business Server Enterprise Voice 中规划呼叫寄存，这样便可将通话置于保持状态，并将呼叫转移到部门。 包括容量规划、支持的呼叫和支持的客户端。
ms.openlocfilehash: 3effeab4afef60fb7a5021206d9fc3cd0227ceb1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803192"
---
# <a name="plan-for-call-park-in-skype-for-business"></a>Skype for business 中的电话寄存计划
 
在 Skype for business Server Enterprise Voice 中规划呼叫寄存，这样便可将通话置于保持状态，并将呼叫转移到部门。 包括容量规划、支持的呼叫和支持的客户端。
  
"呼叫驻留" 应用程序使企业语音用户可以执行以下操作：
  
- 将呼叫置于保持状态并从同一电话或另一电话取回该呼叫。
    
- 将呼叫置于保持状态，以将其转接到某个部门或常规区域（例如，转接到有公用区域电话的销售部门或仓库）。
    
- 将呼叫置于保持状态，并保持原始应答电话处于空闲状态，以接听其他呼叫。
    
当用户公园通话时，Skype for Business 服务器将呼叫转移到一个称为 "轨道" 的临时号码，在此期间，呼叫将一直保持到已被检索或超时。Skype for Business 服务器将轨道发送给停用呼叫的用户。 用户可以通过拨打该通道号或单击“对话”窗口中的通道链接或按钮来取回寄存的呼叫。 
  
寄存呼叫的用户可以使用外部机制（如即时消息 (IM) 或寻呼系统）通知某人取回呼叫，以向其他人通知该通道号。寄存呼叫的用户可以使“对话”窗口保持打开状态，以在取回呼叫时接收通知。
  
由于轨道范围是全局唯一的，因此，如果路由配置正确，则可以从任何 Skype for Business 服务器站点或 PBX 电话检索呼叫。 如果在可配置的时间内没有人取回呼叫，则呼叫将回拨到寄存它的人。 如果此人不应答回拨电话，呼叫将转接到回退目标，例如接线员（如果这样配置的话）。 可以配置呼叫在转接前的回拨次数（1 到 10 次）。 如果没有人应答转接呼叫，则呼叫将断开连接。 呼叫取回或断开连接后会释放通道。
  
部署呼叫寄存时，您需要为呼叫寄存保留一定范围的分机号。 这些分机应该是虚拟分机：尚未分配任何用户或电话的分机。 然后根据分机号的范围配置呼叫寄存通道表，并指定承载负责处理每个范围的呼叫寄存应用程序的应用程序服务。 每个前端池在对应的后端服务器上都有一个 "呼叫驻留" 表，用于管理池中停用的呼叫。 轨道范围列表存储在中央管理存储中，用于将 "轨道式" 路由到目标池。 部署和配置呼叫驻留应用程序的每个 Skype for business 服务器池都可以有一个或多个轨道范围。 在 Skype for Business 服务器部署中，轨道范围必须全局唯一。 
  
您还可以配置其他呼叫寄存设置，例如当呼叫超时时重定向到什么位置以及寄存时打电话的人是否可以听到音乐。您还可以指定呼叫处于保持状态时播放的音乐文件。
  
> [!NOTE]
> Skype for Business Server 灾难恢复过程中不会备份呼叫寄存的自定义的 "保留式音乐" 文件，如果上载到该池的文件已损坏、损坏或删除，将丢失。 始终保留已为呼叫寄存上载的自定义的保持音乐文件的单独备份副本。 
  
呼叫寄存应用程序是企业语音的一个组件。 部署企业语音时，将自动安装和激活通话寄存应用程序。 但是，在您可以使用呼叫寄存之前，企业语音管理员必须配置它并通过语音策略为用户启用它。
  
## <a name="deployment-and-requirements"></a>部署和要求

部署企业语音时，将自动安装呼叫寄存应用程序。 通过配置语音策略启用呼叫寄存。
  
### <a name="software-requirements"></a>软件要求

部署呼叫驻留的所有前端服务器和标准版服务器必须为运行 Windows Server 2008 R2 的服务器安装 Windows Media Format Runtime，或者为运行 Windows Server 2012 或 Windows Server 的服务器安装 Microsoft Media Foundation2012 R2。 对于 Windows Server 2008 R2，Windows Media 格式运行时作为 Windows 桌面体验的一部分进行安装。 Windows media 音频（.wma）文件需要 windows Media 格式运行时或 Microsoft Media Foundation，这些文件用于调用处于暂停状态的所有音乐的寄存播放。
  
### <a name="port-requirements"></a>端口要求

通话寄存应用程序对 SIP 侦听请求使用**端口 5075** 。
    
> [!NOTE]
> 此端口是默认设置，您可以使用 **Set-CsApplicationServer** cmdlet 对其进行更改。 有关此 cmdlet 的详细信息，请参阅 Lync Server Management Shell 文档。
  
### <a name="audio-file-requirements"></a>音频文件要求

通话寄存应用程序仅支持 Windows Media 音频（.wma）文件用于保留音乐。 您可以使用 Microsoft Expression Encoder 4 来自定义用作保持音乐的文件。 若要下载表达式编码器4，请参阅["表达式编码器 4"](https://go.microsoft.com/fwlink/p/?linkId=202843)。 使用该工具可将文件转换为 .wma 格式。 呼叫寄存音乐保留文件的推荐格式是媒体音频9、44 kHz、16位、单声道、CBR、32 kbps。
  
> [!NOTE]
> 转换后的文件仅以 16 KHz 在电话上播放，即使录制时采用 44 KHz 也是如此。 
  
## <a name="supported-clients-and-calls"></a>支持的客户端和呼叫

呼叫寄存支持以下客户端和呼叫类型
  
### <a name="clients-supported-for-parking-calls"></a>支持寄存呼叫的客户端

可寄存来自任意 IP、专用交换机 (PBX)、公用电话交换网 (PSTN) 或移动电话的呼叫。
  
> [!NOTE]
> 只能寄存音频呼叫。不能寄存即时消息和会议。 
  
以下客户端可使用呼叫寄存拨出寄存呼叫：
  
- Skype for Business
    
- Lync 2013
    
- Lync 2010
    
- Lync 2010 Attendant
    
- Lync Phone Edition
    
> [!NOTE]
> 移动电话无法使用呼叫寄存拨出寄存呼叫。 
  
### <a name="clients-supported-for-retrieving-calls"></a>支持取回呼叫的客户端

将通道范围配置为虚拟分机块（未分配用户或电话的分机）。将通道配置为虚拟分机时，移动电话和 PSTN 电话无法取回寄存的呼叫。
  
联盟用户无法取回寄存的呼叫。
  
以下客户端可以检索寄存在呼叫寄存上的呼叫：
  
- Skype for Business
    
- Lync 2013
    
- Lync 2010
    
- Lync 2010 Attendant
    
- Lync Phone Edition
    
- IP 公用区域电话
    
- 连接到 Skype for Business 服务器基础结构的非 IP 电话，包括常见的区域电话和专用分支交换（PBX）电话
    
## <a name="call-park-capacity-planning"></a>呼叫寄存容量规划

下表介绍了可用作容量规划要求基础的 "呼叫驻留" 用户模型。
  
> [!IMPORTANT]
> 请记住，对于灾难恢复容量规划，配对池的每个池都应该能够处理两个池中的呼叫驻留服务的工作负荷。 
  
**呼叫寄存用户模型**

|**指标**|**每个前端池<br/> （具有8个前端服务器）**|**每台 Standard Edition Server**|
|:-----|:-----|:-----|
|寄存速率  <br/> |每分钟 8 个  <br/> |每分钟 1 个  <br/> |
|取回寄存呼叫的速率  <br/> |每分钟 8 个  <br/> |每分钟 1 个  <br/> |
|平均寄存持续时间  <br/> |60 秒  <br/> |60 秒  <br/> |
   

