---
title: 安装本地配置存储
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
ROBOTS: NOINDEX, NOFOLLOW
description: 若要开始安装新的 Skype for Business Server 角色服务器，必须先安装将SQL Server本地配置存储的本地服务器。 本地配置存储将充当 CMS 管理中心Skype for Business Server管理 (只读) 。
ms.openlocfilehash: 2b5ce85cbcfe907ed56c855929ed534bc755ec3e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58621624"
---
# <a name="install-local-configuration-store"></a>安装本地配置存储

若要开始安装新的 Skype for Business Server 角色服务器，必须先安装将SQL Server本地配置存储的本地服务器。 本地配置存储将充当 CMS 管理中心Skype for Business Server管理 (只读) 。 必须以计算机本地管理员的身份登录运行 **“安装本地配置存储”** 步骤的服务器，并具有 RTCUniversalServerAdmins 或 RTCUniversalGlobalReadOnlyGroup 组成员身份。 如果在边缘服务器上执行安装，则不需要具有 RTCUniversalServerAdmins 或 RTCUniversalGlobalReadOnlyGroup 组成员身份。 拓扑生成器定义文档将读取导出的定义文档，而不是从中央管理存储中读取。 若要导出拓扑生成器定义文档，使其对边缘服务器可用，请参阅主题 Export Your[Topology and Copy It to External Media for Edge Installation。](/previous-versions/office/lync-server-2013/lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation)

开始安装：

1. 在"Skype for Business Server"页上，单击"步骤 **1： 安装本地配置存储"** 旁边的"运行 **"。**

2. 在"**本地服务器配置"** 页上，确保选中"从中央管理存储自动检索配置"选项，然后单击"下一步 **"。**

3. 完成本地服务器配置安装后，单击 **“完成”**。

> [!NOTE]
> 安装本地SQL Server可能需要一些时间。 在安装更新时，你将不会在安装摘要屏幕SQL Server更新。 如果要监视安装进度，请使用任务管理器来监视SQL Server设置。