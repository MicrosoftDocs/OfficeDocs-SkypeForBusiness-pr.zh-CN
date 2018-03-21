---
title: "Skype 的企业移动应用程序安全"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: d2be8c74-3ba2-4b2d-9807-634904e1f0e8
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: "了解如何为您的用户的移动应用程序安全性设置。 "
ms.openlocfilehash: 150eb50c4e2c57b3e51b9400d9fdb79d49990174
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2018
---
# <a name="skype-for-business-mobile-app-security"></a><span data-ttu-id="f3d71-103">Skype 的企业移动应用程序安全</span><span class="sxs-lookup"><span data-stu-id="f3d71-103">Skype for Business mobile app security</span></span>

## <a name="skype-for-business-client-security"></a><span data-ttu-id="f3d71-104">Skype for Business 客户端安全性</span><span class="sxs-lookup"><span data-stu-id="f3d71-104">Skype for Business Client Security</span></span>

<span data-ttu-id="f3d71-105">本文介绍了 Skype for Business 移动应用上的数据加密信息。</span><span class="sxs-lookup"><span data-stu-id="f3d71-105">This article covers data encryption information on Skype for Business Mobile Apps.</span></span>
  
|||||
|:-----|:-----|:-----|:-----|
||<span data-ttu-id="f3d71-106">**用户名/密码**</span><span class="sxs-lookup"><span data-stu-id="f3d71-106">**Username/Password**</span></span> <br/> |<span data-ttu-id="f3d71-107">**应用程序数据 (对话，<br/>联系人列表、 会议)**</span><span class="sxs-lookup"><span data-stu-id="f3d71-107">**App Data (Conversations,<br/> Contact List, Meetings)**</span></span> <br/> |<span data-ttu-id="f3d71-108">**诊断日志**</span><span class="sxs-lookup"><span data-stu-id="f3d71-108">**Diagnostic logs**</span></span> <br/> |
|<span data-ttu-id="f3d71-109">**Android**</span><span class="sxs-lookup"><span data-stu-id="f3d71-109">**Android**</span></span> <br/> |<span data-ttu-id="f3d71-p101">我们在 Android 帐户中存储凭据信息。在将凭据保存到帐户之前，我们会使用" **AES/CBC/PKCS5Padding** "算法，对凭据进行加密。</span><span class="sxs-lookup"><span data-stu-id="f3d71-p101">We store credentials information in Android Accounts. We also encrypt credentials before saving them into Accounts. We use " **AES/CBC/PKCS5Padding** " algorithm for encryption. </span></span><br/> |<span data-ttu-id="f3d71-p102">我们使用名为 [sqlcipher](https://www.zetetic.net/sqlcipher/design/) 的库存储在加密的 SQL 数据库中。使用其默认的 256 位 CBC 模式 AES 算法。静态数据在数据库文件中始终加密，并且仅在应用的易失存储器和呼叫堆栈中传输时才进行解密。我们还使用与用户名和密码加密（不存储在数据库中）相同的方法来加密语音邮件文件。语音邮件在磁盘上临时解密以便进行播放。</span><span class="sxs-lookup"><span data-stu-id="f3d71-p102">We store in an encrypted SQL database using a library called [sqlcipher](https://www.zetetic.net/sqlcipher/design/). We use their default algorithm of 256-bit AES in CBC mode. The data at rest is always encrypted in the database file and is only unencrypted in transit inside of the app's volatile memory and call stacks. We also encrypt voicemail files using the same method as the user's name and password encryption (they are not stored in the DB). Voicemails are temporarily unencrypted on disk to allow playback.  </span></span><br/> |<span data-ttu-id="f3d71-118">此信息不加密。</span><span class="sxs-lookup"><span data-stu-id="f3d71-118">This information is not encrypted.</span></span>  <br/> |
|<span data-ttu-id="f3d71-119">**iOS**</span><span class="sxs-lookup"><span data-stu-id="f3d71-119">**iOS**</span></span> <br/> |<span data-ttu-id="f3d71-p103">我们不加密密钥链中的用户名/密码。 但是，密钥链本身经过加密。</span><span class="sxs-lookup"><span data-stu-id="f3d71-p103">We DO NOT encrypt the username/password in the keychain. The keychain is encrypted, however, on its own.</span></span>  <br/> |<span data-ttu-id="f3d71-p104">我们已经对应用存储中的所有文件使用 [NSFileProtectionCompleteUntilFirstUserAuthentication](https://developer.apple.com/reference/foundation/fileprotectiontype/1616633-completeuntilfirstuserauthentica) 数据保护标记。这意味着位于应用数据存储中的文件始终处于加密状态，直到用户在设备重新引导后首次解锁设备为止。</span><span class="sxs-lookup"><span data-stu-id="f3d71-p104">We are already using [NSFileProtectionCompleteUntilFirstUserAuthentication](https://developer.apple.com/reference/foundation/fileprotectiontype/1616633-completeuntilfirstuserauthentica) data protection flag on all files in the app storage. This means that files in the app storage would be encrypted until user unlocks the device for the very first time after the device reboot. </span></span><br/> |<span data-ttu-id="f3d71-124">此信息不加密。</span><span class="sxs-lookup"><span data-stu-id="f3d71-124">This information is not encrypted.</span></span>  <br/> |
|<span data-ttu-id="f3d71-125">**Windows Phone**</span><span class="sxs-lookup"><span data-stu-id="f3d71-125">**Windows Phone**</span></span> <br/> |<span data-ttu-id="f3d71-p105">Windows Phone 使用 Windows 中的 DPAPI（数据保护 API）来保护密码。 我相信使用的加密方案是 AES。 Windows 不向我们提供配置密钥大小（或方案）的选项，因此这由 DPAPI 提供。 它使用设备 TPM 来保护特定于用户和设备的密钥。 请注意，DPAPI 密钥并不特定于应用。</span><span class="sxs-lookup"><span data-stu-id="f3d71-p105">Windows Phone uses the DPAPI (Data Protection API) in Windows to secure passwords. I believe the encryption scheme used is AES. Windows doesn't give us an option to configure the key size (or scheme), so it's whatever DPAPI gives. It will use the device TPM to secure keys which are specific to the user and device. Note that DPAPI keys are not specific to the app.</span></span>  <br/> |<span data-ttu-id="f3d71-p106">WP 应用数据（如凭据）使用 [DPAPI](https://msdn.microsoft.com/en-us/library/windows/apps/hh487164%28v=vs.105%29.aspx) 来提供保护。根据我们所需的详细程度，一些应用数据的索引信息由（非 DPAPI）AES 加密来保护，以避免繁琐，因此我们可以在未经解密的情况下进行查找，此密钥由 DPAPI 进一步提供保护。同一个手机的任何进程都可以读取缓存数据，但前提是此手机能够访问我们的数据文件夹。Windows 加密仅防御外部访问尝试，不能防御沙盒漏洞。</span><span class="sxs-lookup"><span data-stu-id="f3d71-p106">WP App Data is protected with [DPAP](https://msdn.microsoft.com/en-us/library/windows/apps/hh487164%28v=vs.105%29.aspx)I, like the creds. Depending on how much detail we want, some of the index information for the App Data is protected by (non-DPAPI) AES encryption to avoid salting, so we can look up without decrypting, and that key is in turn protected with DPAPI. Cached data can be read by any process from the same phone, assuming it can reach our data folder. Windows encryption does not protect from sandbox breach, only external access attempts.  </span></span><br/> |<span data-ttu-id="f3d71-135">此信息不加密。</span><span class="sxs-lookup"><span data-stu-id="f3d71-135">This information is not encrypted.</span></span>  <br/> |
   
<span data-ttu-id="f3d71-136">**注意：**请在每个上述的移动平台上可用的设备 pin 实施[此公用文档](https://docs.microsoft.com/en-us/InTune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune)，参阅</span><span class="sxs-lookup"><span data-stu-id="f3d71-136">**Note:** Please refer to [this public documentation](https://docs.microsoft.com/en-us/InTune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune) for device pin enforcement available on each of the above Mobile platforms</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="f3d71-137">相关主题</span><span class="sxs-lookup"><span data-stu-id="f3d71-137">Related topics</span></span>
[<span data-ttu-id="f3d71-138">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="f3d71-138">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="f3d71-139">允许 Skype for Business 用户添加 Skype 联系人</span><span class="sxs-lookup"><span data-stu-id="f3d71-139">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)
