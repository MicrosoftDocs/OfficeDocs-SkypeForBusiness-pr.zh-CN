---
title: Skype 会议室系统迁移注意事项
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df9f33b6-0360-4354-b651-bd35da533e33
description: 阅读本主题, 了解如何在具有多个版本的 Skype for Business Server 和 Lync Server 的环境中部署 Skype 会议室系统。
ms.openlocfilehash: f5da7f92c7ab947d5e6d68c19823d227f8ae3ca3
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234205"
---
# <a name="skype-room-system-migration-considerations"></a>Skype 会议室系统迁移注意事项
 
阅读本主题, 了解如何在具有多个版本的 Skype for Business Server 和 Lync Server 的环境中部署 Skype 会议室系统。
  
## <a name="migration-considerations"></a>迁移注意事项

本部分介绍了如何在包含不同版本的 Skype for Business Server 或 Lync Server 的多池环境中部署 Skype 会议室系统。 
  
Lync Server 中的用户复制程序 (UR) 组件从 Active Directory 获取用户对象并将它们放入 Lync Server 后端 SQL Server 数据库中。 只有 Lync Server 2013 中的 UR 知道 Skype 会议室系统对象。 以前版本的 Lync Server 和 Office Communications Server 中的 UR 不影响指定 LR 对象的 Active Directory 属性，因此无法识别它们。 
  
如果 Skype 会议室系统帐户尝试登录 Lync, 并基于 SRV 记录或 DNS A 记录查找来执行自动发现, 并且如果这些帐户指向的是早期版本的 Lync Server 或 Office 通信服务器, LRS 将收到404未找到的响应 旧版池。 旧版池将无法将 Skype 会议室系统重定向到其 Lync Server 2013 主池。 
  
你可以通过以下方法解决此问题： 
  
- 将你的自动发现 SRV 记录 (_sipinternaltls._tcp.contoso.com) 指向 Lync Server 2013 池。
    
- 如果无法使用第一个选项, 则必须手动配置 LRS, 并通过在 Skype 会议室系统控制台应用程序中直接配置来提供 Lync Server 2013 池地址。 
    
- 如果 Skype 会议室系统部署在公司网络外部, 并且 Lync Edge 服务器已部署并配置为指向旧版池或控制器, 则需要辅助边缘服务器网站, 该站点指向 Lync Server 2013 池。 有关部署第二个边缘服务器的详细信息，请参阅边缘服务器部署文档。 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a>Skype 会议室系统与 Lync Server 2010 池的互操作性

在迁移过程中, 如果托管在 Lync Server 2010 池中的用户安排会议并邀请 Skype 会议室系统帐户, 则 Skype 会议室系统客户将在参加会议时拥有有限的功能。 
  
当 Skype 会议室系统客户加入由驻留在 Lync Server 2010 上的用户组织的计划会议呼叫时, Skype 会议室系统具有下列会议内限制: 
  
- Skype 会议室系统无法显示多视图视频库。
    
- 如果 Skype 会议室系统客户是演示者, 则不能对参与者应用视频锁。
    
- 由于以下原因, Skype 会议室系统无法显示1080p 视频分辨率 (入站或出站), 即使 Lync Server 2013 会议策略允许它, 也是如此: 
    
  - Lync Server 2010 不支持1080p 分辨率。
    
  - Skype 会议室系统始终受组织者的视频分辨率的会议策略的限制。 因此, 即使 Lync 2010 池支持720p 解析, 如果组织者的策略不支持720p 解析, 则 Skype 会议室系统将无法利用720p 解析。 
    
- Lync 2013 客户端在会议室中检测 LRS 状态，它们会自动将自己静音以避免物理会议室中产生回声。此功能在 Lync Server 2010 上主持的会议中不适用。
    
- 对于在 Lync Server 2010 上主持的会议，桌面共享功能存在一些限制。
    
- 用户无法通过 Skype 会议室系统加入 Lync 2010 上托管的专用 (受限) 会议。
    

