---
title: Skype 会议室系统迁移注意事项
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/4/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df9f33b6-0360-4354-b651-bd35da533e33
description: 阅读本主题以了解有关如何在环境中的多个版本的 Skype 业务服务器和 Lync Server 部署 Skype 的空间系统。
ms.openlocfilehash: f71c6557a8b9a98f712541c4424ba57a49536164
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-system-migration-considerations"></a>Skype 会议室系统迁移注意事项
 
阅读本主题以了解有关如何在环境中的多个版本的 Skype 业务服务器和 Lync Server 部署 Skype 的空间系统。
  
## <a name="migration-considerations"></a>迁移注意事项

此部分提供了指南，如果包括不同版本的 Skype 业务服务器、 Lync Server 或办公室通信服务器 2007 R2 多池环境中部署 Skype 的空间系统。 
  
Lync Server 中的用户复制程序 (UR) 组件从 Active Directory 获取用户对象并将它们放入 Lync Server 后端 SQL Server 数据库中。 仅在 Lync Server 2013 UR 已知道 Skype 的空间系统对象。 以前版本的 Lync Server 和 Office Communications Server 中的 UR 不影响指定 LR 对象的 Active Directory 属性，因此无法识别它们。 
  
LRS 如果 Skype 的空间系统帐户尝试登录 Lync，并执行基于 SRV 记录或 DNS A 记录查找的自动发现和这些帐户指向 Lync Server 或办公室通信服务器的早期版本，将会收到从 404 找不到回复 传统的池。 传统的池不能重定向到其 Lync Server 2013 主池 Skype 的空间系统。 
  
你可以通过以下方法解决此问题： 
  
- 将你的自动发现 SRV 记录 (_sipinternaltls._tcp.contoso.com) 指向 Lync Server 2013 池。
    
- 如果第一个选项不是可能的您必须手动配置 LRS 并提供通过 Skype 的空间系统控制台应用程序中直接配置 Lync Server 2013 池地址。 
    
- 如果企业网络外部的部署 Skype 的空间系统和部署 Lync 边缘服务器并将其配置为指向旧池或控制器，辅助的边缘服务器站点是必需的它指向 Lync Server 2013 池。 有关部署第二个边缘服务器的详细信息，请参阅边缘服务器部署文档。 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a>Skype 的空间与 Lync 服务器 2010年池的系统互操作性

在迁移期间，位于 Lync Server 2010 池的用户安排会议并邀请 Skype 的空间系统帐户，如果 Skype 的空间系统客户端功能将受到限制参加会议时。 
  
当 Skype 的空间系统客户端加入已按计划的会议呼叫用户驻留在 Lync Server 2010 上，Skype 的空间系统具有以下会议在限制： 
  
- Skype 的空间系统无法显示多视图视频库。
    
- 如果 Skype 的空间系统客户端的演示者，它不能在参与者应用视频锁。
    
- Skype 的空间系统无法显示 1080p 视频分辨率 （入站或出站），即使 Lync Server 2013 会议策略允许，原因如下： 
    
  - Lync Server 2010 不支持 1080p 分辨率。
    
  - Skype 的空间系统始终受到组织者的会议策略的视频分辨率。 因此，即使 Lync 2010 池支持 720p 分辨率，Skype 的空间系统将无法利用 720p 分辨率，只要组织者的策略不支持它。 
    
- Lync 2013 客户端在会议室中检测 LRS 状态，它们会自动将自己静音以避免物理会议室中产生回声。此功能在 Lync Server 2010 上主持的会议中不适用。
    
- 对于在 Lync Server 2010 上主持的会议，桌面共享功能存在一些限制。
    
- 用户将不能加入专用 （受限） 会议承载 Lync 2010 与 Skype 的空间系统。
    

