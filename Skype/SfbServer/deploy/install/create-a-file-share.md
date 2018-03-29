---
title: 在 Skype for Business Server 2015 中创建文件共享
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 053076b0-441c-44d9-8dbc-7a36d8ecafe4
description: '摘要： 了解如何创建 Windows 服务器的文件共享作为业务服务器 2015年的 Skype 安装的一部分。 有关从 Microsoft 评估中心的业务服务器 2015年下载免费试用版的 Skype: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server。'
ms.openlocfilehash: 697325cbe7616ca82734895e1af4922aeb580068
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="create-a-file-share-in-skype-for-business-server-2015"></a><span data-ttu-id="4e610-104">在 Skype for Business Server 2015 中创建文件共享</span><span class="sxs-lookup"><span data-stu-id="4e610-104">Create a file share in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="4e610-105">**摘要：**了解如何创建 Windows 服务器的文件共享作为业务服务器 2015年的 Skype 安装的一部分。</span><span class="sxs-lookup"><span data-stu-id="4e610-105">**Summary:** Learn how to create a Windows Server file share as part of the installation of Skype for Business Server 2015.</span></span> <span data-ttu-id="4e610-106">有关从 Microsoft 评估中心的业务服务器 2015年下载免费试用版的 Skype:[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)。</span><span class="sxs-lookup"><span data-stu-id="4e610-106">Download a free trial of Skype for Business Server 2015 from the Microsoft Evaluation center at:[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).</span></span>
  
