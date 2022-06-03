---
title: 在Skype for Business Server中创建文件共享
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
description: 摘要：了解如何在安装Skype for Business Server过程中创建Windows服务器文件共享。
ms.openlocfilehash: 12ea75a11470d5730c891b1c738a3337ccb28ac8
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860723"
---
# <a name="create-a-file-share-in-skype-for-business-server"></a>在Skype for Business Server中创建文件共享
 
**总结：** 了解如何在安装Skype for Business Server时创建Windows服务器文件共享。
  
Skype for Business Server需要文件共享，以便整个拓扑中的计算机可以交换文件。 在Skype for Business Server的安装过程中，创建文件共享是第 8 步中的步骤 8。 可以按任何顺序执行步骤 1 到 5。 但是，必须按顺序执行步骤 6、7 和 8 以及步骤 1 到 5，如下图所述。 有关文件共享的规划详细信息，请参阅 [2019](../../../SfBServer2019/plan/system-requirements.md) Skype for Business Server Skype for Business Server或服务器要求[的环境要求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)。
  
![概述图。](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a>创建基本文件共享

本部分介绍如何创建基本Windows服务器文件共享。 Skype for Business Server支持基本Windows服务器文件共享。 但是，它不会显式提供高可用性。 对于高可用性环境，建议使用分布式文件系统 (DFS) 文件共享。 有关高可用性文件共享和 DFS 的详细信息，请参阅 [Skype for Business Server 中的高可用性和灾难恢复计划](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。
  
> [!NOTE]
> Windows Server 2012 R2 在使用 Windows Server 平台提供存储区域网络 (SAN) 型文件共享解决方案方面取得了重大进展。 与传统的基于 SAN 的设备相比，Windows Server 2012 R2 存储解决方案可将成本降低一半，对性能的影响极小。 有关 Windows Server 2012 R2 中的文件共享选项的详细信息，请[参阅可下载的白皮书Windows Server 2012 R2 存储](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf)。 
  
观看视频步骤以 **创建文件共享**：
  
> [!video https://www.microsoft.com/videoplayer/embed/dbef31be-e899-4a32-a1ca-370053284f56?autoplay=false]
  
### <a name="create-a-basic-file-share"></a>创建基本文件共享

1. 登录到将托管文件共享的计算机。
    
2. 右键单击计划共享的文件夹，然后选择 **“属性**”。
    
3. 选择“ **共享** ”选项卡，然后单击 **“高级共享**”。
    
4. 单击 **“共享此文件夹**”。
    
5. 单击“**权限**”。
    
6. 添加托管文件共享的服务器的本地 **管理员** 组，授予 **“允许：完全控制”、“更改”和“读取** 权限”，然后单击 **“确定**”。
    
7. 再次单击 **“确定** ”并记下网络路径。
    
8. 单击 **“完成”** 关闭向导。
    
     ![用于共享文件夹的“共享”选项卡。](../../media/78fe8441-dead-43ed-9a04-3c7c8c657c15.png)
  
> [!NOTE]
>如果文件存储托管在 DFS 共享上，将收到以下警告：

`Warning: Unable to access share permissions for "\\<domain>\<share>".`

>如果你不是文件服务器上的管理员，或者这是分布式文件系统 (DFS) 共享，则预期会出现这种情况。 如果已配置共享权限，则可以忽略此警告。 如果是新共享，请参阅文档，了解有关手动配置共享权限的详细信息。

>由于无法访问 DFS 共享的共享权限，Skype for Business Server将无法在文件共享上显式设置组。 若要确保Skype for Business Server组件可以使用适当的权限访问文件共享，请确保除了具有完全控制共享权限的本地管理员外，还使用读取和更改级别共享权限添加以下 RTC 组。
* RTCHSUniversalServices
* RTCComponentUniversalServices
* RTCUniversalServerAdmins
