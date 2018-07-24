---
title: 准备单个 Standard Edition Server（简介）
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployAIOIntro
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fe11d380-54c9-47e7-a676-02b9a59dc93f
ROBOTS: NOINDEX, NOFOLLOW
description: 若要开始安装 Business Server Standard Edition server 中央管理存储和您选择其他并置的服务将保存 Skype，您必须登录将成为的服务器上本地 Administrators 组的成员身份Standard Edition server。 “准备单个 Standard Edition Server”页将详细阐述初始安装要求。 计算机必须是要部署在其中的域的成员，并且必须已成功为林完成架构、林和域准备。
ms.openlocfilehash: a1d14b5d651cac9a3a779e78be48ecf45d4980bd
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20987069"
---
# <a name="prepare-single-standard-edition-server-intro"></a><span data-ttu-id="85748-105">准备单个 Standard Edition Server（简介）</span><span class="sxs-lookup"><span data-stu-id="85748-105">Prepare Single Standard Edition Server (Intro)</span></span>
 
<span data-ttu-id="85748-106">若要开始安装 Business Server Standard Edition server 中央管理存储和您选择其他并置的服务将保存 Skype，您必须登录将成为的服务器上本地 Administrators 组的成员身份Standard Edition server。</span><span class="sxs-lookup"><span data-stu-id="85748-106">To begin the installation of a Skype for Business Server Standard Edition server that will hold the Central Management store and other collocated services that you select, you must be logged in as a member of the local Administrators group on the server that will become the Standard Edition server.</span></span> <span data-ttu-id="85748-107">“**准备单个 Standard Edition Server**”页将详细阐述初始安装要求。</span><span class="sxs-lookup"><span data-stu-id="85748-107">The **Prepare single Standard Edition Server** page details the requirements for the initial install.</span></span> <span data-ttu-id="85748-108">计算机必须是要部署在其中的域的成员，并且必须已成功为林完成架构、林和域准备。</span><span class="sxs-lookup"><span data-stu-id="85748-108">The computer must be a member of the domain in which you are going to deploy it, and you must have successfully completed the Schema, Forest, and Domain prep for your forest.</span></span>
  
<span data-ttu-id="85748-109">这一特定任务旨在将 Standard Edition Server 设置为基础结构中的第一台服务器。</span><span class="sxs-lookup"><span data-stu-id="85748-109">This particular task is designed to set up a Standard Edition server as the first server in your infrastructure.</span></span> <span data-ttu-id="85748-110">此任务将安装中央管理存储，它是 Standard Edition server 上的 SQL Server Express。</span><span class="sxs-lookup"><span data-stu-id="85748-110">This task installs the Central Management store, which is SQL Server Express, onto the Standard Edition server.</span></span> <span data-ttu-id="85748-111">如果已部署其他 Standard Edition Server 或前端池，则应单击“**取消**”。</span><span class="sxs-lookup"><span data-stu-id="85748-111">If you already have another Standard Edition server or Front End pool deployed, you should click **Cancel**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="85748-112">完成此任务后，将安装拓扑生成器 （如果尚未安装它） 和配置拓扑文档。</span><span class="sxs-lookup"><span data-stu-id="85748-112">After completing this task, you will install Topology Builder (if you have not already installed it) and configure your topology document.</span></span> <span data-ttu-id="85748-113">不能发布拓扑文档，直到您拥有可用中央管理存储 — 该部署完成本主题中描述的任务。</span><span class="sxs-lookup"><span data-stu-id="85748-113">You cannot publish your topology document until you have a Central Management store available—which is deployed by completing the task described in this topic.</span></span> 
  

