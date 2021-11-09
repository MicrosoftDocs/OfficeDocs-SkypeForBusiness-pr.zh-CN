---
title: 准备当前域
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainDomainPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: bfcb37ca-34eb-4d0d-9694-6edd2e7fe0f3
ROBOTS: NOINDEX, NOFOLLOW
description: 若要准备一个域以托管运行 Skype for Business Server 或 Skype for Business Server 用户的服务器，必须完成步骤 5：准备当前域，如使用安装程序运行域准备主题中所述。 要完成此步骤，必须以准备的域中 Domain Admins 组成员身份登录，或以该域所属的林中 Enterprise Admins 组成员身份登录。 要准备域，请执行以下操作：
ms.openlocfilehash: f62031c36365abb974a41a0a6e9ed9557c3215ac
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60838274"
---
# <a name="prepare-current-domain"></a>准备当前域

若要准备域以托管Skype for Business Server或 Skype for Business Server 服务器的域，必须完成步骤 **5：** 准备当前域，如使用安装程序运行域准备主题 [中所述](/previous-versions/office/lync-server-2013/lync-server-2013-running-domain-preparation)。 要完成此步骤，必须以准备的域中 Domain Admins 组成员身份登录，或以该域所属的林中 Enterprise Admins 组成员身份登录。 要准备域，请执行以下操作：

1. 从Skype for Business Server安装文件夹或媒体中，Setup.exe启动"Skype for Business Server向导"。

2. 单击“准备 Active Directory”，然后等待确定部署状态。

3. 在“步骤 5: 准备当前域”中，单击“运行”。

4. 在“正在执行命令”页上，查找“任务状态: 已完成”，然后单击“查看日志”。

5. 在"**操作**"列下，展开"域准备"，在每项任务结束时查找"执行结果"以验证域准备是否成功完成，关闭日志，然后单击 **\<Success\>** "完成 **"。**

> [!TIP]
> 如果需要查看 Skype for Business Server 部署向导创建的日志文件，可以在运行部署向导的计算机上找到这些文件，该计算机位于运行该步骤的 Active Directory 域服务用户的 Users 目录中。 例如，如果用户以域 Contoso.net 的域管理员身份登录，则日志文件位于：C：\Users\Administrator.Contoso\AppData\Local\Temp。