---
title: 配置与会页面
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
description: 当用户单击会议请求中的会议链接时，"会议加入" 页将检测用户计算机上已安装的客户端。 如果已经安装，则该客户端会打开并加入会议。 如果未安装客户端，则默认情况下会打开 Web 应用。
ms.openlocfilehash: a7bb0983438708bbc0d30cd527eb494491c3cbf2
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754022"
---
# <a name="configure-the-meeting-join-page"></a>配置与会页面

当用户单击会议请求中的会议链接时，"会议加入" 页将检测用户计算机上已安装的客户端。 如果已经安装，则该客户端会打开并加入会议。 如果未安装客户端，则默认情况下会打开 Web 应用。
  
如果您希望允许用户加入会议，则可以修改会议加入页面的行为。 这些配置选项已从控制面板中删除，但可使用 CsWebServiceConfiguration cmdlet 对其进行配置。
  
**会议加入页面 CsWebServiceConfiguration 参数**

|**CsWebServiceConfiguration 参数**|**说明**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |如果设置为 True，则通过使用 Lync 之外的客户端应用程序加入会议的用户将具有加入会议的机会。 默认值为 False。  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |如果设置为 True，则将自动扩展用于加入联机会议的备用选项，并向用户显示。 如果设置为 False （默认值），则可以使用这些选项，但用户必须为自己显示选项列表。  <br/> |
   
### <a name="to-configure-the-meeting-join-page-by-using-skype-for-business-server-2019-management-shell"></a>使用 Skype for Business Server 2019 命令行管理程序配置会议加入页面

1. 启动 Skype for Business Server 2019 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Skype for business server 2019**"，然后单击 " **Skype for business server Management Shell**"。
    
2. 运行以下 cmdlet： 
    
   ```PowerShell
   Get-CsWebServiceConfiguration
   ```

    此 cmdlet 将返回 Web 服务配置设置。
    
3. 运行以下命令，将参数设置为 True 或 False，具体取决于你的首选项（有关此 cmdlet 的参数的详细信息，请参阅[Skype For Business Server 命令行管理](../../SfbServer/manage/management-shell.md)程序文档）：
    
   ```PowerShell
   Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True
   ```


