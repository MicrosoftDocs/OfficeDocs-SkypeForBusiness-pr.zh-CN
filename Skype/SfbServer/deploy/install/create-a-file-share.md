---
title: 在 Skype for Business Server 中创建文件共享
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 053076b0-441c-44d9-8dbc-7a36d8ecafe4
description: 摘要：了解如何创建 Windows Server 文件共享作为安装 Skype for Business Server 的一部分。 从 Microsoft 评估中心下载 Skype for Business Server 的免费试用版， https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server 位置为：
ms.openlocfilehash: 63ed4c54154698336bea7adb87db4e81d5fd35b4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812232"
---
# <a name="create-a-file-share-in-skype-for-business-server"></a><span data-ttu-id="13f59-104">在 Skype for Business Server 中创建文件共享</span><span class="sxs-lookup"><span data-stu-id="13f59-104">Create a file share in Skype for Business Server</span></span>
 
<span data-ttu-id="13f59-105">**摘要：** 了解如何在安装 Skype for Business Server 时创建 Windows Server 文件共享。</span><span class="sxs-lookup"><span data-stu-id="13f59-105">**Summary:** Learn how to create a Windows Server file share as part of the installation of Skype for Business Server.</span></span> <span data-ttu-id="13f59-106">从 Microsoft 评估中心下载 Skype for Business Server 的免费试用版， [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) 位置为：</span><span class="sxs-lookup"><span data-stu-id="13f59-106">Download a free trial of Skype for Business Server from the Microsoft Evaluation center at:[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="13f59-107">Skype for Business Server 需要文件共享，以便整个拓扑中的计算机可以交换文件。</span><span class="sxs-lookup"><span data-stu-id="13f59-107">Skype for Business Server requires a file share so that computers throughout the topology can exchange files.</span></span> <span data-ttu-id="13f59-108">创建文件共享是 Skype for Business Server 安装过程中第 2 步（第 8 步）。</span><span class="sxs-lookup"><span data-stu-id="13f59-108">Creating a file share is step 2 of 8 in the installation process for Skype for Business Server.</span></span> <span data-ttu-id="13f59-109">可以按任意顺序执行步骤 1 到步骤 5。</span><span class="sxs-lookup"><span data-stu-id="13f59-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="13f59-110">但是，必须按顺序执行步骤 6、7 和 8，步骤 1 到步骤 5 之后，如图中所述。</span><span class="sxs-lookup"><span data-stu-id="13f59-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5 as outlined in the diagram.</span></span> <span data-ttu-id="13f59-111">有关文件共享的规划详细信息，请参阅 [Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) 的环境要求或 [Skype for Business Server 2019 的服务器要求](../../../SfBServer2019/plan/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="13f59-111">For planning details about file share, see [Environmental requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md).</span></span>
  
![概述图表](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a><span data-ttu-id="13f59-113">创建基本文件共享</span><span class="sxs-lookup"><span data-stu-id="13f59-113">Create a basic file share</span></span>

<span data-ttu-id="13f59-114">本部分将指导你创建基本的 Windows Server 文件共享。</span><span class="sxs-lookup"><span data-stu-id="13f59-114">This section walks you through creating a basic Windows Server file share.</span></span> <span data-ttu-id="13f59-115">Skype for Business Server 支持基本的 Windows Server 文件共享。</span><span class="sxs-lookup"><span data-stu-id="13f59-115">A basic Windows Server file share is supported with Skype for Business Server.</span></span> <span data-ttu-id="13f59-116">但是，它未明确提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="13f59-116">However, it does not explicitly provide high availability.</span></span> <span data-ttu-id="13f59-117">对于高可用性环境，建议使用分布式文件系统 (DFS) 文件共享。</span><span class="sxs-lookup"><span data-stu-id="13f59-117">For a high availability environment, a Distributed File System (DFS) file share is recommended.</span></span> <span data-ttu-id="13f59-118">有关高可用性文件共享和 DFS 详细信息，请参阅 Plan [for high availability and disaster recovery in Skype for Business Server.](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="13f59-118">For more information about a high availability file share and DFS, see [Plan for high availability and disaster recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="13f59-119">Windows Server 2012 R2 在使用 Windows Server 平台 (SAN) 文件共享解决方案方面进行了重大跨越。</span><span class="sxs-lookup"><span data-stu-id="13f59-119">Windows Server 2012 R2 has made major leaps in providing Storage Area Network (SAN)-like file share solutions using the Windows Server platform.</span></span> <span data-ttu-id="13f59-120">与传统的基于 SAN 的设备相比，Windows Server 2012 R2 存储解决方案可以将成本减少一半，对性能的影响很小。</span><span class="sxs-lookup"><span data-stu-id="13f59-120">When compared to a traditional SAN-based appliance, a Windows Server 2012 R2 storage solution can cut costs in half with very minimal impact to performance.</span></span> <span data-ttu-id="13f59-121">有关 R2 中文件共享选项Windows Server 2012，请参阅 [R2](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf)存储中的可下载Windows Server 2012白皮书。</span><span class="sxs-lookup"><span data-stu-id="13f59-121">For more information about file share options in Windows Server 2012 R2, see the downloadable white paper [Windows Server 2012 R2 Storage](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf).</span></span> 
  
<span data-ttu-id="13f59-122">观看创建文件共享 **的视频步骤**：</span><span class="sxs-lookup"><span data-stu-id="13f59-122">Watch the video steps for **create a file share**:</span></span>
  
> [!video https://www.microsoft.com/videoplayer/embed/dbef31be-e899-4a32-a1ca-370053284f56?autoplay=false]
  
### <a name="create-a-basic-file-share"></a><span data-ttu-id="13f59-123">创建基本文件共享</span><span class="sxs-lookup"><span data-stu-id="13f59-123">Create a basic file share</span></span>

1. <span data-ttu-id="13f59-124">登录到将承载文件共享的计算机。</span><span class="sxs-lookup"><span data-stu-id="13f59-124">Log on to the computer that will host the file share.</span></span>
    
2. <span data-ttu-id="13f59-125">右键单击计划共享的文件夹，然后选择"**属性"。**</span><span class="sxs-lookup"><span data-stu-id="13f59-125">Right-click the folder you plan to share, and select **Properties**.</span></span>
    
3. <span data-ttu-id="13f59-126">选择"**共享"** 选项卡，然后单击 **"高级共享"。**</span><span class="sxs-lookup"><span data-stu-id="13f59-126">Select the **Sharing** tab, and click **Advanced Sharing**.</span></span>
    
4. <span data-ttu-id="13f59-127">单击 **"共享此文件夹"。**</span><span class="sxs-lookup"><span data-stu-id="13f59-127">Click **Share this folder**.</span></span>
    
5. <span data-ttu-id="13f59-128">单击“**权限**”。</span><span class="sxs-lookup"><span data-stu-id="13f59-128">Click **Permissions**.</span></span>
    
6. <span data-ttu-id="13f59-129">添加托管文件共享的服务器的本地 **Administrators** 组，授予"允许：完全控制、更改和 **读取**"权限，然后单击"**确定"。**</span><span class="sxs-lookup"><span data-stu-id="13f59-129">Add the local **Administrators** group of the server hosting the file share, grant **Allow: Full Control, Change, and Read** rights, and then click **OK**.</span></span>
    
7. <span data-ttu-id="13f59-130">再次 **单击** "确定"，并记下网络路径。</span><span class="sxs-lookup"><span data-stu-id="13f59-130">Click **OK** again and take note of the network path.</span></span>
    
8. <span data-ttu-id="13f59-131">单击 **"** 完成"关闭向导。</span><span class="sxs-lookup"><span data-stu-id="13f59-131">Click **Done** to close the wizard.</span></span>
    
     ![用于共享文件夹的"共享"选项卡。](../../media/78fe8441-dead-43ed-9a04-3c7c8c657c15.png)
  
> [!NOTE]
><span data-ttu-id="13f59-133">如果文件存储托管在 DFS 共享上，将接收到以下警告：</span><span class="sxs-lookup"><span data-stu-id="13f59-133">If the file store is hosted on a DFS share, the following warning will be received:</span></span>

<span data-ttu-id="13f59-134">警告：无法访问""的共享 \\ <domain> \<share> 权限。</span><span class="sxs-lookup"><span data-stu-id="13f59-134">Warning: Unable to access share permissions for "\\<domain>\<share>".</span></span>

><span data-ttu-id="13f59-135">如果您不是文件服务器的管理员，或者这是 DFS 共享中的分布式文件系统， (此) 。</span><span class="sxs-lookup"><span data-stu-id="13f59-135">This is expected if you are not an administrator on the file server, or if this is a Distributed File System (DFS) share.</span></span> <span data-ttu-id="13f59-136">如果已配置共享权限，可以忽略此警告。</span><span class="sxs-lookup"><span data-stu-id="13f59-136">If the share permissions have already been configured, this warning can be ignored.</span></span> <span data-ttu-id="13f59-137">如果是新共享，请参阅文档，详细了解如何手动配置共享权限。</span><span class="sxs-lookup"><span data-stu-id="13f59-137">If it is a new share, refer to the documentation for details on manually configuring share permissions.</span></span>

><span data-ttu-id="13f59-138">由于无法访问 DFS 共享上的共享权限，Skype for Business Server 将无法显式设置文件共享上的组。</span><span class="sxs-lookup"><span data-stu-id="13f59-138">Due to the inability to access the share permissions on a DFS share, Skype for Business Server will not be able to explicitly set groups on the file share.</span></span> <span data-ttu-id="13f59-139">若要确保 Skype for Business Server 组件可以使用适当的权限访问文件共享，请确保除了具有"完全控制"共享权限的本地管理员之外，还添加了以下 RTC 组以及读取和更改级别共享权限。</span><span class="sxs-lookup"><span data-stu-id="13f59-139">To ensure Skype for Business Server components can access the file share with the appropriate permissions, ensure the following RTC groups are added with Read and Change level share permissions in addition to the local Administrators with Full Control share permissions.</span></span>
* <span data-ttu-id="13f59-140">RTCHSUniversalServices</span><span class="sxs-lookup"><span data-stu-id="13f59-140">RTCHSUniversalServices</span></span>
* <span data-ttu-id="13f59-141">RTCComponentUniversalServices</span><span class="sxs-lookup"><span data-stu-id="13f59-141">RTCComponentUniversalServices</span></span>
* <span data-ttu-id="13f59-142">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="13f59-142">RTCUniversalServerAdmins</span></span>
