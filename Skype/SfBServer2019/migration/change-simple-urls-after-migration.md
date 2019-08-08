---
title: 迁移后更改简单 URL
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype for Business 服务器支持简单的 Url。
ms.openlocfilehash: 806003a2639d3861c066248657521ceb58a4e986
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239491"
---
# <a name="change-simple-urls-after-migration"></a>迁移后更改简单 URL

Skype for Business 服务器支持三个简单的 Url:
  
- "**开会**" 用作网站或组织中的所有会议的基本 URL。 通过 "满足简单 URL", 加入会议的链接易于理解, 并且易于沟通和分发。 
    
- 通过**拨入功能**, 可以访问 "电话拨入式会议设置" 网页。 拨入式简单 URL 包含在所有会议邀请中, 以便希望拨入会议的用户可以访问必要的电话号码和 PIN 信息。 
    
- **管理员**可快速访问 Skype For Business 服务器控制面板。 管理员简单的 URL 是您的组织内部的。 
    
迁移到 Skype for business 服务器之后, 你必须知道更改对简单 Url 的 DNS 记录和证书有何影响。 如果旧版 Skype for Business 服务器控制器仍在拓扑中使用, 则不需要对您的简单 Url 进行任何更改。 如果迁移后从拓扑中删除了 Skype for Business 服务器主管, 则必须更新简单 URL DNS 记录以指向其中一个 Skype for Business 服务器池。 但是, 当您更改简单的 URL 名称时, 必须在每个 Director 和前端服务器上运行 Enable-CsComputer 以注册更改。

## <a name="to-update-the-meet-simple-url"></a>更新 "满足简单 URL"

1. 在拓扑生成器中, 右键单击顶部节点 " **Skype for Business 服务器**", 然后单击 "**编辑属性**"。
    
2. 在左窗格中选择 "**简单 url** ", 然后单击 "**会议 url":** 选择 "满足 url", 然后单击 "**编辑 URL**"。
    
3. 将 URL 更新为所需的值，然后单击“**确定**”保存已编辑的 URL。 
    
## <a name="to-update-the-admin-simple-url"></a>更新管理员简单 URL

1. 在拓扑生成器中, 右键单击顶部节点 " **Skype for Business 服务器**", 然后单击 "**编辑属性**"。
    
2. 在左窗格中选择 "**简单 url** ", 然后在 "**管理访问 URL** " 框下方输入要用于管理对 Skype for business 服务器控制面板的简单 URL, 然后单击 **"确定"**。
    
   > [!TIP]
   > 建议尽可能使用最简单的 URL 作为管理 URL。 最简单的选项https://admin是。<em> \<域\></em>。 
  
## <a name="see-also"></a>另请参阅

[Skype for Business 服务器中的简单 Url 的 DNS 要求](../../SfbServer/plan-your-deployment/network-requirements/simple-urls.md)
