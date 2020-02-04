---
title: 配置 XMPP 网关访问策略和证书
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure XMPP gateway access policies and certificates
ms:assetid: cd91433e-6dfb-4553-8316-c1086b394221
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721885(v=OCS.15)
ms:contentKeyID: 49733819
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f3f1aabeeb49ecc413107d5cd346f310c0d2d294
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723202"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a><span data-ttu-id="b6f3a-102">配置 XMPP 网关访问策略和证书</span><span class="sxs-lookup"><span data-stu-id="b6f3a-102">Configure XMPP gateway access policies and certificates</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b6f3a-103">_**主题上次修改时间：** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="b6f3a-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="b6f3a-104">XMPP 联合身份验证基于可扩展消息和状态协议（XMPP）定义外部部署。</span><span class="sxs-lookup"><span data-stu-id="b6f3a-104">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol (XMPP).</span></span> <span data-ttu-id="b6f3a-105">XMPP 配置允许 Lync 用户通过以下方式访问 XMPP 域用户：</span><span class="sxs-lookup"><span data-stu-id="b6f3a-105">An XMPP configuration allows Lync users access to XMPP domain users by:</span></span>

  - <span data-ttu-id="b6f3a-106">IM 和状态-仅限人员</span><span class="sxs-lookup"><span data-stu-id="b6f3a-106">IM and Presence – person to person only</span></span>

  - <span data-ttu-id="b6f3a-107">在 Lync 客户端中创建 XMPP 联盟联系人</span><span class="sxs-lookup"><span data-stu-id="b6f3a-107">Creation of XMPP federated contacts in the Lync client</span></span>

<span data-ttu-id="b6f3a-108">当您为支持可扩展消息和状态协议（XMPP）联盟伙伴的策略配置策略时，这些策略适用于 XMPP 联盟域的用户，但不适用于会话初始协议（SIP）的用户（IM）服务提供商（例如，Windows Live）或 SIP 联盟域。</span><span class="sxs-lookup"><span data-stu-id="b6f3a-108">When you configure policies for support of extensible messaging and presence protocol (XMPP) federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers (for example, Windows Live), or SIP federated domains.</span></span> <span data-ttu-id="b6f3a-109">为你希望允许用户添加联系人并与之通信的每个 XMPP 联盟域配置 XMPP 联盟合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="b6f3a-109">You configure an XMPP Federated Partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="b6f3a-110">策略准备好后，您需要配置 XMPP 网关证书。</span><span class="sxs-lookup"><span data-stu-id="b6f3a-110">Once the policies are in place, you need to configure the XMPP Gateway certificates.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b6f3a-111">若要开始 XMPP 网关迁移，你需要部署 Lync Server 2013 XMPP 网关，并配置访问策略以启用 Lync Server 2013 XMPP 网关的用户。</span><span class="sxs-lookup"><span data-stu-id="b6f3a-111">To begin the XMPP Gateway migration, you need to deploy the Lync Server 2013 XMPP Gateway, and configure access policies to enable users for Lync Server 2013 XMPP Gateway.</span></span> <span data-ttu-id="b6f3a-112">在执行这些步骤之前，必须将所有用户移到 Lync Server 2013 部署。</span><span class="sxs-lookup"><span data-stu-id="b6f3a-112">All users must be moved to the Lync Server 2013 deployment before you perform these steps.</span></span> <span data-ttu-id="b6f3a-113">有关详细信息，请参阅<A href="configure-xmpp-gateway-on-lync-server-2013_1.md">在 Lync Server 2013 上配置 XMPP 网关</A>。</span><span class="sxs-lookup"><span data-stu-id="b6f3a-113">For details, see <A href="configure-xmpp-gateway-on-lync-server-2013_1.md">Configure XMPP gateway on Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="configure-an-external-access-policy-to-enable-users-for-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="b6f3a-114">将外部访问策略配置为启用 Lync Server 2013 XMPP 网关的用户</span><span class="sxs-lookup"><span data-stu-id="b6f3a-114">Configure an External Access Policy to Enable Users for Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="b6f3a-115">打开“Lync Server 控制面板”。</span><span class="sxs-lookup"><span data-stu-id="b6f3a-115">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="b6f3a-116">在左侧导航栏中，单击 "**联盟和外部访问**"，然后单击 "**外部访问策略**"。</span><span class="sxs-lookup"><span data-stu-id="b6f3a-116">In the left navigation bar, click **Federation and External Access**, and then click **External Access Policy**.</span></span>

3.  <span data-ttu-id="b6f3a-117">单击 "**新建**"，然后单击 "**用户策略**"。</span><span class="sxs-lookup"><span data-stu-id="b6f3a-117">Click **New** and then click **User policy**.</span></span>

4.  <span data-ttu-id="b6f3a-118">输入外部 access 用户策略的名称。</span><span class="sxs-lookup"><span data-stu-id="b6f3a-118">Enter a name for the external access user policy.</span></span>

5.  <span data-ttu-id="b6f3a-119">提供外部 access 用户策略的说明。</span><span class="sxs-lookup"><span data-stu-id="b6f3a-119">Provide a description for external access user policy.</span></span>

6.  <span data-ttu-id="b6f3a-120">选择 "**启用与联盟用户的通信**"。</span><span class="sxs-lookup"><span data-stu-id="b6f3a-120">Select **Enable communications with federated users**.</span></span>

7.  <span data-ttu-id="b6f3a-121">选择 "**启用与 XMPP 联盟用户的通信**"。</span><span class="sxs-lookup"><span data-stu-id="b6f3a-121">Select **Enable communications with XMPP federated users**.</span></span>

8.  <span data-ttu-id="b6f3a-122">单击 "**提交**" 将更改保存到 "网站" 或 "用户策略"。</span><span class="sxs-lookup"><span data-stu-id="b6f3a-122">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

