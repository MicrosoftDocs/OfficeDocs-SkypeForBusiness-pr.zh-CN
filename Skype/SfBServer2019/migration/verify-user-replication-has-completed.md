---
title: 确认用户复制已完成
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 运行 Move-CsUser cmdlet 时，可能会遇到失败，因为 Active Directory 域服务 (AD DS) 和 Skype for Business Server 2019 数据库之间的用户信息不同步，因为初始复制不完整。 成功完成 Skype for Business Server 2019 用户复制程序服务的初始同步所花的时间取决于承载 Skype for Business Server 2019 池的 Active Directory 林中托管的域控制器的数量。 当 Skype for Business Server 2019 前端服务器首次启动时，将执行 Skype for Business Server 2019 用户复制程序服务的初始同步过程。 此后，同步将基于用户复制程序间隔执行。 在运行 Move-CsUser cmdlet 之前，请先完成下列步骤以确认用户复制已完成。
ms.openlocfilehash: 0fe1c205b04ed32f5ac4281e555d5a44262905aa23b74eb69148d447337b59f7
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54325679"
---
# <a name="verify-user-replication-has-completed"></a>确认用户复制已完成

运行 **Move-CsUser** cmdlet 时，如果 Active Directory 域服务 (AD DS) 和 Skype for Business Server 2019 数据库之间的用户信息由于初始复制不完整而不同步，则可能会遇到失败。 成功完成 Skype for Business Server 2019 用户复制程序服务的初始同步所花的时间取决于承载 Skype for Business Server 2019 池的 Active Directory 林中托管的域控制器的数量。 当 Skype for Business Server 2019 前端服务器首次启动时，将执行 Skype for Business Server 2019 用户复制程序服务的初始同步过程。 此后，同步将基于用户复制程序间隔。 在运行 **Move-CsUser** cmdlet 之前，请完成以下步骤以验证用户复制是否已完成。 
  
### <a name="to-verify-that-user-replication-has-completed"></a>确认用户复制已完成

1. 以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。
    
2. 单击“开始”菜单，然后单击“运行”。 
    
3. 输入 **eventvwr.exe**，然后单击“确定”。
    
4. 在事件查看器中，单击 **"应用程序和服务日志**"将其展开，然后选择"Skype for Business Server"。 
    
5. 在“操作”窗格中，单击“筛选当前日志”。
    
6. 在“事件来源”列表中，单击“LS 用户复制程序”。
    
7. 在 **\<All Event IDs\>** 中，输入 **30024**，然后单击"确定 **"。** 
    
8. 在筛选的事件列表中，在"常规"选项卡上查找一个表明用户复制已成功完成的条目。 
    

