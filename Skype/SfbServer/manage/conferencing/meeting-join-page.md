---
title: 配置会议加入页在 Skype 的业务服务器 2015年
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6537765e-4384-416f-92f1-a7f3b39ebe56
description: 摘要： 了解如何配置会议业务服务器 2015年的 Skype 连接页。
ms.openlocfilehash: c0b3ed39fc2f7a1a48635353cc1db673a4bd1cd5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-the-meeting-join-page-in-skype-for-business-server-2015"></a>配置会议加入页在 Skype 的业务服务器 2015年
 
**摘要：**了解如何配置会议业务服务器 2015年的 Skype 连接页。
  
当用户单击会议链接在会议要求中，会议加入页检测 Skype 业务客户端是否已安装在用户的计算机上。 如果已安装客户端，客户端将打开，并加入会议。 如果未安装客户端，则默认情况下的业务客户端的 Skype 2015 版本打开。 
  
## <a name="configure-the-meeting-join-page"></a>配置会议加入页

您可以修改行为的会议加入页，如果您希望允许用户加入会议与其他版本的客户端。 这些配置选项已从中移除 Skype 业务服务器控制面板，但将它们配置通过使用一组 CsWebServiceConfiguration cmdlet。
  
**会议加入页集 CsWebServiceConfiguration 参数**

|**一组 CsWebServiceConfiguration 参数**|**说明**|
|:-----|:-----|
|ShowJoinUsingLegacyClientLink  <br/> |此参数用于内部部署版本的 Skype 业务服务器 2015年已弃用。  <br/> 如果设置为 True，用户加入会议，而不使用客户端应用程序业务的 Skype 将有机会通过其当前的客户端应用程序中加入会议。 默认值为 False。  <br/> |
|ShowAlternateJoinOptionsExpanded  <br/> |此参数用于内部部署版本的 Skype 业务服务器 2015年已弃用。  <br/>  如果设置为 True 时，备用选项适用于： 加入一个联机会议自动展开并显示给用户。 如果设置为 False （默认值），这些选项将可用，但用户必须要显示自己的选项的列表。  <br/> |
   

