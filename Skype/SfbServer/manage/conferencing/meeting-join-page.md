---
title: 在 Skype for Business Server 中配置与会页面
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6537765e-4384-416f-92f1-a7f3b39ebe56
description: 摘要：了解如何在 Skype for Business Server 中配置与会页面。
ms.openlocfilehash: 247664a3ff4bbc4ee055775d26f1d077b662752b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828032"
---
# <a name="configure-the-meeting-join-page-in-skype-for-business-server"></a>在 Skype for Business Server 中配置与会页面
 
**摘要：** 了解如何在 Skype for Business Server 中配置与会页面。
  
当用户在会议请求中单击会议链接时，与会页面将检测用户计算机上是否已安装 Skype for Business 客户端。 如果已安装客户端，则将打开该客户端并加入会议。 如果未安装客户端，则默认情况下将打开 Skype for Business 客户端。 
  
## <a name="configure-the-meeting-join-page"></a>配置会议加入页面

如果要允许用户使用客户端的其他版本加入会议，可以修改与会页面的行为。 这些配置选项已从 Skype for Business Server 控制面板中删除，但您可以使用 Set-CsWebServiceConfiguration cmdlet 进行配置。
  
**与会页面Set-CsWebServiceConfiguration参数**

|**Set-CsWebServiceConfiguration 参数**|**说明**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |此参数已弃用，以用于本地版本的 Skype for Business Server。  <br/> 如果设置为 True，则使用除 Skype for Business 外的其他客户端应用程序加入会议的用户将有机会使用其当前客户端应用程序加入会议。 默认值为 False。  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |此参数已弃用，以用于本地版本的 Skype for Business Server。  <br/>  如果设置为 True，则用于加入联机会议的备用选项将自动展开并显示给用户。 如果设置为 False (默认值) ，这些选项将可用，但用户必须自行显示选项列表。  <br/> |
   

