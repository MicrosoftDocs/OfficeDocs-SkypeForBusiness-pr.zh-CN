---
title: 安装本地配置存储
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 4/13/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
description: 若要开始新的 Skype 业务服务器 2015年角色服务器的安装，必须首先安装本地 SQL Server 将承载本地配置存储。 本地配置存储将作为业务服务器集中管理存储 (CMS) 的 Skype 的只读副本。 必须登录到服务器，您的计算机上以本地管理员身份运行安装本地配置存储步骤并且有 RTCUniversalServerAdmins 或 RTCUniversalGlobalReadOnlyGroup 组中的成员资格。 如果在边缘服务器上执行安装，则不需要具有 RTCUniversalServerAdmins 或 RTCUniversalGlobalReadOnlyGroup 组成员身份。 拓扑生成器定义文档将从导出的定义文档而不是从中央管理存储读取。 要导出拓扑生成器定义文档并将其提供给边缘服务器，请参阅主题导出您的拓扑并复制到外部介质它边缘安装。
ms.openlocfilehash: adce98e053b6959c3513885fc53f1616df1c1125
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="install-local-configuration-store"></a>安装本地配置存储
 
若要开始新的 Skype 业务服务器 2015年角色服务器的安装，必须首先安装本地 SQL Server 将承载本地配置存储。 本地配置存储将作为业务服务器集中管理存储 (CMS) 的 Skype 的只读副本。 必须以计算机本地管理员的身份登录运行“**安装本地配置存储**”步骤的服务器，并具有 RTCUniversalServerAdmins 或 RTCUniversalGlobalReadOnlyGroup 组成员身份。 如果在边缘服务器上执行安装，则不需要具有 RTCUniversalServerAdmins 或 RTCUniversalGlobalReadOnlyGroup 组成员身份。 拓扑生成器定义文档将从导出的定义文档而不是从中央管理存储读取。 若要导出拓扑生成器定义文档并将其提供给边缘服务器，请参阅[导出您的拓扑结构和复制到外部介质边缘安装它](http://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx)的主题。
  
开始安装：
  
1. 对于业务服务器 2015年页，Skype 在旁边**步骤 1： 安装本地配置存储**，单击**运行**。
    
2. 在“**本地服务器配置**”页上，确保选择“**自动从中央管理存储检索配置**”选项，然后单击“**下一步**”。
    
3. 完成本地服务器配置安装后，单击“**完成**”。
    
> [!NOTE]
> 本地 SQL Server 安装可能需要一些时间。 正在安装 SQL Server 时，不会在进度中安装摘要屏幕上看到更新。 如果您想要监视安装进度，使用任务管理器监视 SQL Server 安装程序。 
  

