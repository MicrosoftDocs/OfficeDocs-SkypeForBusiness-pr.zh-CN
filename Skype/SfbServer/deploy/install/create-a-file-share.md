---
title: 在 Skype for Business 服务器中创建文件共享
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 053076b0-441c-44d9-8dbc-7a36d8ecafe4
description: '摘要: 了解如何在安装 Skype for Business 服务器的过程中创建 Windows Server 文件共享。 从 Microsoft 评估中心下载免费试用版 Skype for Business 服务器, 网址为: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server。'
ms.openlocfilehash: d6a34ad4807948a5580fc572628a4fd6333dd9f8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34292163"
---
# <a name="create-a-file-share-in-skype-for-business-server"></a>在 Skype for Business 服务器中创建文件共享
 
**摘要:** 了解如何在安装 Skype for Business 服务器的过程中创建 Windows Server 文件共享。 从 Microsoft 评估中心下载免费试用版 Skype for Business 服务器, 网址为:[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)。
  
Skype for business 服务器需要一个文件共享, 以便整个拓扑中的计算机可以交换文件。 在 Skype for business 服务器的安装过程中, 创建文件共享是第2步 (共8步)。 第 1 步至第 5 步可以按任意顺序执行。 但第 6、7、8 步必须在第 1 步至第 5 步之后按照图表所示顺序依次完成。 有关文件共享的计划详细信息, 请参阅 Skype for business 服务器2019的[环境要求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)或 skype For business [Server 的服务器要求](../../../SfBServer2019/plan/system-requirements.md)。
  
![概述图表](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a>创建基本文件共享

此部分逐步说明如何创建基本的 Windows Server 文件共享。 Skype for Business Server 支持基本 Windows Server 文件共享。 但是, 它不会显式提供高可用性。 对于高可用性环境，建议使用分布式文件系统 (DFS) 文件共享。 有关高可用性文件共享和 DFS 的详细信息, 请参阅[Skype For Business 服务器中的 "高可用性和灾难恢复计划](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)"。
  
> [!NOTE]
> Windows Server 2012 R2 在使用 Windows Server 平台提供存储区域网络 (SAN) 型文件共享解决方案方面作出了重大改进。 与基于传统 SAN 的设备相比，Windows Server 2012 R2 存储解决方案可以将成本削减一半，同时对性能造成的影响很小。 有关 Windows Server 2012 R2 中的文件共享选项的详细信息, 请参阅可下载的白皮书[Windows Server 2012 R2 存储](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf)。 
  
观看视频，了解**创建文件共享**的步骤：
  
> [!video https://www.microsoft.com/en-us/videoplayer/embed/dbef31be-e899-4a32-a1ca-370053284f56?autoplay=false]
  
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
  
> [!NOTE]
>如果文件存储在 DFS 共享上托管, 将收到以下警告:

警告: 无法访问 "\\<domain>\<share>" 的共享权限。

>如果您不是文件服务器上的管理员, 或者这是分布式文件系统 (DFS) 共享, 则应该这样做。 如果已配置共享权限, 则可以忽略此警告。 如果是新共享, 请参阅文档以了解有关手动配置共享权限的详细信息。

>由于无法访问 DFS 共享的共享权限, Skype for Business 服务器将无法显式设置文件共享上的组。 为确保 Skype for Business 服务器组件可以使用相应权限访问文件共享, 请确保除了具有 "完全控制共享权限" 的本地管理员之外, 还添加了 "更改级别共享权限" 的以下 RTC 组。

RTCHSUniversalServices RTCComponentUniversalServices RTCUniversalServerAdmins
