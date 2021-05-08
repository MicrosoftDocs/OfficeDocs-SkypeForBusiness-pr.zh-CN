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
ms.openlocfilehash: f600230574b8d16a0f7907b4484da8ffcca6124e
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239629"
---
# <a name="skype-for-business-mobile-app-security"></a><span data-ttu-id="609ee-103">Skype for Business 移动应用安全</span><span class="sxs-lookup"><span data-stu-id="609ee-103">Skype for Business mobile app security</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

## <a name="skype-for-business-client-security"></a><span data-ttu-id="609ee-104">Skype for Business 客户端安全性</span><span class="sxs-lookup"><span data-stu-id="609ee-104">Skype for Business Client Security</span></span>

<span data-ttu-id="609ee-105">本文介绍了 Skype for Business 移动应用上的数据加密信息。</span><span class="sxs-lookup"><span data-stu-id="609ee-105">This article covers data encryption information on Skype for Business Mobile Apps.</span></span>
  
|||||
|:-----|:-----|:-----|:-----|
||<span data-ttu-id="609ee-106">**用户名/密码**</span><span class="sxs-lookup"><span data-stu-id="609ee-106">**Username/Password**</span></span> <br/> |<span data-ttu-id="609ee-107">**应用数据 (对话、 <br/> 联系人列表、会议)**</span><span class="sxs-lookup"><span data-stu-id="609ee-107">**App Data (Conversations,<br/> Contact List, Meetings)**</span></span> <br/> |<span data-ttu-id="609ee-108">**诊断日志**</span><span class="sxs-lookup"><span data-stu-id="609ee-108">**Diagnostic logs**</span></span> <br/> |
|<span data-ttu-id="609ee-109">**Android**</span><span class="sxs-lookup"><span data-stu-id="609ee-109">**Android**</span></span> <br/> |<span data-ttu-id="609ee-110">我们将凭据信息存储在 Android 帐户。</span><span class="sxs-lookup"><span data-stu-id="609ee-110">We store credentials information in Android Accounts.</span></span> <span data-ttu-id="609ee-111">我们还在将凭据保存到"帐户"之前对其进行加密。</span><span class="sxs-lookup"><span data-stu-id="609ee-111">We also encrypt credentials before saving them into Accounts.</span></span> <span data-ttu-id="609ee-112">我们使用 **"AES/CBC/PKCS5Padding"** 算法进行加密。</span><span class="sxs-lookup"><span data-stu-id="609ee-112">We use " **AES/CBC/PKCS5Padding** " algorithm for encryption.</span></span> <br/> |<span data-ttu-id="609ee-113">我们使用名为[sqlcipher](https://www.zetetic.net/sqlcipher/design/)的库SQL加密的加密数据库。</span><span class="sxs-lookup"><span data-stu-id="609ee-113">We store in an encrypted SQL database using a library called [sqlcipher](https://www.zetetic.net/sqlcipher/design/).</span></span> <span data-ttu-id="609ee-114">我们在 CBC 模式下使用 256 位 AES 的默认算法。</span><span class="sxs-lookup"><span data-stu-id="609ee-114">We use their default algorithm of 256-bit AES in CBC mode.</span></span> <span data-ttu-id="609ee-115">其余数据始终在数据库文件中加密，并且仅在应用的易失性内存和调用堆栈内传输时未加密。</span><span class="sxs-lookup"><span data-stu-id="609ee-115">The data at rest is always encrypted in the database file and is only unencrypted in transit inside of the app's volatile memory and call stacks.</span></span> <span data-ttu-id="609ee-116">我们还使用与用户名称和密码加密相同的方法加密语音邮件 (它们不会存储在 DB) 。</span><span class="sxs-lookup"><span data-stu-id="609ee-116">We also encrypt voicemail files using the same method as the user's name and password encryption (they are not stored in the DB).</span></span> <span data-ttu-id="609ee-117">语音邮件在磁盘上暂时未加密，以便播放。</span><span class="sxs-lookup"><span data-stu-id="609ee-117">Voicemails are temporarily unencrypted on disk to allow playback.</span></span>  <br/> |<span data-ttu-id="609ee-118">此信息未加密。</span><span class="sxs-lookup"><span data-stu-id="609ee-118">This information is not encrypted.</span></span>  <br/> |
|<span data-ttu-id="609ee-119">**iOS**</span><span class="sxs-lookup"><span data-stu-id="609ee-119">**iOS**</span></span> <br/> |<span data-ttu-id="609ee-120">我们不加密密钥链中的用户名/密码。</span><span class="sxs-lookup"><span data-stu-id="609ee-120">We DO NOT encrypt the username/password in the keychain.</span></span> <span data-ttu-id="609ee-121">但是，密钥链是自行加密的。</span><span class="sxs-lookup"><span data-stu-id="609ee-121">The keychain is encrypted, however, on its own.</span></span>  <br/> |<span data-ttu-id="609ee-122">我们已对应用存储中所有文件使用 [NSFileProtectionCompleteUntilFirstUserAuthentication](https://developer.apple.com/reference/foundation/fileprotectiontype/1616633-completeuntilfirstuserauthentica) 数据保护标志。</span><span class="sxs-lookup"><span data-stu-id="609ee-122">We are already using [NSFileProtectionCompleteUntilFirstUserAuthentication](https://developer.apple.com/reference/foundation/fileprotectiontype/1616633-completeuntilfirstuserauthentica) data protection flag on all files in the app storage.</span></span> <span data-ttu-id="609ee-123">这意味着，应用存储中的文件将加密，直到用户在设备重新启动后首次解锁设备。</span><span class="sxs-lookup"><span data-stu-id="609ee-123">This means that files in the app storage would be encrypted until user unlocks the device for the very first time after the device reboot.</span></span> <br/> |<span data-ttu-id="609ee-124">此信息未加密。</span><span class="sxs-lookup"><span data-stu-id="609ee-124">This information is not encrypted.</span></span>  <br/> |
|<span data-ttu-id="609ee-125">**Windows Phone**</span><span class="sxs-lookup"><span data-stu-id="609ee-125">**Windows Phone**</span></span> <br/> |<span data-ttu-id="609ee-126">Windows Phone DPAPI (Data Protection API) Windows保护密码。</span><span class="sxs-lookup"><span data-stu-id="609ee-126">Windows Phone uses the DPAPI (Data Protection API) in Windows to secure passwords.</span></span> <span data-ttu-id="609ee-127">我认为使用的加密方案是 AES。</span><span class="sxs-lookup"><span data-stu-id="609ee-127">I believe the encryption scheme used is AES.</span></span> <span data-ttu-id="609ee-128">Windows未提供配置密钥大小的选项， (或方案) ，因此 DPAPI 提供的任何功能都一样。</span><span class="sxs-lookup"><span data-stu-id="609ee-128">Windows doesn't give us an option to configure the key size (or scheme), so it's whatever DPAPI gives.</span></span> <span data-ttu-id="609ee-129">它将使用设备 TPM 保护特定于用户和设备的密钥。</span><span class="sxs-lookup"><span data-stu-id="609ee-129">It will use the device TPM to secure keys which are specific to the user and device.</span></span> <span data-ttu-id="609ee-130">请注意，DPAPI 密钥不特定于应用。</span><span class="sxs-lookup"><span data-stu-id="609ee-130">Note that DPAPI keys are not specific to the app.</span></span>  <br/> |<span data-ttu-id="609ee-131">WP 应用数据受 [DPAP](/previous-versions/windows/apps/hh487164(v=vs.105))I 保护，如 creds。</span><span class="sxs-lookup"><span data-stu-id="609ee-131">WP App Data is protected with [DPAP](/previous-versions/windows/apps/hh487164(v=vs.105))I, like the creds.</span></span> <span data-ttu-id="609ee-132">根据我们需要的详细信息，应用数据的一些索引信息受 (非 DPAPI) AES 加密的保护，以避免加盐，因此我们可以在不解密的情况下进行查找，并且该密钥反过来受 DPAPI 的保护。</span><span class="sxs-lookup"><span data-stu-id="609ee-132">Depending on how much detail we want, some of the index information for the App Data is protected by (non-DPAPI) AES encryption to avoid salting, so we can look up without decrypting, and that key is in turn protected with DPAPI.</span></span> <span data-ttu-id="609ee-133">任何进程都可以从同一手机读取缓存的数据，假设它可以到达数据文件夹。</span><span class="sxs-lookup"><span data-stu-id="609ee-133">Cached data can be read by any process from the same phone, assuming it can reach our data folder.</span></span> <span data-ttu-id="609ee-134">Windows加密不能防止沙盒泄露，只能防止外部访问尝试。</span><span class="sxs-lookup"><span data-stu-id="609ee-134">Windows encryption does not protect from sandbox breach, only external access attempts.</span></span>  <br/> |<span data-ttu-id="609ee-135">此信息未加密。</span><span class="sxs-lookup"><span data-stu-id="609ee-135">This information is not encrypted.</span></span>  <br/> |
   
<span data-ttu-id="609ee-136">**注意：** 请参阅此 [公共文档，](/InTune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune) 了解上述每个移动平台上可用的设备 PIN 强制措施</span><span class="sxs-lookup"><span data-stu-id="609ee-136">**Note:** Please refer to [this public documentation](/InTune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune) for device pin enforcement available on each of the above Mobile platforms</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="609ee-137">相关主题</span><span class="sxs-lookup"><span data-stu-id="609ee-137">Related topics</span></span>
[<span data-ttu-id="609ee-138">设置 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="609ee-138">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="609ee-139">允许 Skype for Business 用户添加 Skype 联系人</span><span class="sxs-lookup"><span data-stu-id="609ee-139">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
