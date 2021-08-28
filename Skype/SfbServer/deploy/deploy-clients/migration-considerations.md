---
title: Skype会议室系统迁移注意事项
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: df9f33b6-0360-4354-b651-bd35da533e33
description: 阅读本主题，了解如何在具有多个 Skype Lync Server 版本的环境中部署会议室Skype for Business Server系统。
ms.openlocfilehash: 5a158c3f0797bb3d0377762ea2876dbe5b9d26bb
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58598156"
---
# <a name="skype-room-system-migration-considerations"></a>Skype会议室系统迁移注意事项
 
阅读本主题，了解如何在具有多个 Skype Lync Server 版本的环境中部署会议室Skype for Business Server系统。
  
## <a name="migration-considerations"></a>迁移注意事项

如果您要在包含不同版本 Skype Lync Server 的多池环境中部署会议室系统，本节Skype for Business Server指南。 
  
Lync Server 中的用户 (UR) 组件从 Active Directory 获取用户对象，然后将它们放入 Lync Server 后端 SQL Server 数据库。 只有 Lync Server 2013 中的 UR 可以Skype会议室系统对象。 以前版本的 Lync Server 和 Office Communications Server 中的 UR 不会检测指定 LRS 对象的 Active Directory 属性，因此不知道这些属性。 
  
如果 Skype 会议室系统帐户尝试登录 Lync，并基于 SRV 记录或 DNS A 记录进行自动发现，并且如果这些帐户指向以前版本的 Lync Server 或 Office Communications Server，LRS 将收到来自旧池的 404 未找到响应。 旧池将无法将会议室系统Skype Lync Server 2013 主池。 
  
可以使用以下选项解决此问题： 
  
- 将自动发现 SRV 记录指向 (_sipinternaltls._tcp.contoso.com) Lync Server 2013 池。
    
- 如果第一个选项不可行，则必须手动配置 LRS，并直接在会议室系统控制台应用程序中Skype Lync Server 2013 池地址。 
    
- 如果Skype会议室系统部署在企业网络外部，并且 Lync 边缘服务器已部署并配置为指向旧池或控制器，则需要指向 Lync Server 2013 池的辅助边缘服务器站点。 有关部署辅助边缘服务器的信息，请参阅边缘服务器部署文档。 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a>Skype会议室系统与 Lync Server 2010 池的互操作性

在迁移过程中，如果位于 Lync Server 2010 池上的用户安排会议并邀请 Skype 会议室系统帐户，Skype 会议室系统客户端在参加会议时将具有有限的功能。 
  
当 Skype 会议室系统客户端加入由 Lync Server 2010 上用户组织的计划电话会议时，Skype 会议室系统具有以下会议限制： 
  
- Skype会议室系统无法显示多视图视频库。
    
- 如果Skype系统客户端是演示者，则不能对参与者应用视频锁定。
    
- Skype会议室系统无法在入站或 (出站) 显示 1080p 视频分辨率，即使 Lync Server 2013 会议策略允许，原因如下： 
    
  - Lync Server 2010 不支持 1080p 分辨率。
    
  - Skype会议室系统始终受组织者的会议策略的视频分辨率限制。 因此，即使 Lync 2010 池支持 720p 分辨率，Skype 会议室系统也将无法利用 720p 分辨率，只要组织者的策略不支持它。 
    
- Lync 2013 客户端在会议室中检测 LRS 状态，并且会自动将自己静音以避免物理会议室中出现回声。 此功能在 Lync Server 2010 上托管的会议中不起作用。
    
- Lync Server 2010 上托管的会议的桌面共享性能存在限制。
    
- 用户将无法加入在 Lync 2010 上 (会议室) 的专用会议Skype会议。
    

