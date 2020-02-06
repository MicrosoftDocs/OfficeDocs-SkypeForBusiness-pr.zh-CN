---
title: 准备当前域
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 若要准备域以托管运行 Skype for Business 服务器或 Skype for business 服务器用户的服务器，您必须完成步骤5：准备当前域，如使用安装程序运行域准备主题中所述。 要完成此步骤，必须以准备的域中 Domain Admins 组成员身份登录，或以该域所属的林中 Enterprise Admins 组成员身份登录。 若要准备域：
ms.openlocfilehash: 2902e92f2b785e43208d46b714d069f382bb24f7
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798319"
---
# <a name="prepare-current-domain"></a>准备当前域

若要准备域以托管运行 Skype for Business 服务器或 Skype for business 服务器用户的服务器，您必须完成**步骤5：准备当前域**，如[使用安装程序运行域准备](https://technet.microsoft.com/library/95dab800-1f2c-4506-b36c-99986643b149.aspx)主题中所述。 要完成此步骤，必须以准备的域中 Domain Admins 组成员身份登录，或以该域所属的林中 Enterprise Admins 组成员身份登录。 若要准备域：

1. 从 Skype for Business 服务器安装文件夹或媒体中，运行 Setup.exe 以启动 Skype for Business 服务器部署向导。

2. 单击“**准备 Active Directory**”，然后等待确定部署状态。

3. 在“**步骤 5：准备当前域**”中，单击“**运行**”。

4. 在“**正在执行命令**”页上，查找“**任务状态：已完成**”，然后单击“**查看日志**”。

5. 在 "**操作**" 列下，展开 "**域准备**"，查找每个任务末尾的** \<\>成功**执行结果，验证域准备是否成功完成，关闭日志，然后单击 "**完成**"。

> [!TIP]
> 如果你需要查看由 Skype for Business Server 部署向导创建的日志文件，你可以在运行该步骤的 Active Directory 域服务用户的用户目录中找到运行部署向导的计算机上的日志文件。 例如，如果用户在域 Contoso.net 中以域管理员身份登录，则日志文件位于： C:\Users\Administrator.Contoso\AppData\Local\Temp。


