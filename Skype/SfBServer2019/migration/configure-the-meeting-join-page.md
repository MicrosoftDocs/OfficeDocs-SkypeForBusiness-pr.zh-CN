---
title: 配置与会页面
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: End User
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 当用户单击会议请求中的会议链接时，"会议加入" 页面将检测用户计算机上已安装的客户端。 如果已安装客户端，该客户端将打开并加入会议。 如果未安装客户端，则默认情况下将打开 Web 应用。
ms.openlocfilehash: 5c9e6653783d90411e0f701b5d3395c569d8bdff
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40989557"
---
# <a name="configure-the-meeting-join-page"></a>配置与会页面

当用户单击会议请求中的会议链接时，"会议加入" 页面将检测用户计算机上已安装的客户端。 如果已安装客户端，该客户端将打开并加入会议。 如果未安装客户端，则默认情况下将打开 Web 应用。
  
如果您希望允许用户加入会议，则可以修改会议加入页面的行为。 这些配置选项已从控制面板中删除，但你可以使用 CsWebServiceConfiguration cmdlet 对其进行配置。
  
**会议加入页 CsWebServiceConfiguration 参数**

|**CsWebServiceConfiguration 参数**|**说明**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |如果设置为 True，则通过使用 Lync 之外的客户端应用程序加入会议的用户将有机会加入会议。 默认值为 False。  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |当设置为 True 时，用于加入联机会议的备用选项将自动展开并向用户显示。 当设置为 False （默认值）时，这些选项将可用，但用户将必须显示其自身的选项列表。  <br/> |
   
### <a name="to-configure-the-meeting-join-page-by-using-skype-for-business-server-2019-management-shell"></a>使用 Skype for Business Server 2019 命令行管理程序配置会议加入页面

1. 启动 Skype for Business Server 2019 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft skype for business server 2019**"，然后单击 " **skype for business 服务器管理外壳程序**"。
    
2. 运行以下 cmdlet： 
    
   ```PowerShell
   Get-CsWebServiceConfiguration
   ```

    此 cmdlet 返回 web 服务配置设置。
    
3. 运行以下命令，将参数设置为 True 或 False，具体取决于你的首选项（有关此 cmdlet 的参数的详细信息，请参阅[Skype For Business Server Management Shell](../../SfbServer/manage/management-shell.md)文档）：
    
   ```PowerShell
   Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True
   ```


