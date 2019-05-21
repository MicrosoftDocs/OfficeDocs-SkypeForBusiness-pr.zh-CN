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
f1keywords: None
ms.custom:
- Setup
description: '了解如何为你的用户设置移动应用安全性。 '
ms.openlocfilehash: 109fd6cb2ddccbc69ddae3e912506836ee49a399
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34285131"
---
# <a name="skype-for-business-mobile-app-security"></a>Skype for Business 移动应用安全

## <a name="skype-for-business-client-security"></a>Skype for Business 客户端安全性

本文介绍了 Skype for Business 移动应用上的数据加密信息。
  
|||||
|:-----|:-----|:-----|:-----|
||**用户名/密码** <br/> |**应用数据 (对话、<br/>联系人列表、会议)** <br/> |**诊断日志** <br/> |
|**Android** <br/> |我们将凭据信息存储在 Android 帐户中。 我们还会在将凭据保存到帐户之前对其进行加密。 我们使用 " **AES/CBC/PKCS5Padding** " 算法进行加密。 <br/> |我们使用名为[sqlcipher](https://www.zetetic.net/sqlcipher/design/)的库存储在加密的 SQL 数据库中。 我们在 CBC 模式下使用的是256位 AES 的默认算法。 Rest 上的数据始终在数据库文件中加密, 并且仅在应用的易失性内存和调用堆栈内部传输时才被加密。 我们还使用与用户的用户名和密码加密相同的方法加密语音邮件文件 (它们不存储在数据库中)。 语音邮件在磁盘上暂时未加密以允许播放。  <br/> |此信息不加密。  <br/> |
|**iOS** <br/> |我们不会在密钥链中加密用户名/密码。 但是, 密钥链是加密的。  <br/> |我们已在应用存储中的所有文件上使用[NSFileProtectionCompleteUntilFirstUserAuthentication](https://developer.apple.com/reference/foundation/fileprotectiontype/1616633-completeuntilfirstuserauthentica)数据保护标志。 这意味着应用存储中的文件将被加密, 直到用户在设备重启后首次解锁设备时。 <br/> |此信息不加密。  <br/> |
|**Windows Phone** <br/> |Windows Phone 使用 Windows 中的 DPAPI (数据保护 API) 来保护密码。 我相信使用的加密方案是 AES。 Windows 无法为我们提供配置密钥大小 (或方案) 的选项, 因此它就是 DPAPI 提供的任何内容。 它将使用设备 TPM 保护特定于用户和设备的密钥。 请注意, DPAPI 密钥并非特定于该应用。  <br/> |WP 应用数据通过[DPAP](https://msdn.microsoft.com/en-us/library/windows/apps/hh487164%28v=vs.105%29.aspx)I (如凭据) 进行保护。 根据所需的详细信息量, 应用数据的一些索引信息受 (非 DPAPI) AES 加密的保护, 以避免 salting, 因此我们可以查找而不进行解密, 并且该密钥又受 DPAPI 保护。 可以通过同一电话中的任何进程读取缓存的数据, 假定它可以访问我们的数据文件夹。 Windows 加密不会防止受到沙盒破坏, 仅限于外部访问尝试。  <br/> |此信息不加密。  <br/> |
   
**注意:** 请参阅[此公共文档](https://docs.microsoft.com/InTune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune), 了解上述每个移动平台上的可用设备 pin 实施情况
  
## <a name="related-topics"></a>相关主题
[设置 Skype for Business Online](set-up-skype-for-business-online.md)

[允许 Skype for Business 用户添加 Skype 联系人](let-skype-for-business-users-add-skype-contacts.md)

  
 
