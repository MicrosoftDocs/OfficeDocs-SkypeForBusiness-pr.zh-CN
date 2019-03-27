---
title: Skype for Business 移动应用安全
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d2be8c74-3ba2-4b2d-9807-634904e1f0e8
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: '了解如何设置您的用户的移动应用程序安全性。 '
ms.openlocfilehash: 0c07bbbe7d186774c4c8aa13d7fcb08bf81dcb63
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30886828"
---
# <a name="skype-for-business-mobile-app-security"></a>Skype for Business 移动应用安全

## <a name="skype-for-business-client-security"></a>Skype for Business 客户端安全性

本文介绍了 Skype for Business 移动应用上的数据加密信息。
  
|||||
|:-----|:-----|:-----|:-----|
||**用户名/密码** <br/> |**应用程序数据 (对话，<br/>联系人列表中，会议)** <br/> |**诊断日志** <br/> |
|**Android** <br/> |我们 Android 帐户存储的凭据信息。 我们还加密之前将其保存到帐户的凭据。 我们使用" **AES/CBC/PKCS5Padding** "算法进行加密。 <br/> |我们将存储在加密 SQL 数据库中使用一个名为[sqlcipher](https://www.zetetic.net/sqlcipher/design/)库。 我们在 CBC 模式下使用 256 位 AES 其默认的算法。 在 rest 的数据始终加密数据库文件中，并仅加密在传输过程内部应用程序的可变内存和调用堆栈中。 我们还加密的语音邮件文件使用相同的方法为用户的名称和密码加密 （它们不存储在数据库中）。 语音邮件是临时磁盘以允许播放上未加密的。  <br/> |此信息不加密。  <br/> |
|**iOS** <br/> |我们不加密钥匙链中的用户名/密码。 钥匙链加密，但是，在自己计算机上。  <br/> |我们已在应用程序存储中的所有文件使用[NSFileProtectionCompleteUntilFirstUserAuthentication](https://developer.apple.com/reference/foundation/fileprotectiontype/1616633-completeuntilfirstuserauthentica)数据保护标志。 这意味着用户第一次在设备重新启动后解锁设备之前应用程序存储中的文件将被加密。 <br/> |此信息不加密。  <br/> |
|**Windows Phone** <br/> |Windows Phone 在 Windows 中使用 DPAPI (数据保护 API) 以确保以安全密码。 我相信所用的加密方案是 AES。 Windows 不为我们提供选项配置的关键大小 （或方案），使其 DPAPI 所提供的任何内容。 它将使用设备 TPM 保护密钥的特定于用户和设备。 请注意 DPAPI 键并不特定于应用程序。  <br/> |保护 WP 应用程序数据与[DPAP](https://msdn.microsoft.com/en-us/library/windows/apps/hh487164%28v=vs.105%29.aspx)I like 凭据设置。 根据我们希望多少详细信息，某些应用程序数据的索引信息都受 (非 DPAPI) AES 加密，以避免盐，以便我们可以无需解密，查找和 DPAPI 反过来受该注册表项。 缓存的数据可以读取从同一电话，假定它可以到达我们数据文件夹的任何进程。 Windows 加密不保护以下项从沙盒违反、 仅外部访问尝试。  <br/> |此信息不加密。  <br/> |
   
**注意：** 请参考[本公共文档](https://docs.microsoft.com/InTune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune)的每个以上的移动平台上可用的设备 pin 实施
  
## <a name="related-topics"></a>相关主题
[设置 Skype for Business Online](set-up-skype-for-business-online.md)

[允许 Skype for Business 用户添加 Skype 联系人](let-skype-for-business-users-add-skype-contacts.md)

  
 
