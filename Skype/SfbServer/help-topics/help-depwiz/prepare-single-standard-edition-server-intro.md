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
description: 若要开始安装 Skype for Business Server 2015 Standard Edition Server，该服务器将保留中央管理存储以及您选择的其他并并的服务，您必须以将成为 Standard Edition Server 的服务器上本地 管理员组 的成员身份登录。 “准备单个 Standard Edition Server”页将详细阐述初始安装要求。 计算机必须是要部署在其中的域的成员，并且必须已成功为林完成架构、林和域准备。
ms.openlocfilehash: 0523645350c6d6f2c0e42237b944f29193e06555
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49829778"
---
# <a name="prepare-single-standard-edition-server-intro"></a><span data-ttu-id="c48ea-105">准备单个 Standard Edition Server（简介）</span><span class="sxs-lookup"><span data-stu-id="c48ea-105">Prepare Single Standard Edition Server (Intro)</span></span>
 
<span data-ttu-id="c48ea-106">若要开始安装 Skype for Business Server 2015 Standard Edition Server，该服务器将保留中央管理存储以及您选择的其他并并的服务，您必须以将成为 Standard Edition Server 的服务器上本地 管理员组 的成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="c48ea-106">To begin the installation of a Skype for Business Server 2015 Standard Edition server that will hold the Central Management store and other collocated services that you select, you must be logged in as a member of the local Administrators group on the server that will become the Standard Edition server.</span></span> <span data-ttu-id="c48ea-107">“准备单个 Standard Edition Server”页将详细阐述初始安装要求。</span><span class="sxs-lookup"><span data-stu-id="c48ea-107">The **Prepare single Standard Edition Server** page details the requirements for the initial install.</span></span> <span data-ttu-id="c48ea-108">计算机必须是要部署在其中的域的成员，并且必须已成功为林完成架构、林和域准备。</span><span class="sxs-lookup"><span data-stu-id="c48ea-108">The computer must be a member of the domain in which you are going to deploy it, and you must have successfully completed the Schema, Forest, and Domain prep for your forest.</span></span>
  
<span data-ttu-id="c48ea-109">这一特定任务旨在将 Standard Edition Server 设置为基础结构中的第一台服务器。</span><span class="sxs-lookup"><span data-stu-id="c48ea-109">This particular task is designed to set up a Standard Edition server as the first server in your infrastructure.</span></span> <span data-ttu-id="c48ea-110">此任务将中央管理存储（SQL Server Express）安装到 Standard Edition Server。</span><span class="sxs-lookup"><span data-stu-id="c48ea-110">This task installs the Central Management store, which is SQL Server Express, onto the Standard Edition server.</span></span> <span data-ttu-id="c48ea-111">如果已部署其他 Standard Edition Server 或前端池，则应单击“取消”。</span><span class="sxs-lookup"><span data-stu-id="c48ea-111">If you already have another Standard Edition server or Front End pool deployed, you should click **Cancel**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c48ea-112">完成此任务后，如果尚未安装拓扑生成器 (配置拓扑文档，) 安装拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="c48ea-112">After completing this task, you will install Topology Builder (if you have not already installed it) and configure your topology document.</span></span> <span data-ttu-id="c48ea-113">在中央管理存储可用（通过完成本主题中所述的任务进行部署）之前，无法发布拓扑文档。</span><span class="sxs-lookup"><span data-stu-id="c48ea-113">You cannot publish your topology document until you have a Central Management store available—which is deployed by completing the task described in this topic.</span></span> 
  

