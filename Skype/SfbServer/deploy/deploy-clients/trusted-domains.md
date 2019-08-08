---
title: Skype 会议室系统受信任域
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9fb63ad4-6eda-4724-be63-10bf5e65cb2b
description: 阅读本主题，了解如何为 Skype 会议室系统和 Skype for Business 配置受信任的域。
ms.openlocfilehash: 2b2aeb98e3b1b6efe585e565c1e288d635fdb26e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235011"
---
# <a name="skype-room-system-trusted-domains"></a>Skype 会议室系统受信任域
 
阅读本主题，了解如何为 Skype 会议室系统和 Skype for Business 配置受信任的域。
  
## <a name="trusted-domains"></a>受信任的域

Skype for Business 客户端将显示一个对话框, 允许用户从 Skype for Business 服务器接受证书 (如果登录的用户帐户的 SIP 域与证书上的主题或使用者替换名称中显示的名称不同)。 如果为组织中的 Skype for Business 服务器配置的证书没有使用主题或主题替换名称中的 Skype 会议室系统帐户的 SIP 域名, 则必须在受信任域下的证书上配置这些域。Skype 会议室系统控制台计算机上的注册表项。 Skype 会议室系统制造商-提供的 Skype 会议室系统管理员指南介绍如何在 Skype for Business 客户端中添加受信任域和在何处添加受信任域。 
  
例如, 假设在 Skype for Business 服务器上配置的证书具有主题/主题的 "CONTOSO" 替换名称。本地 "和为 Skype 会议室系统登录地址分配给用户的 SIP 域之一是" confrm1@contoso.net "。 由于 contoso.net 不在证书中, 在 Skype 会议室系统计算机上, 你需要在注册表中将 "contoso" 配置为受信任域, 如 Skype 会议室系统制造商提供的 Skype 会议室系统管理员指南中所述。 
  

