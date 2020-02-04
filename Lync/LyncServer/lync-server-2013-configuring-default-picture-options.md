---
title: Lync Server 2013：配置默认图片选项
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring default picture options
ms:assetid: b1c986f0-6400-447a-9e36-78c1c3a4f793
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn205074(v=OCS.15)
ms:contentKeyID: 56280893
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e551d069da9a3afb7a884c28096dd97ab3702539
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758146"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-default-picture-options-in-lync-server-2013"></a><span data-ttu-id="33a67-102">在 Lync Server 2013 中配置默认图片选项</span><span class="sxs-lookup"><span data-stu-id="33a67-102">Configuring default picture options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="33a67-103">_**主题上次修改时间：** 2013-03-22_</span><span class="sxs-lookup"><span data-stu-id="33a67-103">_**Topic Last Modified:** 2013-03-22_</span></span>

<span data-ttu-id="33a67-104">默认情况下，将自动显示用户的图片。</span><span class="sxs-lookup"><span data-stu-id="33a67-104">By default, users’ pictures are automatically displayed.</span></span> <span data-ttu-id="33a67-105">如果用户想要隐藏其图片，可以在 Lync 客户端中选择 "**隐藏我的图片**" 选项。</span><span class="sxs-lookup"><span data-stu-id="33a67-105">If users want to hide their pictures, they can select the **Hide my picture** option in the Lync client.</span></span> <span data-ttu-id="33a67-106">但是，其他一些 Office 应用程序将忽略此设置。</span><span class="sxs-lookup"><span data-stu-id="33a67-106">However, this setting is ignored by some other Office applications.</span></span>

<span data-ttu-id="33a67-107">如果在用户关闭图片时也可能显示图片，则可以为网站或服务更改 Lync 图片显示设置，以便默认情况下不显示用户的图片。</span><span class="sxs-lookup"><span data-stu-id="33a67-107">If the possibility of displaying pictures even when turned off by the user is a concern, you can change Lync picture display settings globally or for a site or service so that users’ pictures are not shown by default.</span></span> <span data-ttu-id="33a67-108">使用以下 Lync Server Management Shell cmdlet，以便用户的图片在客户端中明确选择 "**显示我的图片**" 选项，否则不会显示。</span><span class="sxs-lookup"><span data-stu-id="33a67-108">Use the following Lync Server Management Shell cmdlet so that user’s pictures will not be shown unless they explicitly select the **Show my picture** option in the client:</span></span>

    Set-CsPrivacyConfiguration -DisplayPublishedPhotoDefault $False

<span data-ttu-id="33a67-109">有关此 cmdlet 的详细信息，请参阅 Lync Server Management Shell 文档中的 "[设置 CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration) "。</span><span class="sxs-lookup"><span data-stu-id="33a67-109">For more information about this cmdlet, see the [Set-CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration) in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

