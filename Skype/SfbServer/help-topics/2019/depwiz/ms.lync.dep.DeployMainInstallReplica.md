---
title: 安装本地配置存储
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
ROBOTS: NOINDEX, NOFOLLOW
description: 若要开始新的 Skype 业务服务器角色服务器安装，必须首先安装将承载本地配置存储的本地 SQL Server。 本地配置存储将充当业务 Server 中央管理存储 (CMS) 的 Skype 的只读副本。
ms.openlocfilehash: 1aa0e033991c91edd0ff6eef225d357fd9ff0e95
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/28/2018
ms.locfileid: "23260683"
---
# <a name="install-local-configuration-store"></a>安装本地配置存储

若要开始新的 Skype 业务服务器角色服务器安装，必须首先安装将承载本地配置存储的本地 SQL Server。 本地配置存储将充当业务 Server 中央管理存储 (CMS) 的 Skype 的只读副本。 必须以计算机本地管理员的身份登录运行“**安装本地配置存储**”步骤的服务器，并具有 RTCUniversalServerAdmins 或 RTCUniversalGlobalReadOnlyGroup 组成员身份。 如果在边缘服务器上执行安装，则不需要具有 RTCUniversalServerAdmins 或 RTCUniversalGlobalReadOnlyGroup 组成员身份。 拓扑生成器定义文档将读取导出的定义文档而不是从中央管理存储。 若要导出的拓扑生成器定义文档，并使其可供边缘服务器，请参阅主题[导出 Your Topology and 复制到外部介质用于边缘安装它](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx)。

开始安装：

1. Skype Business Server 页上单击**步骤 1： 安装本地配置存储**，单击**运行**。

2. 在“**本地服务器配置**”页上，确保选择“**自动从中央管理存储检索配置**”选项，然后单击“**下一步**”。

3. 完成本地服务器配置安装后，单击“**完成**”。

> [!NOTE]
> 本地 SQL Server 安装可能需要一些时间。 正在安装 SQL Server 时，不会在进行中安装摘要屏幕上看到更新。 如果要监视安装进度，请使用任务管理器观看 SQL Server 安装程序。


