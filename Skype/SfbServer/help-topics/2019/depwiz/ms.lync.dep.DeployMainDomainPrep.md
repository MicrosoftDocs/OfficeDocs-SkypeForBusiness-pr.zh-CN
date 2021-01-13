---
title: 准备当前域
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainDomainPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: bfcb37ca-34eb-4d0d-9694-6edd2e7fe0f3
ROBOTS: NOINDEX, NOFOLLOW
description: 若要准备域以托管运行 Skype for Business Server 或 Skype for Business Server 用户的服务器，必须完成步骤 5：准备当前域，如主题"使用安装程序运行域准备"中所述。 要完成此步骤，必须以准备的域中 Domain Admins 组成员身份登录，或以该域所属的林中 Enterprise Admins 组成员身份登录。 要准备域，请执行以下操作：
ms.openlocfilehash: d6e2efb774d7cad653c0a95e0e2863b97efe55ff
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824932"
---
# <a name="prepare-current-domain"></a>准备当前域

若要准备用于托管运行 Skype for Business Server 或 Skype for Business Server 用户的服务器的域，必须完成步骤 **5：** 准备当前域，如主题"使用安装程序运行域 [准备"中所述](https://technet.microsoft.com/library/95dab800-1f2c-4506-b36c-99986643b149.aspx)。 要完成此步骤，必须以准备的域中 Domain Admins 组成员身份登录，或以该域所属的林中 Enterprise Admins 组成员身份登录。 要准备域，请执行以下操作：

1. 从 Skype for Business Server 安装文件夹或媒体中，Setup.exe启动 Skype for Business Server 部署向导。

2. 单击“准备 Active Directory”，然后等待确定部署状态。

3. 在“步骤 5: 准备当前域”中，单击“运行”。

4. 在“正在执行命令”页上，查找“任务状态: 已完成”，然后单击“查看日志”。

5. 在"**操作**"列下，展开"域准备"，在每项任务结束时查找执行结果以验证域准备是否成功完成， **\<Success\>** 关闭日志，然后单击"**完成"。**

> [!TIP]
> 如果需要查看由 Skype for Business Server 部署向导创建的日志文件，可以在运行部署向导的计算机上找到这些文件，这些日志文件位于运行该步骤的 Active Directory 域服务用户的 Users 目录中。 例如，如果用户以域 Contoso.net 的域管理员身份登录，则日志文件位于：C：\Users\Administrator.Contoso\AppData\Local\Temp。


