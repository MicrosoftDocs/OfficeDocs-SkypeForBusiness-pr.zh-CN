---
title: 为 Business Server Skype 创建文件共享
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 053076b0-441c-44d9-8dbc-7a36d8ecafe4
description: 摘要： 了解如何创建 Windows Server 文件共享作为业务服务器安装的 Skype 的一部分。 下载免费试用版 Skype 业务服务器从 Microsoft 评估中心，网址为： https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server。
ms.openlocfilehash: b92d85d375b76b43dcf65f01205c3826e5637905
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885629"
---
# <a name="create-a-file-share-in-skype-for-business-server"></a>为 Business Server Skype 创建文件共享
 
**摘要：** 了解如何创建 Windows Server 文件共享作为业务服务器安装的 Skype 的一部分。 下载免费试用版 Skype 业务服务器从 Microsoft 评估中心，网址为：[https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)。
  
Skype 业务服务器需要一个文件共享，以便整个拓扑的计算机可以交换文件。 创建文件共享是 8 Skype 业务服务器安装过程中的第 2 步。 第 1 步至第 5 步可以按任意顺序执行。 但第 6、7、8 步必须在第 1 步至第 5 步之后按照图表所示顺序依次完成。 有关规划有关文件共享的详细信息，请参阅[环境要求 Skype 业务服务器](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)或[服务器要求的业务服务器 2019 Skype](../../../SfBServer2019/plan/system-requirements.md)。
  
![概述图表](../../media/e69de059-3040-45ab-9379-1932f9fbb37f.png)
  
## <a name="create-a-basic-file-share"></a>创建基本文件共享

此部分逐步说明如何创建基本的 Windows Server 文件共享。 基本的 Windows Server 文件共享与 Skype 的业务服务器支持。 但是，它不明确提供高可用性。 对于高可用性环境，建议使用分布式文件系统 (DFS) 文件共享。 有关高可用性文件共享和 DFS 的详细信息，请参阅[规划高可用性和灾难恢复 Skype 业务服务器中](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。
  
> [!NOTE]
> Windows Server 2012 R2 在使用 Windows Server 平台提供存储区域网络 (SAN) 型文件共享解决方案方面作出了重大改进。 与基于传统 SAN 的设备相比，Windows Server 2012 R2 存储解决方案可以将成本削减一半，同时对性能造成的影响很小。 有关 Windows Server 2012 R2 中的文件共享选项的详细信息，请参阅可下载的白皮书[的 Windows Server 2012 R2 存储](https://download.microsoft.com/download/9/4/A/94A15682-02D6-47AD-B209-79D6E2758A24/Windows_Server_2012_R2_Storage_White_Paper.pdf)。 
  
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
>如果文件存储位于 DFS 共享上，将收到以下警告：

警告： 无法访问的共享权限"\\<domain>\<share>"。

>此举有望如果您不是管理员在文件服务器上，或者如果这是一个分布式文件系统 (DFS) 共享。 如果已配置了共享权限，可以忽略此警告。 如果是新的共享，请参阅文档的手动配置共享权限的详细信息。

>由于无法访问 DFS 共享上的共享权限，Skype 业务服务器将不能显式设置的文件共享上的组。 若要确保 Skype 业务服务器组件可以访问具有适当权限的文件共享，确保将以下 RTC 组添加具有完全控制共享权限更改级别共享权限除了本地管理员。

RTCHSUniversalServices RTCComponentUniversalServices RTCUniversalServerAdmins
