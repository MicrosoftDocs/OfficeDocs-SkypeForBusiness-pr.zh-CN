---
title: 准备架构
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainSchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 337aa234-c5f3-4468-a047-2023848e942c
description: 若要为 Active Directory 域服务准备架构，请运行 Skype for Business Server 部署向导中的准备架构步骤。 单击“运行”可开始准备架构。 "准备架构"步骤读取运行部署向导的系统的 /Program Files/Microsoft Lync Server 2013/Deployment/Setup 目录中提供的架构定义文件。 这些文件还可用于支持/架构目录中的安装媒体。 “准备架构”步骤将扩展架构并报告准备过程的状态。 还将在完成准备过程时通知您。 通过摘要屏幕可以查看该过程的日志。 查看日志以确保准备工作已成功完成。
ms.openlocfilehash: c3279be54ad5f68d5c2ee61d8d3c12c0fc9d9203
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51108618"
---
# <a name="prepare-schema"></a>准备架构
 
若要为 Active Directory 域服务准备架构，请运行 Skype for Business Server 部署向导中的准备架构步骤。 单击“运行”可开始准备架构。 "准备架构"步骤读取运行部署向导的系统的 \Program Files\Microsoft Lync Server 2013\Deployment\Setup 目录中提供的架构定义文件。 安装介质的 \Support\Schema 目录中也提供了这些文件。 “准备架构”步骤将扩展架构并报告准备过程的状态。 还将在完成准备过程时通知您。 通过摘要屏幕可以查看该过程的日志。 查看日志以确保准备工作已成功完成。
  
> [!IMPORTANT]
> 要扩展架构，必须以 Schema Admins 和 Enterprise Admins 组成员身份登录域。 
  
添加类和属性以扩展 Active Directory 域服务架构以支持 Skype for Business Server 2015 服务器、服务和用户对象。 在扩展架构之前，应该对担任架构主机角色的域控制器进行系统状态备份。 有关 Windows Server 2008 R2 SP1 的备份过程的详细信息，请参阅 [https://go.microsoft.com/fwlink/p/?linkId=207198](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee849849(v=ws.10)) 。 对于 Windows Server 2003 和 Windows Server 2003 R2，请参阅 [https://go.microsoft.com/fwlink/p/?linkId=207199](/previous-versions/windows/it-pro/windows-server-2003/cc787254(v=ws.10)) 。
  
> [!CAUTION]
> 扩展架构是不可逆的。 应尽一切努力限制失败的架构扩展的潜在影响，并确保架构扩展能够成功。 在丧失通信或服务器上出现任何其他故障的情况下，这尤其重要。 您应执行架构主机域控制器的备份和 Active Directory 的完整备份。 
  
要执行架构主机域控制器备份和 Active Directory 的完整备份，请执行以下操作：
  
1. 断开担当架构主机角色的域控制器与网络的连接。
    
2. 对担当架构主机角色的域控制器执行系统状态备份。
    
3. 扩展架构。
    
4. 架构扩展成功后，将域控制器重新连接到网络，并确保复制为活动状态且正常工作。
    
5. 万一架构扩展失败，则使用之前执行的系统状态备份还原域控制器和 Active Directory 的系统状态。
    
> [!NOTE]
> 如果需要查看 Skype for Business Server 部署向导创建的日志文件，可以在运行部署向导的计算机上找到这些文件，位置为运行该步骤的 Active Directory 用户的 Users 目录。 例如，如果用户以域 Contoso.net 的域管理员身份登录，则日志文件位于：C：\Users\Administrator.Contoso\AppData\Local\Temp 
