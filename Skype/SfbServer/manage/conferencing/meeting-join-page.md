---
title: 在"会议"中配置与会Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6537765e-4384-416f-92f1-a7f3b39ebe56
description: 摘要：了解如何在 Skype for Business Server 中配置与会Skype for Business Server。
ms.openlocfilehash: a1f30d2c9bf803b4c41ed4053709b4869f163757
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60832086"
---
# <a name="configure-the-meeting-join-page-in-skype-for-business-server"></a>在"会议"中配置与会Skype for Business Server
 
**摘要：** 了解如何在 Skype for Business Server 中配置与会Skype for Business Server。
  
当用户单击会议请求中的会议链接时，与会页面Skype for Business用户计算机上是否已安装会议客户端。 如果已安装客户端，则将打开该客户端并加入会议。 如果未安装客户端，则默认情况下将打开Skype for Business客户端。 
  
## <a name="configure-the-meeting-join-page"></a>配置会议加入页面

如果要允许用户使用客户端的其他版本加入会议，可以修改与会页面的行为。 已从控制面板中删除这些Skype for Business Server选项，但您可以使用 Set-CsWebServiceConfiguration cmdlet 配置它们。
  
**与会页面Set-CsWebServiceConfiguration参数**

|**Set-CsWebServiceConfiguration 参数**|**说明**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |已弃用此参数，以用于本地版本的 Skype for Business Server。  <br/> 如果设置为 True，则使用客户端应用程序（而不是 Skype for Business）加入会议的用户将有机会使用其当前客户端应用程序加入会议。 默认值为 False。  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |已弃用此参数，以用于本地版本的 Skype for Business Server。  <br/>  如果设置为 True，则用于加入联机会议的备用选项将自动展开并显示给用户。 如果设置为 False (默认值) ，这些选项将可用，但用户必须自己显示选项列表。  <br/> |
   

