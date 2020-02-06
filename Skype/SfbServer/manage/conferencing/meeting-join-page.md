---
title: 在 Skype for Business 服务器中配置会议加入页面
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6537765e-4384-416f-92f1-a7f3b39ebe56
description: 摘要：了解如何在 Skype for Business 服务器中配置会议加入页面。
ms.openlocfilehash: 7381db4983b5a2c1ec6dccf474f0b381e079e222
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818513"
---
# <a name="configure-the-meeting-join-page-in-skype-for-business-server"></a>在 Skype for Business 服务器中配置会议加入页面
 
**摘要：** 了解如何在 Skype for Business 服务器中配置会议加入页面。
  
当用户单击会议请求中的会议链接时，"会议加入" 页面将检测用户计算机上是否已安装 Skype for Business 客户端。 如果已安装客户端，客户端将打开并加入会议。 如果未安装客户端，则默认情况下会打开 Skype for Business 客户端。 
  
## <a name="configure-the-meeting-join-page"></a>配置与会页面

如果你希望允许用户加入与其他版本的客户端的会议，则可以修改会议加入页面的行为。 这些配置选项已从 Skype for Business 服务器控制面板中删除，但你可以使用 CsWebServiceConfiguration cmdlet 对其进行配置。
  
**会议加入页面设置-CsWebServiceConfiguration 参数**

|**CsWebServiceConfiguration 参数**|**说明**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |此参数已弃用，用于 Skype for business Server 的本地版本。  <br/> 如果设置为 True，则通过使用 Skype for Business 之外的客户端应用程序加入会议的用户将有机会通过使用其当前客户端应用程序加入会议。 默认值为 False。  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |此参数已弃用，用于 Skype for business Server 的本地版本。  <br/>  如果设置为 True，则自动展开并向用户显示用于加入联机会议的备用选项。 如果设置为 False （默认值），则可以使用这些选项，但用户将必须为自己显示选项列表。  <br/> |
   

