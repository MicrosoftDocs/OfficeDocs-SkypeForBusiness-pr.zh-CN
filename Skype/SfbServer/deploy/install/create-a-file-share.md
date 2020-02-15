---
title: 在 Skype for Business Server 中创建文件共享
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 摘要：了解如何在安装 Skype for Business Server 的过程中创建 Windows Server 文件共享。 从以下位置的 Microsoft 评估中心下载 Skype for Business Server 的免费试用版https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server：。
ms.openlocfilehash: 74c2c8ddedfb6c2a751822fec51636dddd7747dc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028293"
---
# <a name="create-a-file-share-in-skype-for-business-server"></a>在 Skype for Business Server 中创建文件共享
 
**摘要：** 了解如何在安装 Skype for Business Server 的过程中创建 Windows Server 文件共享。 从以下位置的 Microsoft 评估中心下载 Skype for Business Server 的免费试用版[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)：。
  
Skype for Business Server 需要一个文件共享，以便整个拓扑中的计算机可以交换文件。 在 Skype for business Server 的安装过程中，创建文件共享是第2步（共8步）。 您可以按任意顺序执行步骤1至5。 但是，您必须按顺序执行步骤6、7和8，并在第1步至第5步之后，如图中所述。 有关文件共享的规划详细信息，请参阅 skype for business [server 的环境要求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)或[Skype for business Server 2019 的服务器要求](../../../SfBServer2019/plan/system-requirements.md)。
  
![概述图表](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a>创建基本文件共享

本部分将介绍如何创建基本的 Windows Server 文件共享。 Skype for Business Server 支持基本 Windows Server 文件共享。 但是，它并不显式提供高可用性。 对于高可用性环境，建议使用分布式文件系统（DFS）文件共享。 有关高可用性文件共享和 DFS 的详细信息，请参阅[在 Skype For Business Server 中规划高可用性和灾难恢复](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。
  
> [!NOTE]
> Windows Server 2012 R2 在提供存储区域网络（SAN）（如使用 Windows Server 平台的文件共享解决方案）方面进行了重大突破。 与基于 SAN 的传统设备相比，Windows Server 2012 R2 存储解决方案可将成本降低一半，对性能造成的影响非常小。 有关 Windows Server 2012 R2 中的文件共享选项的详细信息，请参阅可下载的白皮书[Windows Server 2012 R2 存储](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf)。 
  
观看**创建文件共享**的视频步骤：
  
> [!video https://www.microsoft.com/videoplayer/embed/dbef31be-e899-4a32-a1ca-370053284f56?autoplay=false]
  
### <a name="create-a-basic-file-share"></a>创建基本文件共享

1. 登录到将承载文件共享的计算机。
    
2. 右键单击您计划共享的文件夹，然后选择 "**属性**"。
    
3. 选择 "**共享**" 选项卡，然后单击 "**高级共享**"。
    
4. 单击 "**共享此文件夹**"。
    
5. 单击“**权限**”。
    
6. 添加承载文件共享的服务器的本地**Administrators**组，授予**允许：完全控制、更改和读取**权限，然后单击 **"确定"**。
    
7. 再次单击 **"确定"** ，并记录网络路径。
    
8. 单击 "**完成**" 以关闭向导。
    
     ![共享文件夹的 "共享" 选项卡。](../../media/78fe8441-dead-43ed-9a04-3c7c8c657c15.png)
  
> [!NOTE]
>如果文件存储托管在 DFS 共享上，则将收到以下警告：

警告：无法访问 "\\<domain>\<共享>" 的共享权限。

>如果您不是文件服务器上的管理员，或者这是分布式文件系统（DFS）共享，这是预期的。 如果已配置共享权限，则可以忽略此警告。 如果是新的共享，请参阅文档以了解有关手动配置共享权限的详细信息。

>由于无法访问 DFS 共享上的共享权限，因此 Skype for Business Server 将无法显式设置文件共享上的组。 若要确保 Skype for Business Server 组件可以使用适当的权限访问文件共享，请确保使用 "读取" 和 "更改" 级别共享权限添加了以下 RTC 组以及具有完全控制共享的本地管理员对.
* RTCHSUniversalServices
* RTCComponentUniversalServices
* RTCUniversalServerAdmins
