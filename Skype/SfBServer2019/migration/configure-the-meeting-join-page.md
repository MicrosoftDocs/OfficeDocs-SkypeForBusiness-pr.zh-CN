---
title: 配置会议加入页面
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: End User
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 当用户单击会议请求中的会议链接时，与会页面会检测用户计算机上已安装了哪个客户端。 如果已经安装，则该客户端会打开并加入会议。 如果未安装客户端，则默认情况下将打开 Web App。
ms.openlocfilehash: c90e8afa95a73618eb1aa95b3d8d174e950e7e92a49988cb6146209f49cc0e58
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54295119"
---
# <a name="configure-the-meeting-join-page"></a>配置会议加入页面

当用户单击会议请求中的会议链接时，与会页面会检测用户计算机上已安装了哪个客户端。 如果已经安装，则该客户端会打开并加入会议。 如果未安装客户端，则默认情况下将打开 Web App。
  
如果要允许用户加入会议，可以修改与会页面的行为。 这些配置选项已从控制面板中删除，但您可以使用 CsWebServiceConfiguration cmdlet 配置它们。
  
**会议加入页面 CsWebServiceConfiguration 参数**

|**CsWebServiceConfiguration 参数**|**说明**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |如果设置为 True，则使用 Lync 外的其他客户端应用程序加入会议的用户将有机会加入会议。 默认值为 False。  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |设置为 True 时，用于加入联机会议的备用选项将自动展开并显示给用户。 如果设置为 False (默认值) ，这些选项将可用，但用户必须自行显示选项列表。  <br/> |
   
### <a name="to-configure-the-meeting-join-page-by-using-skype-for-business-server-2019-management-shell"></a>使用命令行管理程序配置会议加入Skype for Business Server命令行管理程序

1. 启动 Skype for Business Server 2019 命令行管理程序：单击"开始"，单击"所有程序"，单击 **"Microsoft Skype for Business Server 2019"，** 然后单击"Skype for Business Server **命令行管理程序"。** 
    
2. 运行以下 cmdlet： 
    
   ```PowerShell
   Get-CsWebServiceConfiguration
   ```

    此 cmdlet 将返回 Web 服务配置设置。
    
3. 运行以下命令，参数设置为 True 或 False，具体取决于您的首选项 (有关此 cmdlet 的参数的详细信息，请参阅 Skype for Business Server [Management Shell](../../SfbServer/manage/management-shell.md)文档) ：
    
   ```PowerShell
   Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True
   ```


