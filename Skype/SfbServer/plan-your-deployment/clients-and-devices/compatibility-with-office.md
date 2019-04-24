---
title: Skype 业务 Office 相关应用程序的兼容性
ms.author: jambirk
author: jambirk
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ac3a1046-b438-4e21-9d4f-3b0057dd685d
description: 了解您可以从 Outlook 和其他 Microsoft Office 应用程序的业务功能访问 Skype 的方法。
ms.openlocfilehash: c5636b5c7e41b480a9c8aa5532a22523c3554a54
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32207473"
---
# <a name="skype-for-business-compatibility-with-office-apps"></a>Skype 业务 Office 相关应用程序的兼容性
 
了解您可以从 Outlook 和其他 Microsoft Office 应用程序的业务功能访问 Skype 的方法。
  
本主题介绍与不同版本的 Microsoft Office 套件的兼容性 for Business 的 Skype。 
  
## <a name="office-and-skype-for-business"></a>Office 和 Skype for Business

下表介绍不同版本的 Office 后部署并集成[业务 server 与 Exchange Server 集成 Skype](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)中所述 Exchange 支持的业务功能 Skype。
  
**Skype 商业和 Microsoft Office 兼容性**

|**功能**|**Microsoft Office 2010**|**Microsoft Office 2013、2015 和 2016**|**用于 Mac 的 office 2016** & #x 2776; |
|:-----|:-----|:-----|:-----|
|**Outlook 功能** ||||
|自定义 Outlook 会议邀请（添加徽标、帮助 URL、免责声明、页脚文本）  |否  |是    |是|
|配置会议选项以便在默认情况下将与会者音频和视频设为静音    |否    |是    |否    |
|跨 Office 和 for Business 的 Skype 管理联系人列表的统一的联系人存储库    |否    |是（需要 Exchange 2013 或更高版本）    |是    |
|高分辨率的配置文件图片    |否    |是（需要 Exchange 2013 或更高版本）    |是    |
|在 Microsoft Outlook 发的状态为，和抄送字段    |是     |是     |是     |
|回复 IM 或呼叫从可用性菜单    |是（从联系人卡片）    |是（从联系人卡片）    |是（从联系人卡片）    |
|“日程安排助理”选项卡上的会议请求中的状态    |是     |是     |否    |
|从工具栏或功能区中收到的电子邮件答复 IM 或呼叫    |是     |是     |是     |
|**其他 Office 应用程序**   ||||
|OneNote 共享笔记    |否    |是    |否    |
|安装集成到 Office 安装程序中    |否    |是    |否    |
|PowerPoint 演示文稿内容    |是    |是 (VBSS 也可)    |是    |
|Microsoft Word 文件和 Microsoft Excel 文件（启用了智能标记）中的 IM 和状态    |仅 Microsoft Word    |仅 Microsoft Word    |否    |
|Microsoft SharePoint 站点（必须已安装 Outlook）中的 IM 和状态    |是    |是     |否    |
   
& #x 2776;-假定您已安装，并且当前 Mac 客户端或 Lync 2011 for Mac 客户端上运行的业务 Skype。
  
## <a name="exchange-server-and-skype-for-business"></a>Exchange Server 和 Skype for Business

下表介绍不同版本的 Exchange Server 的业务支持 Skype。 客户端计算机上必须安装 Outlook 才能处理扩展的 MAPI 呼叫，并且某些功能要求启用 Exchange Web 服务 (EWS)。
  
**Skype 商业和 Exchange Server 的兼容性**

|**Exchange Server 版本**|**Skype 业务支持**|
|:-----|:-----|
|Exchange Server 2019 (仅业务服务器 2019 Skype) |与 Exchange Server 2013 支持相同    |
|Exchange Server 2016    |与 Exchange Server 2013 支持相同  <br/> |
|Exchange Server 2013  <br/> |Exchange Server 2010 支持，并添加了相同  <br/>&bull;&nbsp;&nbsp;统一的联系人存储库  <br/>&bull;&nbsp;&nbsp;高分辨率图片  <br/>&bull;&nbsp;&nbsp;存档集成  <br/> **注意：** 有关详细信息，请参阅[Business Server 与 Exchange Server 的集成 Skype](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)。  <br/> |
|Exchange Server 2010  <br/>(仅业务服务器 2015 Skype) |只有通过 EWS 才能使用以下功能：  <br/>&bull;&nbsp;&nbsp;读取或删除对话历史记录文件夹中的项  <br/>&bull;&nbsp;&nbsp;读取或删除语音邮件项  <br/>&bull;&nbsp;&nbsp;显示扩展的忙/闲信息和会议主题和位置  <br/>&bull;&nbsp;&nbsp;Exchange 联系人同步  <br/> 公用文件夹在 Exchange Server 2010 中是可选的。  <br/> |
   
## <a name="see-also"></a>另请参阅
 
[Windows 客户端要求和软件支持](windows-requirements.md)
  
[规划会议客户端 （Web 应用程序和会议应用程序）](meetings-clients.md)

