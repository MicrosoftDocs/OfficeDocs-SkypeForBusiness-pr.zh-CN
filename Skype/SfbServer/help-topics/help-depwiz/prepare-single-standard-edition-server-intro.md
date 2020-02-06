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
- CSH
ms.custom:
- ms.lync.dep.DeployAIOIntro
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fe11d380-54c9-47e7-a676-02b9a59dc93f
description: 要开始安装包含中央管理存储和你选择的其他 collocated 服务的 Skype for Business Server 2015 标准版服务器，你必须作为服务器上本地管理员组的成员登录，该成员将成为标准版服务器。 “准备单个 Standard Edition Server”页将详细阐述初始安装要求。 计算机必须是要部署在其中的域的成员，并且必须已成功为林完成架构、林和域准备。
ms.openlocfilehash: a426d734c7644511d31a5b53d3a4939c95f979f3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823466"
---
# <a name="prepare-single-standard-edition-server-intro"></a><span data-ttu-id="72eb7-105">准备单个 Standard Edition Server（简介）</span><span class="sxs-lookup"><span data-stu-id="72eb7-105">Prepare Single Standard Edition Server (Intro)</span></span>
 
<span data-ttu-id="72eb7-106">要开始安装包含中央管理存储和你选择的其他 collocated 服务的 Skype for Business Server 2015 标准版服务器，你必须作为服务器上本地管理员组的成员登录，该成员将成为标准版服务器。</span><span class="sxs-lookup"><span data-stu-id="72eb7-106">To begin the installation of a Skype for Business Server 2015 Standard Edition server that will hold the Central Management store and other collocated services that you select, you must be logged in as a member of the local Administrators group on the server that will become the Standard Edition server.</span></span> <span data-ttu-id="72eb7-107">“**准备单个 Standard Edition Server**”页将详细阐述初始安装要求。</span><span class="sxs-lookup"><span data-stu-id="72eb7-107">The **Prepare single Standard Edition Server** page details the requirements for the initial install.</span></span> <span data-ttu-id="72eb7-108">计算机必须是要部署在其中的域的成员，并且必须已成功为林完成架构、林和域准备。</span><span class="sxs-lookup"><span data-stu-id="72eb7-108">The computer must be a member of the domain in which you are going to deploy it, and you must have successfully completed the Schema, Forest, and Domain prep for your forest.</span></span>
  
<span data-ttu-id="72eb7-109">这一特定任务旨在将 Standard Edition Server 设置为基础结构中的第一台服务器。</span><span class="sxs-lookup"><span data-stu-id="72eb7-109">This particular task is designed to set up a Standard Edition server as the first server in your infrastructure.</span></span> <span data-ttu-id="72eb7-110">此任务将中央管理存储（即 SQL Server Express）安装到标准版服务器。</span><span class="sxs-lookup"><span data-stu-id="72eb7-110">This task installs the Central Management store, which is SQL Server Express, onto the Standard Edition server.</span></span> <span data-ttu-id="72eb7-111">如果已部署其他 Standard Edition Server 或前端池，则应单击“**取消**”。</span><span class="sxs-lookup"><span data-stu-id="72eb7-111">If you already have another Standard Edition server or Front End pool deployed, you should click **Cancel**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="72eb7-112">完成此任务后，你将安装拓扑生成器（如果尚未安装），并配置拓扑文档。</span><span class="sxs-lookup"><span data-stu-id="72eb7-112">After completing this task, you will install Topology Builder (if you have not already installed it) and configure your topology document.</span></span> <span data-ttu-id="72eb7-113">除非有中央管理存储可用（通过完成本主题中所述的任务进行部署），否则你无法发布拓扑文档。</span><span class="sxs-lookup"><span data-stu-id="72eb7-113">You cannot publish your topology document until you have a Central Management store available—which is deployed by completing the task described in this topic.</span></span> 
  

