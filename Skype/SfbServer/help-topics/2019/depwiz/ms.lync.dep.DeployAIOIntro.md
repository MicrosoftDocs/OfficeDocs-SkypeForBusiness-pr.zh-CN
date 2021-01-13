---
title: 准备单个 Standard Edition Server（简介）
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployAIOIntro
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: fe11d380-54c9-47e7-a676-02b9a59dc93f
ROBOTS: NOINDEX, NOFOLLOW
description: 若要开始安装 Skype for Business Server Standard Edition Server，该服务器将保留中央管理存储以及您选择的其他并库服务，必须以将成为 Standard Edition Server 的服务器上本地 管理员组 的成员身份登录。 “准备单个 Standard Edition Server”页将详细阐述初始安装要求。 计算机必须是要部署在其中的域的成员，并且必须已成功为林完成架构、林和域准备。
ms.openlocfilehash: 08ea84c0d136339e782c32785c1c4fb536f877cd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820622"
---
# <a name="prepare-single-standard-edition-server-intro"></a>准备单个 Standard Edition Server（简介）
 
若要开始安装 Skype for Business Server Standard Edition Server，该服务器将保留中央管理存储以及您选择的其他并库服务，必须以将成为 Standard Edition Server 的服务器上本地 管理员组 的成员身份登录。 “准备单个 Standard Edition Server”页将详细阐述初始安装要求。 计算机必须是要部署在其中的域的成员，并且必须已成功为林完成架构、林和域准备。
  
这一特定任务旨在将 Standard Edition Server 设置为基础结构中的第一台服务器。 此任务将中央管理存储（SQL Server Express）安装到 Standard Edition Server。 如果已部署其他 Standard Edition Server 或前端池，则应单击“取消”。
  
> [!NOTE]
> 完成此任务后，如果尚未安装拓扑生成器 (配置拓扑文档，) 安装拓扑生成器。 在中央管理存储可用（通过完成本主题中所述的任务进行部署）之前，无法发布拓扑文档。 
  

