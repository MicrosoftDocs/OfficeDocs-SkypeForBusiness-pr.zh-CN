---
title: Skype 会议室系统迁移注意事项
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: df9f33b6-0360-4354-b651-bd35da533e33
description: 阅读本主题，了解如何在具有多个版本的 Skype for Business Server 和 Lync Server 的环境中部署 Skype 会议室系统。
ms.openlocfilehash: 30b2a4733ea2e2e42b8a879914a2e0e3c4903c8e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805782"
---
# <a name="skype-room-system-migration-considerations"></a>Skype 会议室系统迁移注意事项
 
阅读本主题，了解如何在具有多个版本的 Skype for Business Server 和 Lync Server 的环境中部署 Skype 会议室系统。
  
## <a name="migration-considerations"></a>迁移注意事项

如果正在包含不同版本的 Skype for Business Server 或 Lync Server 的多池环境中部署 Skype 会议室系统，本部分将提供指导。 
  
Lync Server 中的用户 (URL) 组件从 Active Directory 获取用户对象，然后将它们放入 Lync Server 后端SQL Server数据库中。 只有 Lync Server 2013 中的 UR 可以识别 Skype 会议室系统对象。 以前版本的 Lync Server 和 Office Communications Server 中的 UR 不会检测指定 LRS 对象的 Active Directory 属性，因此无法识别它们。 
  
如果 Skype 会议室系统帐户尝试登录 Lync，并基于 SRV 记录或 DNS A 记录执行自动发现，如果这些帐户指向以前版本的 Lync Server 或 Office Communications Server，LRS 将收到来自旧池的 404 未找到响应。 旧池将无法将 Skype 会议室系统重定向到其 Lync Server 2013 主池。 
  
可以通过以下选项解决此问题： 
  
- 将自动发现 SRV 记录 (_sipinternaltls._tcp.contoso.com) Lync Server 2013 池。
    
- 如果第一个选项不可行，则必须手动配置 LRS，并直接在 Skype 会议室系统控制台应用程序中配置 Lync Server 2013 池地址并提供该地址。 
    
- 如果 Skype 会议室系统部署在企业网络外部，并且 Lync 边缘服务器已部署并配置为指向旧池或控制器，则需要指向 Lync Server 2013 池的辅助边缘服务器站点。 有关部署辅助边缘服务器详细信息，请参阅边缘服务器部署文档。 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a>与 Lync Server 2010 池的 Skype 会议室系统互操作性

在迁移过程中，如果位于 Lync Server 2010 池上的用户安排会议并邀请 Skype 会议室系统帐户，则 Skype 会议室系统客户端在参加会议时将具有有限的功能。 
  
当 Skype 会议室系统客户端加入由 Lync Server 2010 上用户组织的计划电话会议时，Skype 会议室系统具有以下会议限制： 
  
- Skype 会议室系统无法显示多视图视频库。
    
- 如果 Skype 会议室系统客户端是演示者，它将无法对参与者应用视频锁定。
    
- Skype 会议室系统无法显示 1080p 视频分辨率 (入站或出站) ，即使 Lync Server 2013 会议策略允许，原因如下： 
    
  - Lync Server 2010 不支持 1080p 分辨率。
    
  - Skype 会议室系统始终受组织者的视频分辨率会议策略限制。 因此，即使 Lync 2010 池支持 720p 分辨率，只要组织者的策略不支持 720p 分辨率，Skype 会议室系统也将无法利用它。 
    
- Lync 2013 客户端检测会议室中的 LRS 状态，并自动将自己静音以避免物理会议室中出现回声。 此功能在 Lync Server 2010 上托管的会议中不起作用。
    
- Lync Server 2010 上托管的会议的桌面共享性能存在限制。
    
- 用户将无法加入在 Lync 2010 (Skype 会议室) 托管的受限会议。
    

