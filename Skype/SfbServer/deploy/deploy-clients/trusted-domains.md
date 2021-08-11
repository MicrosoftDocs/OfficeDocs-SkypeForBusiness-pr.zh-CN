---
title: Skype会议室系统受信任域
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9fb63ad4-6eda-4724-be63-10bf5e65cb2b
description: 阅读本主题，了解如何为会议室系统和会议室Skype域Skype for Business。
ms.openlocfilehash: 0cdf7806a40dbbe440614e7d9407926cb17a6a2e817a73c6c0026b0d7078ee19
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54298722"
---
# <a name="skype-room-system-trusted-domains"></a>Skype会议室系统受信任域
 
阅读本主题，了解如何为会议室系统和会议室Skype域Skype for Business。
  
## <a name="trusted-domains"></a>受信任的域

Skype for Business 客户端显示一个对话框，如果用户登录的用户帐户的 SIP 域与证书上的"使用者"或"使用者替代名称"中显示的名称不同，则用户可以从 Skype for Business Server 接受证书。 如果组织中为 Skype for Business Server 配置的证书在"主题"或"主题替换名称"中没有 Skype 会议室系统帐户的 SIP 域名，则必须在 Skype 会议室系统控制台计算机上"受信任的域"注册表项下配置证书上呈现的这些域。 会议室Skype制造商提供的 Skype 会议室系统管理员指南介绍了如何在 Skype for Business 客户端中添加受信任域。 
  
例如，假定在证书上配置的Skype for Business Server主题/主题替换名称为"CONTOSO"。LOCAL"，分配给用户用于会议室系统登录地址Skype SIP 域之一为"confrm1@contoso.net"。 由于 contoso.net 不在证书中，因此在 Skype 会议室系统计算机上，您需要在注册表中将"contoso.local"配置为受信任的域，如 Skype 会议室系统制造商提供的 Skype Room System Administrator's Guide 中的说明。 
  

