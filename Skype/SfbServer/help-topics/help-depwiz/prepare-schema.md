---
title: 准备架构
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployMainSchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 337aa234-c5f3-4468-a047-2023848e942c
description: 若要准备 Active Directory 域服务的架构，请在 "Skype for Business 服务器部署" 向导中运行 "准备架构" 步骤。 单击“运行”可开始准备架构。 准备架构步骤将在运行部署向导的系统上的/Program 文件/Microsoft Lync Server 2013/部署/安装目录中读取所提供的架构定义文件。 这些文件也可在支持/架构目录中的安装媒体上使用。 “准备架构”步骤将扩展架构并报告准备过程的状态。 还将在完成准备过程时通知您。 通过摘要屏幕可以查看该过程的日志。 查看日志以确保准备工作已成功完成。
ms.openlocfilehash: fd1e79411c9820013954be0add7b68c326188e9e
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41700817"
---
# <a name="prepare-schema"></a>准备架构
 
若要准备 Active Directory 域服务的架构，请在 "Skype for Business 服务器部署" 向导中运行 "准备架构" 步骤。 单击“**运行**”可开始准备架构。 “准备架构”步骤会在运行部署向导的系统的 \Program Files\Microsoft Lync Server 2013\Deployment\Setup 目录中读取提供的架构定义文件。 安装介质的 \Support\Schema 目录中也提供了这些文件。 “准备架构”步骤将扩展架构并报告准备过程的状态。 还将在完成准备过程时通知您。 通过摘要屏幕可以查看该过程的日志。 查看日志以确保准备工作已成功完成。
  
> [!IMPORTANT]
> 要扩展架构，必须以 Schema Admins 和 Enterprise Admins 组成员身份登录域。 
  
将添加类和属性以扩展 Active Directory 域服务架构，以支持 Skype for Business Server 2015 服务器、服务和用户对象。 在扩展架构之前，应该对担任架构主机角色的域控制器进行系统状态备份。 有关 Windows Server 2008 R2 适用于 SP1 的备份过程的详细信息， [https://go.microsoft.com/fwlink/p/?linkId=207198](https://go.microsoft.com/fwlink/p/?linkId=207198)请参阅。 对于 Windows Server 2003 和 Windows Server 2003 R2，请[https://go.microsoft.com/fwlink/p/?linkId=207199](https://go.microsoft.com/fwlink/p/?linkId=207199)参阅。
  
> [!CAUTION]
> 扩展架构是不可逆的。 应尽一切努力限制失败的架构扩展的潜在影响，并确保架构扩展能够成功。 在通信中断或服务器上出现任何其他故障的情况下，这一点尤为重要。 你应该执行架构主机域控制器的备份和 Active Directory 的完整备份。 
  
若要执行架构主机域控制器的备份和 Active Directory 的完整备份，请执行以下操作：
  
1. 断开担当架构主机角色的域控制器与网络的连接。
    
2. 对担当架构主机角色的域控制器执行系统状态备份。
    
3. 扩展架构。
    
4. 架构扩展成功后，将域控制器重新连接到网络，并确保复制为活动状态且正常工作。
    
5. 在架构扩展出现故障的情况下，请使用之前的系统状态备份还原域控制器和 Active Directory 的系统状态。
    
> [!NOTE]
> 如果需要查看由 Skype for Business 服务器部署向导创建的日志文件，可以在运行该步骤的 Active Directory 用户的用户目录中找到运行部署向导的计算机上的文件。 例如，如果用户在域 Contoso.net 中以域管理员身份登录，则日志文件位于： C:\Users\Administrator.Contoso\AppData\Local\Temp 
  

