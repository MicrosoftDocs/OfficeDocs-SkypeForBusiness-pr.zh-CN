---
title: Skype 业务与 Office 应用程序的兼容性
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: ac3a1046-b438-4e21-9d4f-3b0057dd685d
description: 了解您可以从 Outlook 和其他 Microsoft Office 应用程序的业务功能访问 Skype 的方法。
ms.openlocfilehash: 2b58c9f8decef9be329dbb3f9e77422b3f0a59c0
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="skype-for-business-compatibility-with-office-apps"></a>Skype 业务与 Office 应用程序的兼容性
 
了解您可以从 Outlook 和其他 Microsoft Office 应用程序的业务功能访问 Skype 的方法。
  
本主题介绍与 Microsoft Office 套件的不同版本的兼容性业务的 Skype。 
  
## <a name="office-and-skype-for-business"></a>办公室和 Skype 业务

下表描述业务功能所支持的各种版本的 Office，一旦 Exchange 部署和集成[业务服务器 2015 与 Exchange Server 的集成 Skype](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)所述 Skype。
  
**Skype 业务和 Microsoft Office 兼容性**

|**功能**|**Microsoft Office 2010**|**Microsoft Office 2013 年，2015 和 2016**|**对于 Mac office 2016** & #x 2776; |
|:-----|:-----|:-----|:-----|
|**Outlook 功能** <br/> ||||
|自定义 Outlook 会议邀请（添加徽标、帮助 URL、免责声明、页脚文本）  <br/> |否  <br/> |是  <br/> |否  <br/> |
|配置会议选项以便在默认情况下将与会者音频和视频设为静音  <br/> |否  <br/> |是  <br/> |否  <br/> |
|统一的联系人存储用于跨机构和业务的 Skype 管理联系人列表  <br/> |否  <br/> |是（需要 Exchange 2013 或更高版本）  <br/> |是  <br/> |
|高分辨率资料图片  <br/> |否  <br/> |是（需要 Exchange 2013 或更高版本）  <br/> |是  <br/> |
|在 Microsoft Outlook 发的状态，和抄送字段  <br/> |是  <br/> |是  <br/> |是  <br/> |
|使用即时消息答复或从可用性菜单调用  <br/> |是（从联系人卡片）  <br/> |是（从联系人卡片）  <br/> |是（从联系人卡片）  <br/> |
|“日程安排助理”选项卡上的会议请求中的状态  <br/> |是  <br/> |是  <br/> |否  <br/> |
|从工具栏或功能区中接收到的电子邮件与即时消息或调用回复  <br/> |是  <br/> |是  <br/> |是  <br/> |
|**其他 Office 应用程序** <br/> ||||
|OneNote 共享笔记  <br/> |否  <br/> |是  <br/> |否  <br/> |
|安装集成到 Office 安装程序中  <br/> |否  <br/> |是  <br/> |否  <br/> |
|PowerPoint 演示文稿内容  <br/> |是  <br/> |是  <br/> （VBSS 也可用）  <br/> |是  <br/> |
|Microsoft Word 文件和 Microsoft Excel 文件（启用了智能标记）中的 IM 和状态  <br/> |仅 Microsoft Word  <br/> |仅 Microsoft Word  <br/> |否  <br/> |
|Microsoft SharePoint 站点（必须已安装 Outlook）中的 IM 和状态  <br/> |是  <br/> |是  <br/> |否  <br/> |
   
& #x 2776;-假定已安装并且当前正在运行的业务 Skype Mac 客户端或 Lync 2011 Mac 客户机上。
  
## <a name="exchange-server-and-skype-for-business"></a>Exchange Server 和 Skype 业务

下表描述了各种版本的 Exchange Server 的业务支持的 Skype。 客户端计算机上必须安装 Outlook 才能处理扩展的 MAPI 呼叫，并且某些功能要求启用 Exchange Web 服务 (EWS)。
  
**Skype 业务和 Exchange Server 兼容性**

|**Exchange Server 版本**|**Skype 的业务支持**|
|:-----|:-----|
|Exchange Server 2016  <br/> |与 Exchange Server 2013 支持相同  <br/> |
|Exchange Server 2013  <br/> |Exchange Server 2010年支持，加上的相同  <br/>&bull;&nbsp;&nbsp;联系人的统一的存储  <br/>&bull;&nbsp;&nbsp;高分辨率的图片  <br/>&bull;&nbsp;&nbsp;归档集成  <br/> **注意：**有关详细信息，请参阅[Exchange Server 具有的业务服务器 2015年的集成 Skype](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)。  <br/> |
|Exchange Server 2010  <br/> |只有通过 EWS 才能使用以下功能：  <br/>&bull;&nbsp;&nbsp;读取或删除对话历史记录文件夹中的项目  <br/>&bull;&nbsp;&nbsp;读取或删除语音邮件项目  <br/>&bull;&nbsp;&nbsp;显示扩展的忙/闲信息和会议主题以及位置  <br/>&bull;&nbsp;&nbsp;交换联系人同步  <br/> 公用文件夹在 Exchange Server 2010 中是可选的。  <br/> |
   
## <a name="see-also"></a>另请参阅
 

[Windows 客户端要求和软件支持](windows-requirements.md)
  
[规划会议客户端 （Web 应用程序和会议的应用程序）](meetings-clients.md)
#### 

[Lync 2013 客户端互操作性](http://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx)
  
[客户端系统要求](http://technet.microsoft.com/library/38f3a465-dac1-4381-bc59-270a4ef07ced.aspx)
  
[Lync Windows 应用商店应用程序要求](http://technet.microsoft.com/library/5f2e0a40-8450-4f61-b6f6-913fc1906020.aspx)

