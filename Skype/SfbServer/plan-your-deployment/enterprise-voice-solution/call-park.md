---
title: 在 Skype for Business 2015 中规划呼叫寄存
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
ms.assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
description: 规划在 Skype 呼叫公园的业务服务器企业语音，这样使调用保留并将呼叫转接到部门。 包括容量规划、支持的呼叫和支持的客户端。
ms.openlocfilehash: 6198b54a93c36c2e6a2fcd28fa91f51c43fb59de
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-call-park-in-skype-for-business-2015"></a>在 Skype for Business 2015 中规划呼叫寄存
 
规划在 Skype 呼叫公园的业务服务器企业语音，这样使调用保留并将呼叫转接到部门。 包括容量规划、支持的呼叫和支持的客户端。
  
调用公园应用程序启用企业语音用户，请执行下列操作：
  
- 将呼叫置于保持状态并从同一电话或另一电话取回该呼叫。
    
- 将呼叫置于保持状态，以将其转接到某个部门或常规区域（例如，转接到有公用区域电话的销售部门或仓库）。
    
- 将呼叫置于保持状态，并保持原始应答电话处于空闲状态，以接听其他呼叫。
    
当用户公园 Skype 业务服务器的调用，将传输调用一个称为轨道中，检索或超时之前调用地点的临时数字。Skype 业务服务器发送到停呼叫的用户运行轨道。 用户可以通过拨打该通道号或单击“对话”窗口中的通道链接或按钮来取回寄存的呼叫。 
  
寄存呼叫的用户可以使用外部机制（如即时消息 (IM) 或寻呼系统）通知某人取回呼叫，以向其他人通知该通道号。寄存呼叫的用户可以使“对话”窗口保持打开状态，以在取回呼叫时接收通知。
  
由于轨道范围是全局唯一的就可以从任何业务服务器站点或 PBX 电话 Skype 检索调用，如果路由配置正确。 如果在可配置的时间内没有人取回呼叫，则呼叫将回拨到寄存它的人。 如果此人不应答回拨电话，呼叫将转接到回退目标，例如接线员（如果这样配置的话）。 可以配置呼叫在转接前的回拨次数（1 到 10 次）。 如果没有人应答转接呼叫，则呼叫将断开连接。 呼叫取回或断开连接后会释放通道。
  
部署呼叫寄存时，您需要为呼叫寄存保留一定范围的分机号。 这些分机应该是虚拟分机：尚未分配任何用户或电话的分机。 然后根据分机号的范围配置呼叫寄存通道表，并指定承载负责处理每个范围的呼叫寄存应用程序的应用程序服务。 每个前端池中有一个调用公园表上相应后端服务器，用于管理在池停的呼叫。 轨道范围的列表存储在集中管理存储并被用来传送给目标池的轨道。 每个 Skype 业务服务器池公园调用应用程序在部署和配置可以有一个或多个运行轨道范围。 对于业务服务器部署 Skype 轨道范围必须全局唯一。 
  
您还可以配置其他呼叫寄存设置，例如当呼叫超时时重定向到什么位置以及寄存时打电话的人是否可以听到音乐。您还可以指定呼叫处于保持状态时播放的音乐文件。
  
> [!NOTE]
> 自定义的音乐上保留文件调用公园未备份的 Skype 业务服务器的灾难恢复过程的一部分，将会丢失，如果将文件上载到该池被破坏、 损坏或删除。 始终保留已为呼叫寄存上载的自定义的保持音乐文件的单独备份副本。 
  
呼叫寄存应用程序是企业语音的一个组件。 当您部署企业语音时，调用公园应用程序安装，并自动激活。 可以使用调用公园之前，但是，企业语音管理员必须配置它并使其用户通过语音策略。
  
## <a name="deployment-and-requirements"></a>部署和要求

当您部署企业语音，调用公园应用程序将自动安装。 您可以通过配置语音策略启用调用公园。
  
