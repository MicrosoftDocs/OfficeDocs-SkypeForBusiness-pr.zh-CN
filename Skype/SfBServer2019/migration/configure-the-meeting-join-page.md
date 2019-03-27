---
title: 配置与会页面
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: End User
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 当用户单击会议请求中，会议中的会议链接与会页面检测用户的计算机上已安装的客户端。 如果已安装客户端，该客户端将打开并加入会议。 如果未安装客户端，则默认情况下 Web 应用程序将打开。
ms.openlocfilehash: 88ae915318505efef6ae716a17217aaa1e7b12df
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879938"
---
# <a name="configure-the-meeting-join-page"></a>配置与会页面

当用户单击会议请求中，会议中的会议链接与会页面检测用户的计算机上已安装的客户端。 如果已安装客户端，该客户端将打开并加入会议。 如果未安装客户端，则默认情况下 Web 应用程序将打开。
  
您可以修改的行为的与会页面如果您想要允许用户加入会议。 已从控制面板中，这些配置选项，但使用 CsWebServiceConfiguration cmdlet 对其进行配置。
  
**会议加入页面 CsWebServiceConfiguration 参数**

|**CsWebServiceConfiguration 参数**|**说明**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |如果设置为 True，通过使用除 Lync 以外的客户端应用程序加入会议的用户将有机会加入会议。 默认值为 False。  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |当设置为 true，则加入联机会议将自动展开和向用户显示的备用选项。 设置为 False （默认值） 时，这些选项将可用，但用户会显示为自己的选项的列表。  <br/> |
   
### <a name="to-configure-the-meeting-join-page-by-using-skype-for-business-server-2019-management-shell"></a>若要将会议配置为使用适用于业务服务器 2019年命令行管理程序 Skype 的与会页面

1. 为业务服务器 2019年命令行管理程序启动 Skype： 单击**开始**，单击**所有程序**，都单击**Microsoft Skype 的业务服务器 2019年**，，然后都单击**Skype 的业务 Server Management Shell**。
    
2. 运行以下 cmdlet： 
    
   ```
   Get-CsWebServiceConfiguration
   ```

    此 cmdlet 返回 web 服务配置设置。
    
3. 运行以下命令，与参数设置为 True 或 False，具体取决于您的首选项 （有关此 cmdlet 的参数的详细信息，请参阅[Business Server Management Shell 的 Skype](../../SfbServer/manage/management-shell.md)文档）：
    
   ```
   Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True
   ```


