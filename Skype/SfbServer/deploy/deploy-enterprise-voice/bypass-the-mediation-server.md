---
title: Skype 的业务服务器 2015 以始终绕过中介服务器中配置媒体绕过
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
description: 启用媒体绕过以始终绕过中介服务器中 Skype，业务 Server 企业语音。
ms.openlocfilehash: 9e28af8bd794c3c0924e9a6688eeca159c435d28
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2018
ms.locfileid: "19500432"
---
# <a name="configure-media-bypass-in-skype-for-business-server-2015-to-always-bypass-the-mediation-server"></a>Skype 的业务服务器 2015 以始终绕过中介服务器中配置媒体绕过
 
启用媒体绕过以始终绕过中介服务器中 Skype，业务 Server 企业语音。 
  
 如果您使用本主题可配置为媒体的全局设置中的步骤绕过，假设您有良好 Skype 业务终结点和任何在中继连接为其配置媒体绕过的对等方之间的连接性。
  
如果您没有为业务终结点的 Skype 和到其各自的中继连接已启用媒体绕过中介服务器的所有对等方之间的良好连接，则必须配置全局媒体绕过设置以使用站点和区域信息当采用媒体绕过。 这样，确定当媒体绕过中介服务器中的多个控件。 若要执行此操作，而是使用[配置媒体绕过全局设置中的业务服务器 2015 以使用站点和区域信息的 Skype](use-site-and-region-information.md)和[关联子网与网络站点](deploy-network.md#BKMK_AssociateSubnets)中的步骤。
  
### <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a>在全局范围启用媒体旁路以始终绕过中介服务器

1. 打开 Skype 业务 Server Control Panel。
    
2. 在左侧导航栏中，单击“网络配置”****。
    
3. 双击列表中的“全局”**** 配置。
    
4. 在“编辑全局设置”**** 页上，选中“启用媒体旁路”**** 复选框。
    
5. 单击“始终绕过”****。
    
6. 单击“**提交**”。
    
## <a name="see-also"></a>另请参阅

[规划媒体绕过中的业务 2015 Skype](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)
  
[部署业务服务器 2015 Skype 中的媒体绕过](deploy-media-bypass.md)