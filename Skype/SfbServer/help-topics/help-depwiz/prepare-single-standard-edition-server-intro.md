---
title: 准备单个 Standard Edition Server（简介）
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/23/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployAIOIntro
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fe11d380-54c9-47e7-a676-02b9a59dc93f
description: 若要开始安装将保留中央管理存储以及您选择的其他并场服务的 Skype for Business Server 2015 Standard Edition 服务器，您必须以将成为 Standard Edition 服务器的服务器上本地 管理员组 的成员身份登录。 “准备单个 Standard Edition Server”页将详细阐述初始安装要求。 计算机必须是要部署在其中的域的成员，并且必须已成功为林完成架构、林和域准备。
ms.openlocfilehash: daca3f64809b6ea6d2ed5e94cdaf3a38ebef6f4d9ba75885b6d6d0aff50ecfd3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54313520"
---
# <a name="prepare-single-standard-edition-server-intro"></a>准备单个 Standard Edition Server（简介）
 
若要开始安装将保留中央管理存储以及您选择的其他并场服务的 Skype for Business Server 2015 Standard Edition 服务器，您必须以将成为 Standard Edition 服务器的服务器上本地 管理员组 的成员身份登录。 “准备单个 Standard Edition Server”页将详细阐述初始安装要求。 计算机必须是要部署在其中的域的成员，并且必须已成功为林完成架构、林和域准备。
  
这一特定任务旨在将 Standard Edition Server 设置为基础结构中的第一台服务器。 此任务将中央管理存储（SQL Server Express）安装到Standard Edition服务器上。 如果已部署其他 Standard Edition Server 或前端池，则应单击“取消”。
  
> [!NOTE]
> 完成此任务后，如果尚未安装拓扑生成器 (安装拓扑生成器) 配置拓扑文档。 在提供中央管理存储（通过完成本主题中介绍的任务进行部署）之前，无法发布拓扑文档。 
  

