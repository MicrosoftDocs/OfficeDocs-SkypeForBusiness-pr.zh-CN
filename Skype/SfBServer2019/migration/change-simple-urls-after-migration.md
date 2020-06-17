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
description: Skype for Business Server 支持简单 Url。
ms.openlocfilehash: 1b25dd74f5bdca433554091b3f8ce1c1d2dfa8ce
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753902"
---
# <a name="change-simple-urls-after-migration"></a>迁移后更改简单 URL

Skype for Business Server 支持三个简单的 Url：
  
- ****“会议”用作站点或组织中所有会议的基 URL。 通过使用会议简单 URL，用于加入会议的链接将易于理解且易于传达和分发。 
    
- ****“拨入”允许访问“电话拨入式会议设置”网页。 拨入简单 URL 包含在所有会议邀请中，因此要拨号加入会议的用户可以访问所需的电话号码和 PIN 信息。 
    
- **管理员**可以快速访问 Skype For Business Server 控制面板。 管理简单 URL 是组织内部的。 
    
迁移到 Skype for business Server 后，必须了解更改如何影响简单 Url 的 DNS 记录和证书。 如果旧版 Skype for Business Server 控制器在拓扑中仍处于使用中，则不需要对简单 Url 进行任何更改。 如果迁移后从拓扑中删除了 Skype for Business Server 控制器，则必须将简单 URL DNS 记录更新为指向某个 Skype for Business Server 池。 但是，每次更改简单 URL 名称时，都必须在每台控制器和前端服务器上运行 Enable-CsComputer，以注册该更改。

## <a name="to-update-the-meet-simple-url"></a>更新 "符合简单 URL"

1. 在拓扑生成器中，右键单击顶部节点 " **Skype For Business Server**"，然后单击 "**编辑属性**"。
    
2. 在左窗格中选择 "**简单 url** "，然后单击 "**会议 url"：** 选择 "满足 url"，然后单击 "**编辑 URL**"。
    
3. 将 URL 更新为所需的值，然后单击“确定”**** 保存已编辑的 URL。 
    
## <a name="to-update-the-admin-simple-url"></a>更新管理员简单 URL

1. 在拓扑生成器中，右键单击顶部节点 " **Skype For Business Server**"，然后单击 "**编辑属性**"。
    
2. 在左窗格中选择 "**简单 url** "，然后在 "**管理访问 URL** " 框下，输入要用于对 Skype for business Server 控制面板的管理访问权限的简单 URL，然后单击 **"确定"**。
    
   > [!TIP]
   > 建议尽可能使用最简单的 URL 作为管理 URL。 最简单的方法是 https://admin ... <em>\<domain\></em> 
  
## <a name="see-also"></a>另请参阅

[Skype for Business Server 中简单 Url 的 DNS 要求](../../SfbServer/plan-your-deployment/network-requirements/simple-urls.md)
