---
title: Skype 会议室系统受信任域
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9fb63ad4-6eda-4724-be63-10bf5e65cb2b
description: 阅读本主题，了解如何为 Skype 会议室系统和 Skype for Business 配置受信任的域。
ms.openlocfilehash: bc025849f56a7257ac3684b9783e551959bd0228
ms.sourcegitcommit: d3c3467320a2928d3bad14a1a44a31ee5a9a988c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2018
ms.locfileid: "25699684"
---
# <a name="skype-room-system-trusted-domains"></a>Skype 会议室系统受信任域
 
阅读本主题，了解如何为 Skype 会议室系统和 Skype for Business 配置受信任的域。
  
## <a name="trusted-domains"></a>受信任的域

业务客户端 Skype 显示一个对话框，允许用户接受来自 Skype 的证书 Business Server 如果登录的用户帐户的 SIP 域不同证书上的主题或使用者替代名称中显示的名称。 如果您的组织中为 Business Server 配置为 Skype 的证书没有主题或使用者替代名称中的 Skype 会议室系统帐户的 SIP 域名，则必须配置该页上的证书，在受信任域下显示这些域Skype 会议室系统控制台的计算机上的注册表项。 Skype 会议室系统提供制造商 Skype 会议室系统管理员的指南介绍了如何以及在哪里业务客户端 Skype 中添加受信任的域。 
  
例如，假定为业务服务器配置上 Skype 的证书具有主题/使用者替代名称的"CONTOSO。本地"和 SIP 域分配给用户的登录地址 Skype 会议室系统之一是"confrm1@contoso.net。" 因为 contoso.net 不在该证书，Skype 会议室系统在计算机上，您将需要您 Skype 会议室系统提供制造商 Skype 会议室系统管理员指南 》 中所述作为注册表中的受信任域配置"contoso.local"。 
  

