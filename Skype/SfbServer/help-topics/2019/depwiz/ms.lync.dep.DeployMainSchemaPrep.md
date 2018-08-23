---
title: 准备架构
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainSchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 337aa234-c5f3-4468-a047-2023848e942c
ROBOTS: NOINDEX, NOFOLLOW
description: 准备 Active Directory 域服务的架构，您运行架构准备步骤中 Skype 业务 Server 部署向导。 单击“运行”可开始准备架构。
ms.openlocfilehash: 5cc9f4136d86408296a95c8bad0ffdbd13185d8d
ms.sourcegitcommit: ddedcfe6efd4d8adec794a70c904468a45fbdeb4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/14/2018
ms.locfileid: "22601960"
---
# <a name="prepare-schema"></a>准备架构
 
准备 Active Directory 域服务的架构，您运行架构准备步骤中 Skype 业务 Server 部署向导。 单击“**运行**”可开始准备架构。 架构准备步骤读取提供的架构定义文件中 \Program Files\Skype 业务服务器 2019\Deployment\Setup 目录运行部署向导的系统上。 安装介质的 \Support\Schema 目录中也提供了这些文件。 “准备架构”步骤将扩展架构并报告准备过程的状态。 还将在完成准备过程时通知您。 通过摘要屏幕可以查看该过程的日志。 查看日志以确保准备工作已成功完成。
  
> [!IMPORTANT]
> 要扩展架构，必须以 Schema Admins 和 Enterprise Admins 组成员身份登录域。 
  
添加的类和属性扩展 Active Directory 域服务架构以支持 Skype Business Server 服务器、 服务和用户对象。 在扩展架构之前，应该对担任架构主机角色的域控制器进行系统状态备份。 
  
> [!CAUTION]
> 扩展架构是不可逆的。 应尽一切努力限制失败的架构扩展的潜在影响，并确保架构扩展能够成功。 在通信中断或服务器上出现任何其他故障的情况下，这一点尤为重要。 您应执行备份的架构主机的域控制器和 Active Directory 的完整备份。 
  
若要执行备份的架构主机的域控制器和 Active Directory 的完整备份：
  
1. 断开担当架构主机角色的域控制器与网络的连接。
    
2. 对担当架构主机角色的域控制器执行系统状态备份。
    
3. 扩展架构。
    
4. 架构扩展成功后，将域控制器重新连接到网络，并确保复制为活动状态且正常工作。
    
5. 万一架构扩展失败，使用您之前生成的系统状态备份还原域控制器和 Active Directory 的系统状态。
    
> [!NOTE]
> 如果您需要查看 Skype 业务 Server 部署向导创建的日志文件，您可以找到其中运行部署向导中，运行该步骤的 Active Directory 用户的用户目录中的计算机上的文件。 例如，如果用户登录以域管理员的域 Contoso.net 中，日志文件位于： C:\Users\Administrator.Contoso\AppData\Local\Temp 
  

