---
title: "Skype for Business 移动应用安全性"
ms.author: kenwith
author: kenwith
ms.date: 3/21/2017
ms.audience: ITPro
ms.topic: concetpual
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: d2be8c74-3ba2-4b2d-9807-634904e1f0e8
description: ""
---

# Skype for Business 移动应用安全性

> [!IMPORTANT]
> 本文是由机器翻译的，请参阅[免责声明](d2be8c74-3ba2-4b2d-9807-634904e1f0e8.md#MT_Footer)。请在 [此处](https://support.office.com/en-us/article/d2be8c74-3ba2-4b2d-9807-634904e1f0e8) 中查找本文的英文版本以便参考。
  
## Skype for Business 客户端安全性

本文介绍了 Skype for Business 移动应用上的数据加密信息。
  
|||||
|:-----|:-----|:-----|:-----|
||**用户名/密码** <br/> |**应用数据（对话、联系人列表、会议）** <br/> |**诊断日志** <br/> |
|**Android** <br/> |我们在 Android 帐户中存储凭据信息。在将凭据保存到帐户之前，我们会使用" **AES/CBC/PKCS5Padding** "算法，对凭据进行加密。 <br/> |我们使用名为 [sqlcipher](https://www.zetetic.net/sqlcipher/design/) 的库存储在加密的 SQL 数据库中。使用其默认的 256 位 CBC 模式 AES 算法。静态数据在数据库文件中始终加密，并且仅在应用的易失存储器和呼叫堆栈中传输时才进行解密。我们还使用与用户名和密码加密（不存储在数据库中）相同的方法来加密语音邮件文件。语音邮件在磁盘上临时解密以便进行播放。 <br/> |此信息不加密。  <br/> |
|**iOS** <br/> |我们不加密密钥链中的用户名/密码。 但是，密钥链本身经过加密。  <br/> |我们已经对应用存储中的所有文件使用 [NSFileProtectionCompleteUntilFirstUserAuthentication](https://developer.apple.com/reference/foundation/fileprotectiontype/1616633-completeuntilfirstuserauthentica) 数据保护标记。这意味着位于应用数据存储中的文件始终处于加密状态，直到用户在设备重新引导后首次解锁设备为止。 <br/> |此信息不加密。  <br/> |
|**Windows Phone** <br/> |Windows Phone 使用 Windows 中的 DPAPI（数据保护 API）来保护密码。 我相信使用的加密方案是 AES。 Windows 不向我们提供配置密钥大小（或方案）的选项，因此这由 DPAPI 提供。 它使用设备 TPM 来保护特定于用户和设备的密钥。 请注意，DPAPI 密钥并不特定于应用。  <br/> |WP 应用数据（如凭据）使用 [DPAPI](https://msdn.microsoft.com/zh-cn/library/windows/apps/hh487164%28v=vs.105%29.aspx) 来提供保护。根据我们所需的详细程度，一些应用数据的索引信息由（非 DPAPI）AES 加密来保护，以避免繁琐，因此我们可以在未经解密的情况下进行查找，此密钥由 DPAPI 进一步提供保护。同一个手机的任何进程都可以读取缓存数据，但前提是此手机能够访问我们的数据文件夹。Windows 加密仅防御外部访问尝试，不能防御沙盒漏洞。 <br/> |此信息不加密。  <br/> |
   
注意：有关上述各个移动平台上适用的设备 PIN 执行信息，请参阅[此公共文档](https://docs.microsoft.com/zh-cn/InTune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune)。
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **机器翻译免责声明**：本文是由无人工介入的计算机系统翻译的。Microsoft 提供机器翻译是为了帮助非英语国家/地区用户方便阅读有关 Microsoft 产品、服务和技术的内容。由于机器翻译的原因，本文可能包含词汇、语法或文法方面的错误。 
  

