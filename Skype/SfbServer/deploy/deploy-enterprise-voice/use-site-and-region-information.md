---
title: 在 Business Server 以使用站点和区域信息的 Skype 中配置媒体绕过全局设置
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0a21cdf1-f350-49da-b346-70806f256bea
description: 配置媒体绕过以用于某些网站和区域中 Skype 业务 Server 企业语音。
ms.openlocfilehash: 93cc6bea9a4f130bd4b2c0e455b979b477888eeb
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32222567"
---
# <a name="configure-media-bypass-global-settings-in-skype-for-business-server-to-use-site-and-region-information"></a>在 Business Server 以使用站点和区域信息的 Skype 中配置媒体绕过全局设置
 
配置媒体绕过以用于某些网站和区域中 Skype 业务 Server 企业语音。 
  
 如果您使用绕过本主题可配置为媒体的全局设置中的步骤，假设您没有良好所有 Skype 业务终结点和任何在中继连接为其配置媒体绕过的对等方之间的连接性。
  
> [!NOTE]
> 启用呼叫允许控制和媒体旁路高级企业语音功能后，会在两者之间共享网络区域和网络站点信息。因此，如果您已配置了呼叫允许控制，则不需要使用以下过程专门为媒体旁路编辑站点和区域信息。如果尚未为呼叫允许控制配置网络区域和站点，并且想要更改媒体旁路设置，请按照该过程中的步骤进行操作。 
  
为媒体绕过以正确之间必须存在一致性网站随着拓扑生成器中定义以及定义当您配置网络区域和网络站点。 例如，如果已在拓扑生成器中定义为具有分支站点部署 PSTN 网关，则必须使用企业语音策略，以使其 PSTN 呼叫路由到 PSTN 的分支站点用户配置该分支站点在分支站点的网关。
  
### <a name="to-configure-site-and-region-information-for-media-bypass"></a>为媒体旁路配置站点和区域信息

1. 打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。  
    
2. 在左侧导航栏中，单击“网络配置”****。
    
3. 双击表中的“全局”**** 配置。
    
4. 在“编辑全局设置”**** 页上，选中“启用媒体旁路”**** 复选框。
    
5. 单击“使用站点和区域配置”****。
    
6. 如有必要，请选中“为非映射站点启用旁路”**** 复选框。
    
    > [!NOTE]
    > 仅当具有一个或多个与没有带宽限制的同一区域关联的大型站点，但有一些与有带宽限制的同一区域关联的分支站点时，才应选中该复选框。为未映射的站点启用旁路时可以简化配置，这是因为只需指定与分支站点关联的子网，而无需指定与所有站点关联的所有子网。如果启用了呼叫允许控制，则建议不要选中该复选框。 
  
7. 单击“**提交**”。
    
接着，将子网添加到网络站点中，如[Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets)中所述。将所有子网与网络站点相关联后，媒体旁路即部署完成。
> [!IMPORTANT]
> 如果尚未创建网络区域和网络站点，则必须先创建这些区域和站点，才能部署媒体旁路。 有关详细信息，请参阅[Deploy 网络区域、 站点和 Skype for Business 中的子网](deploy-network.md)。 
  
## <a name="see-also"></a>另请参阅

[Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets)

