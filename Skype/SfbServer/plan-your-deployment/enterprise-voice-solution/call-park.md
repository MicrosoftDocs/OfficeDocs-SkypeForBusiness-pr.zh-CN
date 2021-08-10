---
title: Plan for Call Park in Skype for Business
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
ms.assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
description: 规划呼叫呼叫Skype for Business Server 企业语音，从而允许将呼叫置于保持状态以及将呼叫转接到部门。 包括容量规划、支持的呼叫和支持的客户端。
ms.openlocfilehash: 40f6b08512bd76401a8bb881429737f0da53be952e2774099e82396522b79aeb
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54306863"
---
# <a name="plan-for-call-park-in-skype-for-business"></a>Plan for Call Park in Skype for Business
 
规划呼叫呼叫Skype for Business Server 企业语音，从而允许将呼叫置于保持状态以及将呼叫转接到部门。 包括容量规划、支持的呼叫和支持的客户端。
  
通过呼叫企业语音用户可以执行以下操作：
  
- 将呼叫置于保持状态，然后从同一电话或其他电话检索呼叫。
    
- 将呼叫置于保持状态，以将呼叫转接到部门或 (部门，例如销售部门或具有公用区域电话的) 。
    
- 将呼叫置于保持状态，并保持原始应答电话对于其他呼叫是免费的。
    
当用户取回呼叫时，Skype for Business Server呼叫转接到一个称为通道的临时号码，在此通道中，呼叫将一直持续到取回或时间过长。Skype for Business Server呼叫的用户发送通道。 要检索已呼叫，用户可以拨打通道号码，或单击"对话"窗口中的通道链接或按钮。 
  
通过外部机制（如即时消息 (IM) 或分页系统）将通道号码传达给其他人，可通知呼叫者取回呼叫。 在取回呼叫时，将呼叫保留为"对话"窗口打开以接收通知。
  
由于通道范围是全局唯一的，因此，如果正确配置了路由，Skype for Business Server从任何站点或 PBX 电话取回呼叫。 如果在可配置的一定时间内没有人取回该呼叫，呼叫将回响到该呼叫的接听人。 如果此人未应答回叫，则呼叫将转接到回退目标，例如接线员（如果已配置）。 你可以配置呼叫在从 1 到 10 次转接之前回响次数。 如果没有人应答转接的呼叫，则呼叫将断开连接。 检索或断开呼叫时，将释放通道。
  
部署呼叫保留时，需要保留用于呼叫的分机号码范围。 这些分机需要为虚拟分机：未为其分配用户或电话的分机。 然后，使用分机号码范围配置呼叫托管通道表，并指定哪个应用程序服务托管处理每个范围的呼叫托管应用程序。 每个前端池在相应的后端服务器上都有一个呼叫库表，该表用于管理池中的呼叫。 通道范围列表存储在中央管理存储中，用于将通道路由到目标池。 每个Skype for Business Server部署和配置的呼叫库池都可以有一个或多个通道范围。 通道范围在整个部署中必须Skype for Business Server唯一。 
  
还可以配置其他呼叫离开设置，例如呼叫的重定向位置（如果呼叫时间过长）以及电话上的人在离开时是否听到音乐。 还可以指定呼叫保持时要播放的音乐文件。
  
> [!NOTE]
> 呼叫保留的自定义保持音乐文件不会作为 Skype for Business Server 灾难恢复过程的一部分进行备份，如果上载到池的文件已损坏、损坏或擦除，将丢失。 请始终保留为呼叫保留上载的自定义保持音乐文件的单独备份副本。 
  
呼叫管理应用程序是呼叫企业语音。 在部署企业语音时，会自动安装并激活呼叫管理应用程序。 但是，在可以使用呼叫企业语音，管理员必须通过语音策略配置呼叫企业语音为用户启用它。
  
## <a name="deployment-and-requirements"></a>部署和要求

部署呼叫管理程序时，会自动安装呼叫企业语音。 通过配置语音策略启用呼叫管理。
  
### <a name="software-requirements"></a>软件要求

