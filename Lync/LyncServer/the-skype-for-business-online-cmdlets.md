---
title: Lync Online Cmdlet
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: The Skype for Business Online cmdlets
ms:assetid: 71f38305-fd8b-4013-83e1-cb742e3174c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362817(v=OCS.15)
ms:contentKeyID: 56558831
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c0d56a85fda6cb4f46991700b6fa428acb1c823
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738734"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="the-skype-for-business-online-cmdlets"></a><span data-ttu-id="42d7c-102">Lync Online Cmdlet</span><span class="sxs-lookup"><span data-stu-id="42d7c-102">The Skype for Business Online cmdlets</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42d7c-103">_**主题上次修改时间：** 2013-07-05_</span><span class="sxs-lookup"><span data-stu-id="42d7c-103">_**Topic Last Modified:** 2013-07-05_</span></span>

<span data-ttu-id="42d7c-104">使用 Windows PowerShell 连接到 Skype for business Online 时，将在内存中将 Skype for business Online cmdlet 的集合复制到计算机。</span><span class="sxs-lookup"><span data-stu-id="42d7c-104">When you connect to Skype for Business Online by using Windows PowerShell, a collection of Skype for Business Online cmdlets is copied, in memory, to your computer.</span></span> <span data-ttu-id="42d7c-105">这些 cmdlet 以及你在本地计算机上已有的任何其他 cmdlet （包括安装 Windows PowerShell 时安装的核心 cmdlet），可用于管理你的 Skype for Business Online 部署和你的 Skype for business Online 部署和你的 Skype for business Online 部署商业联机用户帐户。</span><span class="sxs-lookup"><span data-stu-id="42d7c-105">These cmdlets, in addition to any other cmdlets you already have on your local computer (including the core cmdlets that are installed when you install Windows PowerShell), are then available for managing your Skype for Business Online deployment and your Skype for Business Online user accounts.</span></span> <span data-ttu-id="42d7c-106">Skype for Business Online cmdlet 将在以下主题中引入：</span><span class="sxs-lookup"><span data-stu-id="42d7c-106">The Skype for Business Online cmdlets are introduced in the following topics:</span></span>

  - [<span data-ttu-id="42d7c-107">管理 Lync Online 租户</span><span class="sxs-lookup"><span data-stu-id="42d7c-107">Managing Skype for Business Online tenants</span></span>](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/manage-skype-for-business-online-organizations)

  - [<span data-ttu-id="42d7c-108">在 Skype for Business Online 中管理用户和用户帐户属性</span><span class="sxs-lookup"><span data-stu-id="42d7c-108">Managing users and user account properties in Skype for Business Online</span></span>](https://docs.microsoft.com/skypeforbusiness/manage/user-accounts/user-accounts)

  - [<span data-ttu-id="42d7c-109">在 Skype for Business Online 中管理策略</span><span class="sxs-lookup"><span data-stu-id="42d7c-109">Managing policies in Skype for Business Online</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-policies-with-office-365-powershell)

  - [<span data-ttu-id="42d7c-110">从 Skype for business Online 管理 Skype for business 客户端</span><span class="sxs-lookup"><span data-stu-id="42d7c-110">Managing the Skype for Business client from Skype for Business Online</span></span>](https://docs.microsoft.com/skypeforbusiness/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365)

  - [<span data-ttu-id="42d7c-111">在 Skype for business Online 中管理 Exchange 统一消息和托管语音邮件</span><span class="sxs-lookup"><span data-stu-id="42d7c-111">Managing Exchange Unified Messaging and hosted voice mail in Skype for Business Online</span></span>](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/manage-exchange-unified-messaging-and-hosted-voicemail)

  - [<span data-ttu-id="42d7c-112">管理与外部用户和组织的 Skype for Business Online 中的通信</span><span class="sxs-lookup"><span data-stu-id="42d7c-112">Managing communications in Skype for Business Online with outside users and organizations</span></span>](https://docs.microsoft.com/skypeforbusiness/set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users)

  - [<span data-ttu-id="42d7c-113">管理 Lync Online 会议</span><span class="sxs-lookup"><span data-stu-id="42d7c-113">Managing Skype for Business Online meetings and conferences</span></span>](https://docs.microsoft.com/skypeforbusiness/manage/conferencing/conferencing-policies)

  - [<span data-ttu-id="42d7c-114">在 Skype for Business Online 中管理手机和移动设备</span><span class="sxs-lookup"><span data-stu-id="42d7c-114">Managing cell phones and mobile devices in Skype for Business Online</span></span>](https://docs.microsoft.com/skypeforbusiness/set-up-policies-in-your-organization/set-up-mobile-policies-for-your-organization)

<div>

## <a name="see-also"></a><span data-ttu-id="42d7c-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="42d7c-115">See Also</span></span>


[<span data-ttu-id="42d7c-116">快速参考：使用 Windows PowerShell 执行常见的 Lync Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="42d7c-116">Quick reference: Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

