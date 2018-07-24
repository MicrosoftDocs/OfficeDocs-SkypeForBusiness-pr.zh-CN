---
title: 配置会议中的业务服务器 Skype 的与会页面
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6537765e-4384-416f-92f1-a7f3b39ebe56
description: 摘要： 了解如何配置会议中的业务服务器 Skype 的与会页面。
ms.openlocfilehash: 7574dee341e0226a6a6e2ee8c77cdfb2353beb5a
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20977612"
---
# <a name="configure-the-meeting-join-page-in-skype-for-business-server"></a>配置会议中的业务服务器 Skype 的与会页面
 
**摘要：** 了解如何配置会议中的业务服务器 Skype 的与会页面。
  
当用户单击会议请求中，会议中的会议链接与会页面检测业务客户端 Skype 是否已安装在用户计算机上。 如果已安装客户端，客户端将打开并加入会议。 如果未安装客户端，则默认情况下，for Business Skype 客户端将打开。 
  
## <a name="configure-the-meeting-join-page"></a>配置与会页面

您可以修改的行为的与会页面如果您想要允许用户加入与其他版本的客户端的会议。 这些配置选项均已从 Skype 的业务 Server Control Panel，但使用 Set-cswebserviceconfiguration cmdlet 对其进行配置。
  
**会议加入页面 Set-cswebserviceconfiguration 参数**

|**Set-cswebserviceconfiguration 参数**|**说明**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |此参数已被弃用业务服务器与 Skype 的内部部署版本一起使用。  <br/> 如果设置为 True，而不使用客户端应用程序加入会议的用户 Skype for Business 将有机会通过其当前的客户端应用程序加入会议。 默认值为 False。  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |此参数已被弃用业务服务器与 Skype 的内部部署版本一起使用。  <br/>  如果设置为 True，备用选项用于加入联机会议自动扩展和向用户显示。 如果设置为 False （默认值），这些选项会可用，但用户会显示为自己的选项的列表。  <br/> |
   

