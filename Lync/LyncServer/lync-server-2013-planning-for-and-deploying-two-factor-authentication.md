---
title: Lync Server 2013：规划和部署双因素身份验证
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for and deploying two-factor authentication
ms:assetid: 442a88df-ebc2-4335-9c59-0ce1adc1471e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308563(v=OCS.15)
ms:contentKeyID: 54973686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0043e99e01c8d0c7b16036ed7824aa7cdd7faad1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526549"
---
# <a name="two-factor-authentication-in-lync-server-2013"></a><span data-ttu-id="78e74-102">Lync Server 2013 中的双重身份验证</span><span class="sxs-lookup"><span data-stu-id="78e74-102">Two-factor authentication in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78e74-103">_**上次修改的主题：** 2013-07-11_</span><span class="sxs-lookup"><span data-stu-id="78e74-103">_**Topic Last Modified:** 2013-07-11_</span></span>

<span data-ttu-id="78e74-104">双重身份验证通过要求用户满足两个身份验证条件来提供改进的安全性：用户名/密码组合和令牌或证书。</span><span class="sxs-lookup"><span data-stu-id="78e74-104">Two-factor authentication provides improved security by requiring users to meet two authentication criteria: a user name/password combination and a token or certificate.</span></span> <span data-ttu-id="78e74-105">这也称为 "您拥有的内容，您知道的东西"。</span><span class="sxs-lookup"><span data-stu-id="78e74-105">This is also known as “something you have, something you know.”</span></span> <span data-ttu-id="78e74-106">使用证书进行双重身份验证的典型示例是使用智能卡。</span><span class="sxs-lookup"><span data-stu-id="78e74-106">A typical example of two-factor authentication with a certificate is the use of smart cards.</span></span> <span data-ttu-id="78e74-107">智能卡包含与用户帐户关联的证书，并且可以根据存储在服务器上的用户和证书信息对其进行验证。</span><span class="sxs-lookup"><span data-stu-id="78e74-107">A smart card contains a certificate associated with the user account, and can be validated against user and certificate information stored on a server.</span></span> <span data-ttu-id="78e74-108">通过将 (用户名和密码) 的用户信息与所提供的证书进行比较，服务器将验证凭据并对用户进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="78e74-108">By comparing the user information (user name and password) to the certificate provided, the server validates the credentials and authenticates the user.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="78e74-109">本部分内容</span><span class="sxs-lookup"><span data-stu-id="78e74-109">In This Section</span></span>

[<span data-ttu-id="78e74-110">在 Lync Server 2013 中规划双因素身份验证</span><span class="sxs-lookup"><span data-stu-id="78e74-110">Planning for two-factor authentication in Lync Server 2013</span></span>](lync-server-2013-planning-for-two-factor-authentication.md)

[<span data-ttu-id="78e74-111">在 Lync Server 2013 中配置双重身份验证</span><span class="sxs-lookup"><span data-stu-id="78e74-111">Configuring two-factor authentication in Lync Server 2013</span></span>](lync-server-2013-configuring-two-factor-authentication.md)

[<span data-ttu-id="78e74-112">对 Lync 客户端和 Lync Server 2013 使用双重身份验证</span><span class="sxs-lookup"><span data-stu-id="78e74-112">Using two-factor authentication with Lync client and Lync Server 2013</span></span>](lync-server-2013-using-two-factor-authentication-with-lync-client.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

