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
description: 若要开始安装新的 Skype for Business Server 2015 角色服务器，必须先安装将SQL Server本地配置存储的本地服务器。 本地配置存储将充当 CMS 中 Skype for Business Server 中央管理存储 (只读) 。 必须以计算机本地管理员的身份登录运行“安装本地配置存储”步骤的服务器，并具有 RTCUniversalServerAdmins 或 RTCUniversalGlobalReadOnlyGroup 组成员身份。 如果在边缘服务器上执行安装，则不需要具有 RTCUniversalServerAdmins 或 RTCUniversalGlobalReadOnlyGroup 组成员身份。 拓扑生成器定义文档将读取导出的定义文档，而不是从中央管理存储中读取。 若要导出拓扑生成器定义文档，使其对边缘服务器可用，请参阅主题 Export Your Topology and Copy It to External Media for Edge Installation。
ms.openlocfilehash: 62a16e441cc95e77aaed7e09152ef2a79221d85f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51108738"
---
# <a name="install-local-configuration-store"></a><span data-ttu-id="9a51c-108">安装本地配置存储</span><span class="sxs-lookup"><span data-stu-id="9a51c-108">Install Local Configuration Store</span></span>

<span data-ttu-id="9a51c-109">若要开始安装新的 Skype for Business Server 2015 角色服务器，必须先安装将SQL Server本地配置存储的本地服务器。</span><span class="sxs-lookup"><span data-stu-id="9a51c-109">To begin the installation of a new Skype for Business Server 2015 role server, you must first install the local SQL Server that will host the local configuration store.</span></span> <span data-ttu-id="9a51c-110">本地配置存储将充当 CMS 中 Skype for Business Server 中央管理存储 (只读) 。</span><span class="sxs-lookup"><span data-stu-id="9a51c-110">The local configuration store will act as a read-only replica of the Skype for Business Server Central Management store (CMS).</span></span> <span data-ttu-id="9a51c-111">必须以计算机本地管理员的身份登录运行 **“安装本地配置存储”** 步骤的服务器，并具有 RTCUniversalServerAdmins 或 RTCUniversalGlobalReadOnlyGroup 组成员身份。</span><span class="sxs-lookup"><span data-stu-id="9a51c-111">You must be logged on to the server that you are running the **Install Local Configuration Store** step as the local administrator on the computer, and have membership in the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="9a51c-112">如果在边缘服务器上执行安装，则不需要具有 RTCUniversalServerAdmins 或 RTCUniversalGlobalReadOnlyGroup 组成员身份。</span><span class="sxs-lookup"><span data-stu-id="9a51c-112">If you are performing the setup on an Edge Server, you do not have to be a member of the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="9a51c-113">拓扑生成器定义文档将读取导出的定义文档，而不是从中央管理存储中读取。</span><span class="sxs-lookup"><span data-stu-id="9a51c-113">The Topology Builder definition document will be read from the exported definition document instead of from the Central Management store.</span></span> <span data-ttu-id="9a51c-114">若要导出拓扑生成器定义文档，使其对边缘服务器可用，请参阅主题 Export Your [Topology and Copy It to External Media for Edge Installation。](/previous-versions/office/lync-server-2013/lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation)</span><span class="sxs-lookup"><span data-stu-id="9a51c-114">To export the Topology Builder definition document and make it available to the Edge Servers, see the topic [Export Your Topology and Copy It to External Media for Edge Installation](/previous-versions/office/lync-server-2013/lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation).</span></span>

<span data-ttu-id="9a51c-115">开始安装：</span><span class="sxs-lookup"><span data-stu-id="9a51c-115">To begin the installation:</span></span>

1. <span data-ttu-id="9a51c-116">在 Skype for Business Server 2015 页面上，在"**步骤 1： 安装本地配置** 存储"旁边，单击"运行 **"。**</span><span class="sxs-lookup"><span data-stu-id="9a51c-116">On the Skype for Business Server 2015 page, next to **Step1: Install Local Configuration Store**, click **Run**.</span></span>

2. <span data-ttu-id="9a51c-117">在"**本地服务器配置"** 页上，确保选中"从中央管理存储自动检索配置"选项，然后单击"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="9a51c-117">On the **Local Server Configuration** page, be sure that the **Retrieve configuration automatically from the Central Management Store** option is selected, and then click **Next**.</span></span>

3. <span data-ttu-id="9a51c-118">完成本地服务器配置安装后，单击 **“完成”**。</span><span class="sxs-lookup"><span data-stu-id="9a51c-118">When the local server configuration installation is complete, click **Finish**.</span></span>

> [!NOTE]
> <span data-ttu-id="9a51c-119">安装本地 SQL Server可能需要一些时间。</span><span class="sxs-lookup"><span data-stu-id="9a51c-119">The installation of the local SQL Server can take some time.</span></span> <span data-ttu-id="9a51c-120">在安装更新时，你将不会在安装摘要屏幕SQL Server更新。</span><span class="sxs-lookup"><span data-stu-id="9a51c-120">You will not see updates on progress in the installation summary screen while SQL Server is being installed.</span></span> <span data-ttu-id="9a51c-121">如果要监视安装进度，请使用任务管理器来监视SQL Server设置。</span><span class="sxs-lookup"><span data-stu-id="9a51c-121">If you want to monitor the progress of the installation, use Task Manager to watch the SQL Server setup.</span></span>