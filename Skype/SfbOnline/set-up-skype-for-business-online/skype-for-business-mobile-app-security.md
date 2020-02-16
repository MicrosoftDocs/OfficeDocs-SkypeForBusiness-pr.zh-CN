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
description: '了解如何为你的用户设置移动应用安全性。 '
ms.openlocfilehash: 2c22f384196f0f05ca89d6f0e07ae84a1548d78a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42010775"
---
# <a name="skype-for-business-mobile-app-security"></a><span data-ttu-id="49e34-103">Skype for Business 移动应用安全</span><span class="sxs-lookup"><span data-stu-id="49e34-103">Skype for Business mobile app security</span></span>

## <a name="skype-for-business-client-security"></a><span data-ttu-id="49e34-104">Skype for Business 客户端安全性</span><span class="sxs-lookup"><span data-stu-id="49e34-104">Skype for Business Client Security</span></span>

<span data-ttu-id="49e34-105">本文介绍了 Skype for Business 移动应用上的数据加密信息。</span><span class="sxs-lookup"><span data-stu-id="49e34-105">This article covers data encryption information on Skype for Business Mobile Apps.</span></span>
  
|||||
|:-----|:-----|:-----|:-----|
||<span data-ttu-id="49e34-106">**用户名/密码**</span><span class="sxs-lookup"><span data-stu-id="49e34-106">**Username/Password**</span></span> <br/> |<span data-ttu-id="49e34-107">**应用数据（对话、<br/>联系人列表、会议）**</span><span class="sxs-lookup"><span data-stu-id="49e34-107">**App Data (Conversations,<br/> Contact List, Meetings)**</span></span> <br/> |<span data-ttu-id="49e34-108">**诊断日志**</span><span class="sxs-lookup"><span data-stu-id="49e34-108">**Diagnostic logs**</span></span> <br/> |
|<span data-ttu-id="49e34-109">**Android**</span><span class="sxs-lookup"><span data-stu-id="49e34-109">**Android**</span></span> <br/> |<span data-ttu-id="49e34-110">我们将凭据信息存储在 Android 帐户中。</span><span class="sxs-lookup"><span data-stu-id="49e34-110">We store credentials information in Android Accounts.</span></span> <span data-ttu-id="49e34-111">我们还会在将凭据保存到帐户之前对其进行加密。</span><span class="sxs-lookup"><span data-stu-id="49e34-111">We also encrypt credentials before saving them into Accounts.</span></span> <span data-ttu-id="49e34-112">我们使用 " **AES/CBC/PKCS5Padding** " 算法进行加密。</span><span class="sxs-lookup"><span data-stu-id="49e34-112">We use " **AES/CBC/PKCS5Padding** " algorithm for encryption.</span></span> <br/> |<span data-ttu-id="49e34-113">我们使用名为[sqlcipher](https://www.zetetic.net/sqlcipher/design/)的库存储在加密的 SQL 数据库中。</span><span class="sxs-lookup"><span data-stu-id="49e34-113">We store in an encrypted SQL database using a library called [sqlcipher](https://www.zetetic.net/sqlcipher/design/).</span></span> <span data-ttu-id="49e34-114">我们在 CBC 模式下使用的是256位 AES 的默认算法。</span><span class="sxs-lookup"><span data-stu-id="49e34-114">We use their default algorithm of 256-bit AES in CBC mode.</span></span> <span data-ttu-id="49e34-115">Rest 上的数据始终在数据库文件中加密，并且仅在应用的易失性内存和调用堆栈内部传输时才被加密。</span><span class="sxs-lookup"><span data-stu-id="49e34-115">The data at rest is always encrypted in the database file and is only unencrypted in transit inside of the app's volatile memory and call stacks.</span></span> <span data-ttu-id="49e34-116">我们还使用与用户的用户名和密码加密相同的方法加密语音邮件文件（它们不存储在数据库中）。</span><span class="sxs-lookup"><span data-stu-id="49e34-116">We also encrypt voicemail files using the same method as the user's name and password encryption (they are not stored in the DB).</span></span> <span data-ttu-id="49e34-117">语音邮件在磁盘上暂时未加密以允许播放。</span><span class="sxs-lookup"><span data-stu-id="49e34-117">Voicemails are temporarily unencrypted on disk to allow playback.</span></span>  <br/> |<span data-ttu-id="49e34-118">此信息不加密。</span><span class="sxs-lookup"><span data-stu-id="49e34-118">This information is not encrypted.</span></span>  <br/> |
|<span data-ttu-id="49e34-119">**iOS**</span><span class="sxs-lookup"><span data-stu-id="49e34-119">**iOS**</span></span> <br/> |<span data-ttu-id="49e34-120">我们不会在密钥链中加密用户名/密码。</span><span class="sxs-lookup"><span data-stu-id="49e34-120">We DO NOT encrypt the username/password in the keychain.</span></span> <span data-ttu-id="49e34-121">但是，密钥链是加密的。</span><span class="sxs-lookup"><span data-stu-id="49e34-121">The keychain is encrypted, however, on its own.</span></span>  <br/> |<span data-ttu-id="49e34-122">我们已在应用存储中的所有文件上使用[NSFileProtectionCompleteUntilFirstUserAuthentication](https://developer.apple.com/reference/foundation/fileprotectiontype/1616633-completeuntilfirstuserauthentica)数据保护标志。</span><span class="sxs-lookup"><span data-stu-id="49e34-122">We are already using [NSFileProtectionCompleteUntilFirstUserAuthentication](https://developer.apple.com/reference/foundation/fileprotectiontype/1616633-completeuntilfirstuserauthentica) data protection flag on all files in the app storage.</span></span> <span data-ttu-id="49e34-123">这意味着应用存储中的文件将被加密，直到用户在设备重启后首次解锁设备时。</span><span class="sxs-lookup"><span data-stu-id="49e34-123">This means that files in the app storage would be encrypted until user unlocks the device for the very first time after the device reboot.</span></span> <br/> |<span data-ttu-id="49e34-124">此信息不加密。</span><span class="sxs-lookup"><span data-stu-id="49e34-124">This information is not encrypted.</span></span>  <br/> |
|<span data-ttu-id="49e34-125">**Windows Phone**</span><span class="sxs-lookup"><span data-stu-id="49e34-125">**Windows Phone**</span></span> <br/> |<span data-ttu-id="49e34-126">Windows Phone 使用 Windows 中的 DPAPI （数据保护 API）来保护密码。</span><span class="sxs-lookup"><span data-stu-id="49e34-126">Windows Phone uses the DPAPI (Data Protection API) in Windows to secure passwords.</span></span> <span data-ttu-id="49e34-127">我相信使用的加密方案是 AES。</span><span class="sxs-lookup"><span data-stu-id="49e34-127">I believe the encryption scheme used is AES.</span></span> <span data-ttu-id="49e34-128">Windows 无法为我们提供配置密钥大小（或方案）的选项，因此它就是 DPAPI 提供的任何内容。</span><span class="sxs-lookup"><span data-stu-id="49e34-128">Windows doesn't give us an option to configure the key size (or scheme), so it's whatever DPAPI gives.</span></span> <span data-ttu-id="49e34-129">它将使用设备 TPM 保护特定于用户和设备的密钥。</span><span class="sxs-lookup"><span data-stu-id="49e34-129">It will use the device TPM to secure keys which are specific to the user and device.</span></span> <span data-ttu-id="49e34-130">请注意，DPAPI 密钥并非特定于该应用。</span><span class="sxs-lookup"><span data-stu-id="49e34-130">Note that DPAPI keys are not specific to the app.</span></span>  <br/> |<span data-ttu-id="49e34-131">WP 应用数据通过[DPAP](https://msdn.microsoft.com/library/windows/apps/hh487164%28v=vs.105%29.aspx)I （如凭据）进行保护。</span><span class="sxs-lookup"><span data-stu-id="49e34-131">WP App Data is protected with [DPAP](https://msdn.microsoft.com/library/windows/apps/hh487164%28v=vs.105%29.aspx)I, like the creds.</span></span> <span data-ttu-id="49e34-132">根据所需的详细信息量，应用数据的一些索引信息受（非 DPAPI） AES 加密的保护，以避免 salting，因此我们可以查找而不进行解密，并且该密钥又受 DPAPI 保护。</span><span class="sxs-lookup"><span data-stu-id="49e34-132">Depending on how much detail we want, some of the index information for the App Data is protected by (non-DPAPI) AES encryption to avoid salting, so we can look up without decrypting, and that key is in turn protected with DPAPI.</span></span> <span data-ttu-id="49e34-133">可以通过同一电话中的任何进程读取缓存的数据，假定它可以访问我们的数据文件夹。</span><span class="sxs-lookup"><span data-stu-id="49e34-133">Cached data can be read by any process from the same phone, assuming it can reach our data folder.</span></span> <span data-ttu-id="49e34-134">Windows 加密不会防止受到沙盒破坏，仅限于外部访问尝试。</span><span class="sxs-lookup"><span data-stu-id="49e34-134">Windows encryption does not protect from sandbox breach, only external access attempts.</span></span>  <br/> |<span data-ttu-id="49e34-135">此信息不加密。</span><span class="sxs-lookup"><span data-stu-id="49e34-135">This information is not encrypted.</span></span>  <br/> |
   
<span data-ttu-id="49e34-136">**注意：** 请参阅[此公共文档](https://docs.microsoft.com/InTune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune)，了解上述每个移动平台上的可用设备 pin 实施情况</span><span class="sxs-lookup"><span data-stu-id="49e34-136">**Note:** Please refer to [this public documentation](https://docs.microsoft.com/InTune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune) for device pin enforcement available on each of the above Mobile platforms</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="49e34-137">相关主题</span><span class="sxs-lookup"><span data-stu-id="49e34-137">Related topics</span></span>
[<span data-ttu-id="49e34-138">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="49e34-138">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="49e34-139">允许 Skype for Business 用户添加 Skype 联系人</span><span class="sxs-lookup"><span data-stu-id="49e34-139">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
