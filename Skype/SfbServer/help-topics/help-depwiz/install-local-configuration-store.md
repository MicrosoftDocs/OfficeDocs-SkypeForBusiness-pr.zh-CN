---
title: 安装本地配置存储
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/13/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
description: 若要开始安装新的 Skype for Business Server 2015 角色服务器，必须先安装将SQL Server本地配置存储的本地服务器。 本地配置存储将充当 CMS (Skype for Business Server 中央管理存储) 。 必须以计算机本地管理员的身份登录运行“安装本地配置存储”步骤的服务器，并具有 RTCUniversalServerAdmins 或 RTCUniversalGlobalReadOnlyGroup 组成员身份。 如果在边缘服务器上执行安装，则不需要具有 RTCUniversalServerAdmins 或 RTCUniversalGlobalReadOnlyGroup 组成员身份。 拓扑生成器定义文档将读取导出的定义文档，而不是从中央管理存储中读取。 若要导出拓扑生成器定义文档并提供给边缘服务器，请参阅主题"导出拓扑并复制到外部媒体以用于边缘安装"。
ms.openlocfilehash: 630a3682d3dd5ca12381d5f5b549bb22121b579e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827142"
---
# <a name="install-local-configuration-store"></a>安装本地配置存储

若要开始安装新的 Skype for Business Server 2015 角色服务器，必须先安装将SQL Server本地配置存储的本地服务器。 本地配置存储将充当 CMS (Skype for Business Server 中央管理存储) 。 必须以计算机本地管理员的身份登录运行 **“安装本地配置存储”** 步骤的服务器，并具有 RTCUniversalServerAdmins 或 RTCUniversalGlobalReadOnlyGroup 组成员身份。 如果在边缘服务器上执行安装，则不需要具有 RTCUniversalServerAdmins 或 RTCUniversalGlobalReadOnlyGroup 组成员身份。 拓扑生成器定义文档将读取导出的定义文档，而不是从中央管理存储中读取。 若要导出拓扑生成器定义文档并提供给边缘服务器，请参阅主题"导出拓扑并复制到外部媒体[以用于边缘安装"。](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx)

开始安装：

1. 在 Skype for Business Server 2015 页面上，在"**步骤 1： 安装本地配置存储**"旁边，单击"**运行"。**

2. 在"**本地服务器配置**"页上，确保已选中"从中央管理存储自动检索配置"选项，然后单击"下一 **步"。**

3. 完成本地服务器配置安装后，单击 **“完成”**。

> [!NOTE]
> 安装本地SQL Server可能需要一些时间。 安装升级时，安装摘要屏幕中不会SQL Server更新。 如果要监视安装进度，请使用任务管理器监视SQL Server安装。


