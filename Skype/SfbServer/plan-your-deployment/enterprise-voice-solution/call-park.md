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
description: 在 Skype for Business Server 企业语音中规划呼叫企业语音，从而将呼叫置于保持状态，以及将呼叫转接到部门。 包括容量规划、支持的呼叫和支持的客户端。
ms.openlocfilehash: c324e8d61f6d0e9e67870f05597a9157965a3eb3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825922"
---
# <a name="plan-for-call-park-in-skype-for-business"></a>Plan for Call Park in Skype for Business
 
在 Skype for Business Server 企业语音中规划呼叫企业语音，从而将呼叫置于保持状态，以及将呼叫转接到部门。 包括容量规划、支持的呼叫和支持的客户端。
  
呼叫企业语音使用户可以执行以下操作：
  
- 将呼叫置于保持状态，然后从同一电话或其他电话检索呼叫。
    
- 将呼叫置于保留状态，以将呼叫转接到部门或 (区域，例如，销售部门或有公用区域电话) 。
    
- 将呼叫置于保持状态，并保持原始应答电话对于其他呼叫是免费的。
    
当用户拨打呼叫时，Skype for Business Server 将呼叫转接到一个称为通道的临时号码，在此通道中，呼叫将一直持续到取回或取回时间。Skype for Business Server 将通道发送给等待呼叫的用户。 若要检索已呼叫，用户可以拨打通道号码或单击"对话"窗口中的通道链接或按钮。 
  
通过外部机制（如即时消息 (IM) 或分页系统）将通道号码传达给其他人，可通知呼叫的呼叫。 在取回呼叫时，将呼叫的保留为"对话"窗口的用户可以保持打开状态以接收通知。
  
由于通道范围在全局范围内是唯一的，因此，如果路由配置得当，可以从任何 Skype for Business Server 站点或 PBX 电话检索呼叫。 如果在可配置的时间范围内没有人取回呼叫，呼叫将回响到该呼叫的接听人。 如果此人未应答回叫，则呼叫将转接到回退目标，如已配置话务员。 可以配置呼叫在从 1 到 10 次转接之前回叫次数。 如果没有人应答转接的呼叫，则呼叫将断开连接。 检索或断开呼叫时，将释放通道。
  
部署呼叫库时，需要保留用于呼叫等待的分机号码范围。 这些分机需要为虚拟分机：未为其分配用户或电话的分机。 然后，使用分机号码范围配置呼叫托管通道表，并指定哪个应用程序服务托管处理每个范围的呼叫托管应用程序。 每个前端池在相应的后端服务器上都有一个呼叫停止表，该表用于管理池中的呼叫。 通道范围列表存储在中央管理存储中，用于将通道路由到目标池。 部署和配置呼叫库应用程序的每个 Skype for Business Server 池可以有一个或多个通道范围。 通道范围必须在 Skype for Business Server 部署中具有全局唯一性。 
  
还可以配置其他呼叫离开设置，例如呼叫的重定向位置（如果呼叫时间过长）以及电话上的人在离开时是否听到音乐。 还可以指定呼叫保持时要播放的音乐文件。
  
> [!NOTE]
> 呼叫保留的自定义保持音乐文件不会作为 Skype for Business Server 灾难恢复过程的一部分进行备份，如果上载到池的文件已损坏、已损坏或擦除，将会丢失。 始终保留为呼叫保留上载的自定义保持音乐文件的单独备份副本。 
  
呼叫 Park 应用程序是呼叫企业语音。 部署呼叫企业语音，将自动安装并激活呼叫停止应用程序。 但是，在可以使用呼叫企业语音管理员必须通过语音策略配置呼叫企业语音为用户启用它。
  
## <a name="deployment-and-requirements"></a>部署和要求

部署呼叫停止应用程序时，会自动安装企业语音。 通过配置语音策略启用呼叫管理。
  
### <a name="software-requirements"></a>软件要求

