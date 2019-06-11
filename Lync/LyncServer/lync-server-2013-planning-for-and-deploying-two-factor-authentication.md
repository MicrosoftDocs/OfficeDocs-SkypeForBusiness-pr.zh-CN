---
title: 'Lync Server 2013: 规划和部署双因素身份验证'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for and deploying two-factor authentication
ms:assetid: 442a88df-ebc2-4335-9c59-0ce1adc1471e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308563(v=OCS.15)
ms:contentKeyID: 54973686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c902a3abd0035cbffa5bb10ed05cad6fa7bcc6b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825091"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="two-factor-authentication-in-lync-server-2013"></a><span data-ttu-id="7f53f-102">Lync Server 2013 中的双重身份验证</span><span class="sxs-lookup"><span data-stu-id="7f53f-102">Two-factor authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f53f-103">_**主题上次修改时间:** 2013-07-11_</span><span class="sxs-lookup"><span data-stu-id="7f53f-103">_**Topic Last Modified:** 2013-07-11_</span></span>

<span data-ttu-id="7f53f-104">双因素身份验证通过要求用户满足两个身份验证条件来提供改进的安全性: 用户名/密码组合和令牌或证书。</span><span class="sxs-lookup"><span data-stu-id="7f53f-104">Two-factor authentication provides improved security by requiring users to meet two authentication criteria: a user name/password combination and a token or certificate.</span></span> <span data-ttu-id="7f53f-105">这也称为“所有之物，所知之事”。</span><span class="sxs-lookup"><span data-stu-id="7f53f-105">This is also known as “something you have, something you know.”</span></span> <span data-ttu-id="7f53f-106">使用证书进行双重身份验证的一个典型示例是使用智能卡。</span><span class="sxs-lookup"><span data-stu-id="7f53f-106">A typical example of two-factor authentication with a certificate is the use of smart cards.</span></span> <span data-ttu-id="7f53f-107">智能卡包含与用户帐户相关联的证书，可对照服务器上存储的用户和证书信息进行验证。</span><span class="sxs-lookup"><span data-stu-id="7f53f-107">A smart card contains a certificate associated with the user account, and can be validated against user and certificate information stored on a server.</span></span> <span data-ttu-id="7f53f-108">通过将用户信息（用户名和密码）与提供的证书进行比较，服务器将验证凭据并验证用户身份。</span><span class="sxs-lookup"><span data-stu-id="7f53f-108">By comparing the user information (user name and password) to the certificate provided, the server validates the credentials and authenticates the user.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7f53f-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="7f53f-109">In This Section</span></span>

[<span data-ttu-id="7f53f-110">在 Lync Server 2013 中规划双因素身份验证</span><span class="sxs-lookup"><span data-stu-id="7f53f-110">Planning for two-factor authentication in Lync Server 2013</span></span>](lync-server-2013-planning-for-two-factor-authentication.md)

[<span data-ttu-id="7f53f-111">在 Lync Server 2013 中配置双因素身份验证</span><span class="sxs-lookup"><span data-stu-id="7f53f-111">Configuring two-factor authentication in Lync Server 2013</span></span>](lync-server-2013-configuring-two-factor-authentication.md)

[<span data-ttu-id="7f53f-112">将双因素身份验证与 Lync 客户端和 Lync Server 2013 结合使用</span><span class="sxs-lookup"><span data-stu-id="7f53f-112">Using two-factor authentication with Lync client and Lync Server 2013</span></span>](lync-server-2013-using-two-factor-authentication-with-lync-client.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

