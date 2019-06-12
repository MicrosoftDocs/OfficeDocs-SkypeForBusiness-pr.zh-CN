---
title: Skype for business 与 Office 应用的兼容性
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ac3a1046-b438-4e21-9d4f-3b0057dd685d
description: 了解您可以从 Outlook 和其他 Microsoft Office 应用程序访问 Skype for Business 功能的方式。
ms.openlocfilehash: c24c6b08e21db357d52b1cc130e53f23b6123ff6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277431"
---
# <a name="skype-for-business-compatibility-with-office-apps"></a>Skype for business 与 Office 应用的兼容性
 
了解您可以从 Outlook 和其他 Microsoft Office 应用程序访问 Skype for Business 功能的方式。
  
本主题介绍 Skype for Business 与各种版本的 Microsoft Office 套件的兼容性。 
  
## <a name="office-and-skype-for-business"></a>Office 和 Skype for business

下表介绍了各种版本的 Office 支持的 Skype for Business 功能, 这些功能是按照将[Skype For Business 服务器与 Exchange Server 集成](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)时所述进行部署和集成的。
  
**Skype for Business 和 Microsoft Office 兼容性**

|**功能**|**Microsoft Office 2010**|**Microsoft Office 2013、2015 和 2016**|**Office 2016 For Mac** &#x2776; |
|:-----|:-----|:-----|:-----|
|**Outlook 功能** ||||
|自定义 Outlook 会议邀请（添加徽标、帮助 URL、免责声明、页脚文本）  |否  |是   |是|
|配置会议选项以便在默认情况下将与会者音频和视频设为静音    |否    |是    |否    |
|用于管理跨 Office 和 Skype for business 的联系人列表的统一联系人存储    |否    |是（需要 Exchange 2013 或更高版本）    |是    |
|高分辨率个人资料图片    |否    |是（需要 Exchange 2013 或更高版本）    |是    |
|Microsoft Outlook "发件人"、"收件人" 和 "抄送" 字段中的状态    |是    |是     |是     |
|通过即时消息或 "可用性" 菜单中的呼叫进行答复    |是（从联系人卡片）    |是（从联系人卡片）    |是（从联系人卡片）    |
|“日程安排助理”选项卡上的会议请求中的状态    |是    |是     |否    |
|在收到的电子邮件的工具栏或功能区中答复即时消息或呼叫    |是    |是     |是     |
|**其他 Office 应用**   ||||
|OneNote 共享笔记    |否    |是    |否    |
|安装集成到 Office 安装程序中    |否    |是    |否    |
|PowerPoint 演示文稿内容    |是    |是 (VBSS 也可以使用)    |是    |
|Microsoft Word 文件和 Microsoft Excel 文件（启用了智能标记）中的 IM 和状态    |仅 Microsoft Word    |仅 Microsoft Word    |否    |
|Microsoft SharePoint 站点（必须已安装 Outlook）中的 IM 和状态    |是    |是     |否    |
   
&#x2776;-假设你已安装并正在运行 Mac 客户端或 Lync 2011 for Mac 客户端的 Skype for Business。
  
## <a name="exchange-server-and-skype-for-business"></a>Exchange Server 和 Skype for Business

下表介绍了各种 Exchange Server 版本的 Skype for Business 支持。 客户端计算机上必须安装 Outlook 才能处理扩展的 MAPI 呼叫，并且某些功能要求启用 Exchange Web 服务 (EWS)。
  
**Skype for Business 和 Exchange Server 兼容性**

|**Exchange Server 版本**|**Skype for Business 支持**|
|:-----|:-----|
|Exchange Server 2019 (仅适用于 Skype for Business Server 2019) |与 Exchange Server 2013 支持相同    |
|Exchange Server 2016    |与 Exchange Server 2013 支持相同  <br/> |
|Exchange Server 2013  <br/> |与 Exchange Server 2010 支持相同, 并且添加了  <br/>&bull;&nbsp;&nbsp;统一联系人存储  <br/>&bull;&nbsp;&nbsp;高分辨率图片  <br/>&bull;&nbsp;&nbsp;存档集成  <br/> **注意:** 有关详细信息, 请参阅将[Skype For Business 服务器与 Exchange Server 集成](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)。  <br/> |
|Exchange Server 2010  <br/>(仅限 Skype for Business 服务器 2015) |只有通过 EWS 才能使用以下功能：  <br/>&bull;&nbsp;&nbsp;在 "对话历史记录" 文件夹中阅读或删除项目  <br/>&bull;&nbsp;&nbsp;阅读或删除语音邮件项目  <br/>&bull;&nbsp;&nbsp;显示扩展的忙/闲信息和会议主题和位置  <br/>&bull;&nbsp;&nbsp;Exchange 联系人同步  <br/> 公用文件夹在 Exchange Server 2010 中是可选的。  <br/> |
   
## <a name="see-also"></a>另请参阅
 
[Windows 客户端要求和软件支持](windows-requirements.md)
  
[规划会议客户端 (Web 应用和会议应用)](meetings-clients.md)

