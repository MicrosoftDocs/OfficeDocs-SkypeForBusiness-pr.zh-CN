---
title: 准备当前林
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainForestPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 11f5e359-97eb-45f7-a730-9ddbbaa40b83
ROBOTS: NOINDEX, NOFOLLOW
description: 若要准备 Active Directory 域服务林，必须成功扩展架构，如"运行架构准备"主题中所述，并确保架构已复制。
ms.openlocfilehash: 4881cb85134fef81cd741d834f319a76d4028e59
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833822"
---
# <a name="prepare-current-forest"></a>准备当前林

若要准备 Active Directory 域服务林，必须成功扩展架构，如"运行架构准备[](https://technet.microsoft.com/library/067726ae-fd3f-4133-a32f-26d2603ac674.aspx)"主题中所述，并确保架构已复制。

完成这些先决任务后，即可开始“步骤 3: 准备当前林”。要准备林，请以林根中 Domain Admins 组成员身份或正在准备的林的 Enterprise Admins 组成员身份登录到林根中的一台计算机。

1. 在部署向导的“步骤 3: 准备当前林”中，单击“运行”。

2. 在 **“准备林”** 页上，单击 **“下一步”**。

    > [!NOTE]
    > 林准备使你能够选择放置 Skype for Business Server 的通用组的位置。 选择与组织要求一致的位置。

3. 在“正在执行命令”页上，查找“任务状态: 已完成”，然后单击“查看日志”。确保没有任何错误。查看警告以确定对于您的基础结构来说，它们是否为预期和典型的问题。

4. 在日志中的"操作"列下，展开"林准备"，在每项任务结束时查找执行结果以验证林准备是否成功完成， **\<Success\>** 关闭日志，然后单击"**完成"。**

5. 等待 Active Directory 域服务复制完成，或强制复制到林根域控制器 **的 Active Directory 站点** 和服务管理单元中列出的所有域控制器，然后再运行域准备。 在所有 Active Directory 站点中的域控制器之间强制进行复制，以使几分钟内就在站点中进行复制操作。

    > [!TIP]
    > 如果需要查看由 Skype for Business Server 部署向导创建的日志文件，可以在运行部署向导的计算机上找到这些文件，位于运行该步骤的 Active Directory 域服务用户的 Users 目录中。 例如，如果用户以域 Contoso.net 域管理员身份登录，则日志文件位于：C：\Users\Administrator.Contoso\AppData\Local\Temp


