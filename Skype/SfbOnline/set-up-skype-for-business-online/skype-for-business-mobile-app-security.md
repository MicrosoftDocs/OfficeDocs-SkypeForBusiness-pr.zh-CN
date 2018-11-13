---
title: Skype for Business 移动应用安全
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
ms.openlocfilehash: a87719bc4135ab429fca8425812b285a2eed5b5e
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2018
ms.locfileid: "26294484"
---
# <a name="skype-for-business-mobile-app-security"></a>Skype for Business 移动应用安全

## <a name="skype-for-business-client-security"></a>Skype for Business 客户端安全性

本文介绍了 Skype for Business 移动应用上的数据加密信息。
  
|||||
|:-----|:-----|:-----|:-----|
||**用户名/密码** <br/> |**应用程序数据 (对话，<br/>联系人列表中，会议)** <br/> |**诊断日志** <br/> |
|**Android** <br/> |我们在 Android 帐户中存储凭据信息。在将凭据保存到帐户之前，我们会使用" **AES/CBC/PKCS5Padding** "算法，对凭据进行加密。<br/> |我们使用名为 [sqlcipher](https://www.zetetic.net/sqlcipher/design/) 的库存储在加密的 SQL 数据库中。使用其默认的 256 位 CBC 模式 AES 算法。静态数据在数据库文件中始终加密，并且仅在应用的易失存储器和呼叫堆栈中传输时才进行解密。我们还使用与用户名和密码加密（不存储在数据库中）相同的方法来加密语音邮件文件。语音邮件在磁盘上临时解密以便进行播放。<br/> |此信息不加密。  <br/> |
|**iOS** <br/> |我们不加密密钥链中的用户名/密码。 但是，密钥链本身经过加密。  <br/> |我们已经对应用存储中的所有文件使用 [NSFileProtectionCompleteUntilFirstUserAuthentication](https://developer.apple.com/reference/foundation/fileprotectiontype/1616633-completeuntilfirstuserauthentica) 数据保护标记。这意味着位于应用数据存储中的文件始终处于加密状态，直到用户在设备重新引导后首次解锁设备为止。<br/> |此信息不加密。  <br/> |
|**Windows Phone** <br/> |Windows Phone 使用 Windows 中的 DPAPI（数据保护 API）来保护密码。 我相信使用的加密方案是 AES。 Windows 不向我们提供配置密钥大小（或方案）的选项，因此这由 DPAPI 提供。 它使用设备 TPM 来保护特定于用户和设备的密钥。 请注意，DPAPI 密钥并不特定于应用。  <br/> |WP 应用数据（如凭据）使用 [DPAPI](https://msdn.microsoft.com/en-us/library/windows/apps/hh487164%28v=vs.105%29.aspx) 来提供保护。根据我们所需的详细程度，一些应用数据的索引信息由（非 DPAPI）AES 加密来保护，以避免繁琐，因此我们可以在未经解密的情况下进行查找，此密钥由 DPAPI 进一步提供保护。同一个手机的任何进程都可以读取缓存数据，但前提是此手机能够访问我们的数据文件夹。Windows 加密仅防御外部访问尝试，不能防御沙盒漏洞。<br/> |此信息不加密。  <br/> |
   
**注意：** 请参考[本公共文档](https://docs.microsoft.com/en-us/InTune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune)的每个以上的移动平台上可用的设备 pin 实施
  
## <a name="related-topics"></a>相关主题
[设置 Skype for Business Online](set-up-skype-for-business-online.md)

[允许 Skype for Business 用户添加 Skype 联系人](let-skype-for-business-users-add-skype-contacts.md)

  
 