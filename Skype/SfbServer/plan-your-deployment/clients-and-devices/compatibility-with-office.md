---
title: Skype 业务 Office 相关应用程序的兼容性
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ac3a1046-b438-4e21-9d4f-3b0057dd685d
description: 了解您可以从 Outlook 和其他 Microsoft Office 应用程序的业务功能访问 Skype 的方法。
ms.openlocfilehash: 186b8951718e6903ec7cc4f8c317504b74917716
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
---
# <a name="skype-for-business-compatibility-with-office-apps"></a>Skype 业务 Office 相关应用程序的兼容性
 
了解您可以从 Outlook 和其他 Microsoft Office 应用程序的业务功能访问 Skype 的方法。
  
本主题介绍与不同版本的 Microsoft Office 套件的兼容性 for Business 的 Skype。 
  
## <a name="office-and-skype-for-business"></a>Office 和 Skype for Business

下表介绍不同版本的 Office 后部署并集成[业务服务器 2015 与 Exchange Server 的集成 Skype](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)中所述 Exchange 支持的业务功能 Skype。
  
**Skype 商业和 Microsoft Office 兼容性**

|**功能**|**Microsoft Office 2010**|**Microsoft Office 2013，2015 和 2016**|**用于 Mac 的 office 2016** = #x 2776; |
|:-----|:-----|:-----|:-----|
|**Outlook 功能** <br/> ||||
|自定义 Outlook 会议邀请（添加徽标、帮助 URL、免责声明、页脚文本）  <br/> |否  <br/> |是  <br/> |否  <br/> |
|配置会议选项以便在默认情况下将与会者音频和视频设为静音  <br/> |否  <br/> |是  <br/> |否  <br/> |
|跨 Office 和 for Business 的 Skype 管理联系人列表的统一的联系人存储库  <br/> |否  <br/> |是（需要 Exchange 2013 或更高版本）  <br/> |是  <br/> |
|高分辨率的配置文件图片  <br/> |否  <br/> |是（需要 Exchange 2013 或更高版本）  <br/> |是  <br/> |
|在 Microsoft Outlook 发的状态为，和抄送字段  <br/> |是  <br/> |是  <br/> |是  <br/> |
|回复 IM 或呼叫从可用性菜单  <br/> |是（从联系人卡片）  <br/> |是（从联系人卡片）  <br/> |是（从联系人卡片）  <br/> |
|“日程安排助理”选项卡上的会议请求中的状态  <br/> |是  <br/> |是  <br/> |否  <br/> |
|从工具栏或功能区中收到的电子邮件答复 IM 或呼叫  <br/> |是  <br/> |是  <br/> |是  <br/> |
|**其他 Office 应用程序** <br/> ||||
|OneNote 共享笔记  <br/> |否  <br/> |是  <br/> |否  <br/> |
|安装集成到 Office 安装程序中  <br/> |否  <br/> |是  <br/> |否  <br/> |
|PowerPoint 演示文稿内容  <br/> |是  <br/> |是  <br/> （VBSS 也可用）  <br/> |是  <br/> |
|Microsoft Word 文件和 Microsoft Excel 文件（启用了智能标记）中的 IM 和状态  <br/> |仅 Microsoft Word  <br/> |仅 Microsoft Word  <br/> |否  <br/> |
|Microsoft SharePoint 站点（必须已安装 Outlook）中的 IM 和状态  <br/> |是  <br/> |是  <br/> |否  <br/> |
   
& #x 2776;-假定您已安装，并且当前 Mac 客户端或 Lync 2011 for Mac 客户端上运行的业务 Skype。
  
## <a name="exchange-server-and-skype-for-business"></a>Exchange Server 和 Skype for Business

下表介绍不同版本的 Exchange Server 的业务支持 Skype。 客户端计算机上必须安装 Outlook 才能处理扩展的 MAPI 呼叫，并且某些功能要求启用 Exchange Web 服务 (EWS)。
  
**Skype 商业和 Exchange Server 的兼容性**

|**Exchange Server 版本**|**Skype 业务支持**|
|:-----|:-----|
|Exchange Server 2016  <br/> |与 Exchange Server 2013 支持相同  <br/> |
|Exchange Server 2013  <br/> |Exchange Server 2010 支持，并添加了相同  <br/>&bull;&nbsp;&nbsp;统一的联系人存储库  <br/>&bull;&nbsp;&nbsp;高分辨率图片  <br/>&bull;&nbsp;&nbsp;存档集成  <br/> **注意：**有关详细信息，请参阅[业务服务器 2015 与 Exchange Server 的集成 Skype](../../deploy/integrate-with-exchange-server/integrate-with-exchange-server.md)。  <br/> |
|Exchange Server 2010  <br/> |只有通过 EWS 才能使用以下功能：  <br/>&bull;&nbsp;&nbsp;读取或删除对话历史记录文件夹中的项  <br/>&bull;&nbsp;&nbsp;读取或删除语音邮件项  <br/>&bull;&nbsp;&nbsp;显示扩展的忙/闲信息和会议主题和位置  <br/>&bull;&nbsp;&nbsp;Exchange 联系人同步  <br/> 公用文件夹在 Exchange Server 2010 中是可选的。  <br/> |
   
## <a name="see-also"></a>另请参阅
 

[Windows 客户端要求和软件支持](windows-requirements.md)
  
[规划会议客户端 （Web 应用程序和会议应用程序）](meetings-clients.md)
#### 

[Lync 2013 中的客户端互操作性](http://technet.microsoft.com/library/0f126571-91a2-45d5-855c-1e4ddb45fc04.aspx)
  
[客户端系统要求](http://technet.microsoft.com/library/38f3a465-dac1-4381-bc59-270a4ef07ced.aspx)
  
[Lync Windows 应用商店应用程序要求](http://technet.microsoft.com/library/5f2e0a40-8450-4f61-b6f6-913fc1906020.aspx)

