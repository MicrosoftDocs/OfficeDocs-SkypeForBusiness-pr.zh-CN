---
title: 准备架构
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainSchemaPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 337aa234-c5f3-4468-a047-2023848e942c
ROBOTS: NOINDEX, NOFOLLOW
description: 若要为 Active Directory 域服务准备架构，请运行 Skype for Business Server 部署向导中的"准备架构"步骤。 单击“运行”可开始准备架构。
ms.openlocfilehash: b666cda29267c6f74eb034389f3f7967d7af99c5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833772"
---
# <a name="prepare-schema"></a>准备架构
 
若要为 Active Directory 域服务准备架构，请运行 Skype for Business Server 部署向导中的"准备架构"步骤。 单击“运行”可开始准备架构。 "准备架构"步骤读取运行部署向导的系统上的 \Program Files\Skype for Business Server 2019\Deployment\Setup 目录中提供的架构定义文件。 安装介质的 \Support\Schema 目录中也提供了这些文件。 “准备架构”步骤将扩展架构并报告准备过程的状态。 还将在完成准备过程时通知您。 通过摘要屏幕可以查看该过程的日志。 查看日志以确保准备工作已成功完成。
  
> [!IMPORTANT]
> 要扩展架构，必须以 Schema Admins 和 Enterprise Admins 组成员身份登录域。 
  
添加类和属性以扩展 Active Directory 域服务架构以支持 Skype for Business Server 服务器、服务和用户对象。 在扩展架构之前，应该对担任架构主机角色的域控制器进行系统状态备份。 
  
> [!CAUTION]
> 扩展架构是不可逆的。 应尽一切努力限制失败的架构扩展的潜在影响，并确保架构扩展能够成功。 在丧失通信或服务器上出现任何其他故障的情况下，这尤其重要。 您应执行架构主机域控制器的备份和 Active Directory 的完整备份。 
  
若要执行架构主机域控制器的备份和 Active Directory 的完整备份，请执行以下操作：
  
1. 断开担当架构主机角色的域控制器与网络的连接。
    
2. 对担当架构主机角色的域控制器执行系统状态备份。
    
3. 扩展架构。
    
4. 架构扩展成功后，将域控制器重新连接到网络，并确保复制为活动状态且正常工作。
    
5. 如果架构扩展失败，则使用之前采用的系统状态备份还原域控制器和 Active Directory 的系统状态。
    
> [!NOTE]
> 如果需要查看由 Skype for Business Server 部署向导创建的日志文件，可以在运行部署向导的计算机上找到运行该步骤的 Active Directory 用户的 Users 目录中的文件。 例如，如果用户以域 Contoso.net 域管理员身份登录，则日志文件位于：C：\Users\Administrator.Contoso\AppData\Local\Temp 
  

