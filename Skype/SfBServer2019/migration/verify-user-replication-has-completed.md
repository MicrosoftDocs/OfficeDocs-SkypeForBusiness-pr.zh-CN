---
title: 确认用户复制已完成
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 运行 Move-csuser cmdlet 时, 你可能会遇到故障, 因为 Active Directory 域服务 (AD DS) 和 Skype for business Server 2019 数据库之间的用户信息不同步, 因为初始复制不完整。 成功完成 Skype for business Server 2019 用户复制器服务的初始同步所需的时间取决于托管 Skype for business 的 Active Directory 林中托管的域控制器的数量服务器2019池。 Skype for Business Server 2019 用户复制器服务在第一次启动 Skype for business 服务器2019前端服务器时, 将发生初始同步过程。 之后, 同步将基于用户复制程序间隔。 在运行 Move-csuser cmdlet 之前, 请完成以下步骤以验证用户复制已完成。
ms.openlocfilehash: d5d0462ec2886c73fb7286860eea2c89e0fea9fb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280644"
---
# <a name="verify-user-replication-has-completed"></a>确认用户复制已完成

运行**move-csuser** cmdlet 时, 如果 Active Directory 域服务 (AD DS) 和 Skype For business Server 2019 数据库之间的用户信息不同步, 则你可能会遇到故障, 因为初始复制不完整。 成功完成 Skype for business Server 2019 用户复制器服务的初始同步所需的时间取决于托管 Skype for business 的 Active Directory 林中托管的域控制器的数量服务器2019池。 Skype for Business Server 2019 用户复制器服务在第一次启动 Skype for business 服务器2019前端服务器时, 将发生初始同步过程。 之后, 同步基于用户复制程序间隔。 完成以下步骤以在运行**move-csuser** cmdlet 之前验证用户复制是否已完成。 
  
### <a name="to-verify-that-user-replication-has-completed"></a>验证用户复制是否已完成

1. 以 Domain Admins 组和 RTCUniversalServerAdmins 组成员的身份登录安装了拓扑生成器的计算机。
    
2. 单击 "**开始**" 菜单, 然后单击 "**运行**"。 
    
3. 输入**eventvwr.exe**, 然后单击 **"确定"**。
    
4. 在事件查看器中, 单击 "**应用程序和服务日志**" 以将其展开, 然后选择 "Skype For business 服务器"。 
    
5. 在 "**操作**" 窗格中, 单击 "**筛选当前日志**"。
    
6. 从 "**事件源**" 列表中, 单击 "**用户复制**"。
    
7. 在** \<所有事件 id\>** 中, 输入**30024**, 然后单击 **"确定"**。 
    
8. 在 "筛选的事件" 列表中的 "**常规**" 选项卡上, 查找指示用户复制已成功完成的条目。 
    

