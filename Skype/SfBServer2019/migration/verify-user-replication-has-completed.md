---
title: 确认用户复制已完成
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 当运行 Move-csuser cmdlet，您可能会遇到故障，因为 Active Directory 域服务 (AD DS) 和业务服务器 2019年数据库 Skype 之间的用户信息不同步的因为不完整的初始复制。 成功完成业务服务器 2019年用户复制程序服务的初始同步的 Skype 所花的时间取决于承载在承载 for Business Skype Active Directory 林中的域控制器数服务器 2019年池。 业务 Server 2019 前端服务器的 Skype 首次启动时，发生此事件业务 Server 2019 用户复制服务初始同步进程的 Skype。 之后，同步然后基于用户复制程序间隔。 完成以下步骤以确认用户复制已完成之前运行 Move-csuser cmdlet。
ms.openlocfilehash: 43b2822303676d209dc14a3b2e06368a7d24e174
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027842"
---
# <a name="verify-user-replication-has-completed"></a>确认用户复制已完成

当运行**Move-csuser** cmdlet，您可能会遇到故障，如果因为的初始复制不完整同步的 Active Directory 域服务 (AD DS) 和业务服务器 2019年数据库 Skype 之间的用户信息。 成功完成业务服务器 2019年用户复制程序服务的初始同步的 Skype 所花的时间取决于承载在承载 for Business Skype Active Directory 林中的域控制器数服务器 2019年池。 业务 Server 2019 前端服务器的 Skype 首次启动时，发生此事件业务 Server 2019 用户复制服务初始同步进程的 Skype。 之后，同步基于用户复制程序间隔。 完成以下步骤以确认用户复制已完成之前运行**Move-csuser** cmdlet。 
  
### <a name="to-verify-that-user-replication-has-completed"></a>确认用户复制已完成

1. 以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。
    
2. 单击**开始**菜单，然后单击**运行**。 
    
3. 输入**eventvwr.exe**，，然后单击**确定**。
    
4. 在事件查看器中，单击**应用程序和服务日志**将其展开，，然后选择业务服务器的 Skype。 
    
5. 在**操作**窗格中，单击**筛选当前日志**。
    
6. 从**事件来源**列表中，单击**LS 用户复制程序**。
    
7. 在**\<所有事件 Id\>**，输入**30024**，，然后单击**确定**。 
    
8. 在筛选的事件列表中，在**常规**选项卡上，查找表明用户复制已成功完成项。 
    