部署呼叫库的所有前端服务器和 Standard Edition Server 都必须为运行 Windows Server 2008 R2 的服务器安装 Windows Media Format Runtime，或为运行 Windows Server 2012 或 Windows Server 2012 R2 的服务器安装 Microsoft Media Foundation。 对于 Windows Server 2008 R2，Windows Media Format Runtime 作为 Windows 桌面体验的一部分进行安装。 呼叫库播放保持音乐的 Windows Media Audio (.wma) 需要 Windows Media Format Runtime 或 Microsoft Media Foundation。
  
### <a name="port-requirements"></a>端口要求

呼叫等待应用程序对 SIP 侦听请求使用 **端口 5075。**
    
> [!NOTE]
> 此端口是默认设置，您可以使用 **Set-CsApplicationServer** cmdlet 对其进行更改。 有关此 cmdlet 的详细信息，请参阅 Lync Server 命令行管理程序文档。
  
### <a name="audio-file-requirements"></a>音频文件要求

呼叫保留应用程序仅支持 Windows Media Audio (.wma) 文件用于保持音乐。 您可以使用 Microsoft Expression Encoder 4 来自定义用作保持音乐的文件。 若要下载表达式编码器 4，请参阅["Expression Encoder 4"。](https://go.microsoft.com/fwlink/p/?linkId=202843) 使用此工具将文件转换为 .wma 格式。 呼叫寄存保持音乐文件的建议格式为 Media Audio 9，44 kHz，16 位，单声道，CBR，32 kbps。
  
> [!NOTE]
> 转换后的文件仅以 16 KHz 在电话上播放，即使录制时采用 44 KHz 也是如此。 
  
## <a name="supported-clients-and-calls"></a>支持的客户端和呼叫

呼叫等待支持以下客户端和呼叫类型
  
### <a name="clients-supported-for-parking-calls"></a>支持寄存呼叫的客户端

可寄存来自任意 IP、专用交换机 (PBX)、公用电话交换网 (PSTN) 或移动电话的呼叫。
  
> [!NOTE]
> 只能寄存音频呼叫。不能寄存即时消息和会议。 
  
以下客户端可以使用呼叫 Park 来呼叫的呼叫：
  
- Skype for Business
    
- Lync 2013
    
- Lync 2010
    
- Lync 2010 Attendant
    
- Lync Phone Edition
    
> [!NOTE]
> 移动电话无法使用呼叫停叫来呼叫。 
  
### <a name="clients-supported-for-retrieving-calls"></a>支持取回呼叫的客户端

将通道范围配置为虚拟分机块（未分配用户或电话的分机）。将通道配置为虚拟分机时，移动电话和 PSTN 电话无法取回寄存的呼叫。
  
联盟用户无法取回寄存的呼叫。
  
以下客户端可以检索在呼叫 Park 上停的呼叫：
  
- Skype for Business
    
- Lync 2013
    
- Lync 2010
    
- Lync 2010 Attendant
    
- Lync Phone Edition
    
- IP 公用区域电话
    
- 连接到 Skype for Business Server 基础结构的非 IP 电话，包括公用区域电话和 PBX (专用交换机) 电话
    
## <a name="call-park-capacity-planning"></a>呼叫安排容量规划

下表介绍了可以用作容量规划要求基础的呼叫等待用户模型。
  
> [!IMPORTANT]
> 请记住，对于灾难恢复容量规划，配对池的每个池都应能够处理这两个池中呼叫保留服务的工作负荷。 
  
**呼叫寄存用户模型**

|**跃点数**|**每个前端池  <br/>  池 (8 台前端服务器)**|**每台 Standard Edition Server**|
|:-----|:-----|:-----|
|寄存速率  <br/> |每分钟 8 个  <br/> |每分钟 1 个  <br/> |
|取回寄存呼叫的速率  <br/> |每分钟 8 个  <br/> |每分钟 1 个  <br/> |
|平均寄存持续时间  <br/> |60 秒  <br/> |60 秒  <br/> |
   

