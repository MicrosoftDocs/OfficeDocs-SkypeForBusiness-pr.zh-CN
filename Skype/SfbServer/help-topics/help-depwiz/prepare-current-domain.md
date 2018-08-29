---
title: 准备当前域
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainDomainPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bfcb37ca-34eb-4d0d-9694-6edd2e7fe0f3
description: 若要准备的企业服务器用户业务服务器 2015年或 Skype 运行 Skype 的主机服务器的域，您必须完成步骤 5： 准备当前域，使用安装程序运行域准备主题中所述。 要完成此步骤，必须以准备的域中 Domain Admins 组成员身份登录，或以该域所属的林中 Enterprise Admins 组成员身份登录。 若要准备域：
ms.openlocfilehash: 3d32329220c59f8d51497bce5412351c412a845d
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2018
ms.locfileid: "23260522"
---
# <a name="prepare-current-domain"></a>准备当前域

若要准备的企业服务器用户业务服务器 2015年或 Skype 运行 Skype 的主机服务器的域，您必须完成**步骤 5： 准备当前域**、 主题[使用 Setup 运行域准备过程](https://technet.microsoft.com/library/95dab800-1f2c-4506-b36c-99986643b149.aspx)中所述。 要完成此步骤，必须以准备的域中 Domain Admins 组成员身份登录，或以该域所属的林中 Enterprise Admins 组成员身份登录。 若要准备域：

1. 从业务服务器 2015年安装文件夹或介质 Skype，运行 Setup.exe 来启动 Skype 的业务 Server 部署向导。

2. 单击“**准备 Active Directory**”，然后等待确定部署状态。

3. 在“**步骤 5：准备当前域**”中，单击“**运行**”。

4. 在“**正在执行命令**”页上，查找“**任务状态：已完成**”，然后单击“**查看日志**”。

5. 在**操作**列中，展开**域准备**，查找**\<成功\>** 每项任务结束时执行结果，以验证是否已成功完成该域准备和关闭该日志中，然后单击**完成**。

> [!TIP]
> 如果您需要查看日志文件中的业务 Server 部署向导创建的 Skype，可以在其中运行步骤的 Active Directory 域服务用户的用户目录中运行部署向导的计算机上找到这些。 例如，如果用户登录以域管理员的域 Contoso.net 中，日志文件位于： C:\Users\Administrator.Contoso\AppData\Local\Temp。