### <a name="software-requirements"></a>软件要求

调用公园的部署位置的所有前端服务器和标准版服务器必须运行 Windows Server 2012 或 Windows 服务器的服务器中运行 Windows Server 2008 R2 或 Microsoft 媒体基础的服务器安装的 Windows 媒体格式运行时2012 R2。 对于 Windows Server 2008 R2，Windows 媒体格式运行时安装作为 Windows 桌面体验的一部分。 Windows 媒体格式运行时或 Microsoft 媒体基础是 Windows Media 音频 (.wma) 文件需要调用公园播放音乐暂候状态。
  
### <a name="port-requirements"></a>端口要求

调用公园应用程序使用**端口 5075** SIP 侦听请求。
    
> [!NOTE]
> 此端口是通过**设置 CsApplicationServer** cmdlet 可以更改默认设置。 此 cmdlet 的详细信息，请参阅 Lync 服务器管理外壳程序文档。
  
### <a name="audio-file-requirements"></a>音频文件要求

保存应用程序仅支持 Windows Media 音频 (.wma) 文件的音乐调用公园。 您可以使用 Microsoft Expression Encoder 4 来自定义用作保持音乐的文件。 若要下载表达式编码器 4，请参阅["表达式编码器 4"](https://go.microsoft.com/fwlink/p/?linkId=202843)。 使用该工具可将文件转换为 .wma 格式。 建议的调用公园音乐上保留文件的格式是媒体音频 9、 44 kHz，16 位，单声道，CBR，32 kbps 速率进行传输。
  
> [!NOTE]
> 转换后的文件仅以 16 KHz 在电话上播放，即使录制时采用 44 KHz 也是如此。 
  
## <a name="supported-clients-and-calls"></a>支持的客户端和呼叫

支持调用公园下面的客户端和调用的类型
  
### <a name="clients-supported-for-parking-calls"></a>支持寄存呼叫的客户端

可寄存来自任意 IP、专用交换机 (PBX)、公用电话交换网 (PSTN) 或移动电话的呼叫。
  
> [!NOTE]
> 只能寄存音频呼叫。不能寄存即时消息和会议。 
  
下列客户端可以使用调用公园到公园的呼叫：
  
- Skype for Business
    
- Lync 2013
    
- Lync 2010
    
- Lync 2010 Attendant
    
- Lync Phone Edition
    
> [!NOTE]
> 手机不能使用调用公园到公园的呼叫。 
  
### <a name="clients-supported-for-retrieving-calls"></a>支持取回呼叫的客户端

将通道范围配置为虚拟分机块（未分配用户或电话的分机）。将通道配置为虚拟分机时，移动电话和 PSTN 电话无法取回寄存的呼叫。
  
联盟用户无法取回寄存的呼叫。
  
下列客户端可以检索调用停车场停的调用：
  
- Skype for Business
    
- Lync 2013
    
- Lync 2010
    
- Lync 2010 Attendant
    
- Lync Phone Edition
    
- IP 公用区域电话
    
- 非 IP 电话连接到企业服务器基础架构，包括公共区域电话和专用分组交换机 (PBX) 电话 Skype
    
## <a name="call-park-capacity-planning"></a>呼叫寄存容量规划

下表描述了可用作容量规划需求基础的调用公园用户模型。
  
> [!IMPORTANT]
> 请记住，对于灾难恢复产能规划，成对池中每个池应该能够处理调用公园服务这两个池中的工作负载。 
  
**调用公园用户模型**

|**跃点计数**|**每个前端池<br/>（带有 8 前端服务器）**|**每个标准版服务器**|
|:-----|:-----|:-----|
|寄存速率  <br/> |每分钟 8 个  <br/> |每分钟 1 个  <br/> |
|取回寄存呼叫的速率  <br/> |每分钟 8 个  <br/> |每分钟 1 个  <br/> |
|平均寄存持续时间  <br/> |60 秒  <br/> |60 秒  <br/> |
   

