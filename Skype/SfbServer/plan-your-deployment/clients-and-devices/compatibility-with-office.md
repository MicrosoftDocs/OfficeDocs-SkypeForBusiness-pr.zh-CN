---
title: Skype for Business应用程序Office兼容性
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
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ac3a1046-b438-4e21-9d4f-3b0057dd685d
description: 了解从应用程序和其他Skype for Business访问Outlook功能Microsoft Office的方法。
ms.openlocfilehash: e8d2ec9d3785d03c0f853021bcb4f33f6eb2c4aa
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58599917"
---
# <a name="skype-for-business-compatibility-with-office-apps"></a>Skype for Business应用程序Office兼容性
 
了解从应用程序和其他Skype for Business访问Outlook功能Microsoft Office的方法。
  
本主题介绍 Skype for Business套件的各种版本的Microsoft Office兼容性。 
  
## <a name="office-and-skype-for-business"></a>Office 和 Skype for Business

下表 Skype for Business介绍部署 Exchange 并集成 Office 后各种 Office 版本支持的 Skype for Business Server 功能，Skype for Business Server [Exchange Server。](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)
  
**Skype for Business和Microsoft Office兼容性**

|**功能**|**Microsoft Office 2010**|**Microsoft Office 2013、2015 和 2016**|**Office 2016 for Mac&#x2776;** |
|:-----|:-----|:-----|:-----|
|**Outlook功能** ||||
|自定义Outlook会议邀请 (添加徽标、帮助 URL、免责声明、页脚文本)   |否  |是   |是|
|将会议选项配置为默认将与会者音频和视频设为静音    |否    |是    |否    |
|统一联系人存储，用于跨 Office 和 Skype for Business    |否    |是 (2013 Exchange或更高版本)     |是    |
|高分辨率个人资料图片    |否    |是 (2013 Exchange或更高版本)     |是    |
|Microsoft Outlook From、To 和 Cc 字段中的状态    |是    |是    |是    |
|使用 IM 或来自可用性菜单的呼叫进行回复    |是 (联系人卡片中的)     |是 (联系人卡片中的)     |是 (联系人卡片中的)     |
|"会议请求"选项卡上的会议日程安排助理状态    |是    |是    |否    |
|使用 IM 答复，或在收到的电子邮件中通过工具栏或功能区进行呼叫    |是    |是    |是    |
|**其他Office应用**   ||||
|OneNote共享笔记    |否    |是    |否    |
|安装程序已集成到 Office 安装程序中    |否    |是    |否    |
|PowerPoint演示文稿内容    |是    |是 (VBSS 也可用)     |是    |
|启用智能标记的Microsoft Word Microsoft Excel中的 IM 和 (状态)     |仅Microsoft Word    |仅Microsoft Word    |否    |
|必须安装 Microsoft SharePoint站点 (Outlook IM 和状态)     |是    |是    |否    |
   
&#x2776; - 假定你已安装并当前在 Mac Skype for Business或 Lync 2011 for Mac 客户端上运行客户端。
  
## <a name="exchange-server-and-skype-for-business"></a>Exchange Server 和 Skype for Business

下表介绍了Skype for Business版本对 Exchange Server 的支持。 Outlook必须安装在客户端计算机上以处理扩展的 MAPI 调用，并且某些功能需要使用 Exchange Web 服务 (EWS) 。
  
**Skype for Business和Exchange Server兼容性**

|**Exchange Server版本**|**Skype for Business支持**|
|:-----|:-----|
|Exchange Server 2019 (Skype for Business Server 2019)  |与 2013 Exchange Server相同    |
|Exchange Server 2016    |与 2013 Exchange Server相同  <br/> |
|Exchange Server 2013  <br/> |与 Exchange Server 2010 支持相同，并添加  <br/>&bull;&nbsp;&nbsp;统一联系人存储  <br/>&bull;&nbsp;&nbsp;高分辨率图片  <br/>&bull;&nbsp;&nbsp;存档集成  <br/> **注意：** 有关详细信息，请参阅 Integrate [Skype for Business Server with Exchange Server](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)。  <br/> |
|Exchange Server 2010  <br/> (Skype for Business Server 2015 年 10 月)  |以下功能仅通过 EWS 提供：  <br/>&bull;&nbsp;&nbsp;读取或删除"对话历史记录"文件夹中的项目  <br/>&bull;&nbsp;&nbsp;读取或删除语音邮件项目  <br/>&bull;&nbsp;&nbsp;显示扩展的忙/闲信息以及会议主题和位置  <br/>&bull;&nbsp;&nbsp;Exchange联系人同步  <br/> 公用文件夹在 2010 Exchange Server可选。  <br/> |
   
## <a name="see-also"></a>另请参阅
 
[Windows客户端要求和软件支持](windows-requirements.md)
  
[Plan for Meetings clients (Web App and Meetings App) ](meetings-clients.md)

