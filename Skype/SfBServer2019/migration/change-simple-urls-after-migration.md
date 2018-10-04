---
title: 迁移后更改简单 Url
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype 业务服务器支持简单 Url。
ms.openlocfilehash: 71935aab09de1598b355d2a7b27dfa02fd169216
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25374988"
---
# <a name="change-simple-urls-after-migration"></a>迁移后更改简单 Url

Skype 业务 server 支持三种简单 Url:
  
- **满足**对站点或组织中的所有会议使用作为基 URL。 与会议的简单 URL，加入会议的链接是易于理解，且轻松地进行通信和分发。 
    
- **电话拨入式**允许访问电话拨入式会议设置网页。 电话拨入式简单 URL 包含所有的会议邀请中，以便想要拨入会议的用户可以访问所需的电话号码和 PIN 信息。 
    
- **管理**业务 Server Control Panel 启用 Skype 快速访问。 组织内部的管理简单 URL。 
    
迁移到 Skype for Business Server 之后，您必须知道如何更改会影响您的 DNS 记录和证书的简单 Url。 如果旧 Skype 的业务 Server Director 仍保留在拓扑中的使用，无需更改简单 Url 是必需的。 如果 Skype 的业务 Server Director 从拓扑中删除迁移后，必须更新简单 URL 的 DNS 记录以指向业务服务器池的 Skype 之一。 无论何时更改简单 URL 名称，但是，必须以注册该更改每台控制器和前端服务器上运行 Enable-cscomputer。

## <a name="to-update-the-meet-simple-url"></a>更新会议简单 URL

1. 在拓扑生成器中，右键单击顶层节点**Skype 业务服务器**，，然后单击**编辑属性**。
    
2. 然后下面选择左窗格中，**简单 Url** **会议 Url:** 选择会议 URL，然后单击**编辑 URL**。
    
3. 将 URL 更新为所需的值，然后单击“**确定**”保存已编辑的 URL。 
    
## <a name="to-update-the-admin-simple-url"></a>更新管理简单 URL

1. 在拓扑生成器中，右键单击顶层节点**Skype 业务服务器**，，然后单击**编辑属性**。
    
2. 选择**简单 Url**的左窗格，然后下方**管理访问 URL**框中输入所需的管理访问权限 Skype 业务 Server Control Panel 的简单 URL，然后单击**确定**。
    
   > [!TIP]
   > 建议尽可能使用最简单的 URL 作为管理 URL。 简单的选项是https://admin。<em>\<域\></em>。 
  
## <a name="see-also"></a>另请参阅

[Skype 中的简单 url 的业务服务器的 DNS 要求](../../SfbServer/plan-your-deployment/network-requirements/simple-urls.md)
