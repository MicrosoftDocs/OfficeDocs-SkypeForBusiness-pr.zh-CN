---
title: 在"会议"中配置与会Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6537765e-4384-416f-92f1-a7f3b39ebe56
description: 摘要：了解如何在 Skype for Business Server 中配置与会Skype for Business Server。
ms.openlocfilehash: 9e2cefa5bb280d2a8570bc65b0c596e42380c19d
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62385730"
---
# <a name="configure-the-meeting-join-page-in-skype-for-business-server"></a>在"会议"中配置与会Skype for Business Server
 
**摘要：** 了解如何在 Skype for Business Server 中配置与会Skype for Business Server。
  
当用户单击会议请求中的会议链接时，与会页面将检测Skype for Business是否已在用户计算机上安装了会议客户端。 如果已安装客户端，则将打开该客户端并加入会议。 如果未安装客户端，则默认情况下将打开Skype for Business客户端。 
  
## <a name="configure-the-meeting-join-page"></a>配置会议加入页面

如果要允许用户使用客户端的其他版本加入会议，可以修改与会页面的行为。 已从控制面板中删除这些Skype for Business Server选项，但您可以使用 Set-CsWebServiceConfiguration cmdlet 对其进行配置。
  
**与会页面Set-CsWebServiceConfiguration参数**

|**Set-CsWebServiceConfiguration 参数**|**说明**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |已弃用此参数，以用于本地版本的 Skype for Business Server。  <br/> 如果设置为 True，则使用客户端应用程序（而不是 Skype for Business）加入会议的用户将有机会使用其当前客户端应用程序加入会议。 默认值为 False。  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |已弃用此参数，以用于本地版本的 Skype for Business Server。  <br/>  如果设置为 True，则用于加入联机会议的备用选项将自动展开并显示给用户。 如果设置为 False (默认值) ，这些选项将可用，但用户必须自己显示选项列表。  <br/> |
   

