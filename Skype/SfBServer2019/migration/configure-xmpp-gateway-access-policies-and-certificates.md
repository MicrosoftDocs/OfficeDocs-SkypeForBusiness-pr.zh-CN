---
title: 配置 XMPP 网关访问策略和证书
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: XMPP 联盟可根据可扩展消息传递和状态协议 (XMPP) 定义外部部署。 通过 XMPP 配置，用户可以通过以下方式访问 XMPP 域用户：
ms.openlocfilehash: f94cd3bc0a769165f6ffe8ecabea8b7f48a1ff07
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753932"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a><span data-ttu-id="859b6-104">配置 XMPP 网关访问策略和证书</span><span class="sxs-lookup"><span data-stu-id="859b6-104">Configure XMPP gateway access policies and certificates</span></span>

<span data-ttu-id="859b6-105">XMPP 联盟可根据可扩展消息传递和状态协议 (XMPP) 定义外部部署。</span><span class="sxs-lookup"><span data-stu-id="859b6-105">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol (XMPP).</span></span> <span data-ttu-id="859b6-106">通过 XMPP 配置，用户可以通过以下方式访问 XMPP 域用户：</span><span class="sxs-lookup"><span data-stu-id="859b6-106">An XMPP configuration allows users access to XMPP domain users by:</span></span>
  
- <span data-ttu-id="859b6-107">即时消息和状态-仅限人员</span><span class="sxs-lookup"><span data-stu-id="859b6-107">IM and Presence - person to person only</span></span>
    
- <span data-ttu-id="859b6-108">在 Skype for Business 客户端中创建 XMPP 联盟联系人</span><span class="sxs-lookup"><span data-stu-id="859b6-108">Creation of XMPP federated contacts in the Skype for Business client</span></span>
    
<span data-ttu-id="859b6-109">为支持 XMPP 联盟伙伴配置策略时，这些策略适用于 XMPP 联盟域的用户，但不适用于会话初始协议（SIP）即时消息（IM）服务提供商或 SIP 联盟域的用户。</span><span class="sxs-lookup"><span data-stu-id="859b6-109">When you configure policies for support of XMPP federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers, or SIP federated domains.</span></span> <span data-ttu-id="859b6-110">为您希望允许用户添加联系人并与之通信的每个 XMPP 联盟域配置 XMPP 联盟伙伴。</span><span class="sxs-lookup"><span data-stu-id="859b6-110">You configure an XMPP federated partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="859b6-111">在制定好这些策略之后，您需要配置 XMPP 网关证书。</span><span class="sxs-lookup"><span data-stu-id="859b6-111">Once the policies are in place, you need to configure the XMPP Gateway certificates.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="859b6-112">XMPP 功能在 Skype for business Server 2019 中已弃用，但可在与 Skype for business Server 2019 共存的旧服务器中继续进行。</span><span class="sxs-lookup"><span data-stu-id="859b6-112">XMPP functionality is deprecated in Skype for Business Server 2019, but can be continued in a legacy server in coexistence with Skype for Business Server 2019.</span></span> <span data-ttu-id="859b6-113">确保已部署旧版服务器（Skype for Business Server 2015/Lync Server 2013） XMPP 网关，并已将访问策略配置为为用户启用旧版 XMPP 网关。</span><span class="sxs-lookup"><span data-stu-id="859b6-113">Make sure you have already deployed the legacy server (Skype for Business Server 2015 / Lync Server 2013) XMPP Gateway, and configured the access policies to enable users for legacy XMPP Gateway.</span></span> <span data-ttu-id="859b6-114">有关详细信息，请参阅[迁移 XMPP 联合](migrating-xmpp-federation.md)。</span><span class="sxs-lookup"><span data-stu-id="859b6-114">For details, see [Migrating XMPP Federation](migrating-xmpp-federation.md).</span></span> 
  
### <a name="configure-an-external-access-policy-to-enable-users-for-legacy-xmpp-gateway"></a><span data-ttu-id="859b6-115">配置外部访问策略以为用户启用旧版 XMPP 网关</span><span class="sxs-lookup"><span data-stu-id="859b6-115">Configure an External Access Policy to Enable Users for legacy XMPP Gateway</span></span>

1. <span data-ttu-id="859b6-116">打开旧版 Skype for Business Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="859b6-116">Open the legacy Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="859b6-117">在左侧导航栏中，单击“联盟和外部访问”\*\*\*\*，然后单击“外部访问策略”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="859b6-117">In the left navigation bar, click **Federation and External Access**, and then click **External Access Policy**.</span></span>
    
3. <span data-ttu-id="859b6-118">单击 **“新建”**，然后单击 **“用户策略”**。</span><span class="sxs-lookup"><span data-stu-id="859b6-118">Click **New**, and then click **User policy**.</span></span>
    
4. <span data-ttu-id="859b6-119">输入外部访问用户策略的名称。</span><span class="sxs-lookup"><span data-stu-id="859b6-119">Enter a name for the external access user policy.</span></span>
    
5. <span data-ttu-id="859b6-120">提供外部访问用户策略的说明。</span><span class="sxs-lookup"><span data-stu-id="859b6-120">Provide a description for external access user policy.</span></span>
    
6. <span data-ttu-id="859b6-121">选中“启用与联盟用户的通信”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="859b6-121">Select **Enable communications with federated users**.</span></span>
    
7. <span data-ttu-id="859b6-122">选中“启用与 XMPP 联盟用户的通信”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="859b6-122">Select **Enable communications with XMPP federated users**.</span></span>
    
8. <span data-ttu-id="859b6-123">单击“提交”\*\*\*\* 保存对站点或用户策略的更改。</span><span class="sxs-lookup"><span data-stu-id="859b6-123">Click **Commit** to save your changes to the site or user policy.</span></span> 
    

