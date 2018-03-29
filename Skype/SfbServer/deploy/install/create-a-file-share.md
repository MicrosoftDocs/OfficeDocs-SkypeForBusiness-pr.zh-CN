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
# <a name="create-a-file-share-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中创建文件共享
 
**摘要：**了解如何创建 Windows 服务器的文件共享作为业务服务器 2015年的 Skype 安装的一部分。 有关从 Microsoft 评估中心的业务服务器 2015年下载免费试用版的 Skype:[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)。
  
Skype 业务服务器需要的文件共享，以便拓扑结构在各台计算机可以交换文件。 创建一个文件共享是 8 业务服务器 2015年的 Skype 的安装过程中的步骤 2。 您可以按照任意顺序完成第 1 步至第 5 步。 但第 6、7、8 步必须在第 1 步至第 5 步之后按照图表所示顺序依次完成。 有关规划有关文件共享的详细信息，请参阅[业务服务器 2015年的 Skype 的环保要求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)。
  
![概述图表](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a>创建基本文件共享

此部分逐步说明如何创建基本的 Windows Server 文件共享。 基本的 Windows 服务器文件共享与 Skype 业务服务器的支持。 但是，它不显式提供高可用性。 对于高可用性环境，建议使用分布式文件系统 (DFS) 文件共享。 高可用性文件共享和 DFS 有关的详细信息，请参阅[规划高可用性和灾难恢复业务服务器 2015年的 Skype](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。
  
> [!NOTE]
> Windows Server 2012 R2 在使用 Windows Server 平台提供存储区域网络 (SAN) 型文件共享解决方案方面作出了重大改进。 与基于传统 SAN 的设备相比，Windows Server 2012 R2 存储解决方案可以将成本削减一半，同时对性能造成的影响很小。 有关 Windows Server 2012 R2 中的文件共享选项的详细信息，请参阅[Windows Server 2012 R2 存储](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf)下载白皮书。 
  
观看视频，了解**创建文件共享**的步骤：
  
![您的浏览器不支持视频。 安装 Microsoft Silverlight、Adobe Flash Player 或 Internet Explorer 9。](../../media/MSN_Video_Widget.gif)
  
### <a name="create-a-basic-file-share"></a>创建基本文件共享

1. 登录将托管文件共享的计算机。
    
2. 右键单击计划共享的文件夹，然后选择“**属性**”。
    
3. 选择“**共享**”选项卡，然后单击“**高级共享...**”。
    
4. 单击“**共享此文件夹**”。
    
5. 单击“**权限**”。
    
6. 在托管文件共享的服务器上添加本地“**Administrators**”组，授予“**允许：完全控制、更改和读取**”权限，然后单击“**确定**”。
    
7. 再次单击“**确定**”，然后记下新路径。
    
8. 单击“**完成**”关闭该向导。
    
     ![用于共享文件夹的“共享”选项卡。](../../media/78fe8441-dead-43ed-9a04-3c7c8c657c15.png)
  

