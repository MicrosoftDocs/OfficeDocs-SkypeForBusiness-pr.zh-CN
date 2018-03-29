---
title: 会议配置新建或编辑现有的
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ConfMeetingSettingEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8fc19fa-6cd7-4f68-b90a-1c7e1b649abd
description: 会议配置设置定义了用户的连接体验由用户计划的会议。 这些设置仅应用于已安排的会议。 它们不适用于通过单击客户端中的立即开会选项创建的特别会议。
ms.openlocfilehash: af9a1cca6a34320a7e2bd2ba53b08040351f784e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="meeting-configuration-create-new-or-edit-existing"></a>会议配置：创建新的或编辑现有的
 
会议配置设置可定义用户预定会议的用户加入体验。这些设置只适用于预定的会议，不适用于通过单击客户端中的“**现在开会**”选项创建的临时会议。
  
## <a name="ui-reference"></a>用户界面参考

下表介绍了该页上的各个字段。
  
- **作用域**标识要创建或修改的会议配置作用域： 全局站点或池。
    
- **名称**会议配置默认情况下，命名和名称不能更改。
    
- **PSTN 呼叫者绕过大厅**选中此复选框可自动为会议公用交换的电话网络 (PSTN) 电话线上承认正在拨入的用户。 清除此复选框可以路由 PSTN 呼叫到会议大厅，它们位于保留直到会议演示者授予他们对会议的访问。
    
- **指定作为演示者**选择的类别 （除了会议组织者） 的用户被自动指定为演示者加入会议。 无论设置此演示者可以将显式指定为演示者时安排的会议，或它们可以明确提升为演示者在会议过程。 包含以下选项：
    
  - **无**如果没有其他组织者人被自动指定为演示者，请选择此选项。
    
  - **公司**选择此选项可自动将只有您的组织的成员指定为演示者。
    
  - **每个人都**选择此选项可自动指定任何人成为演示者。
    
- **默认情况下分配会议类型**此设置用于控制是否 Outlook 会议外接程序总是安排会议通过组织者的分配会议，这意味着总是安排会议具有相同连接 URL 和音频信息。 选中此复选框可以始终使用同一个连接 URL 的计划的会议。 清除此复选框可以为每个会议使用不同连接 URL。
    
- **Admit 默认的匿名用户**选中此复选框如果匿名 （即未经身份验证的） 都允许用户，默认情况下能够参加会议。 如果允许匿名用户将不能够参加会议，默认情况下，请清除此复选框。
    
- **徽标的 URL**键入具有要用于自定义会议邀请的图像的 URL。
    
- **帮助的 URL**键入用户可用于获取有关加入会议帮助网站的 URL。
    
- **法律文本的 URL**键入具有法律信息的网站的 URL 和会议的免责声明。
    
- **自定义页脚文本**键入的文本用于自定义会议邀请。
    
有关使用会议配置的详细信息，请参阅[创建或修改会议配置设置集合](http://technet.microsoft.com/library/ce6773c1-a0d5-4405-8e32-33a6f3a46a1a.aspx)操作文档中。 大型的会议设置会议配置有关的详细信息，请参见[设置了支持大型会议](http://technet.microsoft.com/library/8e22d34b-b395-408d-9d48-8f2a3abe9513.aspx)的规划文档中。
  