<span data-ttu-id="4e610-107">Skype 业务服务器需要的文件共享，以便拓扑结构在各台计算机可以交换文件。</span><span class="sxs-lookup"><span data-stu-id="4e610-107">Skype for Business Server requires a file share so that computers throughout the topology can exchange files.</span></span> <span data-ttu-id="4e610-108">创建一个文件共享是 8 业务服务器 2015年的 Skype 的安装过程中的步骤 2。</span><span class="sxs-lookup"><span data-stu-id="4e610-108">Creating a file share is step 2 of 8 in the installation process for Skype for Business Server 2015.</span></span> <span data-ttu-id="4e610-109">您可以按照任意顺序完成第 1 步至第 5 步。</span><span class="sxs-lookup"><span data-stu-id="4e610-109">You can do steps 1 through 5 in any order.</span></span> <span data-ttu-id="4e610-110">但第 6、7、8 步必须在第 1 步至第 5 步之后按照图表所示顺序依次完成。</span><span class="sxs-lookup"><span data-stu-id="4e610-110">However, you must do steps 6, 7, and 8 in order, and after steps 1 through 5 as outlined in the diagram.</span></span> <span data-ttu-id="4e610-111">有关规划有关文件共享的详细信息，请参阅[业务服务器 2015年的 Skype 的环保要求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4e610-111">For planning details about file share, see [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).</span></span>
  
![概述图表](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a><span data-ttu-id="4e610-113">创建基本文件共享</span><span class="sxs-lookup"><span data-stu-id="4e610-113">Create a basic file share</span></span>

<span data-ttu-id="4e610-114">此部分逐步说明如何创建基本的 Windows Server 文件共享。</span><span class="sxs-lookup"><span data-stu-id="4e610-114">This section walks you through creating a basic Windows Server file share.</span></span> <span data-ttu-id="4e610-115">基本的 Windows 服务器文件共享与 Skype 业务服务器的支持。</span><span class="sxs-lookup"><span data-stu-id="4e610-115">A basic Windows Server file share is supported with Skype for Business Server.</span></span> <span data-ttu-id="4e610-116">但是，它不显式提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="4e610-116">However, it does not explicitly provide high availability.</span></span> <span data-ttu-id="4e610-117">对于高可用性环境，建议使用分布式文件系统 (DFS) 文件共享。</span><span class="sxs-lookup"><span data-stu-id="4e610-117">For a high availability environment, a Distributed File System (DFS) file share is recommended.</span></span> <span data-ttu-id="4e610-118">高可用性文件共享和 DFS 有关的详细信息，请参阅[规划高可用性和灾难恢复业务服务器 2015年的 Skype](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="4e610-118">For more information about a high availability file share and DFS, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="4e610-119">Windows Server 2012 R2 在使用 Windows Server 平台提供存储区域网络 (SAN) 型文件共享解决方案方面作出了重大改进。</span><span class="sxs-lookup"><span data-stu-id="4e610-119">Windows Server 2012 R2 has made major leaps in providing Storage Area Network (SAN)-like file share solutions using the Windows Server platform.</span></span> <span data-ttu-id="4e610-120">与基于传统 SAN 的设备相比，Windows Server 2012 R2 存储解决方案可以将成本削减一半，同时对性能造成的影响很小。</span><span class="sxs-lookup"><span data-stu-id="4e610-120">When compared to a traditional SAN-based appliance, a Windows Server 2012 R2 storage solution can cut costs in half with very minimal impact to performance.</span></span> <span data-ttu-id="4e610-121">有关 Windows Server 2012 R2 中的文件共享选项的详细信息，请参阅[Windows Server 2012 R2 存储](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf)下载白皮书。</span><span class="sxs-lookup"><span data-stu-id="4e610-121">For more information about file share options in Windows Server 2012 R2, see the downloadable white paper [Windows Server 2012 R2 Storage](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf).</span></span> 
  
<span data-ttu-id="4e610-122">观看视频，了解**创建文件共享**的步骤：</span><span class="sxs-lookup"><span data-stu-id="4e610-122">Watch the video steps for **create a file share**:</span></span>
  
![您的浏览器不支持视频。 安装 Microsoft Silverlight、Adobe Flash Player 或 Internet Explorer 9。](../../media/MSN_Video_Widget.gif)
  
### <a name="create-a-basic-file-share"></a><span data-ttu-id="4e610-125">创建基本文件共享</span><span class="sxs-lookup"><span data-stu-id="4e610-125">Create a basic file share</span></span>

1. <span data-ttu-id="4e610-126">登录将托管文件共享的计算机。</span><span class="sxs-lookup"><span data-stu-id="4e610-126">Log on to the computer that will host the file share.</span></span>
    
2. <span data-ttu-id="4e610-127">右键单击计划共享的文件夹，然后选择“**属性**”。</span><span class="sxs-lookup"><span data-stu-id="4e610-127">Right-click the folder you plan to share, and select **Properties**.</span></span>
    
3. <span data-ttu-id="4e610-128">选择“**共享**”选项卡，然后单击“**高级共享...**”。</span><span class="sxs-lookup"><span data-stu-id="4e610-128">Select the **Sharing** tab, and click **Advanced Sharing**.</span></span>
    
4. <span data-ttu-id="4e610-129">单击“**共享此文件夹**”。</span><span class="sxs-lookup"><span data-stu-id="4e610-129">Click **Share this folder**.</span></span>
    
5. <span data-ttu-id="4e610-130">单击“**权限**”。</span><span class="sxs-lookup"><span data-stu-id="4e610-130">Click **Permissions**.</span></span>
    
6. <span data-ttu-id="4e610-131">在托管文件共享的服务器上添加本地“**Administrators**”组，授予“**允许：完全控制、更改和读取**”权限，然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="4e610-131">Add the local **Administrators** group of the server hosting the file share, grant **Allow: Full Control, Change, and Read** rights, and then click **OK**.</span></span>
    
7. <span data-ttu-id="4e610-132">再次单击“**确定**”，然后记下新路径。</span><span class="sxs-lookup"><span data-stu-id="4e610-132">Click **OK** again and take note of the network path.</span></span>
    
8. <span data-ttu-id="4e610-133">单击“**完成**”关闭该向导。</span><span class="sxs-lookup"><span data-stu-id="4e610-133">Click **Done** to close the wizard.</span></span>
    
     ![用于共享文件夹的“共享”选项卡。](../../media/78fe8441-dead-43ed-9a04-3c7c8c657c15.png)
  

