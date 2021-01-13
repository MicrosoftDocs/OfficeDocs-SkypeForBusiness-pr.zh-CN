---
title: Skype for Business 与 Office 应用的兼容性
ms.author: v-cichur
author: cichur
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ac3a1046-b438-4e21-9d4f-3b0057dd685d
description: 了解从 Outlook 和其他应用程序访问 Skype for Business 功能Microsoft Office方式。
ms.openlocfilehash: b3d792d5e6376e4d845aa74f0585acf7d9a70d81
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802732"
---
# <a name="skype-for-business-compatibility-with-office-apps"></a>Skype for Business 与 Office 应用的兼容性
 
了解从 Outlook 和其他应用程序访问 Skype for Business 功能Microsoft Office方式。
  
本主题介绍 Skype for Business 与各种版本的 Microsoft Office 套件的兼容性。 
  
## <a name="office-and-skype-for-business"></a>Office 和 Skype for Business

下表介绍了各种 Office 版本在部署和集成 Exchange 后支持的 Skype for Business 功能，如"将 Skype for Business Server 与 Exchange Server [集成"中所述](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)。
  
**Skype for Business Microsoft Office兼容性**

|**功能**|**Microsoft Office 2010**|**Microsoft Office 2013、2015 和 2016**|**Office 2016 for Mac** &#x2776; |
|:-----|:-----|:-----|:-----|
|**Outlook 功能** ||||
|自定义 Outlook 会议邀请 (添加徽标、帮助 URL、免责声明、页脚文本)   |否  |是   |是|
|默认情况下，配置会议选项以将与会者音频和视频设为静音    |否    |是    |否    |
|用于跨 Office 和 Skype for Business 管理联系人列表的统一联系人存储    |否    |是 (Exchange 2013 或更高版本)     |是    |
|高分辨率个人资料图片    |否    |是 (Exchange 2013 或更高版本)     |是    |
|Microsoft Outlook From、To 和 Cc 字段中的状态    |是    |是    |是    |
|从可用性菜单使用 IM 或呼叫进行回复    |是 (联系人卡片)     |是 (联系人卡片)     |是 (联系人卡片)     |
|"状态"选项卡上的会议日程安排助理状态    |是    |是    |否    |
|使用 IM 或来自工具栏或功能区中的呼叫回复已接收电子邮件    |是    |是    |是    |
|**其他 Office 应用**   ||||
|OneNote 共享笔记    |否    |是    |否    |
|集成到 Office 安装程序的安装程序    |否    |是    |否    |
|PowerPoint 演示文稿内容    |是    |是 (VBSS 也可用)     |是    |
|Microsoft Word 和 Microsoft Excel 文件的 IM 和状态 (启用智能标记)     |仅适用于 Microsoft Word    |仅适用于 Microsoft Word    |否    |
|必须安装 Outlook (Microsoft SharePoint 网站中的 IM 和状态)     |是    |是    |否    |
   
&#x2776; - 假定你已安装并当前在 Mac 客户端或 Lync 2011 for Mac 客户端上运行 Skype for Business。
  
## <a name="exchange-server-and-skype-for-business"></a>Exchange Server和 Skype for Business

下表介绍了 Skype for Business 对各种版本的 Exchange Server。 必须将 Outlook 安装在客户端计算机上以处理扩展的 MAPI 调用，并且某些功能需要使用 Exchange Web Services (EWS) 。
  
**Skype for Business Exchange Server兼容性**

|**Exchange Server版本**|**Skype for Business 支持**|
|:-----|:-----|
|Exchange Server 2019 (Skype for Business Server 2019)  |与 2013 Exchange Server相同    |
|Exchange Server 2016    |与 2013 Exchange Server相同  <br/> |
|Exchange Server 2013  <br/> |与 Exchange Server 2010 支持相同，并添加  <br/>&bull;&nbsp;&nbsp;统一联系人存储  <br/>&bull;&nbsp;&nbsp;高分辨率图片  <br/>&bull;&nbsp;&nbsp;存档集成  <br/> **注意：** 有关详细信息，请参阅 [将 Skype for Business Server 与 Exchange Server。](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)  <br/> |
|Exchange Server 2010  <br/> (Skype for Business Server 2015)  |以下功能仅通过 EWS 提供：  <br/>&bull;&nbsp;&nbsp;读取或删除"对话历史记录"文件夹中的项目  <br/>&bull;&nbsp;&nbsp;读取或删除语音邮件项目  <br/>&bull;&nbsp;&nbsp;显示扩展的忙/闲信息以及会议主题和位置  <br/>&bull;&nbsp;&nbsp;Exchange 联系人同步  <br/> 公用文件夹在 Exchange Server 2010 中是可选的。  <br/> |
   
## <a name="see-also"></a>另请参阅
 
[Windows 客户端要求和软件支持](windows-requirements.md)
  
[规划 Web 应用和 (会议应用程序的会议) ](meetings-clients.md)

