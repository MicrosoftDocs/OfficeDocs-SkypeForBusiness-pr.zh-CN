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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: '了解如何为用户设置移动应用安全性。 '
ms.openlocfilehash: 1adfc8e44880b89ab9f4b24be532ae4a327744cf69d0ef63ecea3f65ae684fc8
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54295109"
---
# <a name="skype-for-business-mobile-app-security"></a>Skype for Business 移动应用安全

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

## <a name="skype-for-business-client-security"></a>Skype for Business 客户端安全性

本文介绍了 Skype for Business 移动应用上的数据加密信息。
  
|||||
|:-----|:-----|:-----|:-----|
||**用户名/密码** <br/> |**应用数据 (对话、 <br/> 联系人列表、会议)** <br/> |**诊断日志** <br/> |
|**Android** <br/> |我们将凭据信息存储在 Android 帐户。 我们还在将凭据保存到"帐户"之前对其进行加密。 我们使用 **"AES/CBC/PKCS5Padding"** 算法进行加密。 <br/> |我们使用名为[sqlcipher](https://www.zetetic.net/sqlcipher/design/)的库SQL加密的加密数据库。 我们在 CBC 模式下使用 256 位 AES 的默认算法。 其余数据始终在数据库文件中加密，并且仅在应用的易失性内存和调用堆栈内传输时未加密。 我们还使用与用户名称和密码加密相同的方法加密语音邮件 (它们不会存储在 DB) 。 语音邮件在磁盘上暂时未加密，以便播放。  <br/> |此信息未加密。  <br/> |
|**iOS** <br/> |我们不加密密钥链中的用户名/密码。 但是，密钥链是自行加密的。  <br/> |我们已对应用存储中所有文件使用 [NSFileProtectionCompleteUntilFirstUserAuthentication](https://developer.apple.com/reference/foundation/fileprotectiontype/1616633-completeuntilfirstuserauthentica) 数据保护标志。 这意味着，应用存储中的文件将加密，直到用户在设备重新启动后首次解锁设备。 <br/> |此信息未加密。  <br/> |
|**Windows Phone** <br/> |Windows Phone DPAPI (Data Protection API) Windows保护密码。 我认为使用的加密方案是 AES。 Windows未提供配置密钥大小的选项， (或方案) ，因此 DPAPI 提供的任何功能都一样。 它将使用设备 TPM 保护特定于用户和设备的密钥。 请注意，DPAPI 密钥不特定于应用。  <br/> |WP 应用数据受 [DPAP](/previous-versions/windows/apps/hh487164(v=vs.105))I 保护，如 creds。 根据我们需要的详细信息，应用数据的一些索引信息受 (非 DPAPI) AES 加密的保护，以避免加盐，因此我们可以在不解密的情况下进行查找，并且该密钥反过来受 DPAPI 的保护。 任何进程都可以从同一手机读取缓存的数据，假设它可以到达数据文件夹。 Windows加密不能防止沙盒泄露，只能防止外部访问尝试。  <br/> |此信息未加密。  <br/> |
   
**注意：** 请参阅此 [公共文档，](/InTune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune) 了解上述每个移动平台上可用的设备 PIN 强制措施
  
## <a name="related-topics"></a>相关主题
[设置 Skype for Business Online](set-up-skype-for-business-online.md)

[允许 Skype for Business 用户添加 Skype 联系人](let-skype-for-business-users-add-skype-contacts.md)

  
