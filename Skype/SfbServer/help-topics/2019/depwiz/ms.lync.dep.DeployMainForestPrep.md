---
title: 准备当前林
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11f5e359-97eb-45f7-a730-9ddbbaa40b83
description: 若要准备 Active Directory 域服务林，必须成功扩展架构，如 Running Schema Preparation 主题中所述，并确保架构已复制。
ms.openlocfilehash: f993236fc13fc2274acaa8bb4c6b0ae1105afccb
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/21/2018
ms.locfileid: "19987485"
---
# <a name="prepare-current-forest"></a>准备当前林
 
若要准备 Active Directory 域服务林，必须成功扩展架构，如[Running Schema Preparation](http://technet.microsoft.com/library/067726ae-fd3f-4133-a32f-26d2603ac674.aspx)，主题中所述，并确保架构已复制。
  
完成这些先决任务后，即可开始“**步骤 3：准备当前林**”。要准备林，请以林根中 Domain Admins 组成员身份或正在准备的林的 Enterprise Admins 组成员身份登录到林根中的一台计算机。
  
1. 在部署向导的“**步骤 3：准备当前林**”中，单击“**运行**”。
    
2. 在“**准备林**”页上，单击“**下一步**”。
    
    > [!NOTE]
    > 林准备过程，可以选择放置的 Skype 的通用组位置的业务服务器 2015年。 选择与组织要求一致的位置。 
  
3. 在“**正在执行命令**”页上，查找“**任务状态：已完成**”，然后单击“**查看日志**”。确保没有任何错误。查看警告以确定对于您的基础结构来说，它们是否为预期和典型的问题。
    
4. 在日志中的**操作**列中，展开**林准备**，查找**\<成功\>** 每项任务结束时执行结果，以验证是否已成功完成该林准备过程，关闭该日志中，，然后单击**完成**.
    
5. 等待 Active Directory 域服务复制完成，或者强制向**Active Directory 站点和服务**管理单元中的目录林根域控制器上，运行域准备之前列出的所有域控制器进行复制。 强制执行复制，会导致发生分钟内的网站中复制所有 Active Directory 网站中的域控制器之间。
    
    > [!TIP]
    > 如果您需要查看 Skype 业务 Server 部署向导创建的日志文件，您可以在其中运行部署向导中，运行该步骤的 Active Directory 域服务用户的用户目录中的计算机上找到这些。 例如，如果用户登录以域管理员的域 Contoso.net 中，日志文件位于： C:\Users\Administrator.Contoso\AppData\Local\Temp 
  

