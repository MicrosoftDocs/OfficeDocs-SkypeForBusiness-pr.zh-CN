---
title: 在文件中创建Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 053076b0-441c-44d9-8dbc-7a36d8ecafe4
description: 摘要：了解如何在 Windows 安装过程中创建 Skype for Business Server。 从 Microsoft 评估Skype for Business Server下载免费https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server试用版：。
ms.openlocfilehash: c5d072c643061f65f68226eeed43f769a06bd2e4
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62385220"
---
# <a name="create-a-file-share-in-skype-for-business-server"></a>在文件中创建Skype for Business Server
 
**摘要：** 了解如何在安装 Windows Server 文件共享时创建Skype for Business Server。 从 Microsoft 评估Skype for Business Server下载免费[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)试用版：。
  
Skype for Business Server需要文件共享，以便整个拓扑中的计算机可以交换文件。 创建文件共享是安装过程中第 2 步（第 8 步Skype for Business Server）。 可以按任意顺序执行步骤 1 到步骤 5。 但是，您必须按图表所述顺序执行步骤 6、7 和 8，在步骤 1 到步骤 5 之后执行。 有关文件共享的规划详细信息，请参阅 environmental [requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or [Server requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md)。
  
![概述图表。](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a>创建基本文件共享

本节将指导你创建基本的 Windows Server 文件共享。 支持Windows服务器文件共享的基本Skype for Business Server。 但是，它不会明确提供高可用性。 对于高可用性环境，建议使用分布式文件系统 (DFS) 文件共享。 有关高可用性文件共享和 DFS 的信息，请参阅 Plan [for high availability and disaster recovery in Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。
  
> [!NOTE]
> Windows Server 2012 R2 在通过使用 存储 Server 平台存储 SAN () SAN Windows 文件共享解决方案方面实现了重大跃进。 与传统的基于 SAN 的设备相比，Windows Server 2012 R2 存储解决方案可以将成本减少一半，对性能的影响最小。 有关 R2 中文件共享选项Windows Server 2012，请参阅 [R2 Windows Server 2012下载的存储](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf)。 
  
观看创建文件共享 **的视频步骤**：
  
> [!video https://www.microsoft.com/videoplayer/embed/dbef31be-e899-4a32-a1ca-370053284f56?autoplay=false]
  
### <a name="create-a-basic-file-share"></a>创建基本文件共享

1. 登录到将托管文件共享的计算机。
    
2. 右键单击计划共享的文件夹，然后选择"属性 **"**。
    
3. 选择" **共享"** 选项卡，然后单击" **高级共享"**。
    
4. 单击 **"共享此文件夹"**。
    
5. 单击“**权限**”。
    
6. 添加托管文件共享的服务器的本地 **Administrators** 组，授予"允许 **：** 完全控制、更改和读取"权限，然后单击"确定 **"**。
    
7. 再次 **单击** "确定"，并记下网络路径。
    
8. 单击 **"完成** "关闭向导。
    
     ![用于共享文件夹的"共享"选项卡。](../../media/78fe8441-dead-43ed-9a04-3c7c8c657c15.png)
  
> [!NOTE]
>如果文件存储托管在 DFS 共享上，则收到以下警告：

`Warning: Unable to access share permissions for "\\<domain>\<share>".`

>如果你不是文件服务器的管理员，或者是 DFS 共享中的分布式文件系统， (预期) 。 如果已配置共享权限，可以忽略此警告。 如果是新共享，请参阅文档，详细了解如何手动配置共享权限。

>由于无法访问 DFS 共享上的共享权限，Skype for Business Server无法显式设置文件共享上的组。 若要Skype for Business Server具有适当权限访问文件共享，请确保除了具有"完全控制"共享权限的本地管理员之外，还添加了以下 RTC 组以及读取和更改级别共享权限。
* RTCHSUniversalServices
* RTCComponentUniversalServices
* RTCUniversalServerAdmins
