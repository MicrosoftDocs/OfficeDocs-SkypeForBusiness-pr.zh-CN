---
title: 准备单个 Standard Edition Server（简介）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployAIOIntro
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fe11d380-54c9-47e7-a676-02b9a59dc93f
description: 要开始安装包含中央管理存储和你选择的其他 collocated 服务的 Skype for Business Server 2015 标准版服务器，你必须作为服务器上本地管理员组的成员登录，该成员将成为标准版服务器。 “准备单个 Standard Edition Server”页将详细阐述初始安装要求。 计算机必须是要部署在其中的域的成员，并且必须已成功为林完成架构、林和域准备。
ms.openlocfilehash: ed7c353f602d97842e654faa5b539a6dcae01133
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41687345"
---
# <a name="prepare-single-standard-edition-server-intro"></a>准备单个 Standard Edition Server（简介）
 
要开始安装包含中央管理存储和你选择的其他 collocated 服务的 Skype for Business Server 2015 标准版服务器，你必须作为服务器上本地管理员组的成员登录，该成员将成为标准版服务器。 “**准备单个 Standard Edition Server**”页将详细阐述初始安装要求。 计算机必须是要部署在其中的域的成员，并且必须已成功为林完成架构、林和域准备。
  
这一特定任务旨在将 Standard Edition Server 设置为基础结构中的第一台服务器。 此任务将中央管理存储（即 SQL Server Express）安装到标准版服务器。 如果已部署其他 Standard Edition Server 或前端池，则应单击“**取消**”。
  
> [!NOTE]
> 完成此任务后，你将安装拓扑生成器（如果尚未安装），并配置拓扑文档。 除非有中央管理存储可用（通过完成本主题中所述的任务进行部署），否则你无法发布拓扑文档。 
  

