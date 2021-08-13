---
title: 迁移后更改简单 URL
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype for Business Server支持简单 URL。
ms.openlocfilehash: c3d78387ae0bcf16204e2fcaa4ff7db3549334fe814a014a88c80e8ab6658d5b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54324721"
---
# <a name="change-simple-urls-after-migration"></a>迁移后更改简单 URL

Skype for Business Server支持三个简单的 URL：
  
- “会议”用作站点或组织中所有会议的基 URL。 通过使用会议简单 URL，用于加入会议的链接将易于理解且易于传达和分发。 
    
- “拨入”允许访问“电话拨入式会议设置”网页。 拨入简单 URL 包含在所有会议邀请中，因此要拨号加入会议的用户可以访问所需的电话号码和 PIN 信息。 
    
- **管理员** 允许快速访问Skype for Business Server控制面板。 管理简单 URL 是组织内部的。 
    
迁移到 Skype for Business Server后，您必须了解更改如何影响简单 URL 的 DNS 记录和证书。 如果旧 Skype for Business Server 控制器仍在拓扑中使用，则无需更改简单 URL。 如果在迁移Skype for Business Server将控制器从拓扑中删除，则必须更新简单 URL DNS 记录，以指向其中一个Skype for Business Server池。 但是，每次更改简单 URL 名称时，都必须在每台控制器和前端服务器上运行 Enable-CsComputer，以注册该更改。

## <a name="to-update-the-meet-simple-url"></a>更新会议简单 URL

1. 在拓扑生成器中，右键单击顶部节点 **Skype for Business Server，** 然后单击"编辑 **属性"。**
    
2. 在 **左窗格中选择"简单 URL"，** 然后在 **"会议** URL："下方选择"会议 URL"，然后单击"编辑 **URL"。**
    
3. 将 URL 更新为所需的值，然后单击“确定”保存已编辑的 URL。 
    
## <a name="to-update-the-admin-simple-url"></a>更新管理简单 URL

1. 在拓扑生成器中，右键单击顶部节点 **Skype for Business Server，** 然后单击"编辑 **属性"。**
    
2. 在 **左窗格中** 选择"简单 URL"，然后在"管理访问 **URL"** 框下方，输入管理访问"控制面板"Skype for Business Server URL，然后单击"确定 **"。**
    
   > [!TIP]
   > 建议尽可能使用最简单的 URL 作为管理 URL。 最简单的选项是 https://admin 。 <em>\<domain\></em> 
  
## <a name="see-also"></a>另请参阅

[用户中简单 URL 的 DNS Skype for Business Server](../../SfbServer/plan-your-deployment/network-requirements/simple-urls.md)