部署了呼叫库的所有前端服务器和 Standard Edition 服务器必须为运行 Windows Server 2008 R2 的服务器安装 Windows Media Format Runtime，或者为运行 Windows Server 2012 或 Windows Server 2012 R2 的服务器安装 Microsoft Media Foundation。 对于 Windows Server 2008 R2，Windows Media Format Runtime 作为桌面体验的一Windows安装。 Windows媒体格式运行时或 Microsoft Media Foundation 是呼叫Windows播放保持音乐 (.wma) 需要媒体格式运行时或 Microsoft Media Foundation。
  
### <a name="port-requirements"></a>端口要求

呼叫等待应用程序将 **端口 5075**  用于 SIP 侦听请求。
    
> [!NOTE]
> 此端口是默认设置，您可以使用 **Set-CsApplicationServer** cmdlet 对其进行更改。 有关此 cmdlet 的详细信息，请参阅 Lync Server 命令行管理程序文档。
  
### <a name="audio-file-requirements"></a>音频文件要求

呼叫保留应用程序仅支持Windows媒体 (.wma) 保留音乐。 您可以使用 Microsoft Expression Encoder 4 来自定义用作保持音乐的文件。 若要下载 Expression Encoder 4，请参阅["Expression Encoder 4"。](https://go.microsoft.com/fwlink/p/?linkId=202843) 使用此工具将文件转换为 .wma 格式。 呼叫寄存保持音乐文件的建议格式为 Media Audio 9，44 kHz，16 位，单声道，CBR，32 kbps。
  
> [!NOTE]
> 转换后的文件仅以 16 KHz 在电话上播放，即使录制时采用 44 KHz 也是如此。 
  
## <a name="supported-clients-and-calls"></a>支持的客户端和呼叫

呼叫管理支持以下客户端和呼叫类型
  
### <a name="clients-supported-for-parking-calls"></a>支持寄存呼叫的客户端

可寄存来自任意 IP、专用交换机 (PBX)、公用电话交换网 (PSTN) 或移动电话的呼叫。
  
> [!NOTE]
> 只能寄存音频呼叫。不能寄存即时消息和会议。 
  
以下客户端可以使用呼叫管理来呼叫的呼叫：
  
- Skype for Business
    
- Lync 2013
    
- Lync 2010
    
- Lync 2010 Attendant
    
- Lync Phone Edition
    
> [!NOTE]
> 移动电话不能使用呼叫管理来呼叫。 
  
### <a name="clients-supported-for-retrieving-calls"></a>支持取回呼叫的客户端

将通道范围配置为虚拟分机块（未分配用户或电话的分机）。将通道配置为虚拟分机时，移动电话和 PSTN 电话无法取回寄存的呼叫。
  
联盟用户无法取回寄存的呼叫。
  
以下客户端可以检索在呼叫 Park 上所呼叫的呼叫：
  
- Skype for Business
    
- Lync 2013
    
- Lync 2010
    
- Lync 2010 Attendant
    
- Lync Phone Edition
    
- IP 公用区域电话
    
- 连接到专用交换机基础结构的非 IP Skype for Business Server，包括公用区域电话和 PBX 专用交换机 (PBX) 电话
    
## <a name="call-park-capacity-planning"></a>呼叫管理容量规划

下表介绍了可以用作容量规划要求基础的呼叫等待用户模型。
  
> [!IMPORTANT]
> 请记住，对于灾难恢复容量规划，配对池的每个池都应能够处理这两个池中的呼叫呼叫保留服务的工作负荷。 
  
**呼叫寄存用户模型**

|**跃点数**|**每个前端池  <br/>  (8 台前端服务器)**|**每台 Standard Edition Server**|
|:-----|:-----|:-----|
|寄存速率  <br/> |每分钟 8 个  <br/> |每分钟 1 个  <br/> |
|取回寄存呼叫的速率  <br/> |每分钟 8 个  <br/> |每分钟 1 个  <br/> |
|平均寄存持续时间  <br/> |60 秒  <br/> |60 秒  <br/> |
   

