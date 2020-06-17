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
description: 在运行 Get-csuser cmdlet 时，您可能会遇到故障，因为 Active Directory 域服务（AD DS）和 Skype for Business Server 2019 数据库之间的用户信息因初始复制不完整而不同步。 成功完成 Skype for business Server 2019 用户复制程序服务的初始同步所需的时间取决于托管在承载 Skype for Business Server 2019 池的 Active Directory 林中的域控制器数。 当第一次启动 Skype for business Server 2019 前端服务器时，将发生 Skype for Business Server 2019 用户复制程序服务初始同步过程。 此后，同步将基于用户复制程序间隔执行。 在运行 Move-CsUser cmdlet 之前，请先完成下列步骤以确认用户复制已完成。
ms.openlocfilehash: 5aa832216cc5eddce1d80cc9401ec9992c9edbf1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751644"
---
# <a name="verify-user-replication-has-completed"></a>确认用户复制已完成

在运行**get-csuser** cmdlet 时，如果 Active Directory 域服务（AD DS）和 Skype For business Server 2019 数据库之间的用户信息因初始复制不完整而不同步，则可能会遇到故障。 成功完成 Skype for business Server 2019 用户复制程序服务的初始同步所需的时间取决于托管在承载 Skype for Business Server 2019 池的 Active Directory 林中的域控制器数。 当第一次启动 Skype for business Server 2019 前端服务器时，将发生 Skype for Business Server 2019 用户复制程序服务初始同步过程。 之后，同步基于用户复制程序间隔。 完成以下步骤以验证用户复制是否已完成，然后再运行**get-csuser** cmdlet。 
  
### <a name="to-verify-that-user-replication-has-completed"></a>确认用户复制已完成

1. 以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。
    
2. 单击“开始”**** 菜单，然后单击“运行”****。 
    
3. 输入 **eventvwr.exe**，然后单击“确定”****。
    
4. 在事件查看器中，单击 "**应用程序和服务日志**" 以展开它，然后选择 "Skype For business Server"。 
    
5. 在“操作”**** 窗格中，单击“筛选当前日志”****。
    
6. 在“事件来源”**** 列表中，单击“LS 用户复制程序”****。
    
7. 在中 **\<All Event IDs\>** ，输入**30024**，然后单击 **"确定"**。 
    
8. 在 "筛选的事件" 列表中的 "**常规**" 选项卡上，查找指示用户复制已成功完成的条目。 
    

