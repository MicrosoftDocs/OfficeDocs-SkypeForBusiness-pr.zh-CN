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
description: 若要开始新的 Skype 业务服务器 2015年角色服务器安装，必须首先安装将承载本地配置存储的本地 SQL Server。 本地配置存储将充当业务 Server 中央管理存储 (CMS) 的 Skype 的只读副本。 必须以计算机本地管理员的身份登录运行“安装本地配置存储”步骤的服务器，并具有 RTCUniversalServerAdmins 或 RTCUniversalGlobalReadOnlyGroup 组成员身份。 如果在边缘服务器上执行安装，则不需要具有 RTCUniversalServerAdmins 或 RTCUniversalGlobalReadOnlyGroup 组成员身份。 拓扑生成器定义文档将读取导出的定义文档而不是从中央管理存储。 若要导出的拓扑生成器定义文档，并使其可供边缘服务器，请参阅主题导出 Your Topology 并复制到外部介质它边缘安装。
ms.openlocfilehash: e25e43fbcd1001460d7b001d914e1801558af4f1
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2018
ms.locfileid: "26294077"
---
# <a name="install-local-configuration-store"></a><span data-ttu-id="7c7ee-108">安装本地配置存储</span><span class="sxs-lookup"><span data-stu-id="7c7ee-108">Install Local Configuration Store</span></span>

<span data-ttu-id="7c7ee-109">若要开始新的 Skype 业务服务器 2015年角色服务器安装，必须首先安装将承载本地配置存储的本地 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="7c7ee-109">To begin the installation of a new Skype for Business Server 2015 role server, you must first install the local SQL Server that will host the local configuration store.</span></span> <span data-ttu-id="7c7ee-110">本地配置存储将充当业务 Server 中央管理存储 (CMS) 的 Skype 的只读副本。</span><span class="sxs-lookup"><span data-stu-id="7c7ee-110">The local configuration store will act as a read-only replica of the Skype for Business Server Central Management store (CMS).</span></span> <span data-ttu-id="7c7ee-111">必须以计算机本地管理员的身份登录运行“**安装本地配置存储**”步骤的服务器，并具有 RTCUniversalServerAdmins 或 RTCUniversalGlobalReadOnlyGroup 组成员身份。</span><span class="sxs-lookup"><span data-stu-id="7c7ee-111">You must be logged on to the server that you are running the **Install Local Configuration Store** step as the local administrator on the computer, and have membership in the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="7c7ee-112">如果在边缘服务器上执行安装，则不需要具有 RTCUniversalServerAdmins 或 RTCUniversalGlobalReadOnlyGroup 组成员身份。</span><span class="sxs-lookup"><span data-stu-id="7c7ee-112">If you are performing the setup on an Edge Server, you do not have to be a member of the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="7c7ee-113">拓扑生成器定义文档将读取导出的定义文档而不是从中央管理存储。</span><span class="sxs-lookup"><span data-stu-id="7c7ee-113">The Topology Builder definition document will be read from the exported definition document instead of from the Central Management store.</span></span> <span data-ttu-id="7c7ee-114">若要导出的拓扑生成器定义文档，并使其可供边缘服务器，请参阅主题[导出 Your Topology and 复制到外部介质用于边缘安装它](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx)。</span><span class="sxs-lookup"><span data-stu-id="7c7ee-114">To export the Topology Builder definition document and make it available to the Edge Servers, see the topic[Export Your Topology and Copy It to External Media for Edge Installation](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).</span></span>

<span data-ttu-id="7c7ee-115">开始安装：</span><span class="sxs-lookup"><span data-stu-id="7c7ee-115">To begin the installation:</span></span>

1. <span data-ttu-id="7c7ee-116">Skype 业务服务器 2015年页上单击**步骤 1： 安装本地配置存储**，单击**运行**。</span><span class="sxs-lookup"><span data-stu-id="7c7ee-116">On the Skype for Business Server 2015 page, next to **Step1: Install Local Configuration Store**, click **Run**.</span></span>

2. <span data-ttu-id="7c7ee-117">在“**本地服务器配置**”页上，确保选择“**自动从中央管理存储检索配置**”选项，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="7c7ee-117">On the **Local Server Configuration** page, be sure that the **Retrieve configuration automatically from the Central Management Store** option is selected, and then click **Next**.</span></span>

3. <span data-ttu-id="7c7ee-118">完成本地服务器配置安装后，单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="7c7ee-118">When the local server configuration installation is complete, click **Finish**.</span></span>

> [!NOTE]
> <span data-ttu-id="7c7ee-119">本地 SQL Server 安装可能需要一些时间。</span><span class="sxs-lookup"><span data-stu-id="7c7ee-119">The installation of the local SQL Server can take some time.</span></span> <span data-ttu-id="7c7ee-120">正在安装 SQL Server 时，不会在进行中安装摘要屏幕上看到更新。</span><span class="sxs-lookup"><span data-stu-id="7c7ee-120">You will not see updates on progress in the installation summary screen while SQL Server is being installed.</span></span> <span data-ttu-id="7c7ee-121">如果要监视安装进度，请使用任务管理器观看 SQL Server 安装程序。</span><span class="sxs-lookup"><span data-stu-id="7c7ee-121">If you want to monitor the progress of the installation, use Task Manager to watch the SQL Server setup.</span></span>


