---
title: 安装本地配置存储
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainInstallReplica
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: d9c4bcc2-11a7-4d4d-858d-224db217ad32
ROBOTS: NOINDEX, NOFOLLOW
description: 若要开始安装新的 Skype for Business Server 角色服务器，必须先安装将SQL Server本地配置存储的本地服务器。 本地配置存储将充当 CMS (Skype for Business Server 中央管理存储) 。
ms.openlocfilehash: dcaf00e0bd14daecb6d2859bf40463265a3d6bc6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833802"
---
# <a name="install-local-configuration-store"></a><span data-ttu-id="58d65-104">安装本地配置存储</span><span class="sxs-lookup"><span data-stu-id="58d65-104">Install Local Configuration Store</span></span>

<span data-ttu-id="58d65-105">若要开始安装新的 Skype for Business Server 角色服务器，必须先安装将SQL Server本地配置存储的本地服务器。</span><span class="sxs-lookup"><span data-stu-id="58d65-105">To begin the installation of a new Skype for Business Server role server, you must first install the local SQL Server that will host the local configuration store.</span></span> <span data-ttu-id="58d65-106">本地配置存储将充当 CMS (Skype for Business Server 中央管理存储) 。</span><span class="sxs-lookup"><span data-stu-id="58d65-106">The local configuration store will act as a read-only replica of the Skype for Business Server Central Management store (CMS).</span></span> <span data-ttu-id="58d65-107">必须以计算机本地管理员的身份登录运行 **“安装本地配置存储”** 步骤的服务器，并具有 RTCUniversalServerAdmins 或 RTCUniversalGlobalReadOnlyGroup 组成员身份。</span><span class="sxs-lookup"><span data-stu-id="58d65-107">You must be logged on to the server that you are running the **Install Local Configuration Store** step as the local administrator on the computer, and have membership in the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="58d65-108">如果在边缘服务器上执行安装，则不需要具有 RTCUniversalServerAdmins 或 RTCUniversalGlobalReadOnlyGroup 组成员身份。</span><span class="sxs-lookup"><span data-stu-id="58d65-108">If you are performing the setup on an Edge Server, you do not have to be a member of the RTCUniversalServerAdmins or the RTCUniversalGlobalReadOnlyGroup group.</span></span> <span data-ttu-id="58d65-109">拓扑生成器定义文档将读取导出的定义文档，而不是从中央管理存储中读取。</span><span class="sxs-lookup"><span data-stu-id="58d65-109">The Topology Builder definition document will be read from the exported definition document instead of from the Central Management store.</span></span> <span data-ttu-id="58d65-110">若要导出拓扑生成器定义文档并提供给边缘服务器，请参阅主题"导出拓扑并复制到外部媒体[以用于边缘安装"。](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx)</span><span class="sxs-lookup"><span data-stu-id="58d65-110">To export the Topology Builder definition document and make it available to the Edge Servers, see the topic[Export Your Topology and Copy It to External Media for Edge Installation](https://technet.microsoft.com/library/def9f416-c519-4a72-b242-7d3057d9c1fd.aspx).</span></span>

<span data-ttu-id="58d65-111">开始安装：</span><span class="sxs-lookup"><span data-stu-id="58d65-111">To begin the installation:</span></span>

1. <span data-ttu-id="58d65-112">在 Skype for Business Server 页面上，在"**步骤 1： 安装本地配置存储**"旁边，单击"**运行"。**</span><span class="sxs-lookup"><span data-stu-id="58d65-112">On the Skype for Business Server page, next to **Step1: Install Local Configuration Store**, click **Run**.</span></span>

2. <span data-ttu-id="58d65-113">在"**本地服务器配置**"页上，确保已选中"从中央管理存储自动检索配置"选项，然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="58d65-113">On the **Local Server Configuration** page, be sure that the **Retrieve configuration automatically from the Central Management Store** option is selected, and then click **Next**.</span></span>

3. <span data-ttu-id="58d65-114">完成本地服务器配置安装后，单击 **“完成”**。</span><span class="sxs-lookup"><span data-stu-id="58d65-114">When the local server configuration installation is complete, click **Finish**.</span></span>

> [!NOTE]
> <span data-ttu-id="58d65-115">安装本地SQL Server可能需要一些时间。</span><span class="sxs-lookup"><span data-stu-id="58d65-115">The installation of the local SQL Server can take some time.</span></span> <span data-ttu-id="58d65-116">安装升级时，安装摘要屏幕中不会SQL Server更新。</span><span class="sxs-lookup"><span data-stu-id="58d65-116">You will not see updates on progress in the installation summary screen while SQL Server is being installed.</span></span> <span data-ttu-id="58d65-117">如果要监视安装进度，请使用任务管理器监视SQL Server安装。</span><span class="sxs-lookup"><span data-stu-id="58d65-117">If you want to monitor the progress of the installation, use Task Manager to watch the SQL Server setup.</span></span>


