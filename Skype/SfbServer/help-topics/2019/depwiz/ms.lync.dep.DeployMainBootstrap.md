---
title: 安装或删除 Skype for Business Server 组件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainBootstrap
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: f8813f25-eafa-4006-a186-94e4ebcc5ac7
ROBOTS: NOINDEX, NOFOLLOW
description: 若要安装和激活、停用或卸载 Skype for Business 服务器组件，请使用步骤2：设置或删除 Skype 服务器组件。 你必须以你正在安装或修改的计算机上的本地管理员身份登录，并且必须能够读取当前域中的 Active Directory 域服务用户和组。 要开始，请单击“运行”。 执行此操作时，会读取基于中央管理存储的拓扑定义。 需要根据中央管理存储中定义的角色来安装和配置必需的软件组件。 安装完成后，请检查摘要，然后单击“完成”。
ms.openlocfilehash: d19d4946af48f96066d01cea33f0a5c04c22f816
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41798359"
---
# <a name="setup-or-remove-skype-for-business-server-components"></a>安装或删除 Skype for Business Server 组件
 
若要安装和激活、停用或卸载 Skype for Business 服务器组件，请使用**步骤2：设置或删除 Skype 服务器组件**。 你必须以你正在安装或修改的计算机上的本地管理员身份登录，并且必须能够读取当前域中的 Active Directory 域服务用户和组。 要开始，请单击“**运行**”。 执行此操作时，会读取基于中央管理存储的拓扑定义。 需要根据中央管理存储中定义的角色来安装和配置必需的软件组件。 安装完成后，请检查摘要，然后单击“**完成**”。
  
> [!TIP]
> 如果需要查看由部署向导创建的日志文件，可以在运行部署向导的计算机上的 "用户" 目录中找到这些文件，这些文件是在运行该步骤的 Active Directory 用户的用户目录中。 例如，如果用户在域 Contoso.net 中以域管理员身份登录，则日志文件位于： > C:\Users\Administrator.Contoso\AppData\Local\Temp 
  
> [!NOTE]
> 如果之前已在此计算机上安装了 Skype for business 服务器组件，则部署向导将识别此问题，并且步骤2中的按钮将再次显示为 "**运行**"。 这样，您就可以根据需要多次运行此步骤，以正确配置或修改服务器。 
  

