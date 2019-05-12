---
title: Skype 会议室系统迁移注意事项
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df9f33b6-0360-4354-b651-bd35da533e33
description: 阅读本主题可了解如何在具有多个版本的 Skype Business Server 和 Lync Server 环境中部署 Skype 会议室系统。
ms.openlocfilehash: f5e33c36b0c6a58d83f22e5c18f4de34ffb9d648
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33895214"
---
# <a name="skype-room-system-migration-considerations"></a>Skype 会议室系统迁移注意事项
 
阅读本主题可了解如何在具有多个版本的 Skype Business Server 和 Lync Server 环境中部署 Skype 会议室系统。
  
## <a name="migration-considerations"></a>迁移注意事项

本节提供指导，如果企业服务器，或 Lync Server 包括不同版本的 Skype 多池环境中部署 Skype 会议室系统。 
  
Lync Server 中的用户复制程序 (UR) 组件从 Active Directory 获取用户对象并将它们放入 Lync Server 后端 SQL Server 数据库中。 Lync Server 2013 中的 UR 已知道 Skype 会议室系统对象。 以前版本的 Lync Server 和 Office Communications Server 中的 UR 不影响指定 LR 对象的 Active Directory 属性，因此无法识别它们。 
  
LRS 如果 Skype 会议室系统帐户尝试登录到 Lync，并执行基于 SRV 记录或 DNS A 记录查找自动发现，并且这些帐户指向 Lync Server 或 Office Communications Server 的早期版本，将收到 404 找不到响应 旧池。 旧池不能将 Skype 会议室系统重定向到其 Lync Server 2013 的主池。 
  
你可以通过以下方法解决此问题： 
  
- 将你的自动发现 SRV 记录 (_sipinternaltls._tcp.contoso.com) 指向 Lync Server 2013 池。
    
- 如果不可能的第一个选项，您必须手动配置 LRS 并直接 Skype 会议室系统控制台应用程序中对其进行配置，以提供 Lync Server 2013 池地址。 
    
- 如果 Skype 会议室系统部署企业网络外部的并且已部署并配置为指向旧池或控制器 Lync 边缘服务器，第二的边缘服务器网站是必需的其指向 Lync Server 2013 池。 有关部署第二个边缘服务器的详细信息，请参阅边缘服务器部署文档。 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a>Skype 会议室与 Lync Server 2010 池的系统互操作性

在迁移期间，如果用户驻留在 Lync Server 2010 池上安排会议并邀请 Skype 会议室系统帐户的 Skype 会议室 System 客户端功能将受到限制参加会议时。 
  
当的 Skype 会议室 System 客户端加入计划的电话会议的已按驻留在 Lync Server 2010 的用户，Skype 会议室系统具有以下会议中限制： 
  
- Skype 会议室系统无法显示多视图视频库。
    
- 如果演示者的 Skype 会议室 System 客户端，它不能在参与者应用视频锁。
    
- Skype 会议室系统无法显示 1080p 视频分辨率 （入站或出站），即使 Lync Server 2013 会议策略允许，原因如下： 
    
  - Lync Server 2010 不支持 1080p 的分辨率。
    
  - Skype 会议室系统始终受到组织者的会议策略的视频分辨率。 因此，即使 Lync 2010 池支持 720 p 分辨率，Skype 会议室系统将不能利用 720 p 解决方案，只要组织者的策略不支持它。 
    
- Lync 2013 客户端在会议室中检测 LRS 状态，它们会自动将自己静音以避免物理会议室中产生回声。此功能在 Lync Server 2010 上主持的会议中不适用。
    
- 对于在 Lync Server 2010 上主持的会议，桌面共享功能存在一些限制。
    
- 用户将无法加入专用 （受限） 承载的会议在 Lync 2010 与 Skype 会议室系统。
    

