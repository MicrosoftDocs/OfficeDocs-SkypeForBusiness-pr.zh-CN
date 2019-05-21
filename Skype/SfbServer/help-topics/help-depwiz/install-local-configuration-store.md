---
title: 安装本地配置存储
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/13/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
description: 若要开始安装新的 Skype for Business Server 2015 角色服务器, 必须首先安装将托管本地配置存储的本地 SQL Server。 本地配置存储将充当 Skype for Business Server 中央管理存储 (CMS) 的只读副本。 必须以计算机本地管理员的身份登录运行“安装本地配置存储”步骤的服务器，并具有 RTCUniversalServerAdmins 或 RTCUniversalGlobalReadOnlyGroup 组成员身份。 如果在边缘服务器上执行安装，则不需要具有 RTCUniversalServerAdmins 或 RTCUniversalGlobalReadOnlyGroup 组成员身份。 将从导出的定义文档 (而不是从中央管理存储) 读取拓扑生成器定义文档。 若要导出拓扑生成器定义文档并将其提供给边缘服务器, 请参阅主题导出拓扑并将其复制到外部媒体以进行边缘安装。
ms.openlocfilehash: c3da29e6c9630b22e7ae947f9b23ab5dbeebd13c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34301443"
---
# <a name="install-local-configuration-store"></a><span data-ttu-id="4db32-108">安装本地配置存储</span><span class="sxs-lookup"><span data-stu-id="4db32-108">Install Local Configuration Store</span></span>

<span data-ttu-id="4db32-109">若要开始安装新的 Skype for Business Server 2015 角色服务器, 必须首先安装将托管本地配置存储的本地 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="4db32-109">To begin the installation of a new Skype for Business Server 2015 role server, you must first install the local SQL Server that will host the local configuration store.</span></span> <span data-ttu-id="4db32-110">本地配置存储将充当 Skype for Business Server 中央管理存储 (CMS) 的只读副本。</span><span class="sxs-lookup"><span data-stu-id="4db32-110">The local configuration store will act as a read-only replica of the Skype for Business Server Central Management store (CMS).</span></span> <span data-ttu-id="4db32-111">必须以计算机本地管理员的身份登录运行“**安装本地配置存储**”步骤的服务器，并具有 RTCUniversalServerAdmins 或 RTCUniversalGlobalReadOnlyGroup 组成员身份。</span><span class="sxs-lookup"><span data-stu-id="4db32-111">You must be logged on to the server that you are running the **Install Local Configuration Store** step as the local administrator on the computer, and have membership in the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="4db32-112">如果在边缘服务器上执行安装，则不需要具有 RTCUniversalServerAdmins 或 RTCUniversalGlobalReadOnlyGroup 组成员身份。</span><span class="sxs-lookup"><span data-stu-id="4db32-112">If you are performing the setup on an Edge Server, you do not have to be a member of the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="4db32-113">将从导出的定义文档 (而不是从中央管理存储) 读取拓扑生成器定义文档。</span><span class="sxs-lookup"><span data-stu-id="4db32-113">The Topology Builder definition document will be read from the exported definition document instead of from the Central Management store.</span></span> <span data-ttu-id="4db32-114">若要导出拓扑生成器定义文档并将其提供给边缘服务器, 请参阅主题[导出拓扑并将其复制到外部媒体以进行边缘安装](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx)。</span><span class="sxs-lookup"><span data-stu-id="4db32-114">To export the Topology Builder definition document and make it available to the Edge Servers, see the topic [Export Your Topology and Copy It to External Media for Edge Installation](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).</span></span>

<span data-ttu-id="4db32-115">开始安装：</span><span class="sxs-lookup"><span data-stu-id="4db32-115">To begin the installation:</span></span>

1. <span data-ttu-id="4db32-116">在 "Skype for Business 服务器 2015" 页面上, 在 " **Step1: 安装本地配置存储**" 旁边, 单击 "**运行**"。</span><span class="sxs-lookup"><span data-stu-id="4db32-116">On the Skype for Business Server 2015 page, next to **Step1: Install Local Configuration Store**, click **Run**.</span></span>

2. <span data-ttu-id="4db32-117">在“**本地服务器配置**”页上，确保选择“**自动从中央管理存储检索配置**”选项，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="4db32-117">On the **Local Server Configuration** page, be sure that the **Retrieve configuration automatically from the Central Management Store** option is selected, and then click **Next**.</span></span>

3. <span data-ttu-id="4db32-118">完成本地服务器配置安装后，单击“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="4db32-118">When the local server configuration installation is complete, click **Finish**.</span></span>

> [!NOTE]
> <span data-ttu-id="4db32-119">安装本地 SQL Server 可能需要一些时间。</span><span class="sxs-lookup"><span data-stu-id="4db32-119">The installation of the local SQL Server can take some time.</span></span> <span data-ttu-id="4db32-120">在安装 SQL Server 的过程中, 你将看不到 "安装摘要" 屏幕上的进度更新。</span><span class="sxs-lookup"><span data-stu-id="4db32-120">You will not see updates on progress in the installation summary screen while SQL Server is being installed.</span></span> <span data-ttu-id="4db32-121">如果想要监视安装进度, 请使用 "任务管理器" 观看 SQL Server 设置。</span><span class="sxs-lookup"><span data-stu-id="4db32-121">If you want to monitor the progress of the installation, use Task Manager to watch the SQL Server setup.</span></span>


