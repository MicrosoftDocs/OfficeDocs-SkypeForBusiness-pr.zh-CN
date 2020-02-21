---
title: Skype for Business Online cmdlet
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
ms.openlocfilehash: 02365bfeeed60a22ea467091ebb0f2c92b0fa3c2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189185"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="the-skype-for-business-online-cmdlets"></a><span data-ttu-id="1409a-102">Skype for Business Online cmdlet</span><span class="sxs-lookup"><span data-stu-id="1409a-102">The Skype for Business Online cmdlets</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1409a-103">_**上次修改的主题：** 2013-07-05_</span><span class="sxs-lookup"><span data-stu-id="1409a-103">_**Topic Last Modified:** 2013-07-05_</span></span>

<span data-ttu-id="1409a-104">当您使用 Windows PowerShell 连接到 Skype for business Online 时，会将 Skype for business Online cmdlet 的集合复制到计算机上的内存中。</span><span class="sxs-lookup"><span data-stu-id="1409a-104">When you connect to Skype for Business Online by using Windows PowerShell, a collection of Skype for Business Online cmdlets is copied, in memory, to your computer.</span></span> <span data-ttu-id="1409a-105">这些 cmdlet 以及在本地计算机上已有的任何其他 cmdlet （包括安装 Windows PowerShell 时安装的核心 cmdlet），可用于管理 Skype for Business Online 部署和 Skype for business Online商业联机用户帐户。</span><span class="sxs-lookup"><span data-stu-id="1409a-105">These cmdlets, in addition to any other cmdlets you already have on your local computer (including the core cmdlets that are installed when you install Windows PowerShell), are then available for managing your Skype for Business Online deployment and your Skype for Business Online user accounts.</span></span> <span data-ttu-id="1409a-106">Skype for Business Online cmdlet 将在以下主题中引入：</span><span class="sxs-lookup"><span data-stu-id="1409a-106">The Skype for Business Online cmdlets are introduced in the following topics:</span></span>

  - [<span data-ttu-id="1409a-107">管理 Skype for Business Online 租户</span><span class="sxs-lookup"><span data-stu-id="1409a-107">Managing Skype for Business Online tenants</span></span>](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/manage-skype-for-business-online-organizations)

  - [<span data-ttu-id="1409a-108">在 Skype for Business Online 中管理用户和用户帐户属性</span><span class="sxs-lookup"><span data-stu-id="1409a-108">Managing users and user account properties in Skype for Business Online</span></span>](https://docs.microsoft.com/skypeforbusiness/manage/user-accounts/user-accounts)

  - [<span data-ttu-id="1409a-109">管理 Skype for Business Online 中的策略</span><span class="sxs-lookup"><span data-stu-id="1409a-109">Managing policies in Skype for Business Online</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-policies-with-office-365-powershell)

  - [<span data-ttu-id="1409a-110">从 Skype for business Online 管理 Skype for business 客户端</span><span class="sxs-lookup"><span data-stu-id="1409a-110">Managing the Skype for Business client from Skype for Business Online</span></span>](https://docs.microsoft.com/skypeforbusiness/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365)

  - [<span data-ttu-id="1409a-111">在 Skype for Business Online 中管理 Exchange 统一消息和托管语音邮件</span><span class="sxs-lookup"><span data-stu-id="1409a-111">Managing Exchange Unified Messaging and hosted voice mail in Skype for Business Online</span></span>](https://docs.microsoft.com/skypeforbusiness/set-up-your-computer-for-windows-powershell/manage-exchange-unified-messaging-and-hosted-voicemail)

  - [<span data-ttu-id="1409a-112">管理外部用户和组织在 Skype for business Online 中的通信</span><span class="sxs-lookup"><span data-stu-id="1409a-112">Managing communications in Skype for Business Online with outside users and organizations</span></span>](https://docs.microsoft.com/skypeforbusiness/set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users)

  - [<span data-ttu-id="1409a-113">管理 Skype for Business Online 会议和会议</span><span class="sxs-lookup"><span data-stu-id="1409a-113">Managing Skype for Business Online meetings and conferences</span></span>](https://docs.microsoft.com/skypeforbusiness/manage/conferencing/conferencing-policies)

  - [<span data-ttu-id="1409a-114">在 Skype for Business Online 中管理手机和移动设备</span><span class="sxs-lookup"><span data-stu-id="1409a-114">Managing cell phones and mobile devices in Skype for Business Online</span></span>](https://docs.microsoft.com/skypeforbusiness/set-up-policies-in-your-organization/set-up-mobile-policies-for-your-organization)

<div>

## <a name="see-also"></a><span data-ttu-id="1409a-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1409a-115">See Also</span></span>


[<span data-ttu-id="1409a-116">快速参考：使用 Windows PowerShell 执行常见的 Skype for Business Online 管理任务</span><span class="sxs-lookup"><span data-stu-id="1409a-116">Quick reference: Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

