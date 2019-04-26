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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32237255"
---
# <a name="skype-for-business-mobile-app-security"></a><span data-ttu-id="fb722-103">Skype for Business 移动应用安全</span><span class="sxs-lookup"><span data-stu-id="fb722-103">Skype for Business mobile app security</span></span>

## <a name="skype-for-business-client-security"></a><span data-ttu-id="fb722-104">Skype for Business 客户端安全性</span><span class="sxs-lookup"><span data-stu-id="fb722-104">Skype for Business Client Security</span></span>

<span data-ttu-id="fb722-105">本文介绍了 Skype for Business 移动应用上的数据加密信息。</span><span class="sxs-lookup"><span data-stu-id="fb722-105">This article covers data encryption information on Skype for Business Mobile Apps.</span></span>
  
|||||
|:-----|:-----|:-----|:-----|
||<span data-ttu-id="fb722-106">**用户名/密码**</span><span class="sxs-lookup"><span data-stu-id="fb722-106">**Username/Password**</span></span> <br/> |<span data-ttu-id="fb722-107">**应用程序数据 (对话，<br/>联系人列表中，会议)**</span><span class="sxs-lookup"><span data-stu-id="fb722-107">**App Data (Conversations,<br/> Contact List, Meetings)**</span></span> <br/> |<span data-ttu-id="fb722-108">**诊断日志**</span><span class="sxs-lookup"><span data-stu-id="fb722-108">**Diagnostic logs**</span></span> <br/> |
|<span data-ttu-id="fb722-109">**Android**</span><span class="sxs-lookup"><span data-stu-id="fb722-109">**Android**</span></span> <br/> |<span data-ttu-id="fb722-110">我们 Android 帐户存储的凭据信息。</span><span class="sxs-lookup"><span data-stu-id="fb722-110">We store credentials information in Android Accounts.</span></span> <span data-ttu-id="fb722-111">我们还加密之前将其保存到帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="fb722-111">We also encrypt credentials before saving them into Accounts.</span></span> <span data-ttu-id="fb722-112">我们使用" **AES/CBC/PKCS5Padding** "算法进行加密。</span><span class="sxs-lookup"><span data-stu-id="fb722-112">We use " **AES/CBC/PKCS5Padding** " algorithm for encryption.</span></span> <br/> |<span data-ttu-id="fb722-113">我们将存储在加密 SQL 数据库中使用一个名为[sqlcipher](https://www.zetetic.net/sqlcipher/design/)库。</span><span class="sxs-lookup"><span data-stu-id="fb722-113">We store in an encrypted SQL database using a library called [sqlcipher](https://www.zetetic.net/sqlcipher/design/).</span></span> <span data-ttu-id="fb722-114">我们在 CBC 模式下使用 256 位 AES 其默认的算法。</span><span class="sxs-lookup"><span data-stu-id="fb722-114">We use their default algorithm of 256-bit AES in CBC mode.</span></span> <span data-ttu-id="fb722-115">在 rest 的数据始终加密数据库文件中，并仅加密在传输过程内部应用程序的可变内存和调用堆栈中。</span><span class="sxs-lookup"><span data-stu-id="fb722-115">The data at rest is always encrypted in the database file and is only unencrypted in transit inside of the app's volatile memory and call stacks.</span></span> <span data-ttu-id="fb722-116">我们还加密的语音邮件文件使用相同的方法为用户的名称和密码加密 （它们不存储在数据库中）。</span><span class="sxs-lookup"><span data-stu-id="fb722-116">We also encrypt voicemail files using the same method as the user's name and password encryption (they are not stored in the DB).</span></span> <span data-ttu-id="fb722-117">语音邮件是临时磁盘以允许播放上未加密的。</span><span class="sxs-lookup"><span data-stu-id="fb722-117">Voicemails are temporarily unencrypted on disk to allow playback.</span></span>  <br/> |<span data-ttu-id="fb722-118">此信息不加密。</span><span class="sxs-lookup"><span data-stu-id="fb722-118">This information is not encrypted.</span></span>  <br/> |
|<span data-ttu-id="fb722-119">**iOS**</span><span class="sxs-lookup"><span data-stu-id="fb722-119">**iOS**</span></span> <br/> |<span data-ttu-id="fb722-120">我们不加密钥匙链中的用户名/密码。</span><span class="sxs-lookup"><span data-stu-id="fb722-120">We DO NOT encrypt the username/password in the keychain.</span></span> <span data-ttu-id="fb722-121">钥匙链加密，但是，在自己计算机上。</span><span class="sxs-lookup"><span data-stu-id="fb722-121">The keychain is encrypted, however, on its own.</span></span>  <br/> |<span data-ttu-id="fb722-122">我们已在应用程序存储中的所有文件使用[NSFileProtectionCompleteUntilFirstUserAuthentication](https://developer.apple.com/reference/foundation/fileprotectiontype/1616633-completeuntilfirstuserauthentica)数据保护标志。</span><span class="sxs-lookup"><span data-stu-id="fb722-122">We are already using [NSFileProtectionCompleteUntilFirstUserAuthentication](https://developer.apple.com/reference/foundation/fileprotectiontype/1616633-completeuntilfirstuserauthentica) data protection flag on all files in the app storage.</span></span> <span data-ttu-id="fb722-123">这意味着用户第一次在设备重新启动后解锁设备之前应用程序存储中的文件将被加密。</span><span class="sxs-lookup"><span data-stu-id="fb722-123">This means that files in the app storage would be encrypted until user unlocks the device for the very first time after the device reboot.</span></span> <br/> |<span data-ttu-id="fb722-124">此信息不加密。</span><span class="sxs-lookup"><span data-stu-id="fb722-124">This information is not encrypted.</span></span>  <br/> |
|<span data-ttu-id="fb722-125">**Windows Phone**</span><span class="sxs-lookup"><span data-stu-id="fb722-125">**Windows Phone**</span></span> <br/> |<span data-ttu-id="fb722-126">Windows Phone 在 Windows 中使用 DPAPI (数据保护 API) 以确保以安全密码。</span><span class="sxs-lookup"><span data-stu-id="fb722-126">Windows Phone uses the DPAPI (Data Protection API) in Windows to secure passwords.</span></span> <span data-ttu-id="fb722-127">我相信所用的加密方案是 AES。</span><span class="sxs-lookup"><span data-stu-id="fb722-127">I believe the encryption scheme used is AES.</span></span> <span data-ttu-id="fb722-128">Windows 不为我们提供选项配置的关键大小 （或方案），使其 DPAPI 所提供的任何内容。</span><span class="sxs-lookup"><span data-stu-id="fb722-128">Windows doesn't give us an option to configure the key size (or scheme), so it's whatever DPAPI gives.</span></span> <span data-ttu-id="fb722-129">它将使用设备 TPM 保护密钥的特定于用户和设备。</span><span class="sxs-lookup"><span data-stu-id="fb722-129">It will use the device TPM to secure keys which are specific to the user and device.</span></span> <span data-ttu-id="fb722-130">请注意 DPAPI 键并不特定于应用程序。</span><span class="sxs-lookup"><span data-stu-id="fb722-130">Note that DPAPI keys are not specific to the app.</span></span>  <br/> |<span data-ttu-id="fb722-131">保护 WP 应用程序数据与[DPAP](https://msdn.microsoft.com/en-us/library/windows/apps/hh487164%28v=vs.105%29.aspx)I like 凭据设置。</span><span class="sxs-lookup"><span data-stu-id="fb722-131">WP App Data is protected with [DPAP](https://msdn.microsoft.com/en-us/library/windows/apps/hh487164%28v=vs.105%29.aspx)I, like the creds.</span></span> <span data-ttu-id="fb722-132">根据我们希望多少详细信息，某些应用程序数据的索引信息都受 (非 DPAPI) AES 加密，以避免盐，以便我们可以无需解密，查找和 DPAPI 反过来受该注册表项。</span><span class="sxs-lookup"><span data-stu-id="fb722-132">Depending on how much detail we want, some of the index information for the App Data is protected by (non-DPAPI) AES encryption to avoid salting, so we can look up without decrypting, and that key is in turn protected with DPAPI.</span></span> <span data-ttu-id="fb722-133">缓存的数据可以读取从同一电话，假定它可以到达我们数据文件夹的任何进程。</span><span class="sxs-lookup"><span data-stu-id="fb722-133">Cached data can be read by any process from the same phone, assuming it can reach our data folder.</span></span> <span data-ttu-id="fb722-134">Windows 加密不保护以下项从沙盒违反、 仅外部访问尝试。</span><span class="sxs-lookup"><span data-stu-id="fb722-134">Windows encryption does not protect from sandbox breach, only external access attempts.</span></span>  <br/> |<span data-ttu-id="fb722-135">此信息不加密。</span><span class="sxs-lookup"><span data-stu-id="fb722-135">This information is not encrypted.</span></span>  <br/> |
   
<span data-ttu-id="fb722-136">**注意：** 请参考[本公共文档](https://docs.microsoft.com/InTune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune)的每个以上的移动平台上可用的设备 pin 实施</span><span class="sxs-lookup"><span data-stu-id="fb722-136">**Note:** Please refer to [this public documentation](https://docs.microsoft.com/InTune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune) for device pin enforcement available on each of the above Mobile platforms</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="fb722-137">相关主题</span><span class="sxs-lookup"><span data-stu-id="fb722-137">Related topics</span></span>
[<span data-ttu-id="fb722-138">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="fb722-138">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="fb722-139">允许 Skype for Business 用户添加 Skype 联系人</span><span class="sxs-lookup"><span data-stu-id="fb722-139">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
