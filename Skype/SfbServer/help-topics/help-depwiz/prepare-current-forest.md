---
title: 准备当前林
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainForestPrep
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 11f5e359-97eb-45f7-a730-9ddbbaa40b83
description: 若要准备 Active Directory 域服务林，必须成功扩展架构（如运行架构准备主题中所述）并确保架构已复制。
ms.openlocfilehash: 17257199647a0c51a0eabee9ee0b338680f7bcdf
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62388510"
---
# <a name="prepare-current-forest"></a>准备当前林

若要准备 Active Directory 域服务林，必须成功扩展架构（如运行架构准备主题中所述）并确保[](/previous-versions/office/lync-server-2013/lync-server-2013-preparing-the-active-directory-schema)架构已复制。

完成这些先决任务后，即可开始“步骤 3: 准备当前林”。要准备林，请以林根中 Domain Admins 组成员身份或正在准备的林的 Enterprise Admins 组成员身份登录到林根中的一台计算机。

1. 在部署向导的“步骤 3: 准备当前林”中，单击“运行”。

2. 在 **“准备林”** 页上，单击 **“下一步”**。

    > [!NOTE]
    > 林准备使您能够选择在 2015 年 10 月将通用组Skype for Business Server位置。 选择与组织要求一致的位置。

3. 在“正在执行命令”页上，查找“任务状态: 已完成”，然后单击“查看日志”。确保没有任何错误。查看警告以确定对于您的基础结构来说，它们是否为预期和典型的问题。

4. 在 **日志中的**"操作 **\<Success\>**"列下，展开"林准备"，在每项任务结束时查找"执行结果"以验证林准备是否成功完成，关闭日志，然后单击"完成 **"**。

5. 等待 Active Directory 域服务复制完成，或强制复制到林根域控制器 **的 Active Directory 站点** 和服务管理单元中列出的所有域控制器，然后再运行域准备。 在所有 Active Directory 站点中的域控制器之间强制进行复制，以使几分钟内就在站点中进行复制操作。

    > [!TIP]
    > 如果需要查看 Skype for Business Server 部署向导创建的日志文件，可以在运行部署向导的计算机上找到这些文件，位置是运行该步骤的 Active Directory 域服务用户的 Users 目录。 例如，如果用户以域 Contoso.net 的域管理员身份登录，则日志文件位于：C：\Users\Administrator.Contoso\AppData\Local\Temp