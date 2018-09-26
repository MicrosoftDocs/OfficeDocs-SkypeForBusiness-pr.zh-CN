---
title: 配置 XMPP 网关访问策略和证书
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: XMPP 联盟定义基于可扩展消息和状态协议 (XMPP) 外部部署。 XMPP 配置允许用户通过 XMPP 域用户访问：
ms.openlocfilehash: 2ec2440365907632523728238c51cc90e894c84e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027856"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a><span data-ttu-id="ede62-104">配置 XMPP 网关访问策略和证书</span><span class="sxs-lookup"><span data-stu-id="ede62-104">Configure XMPP gateway access policies and certificates</span></span>

<span data-ttu-id="ede62-105">XMPP 联盟定义基于可扩展消息和状态协议 (XMPP) 外部部署。</span><span class="sxs-lookup"><span data-stu-id="ede62-105">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol (XMPP).</span></span> <span data-ttu-id="ede62-106">XMPP 配置允许用户通过 XMPP 域用户访问：</span><span class="sxs-lookup"><span data-stu-id="ede62-106">An XMPP configuration allows users access to XMPP domain users by:</span></span>
  
- <span data-ttu-id="ede62-107">IM 和状态-仅限于面对面</span><span class="sxs-lookup"><span data-stu-id="ede62-107">IM and Presence - person to person only</span></span>
    
- <span data-ttu-id="ede62-108">创建 XMPP 联盟中的商业客户端 Skype 联系人</span><span class="sxs-lookup"><span data-stu-id="ede62-108">Creation of XMPP federated contacts in the Skype for Business client</span></span>
    
<span data-ttu-id="ede62-109">在配置策略支持 XMPP 联盟伙伴、 的策略应用于 XMPP 联盟域用户，但不是向用户的会话初始协议 (SIP) 即时消息 (IM) 服务提供程序或 SIP 联盟域。</span><span class="sxs-lookup"><span data-stu-id="ede62-109">When you configure policies for support of XMPP federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers, or SIP federated domains.</span></span> <span data-ttu-id="ede62-110">配置您想要让用户添加联系人并与之通信的每个 XMPP 联盟域 XMPP 联盟的伙伴。</span><span class="sxs-lookup"><span data-stu-id="ede62-110">You configure an XMPP federated partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="ede62-111">位置策略后，您需要配置 XMPP 网关证书。</span><span class="sxs-lookup"><span data-stu-id="ede62-111">Once the policies are in place, you need to configure the XMPP Gateway certificates.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="ede62-112">XMPP 功能在 Skype 中的业务服务器 2019年已弃用，但可以继续使用在旧服务器以与 Skype 的业务服务器 2019年的共存。</span><span class="sxs-lookup"><span data-stu-id="ede62-112">XMPP functionality is deprecated in Skype for Business Server 2019, but can be continued in a legacy server in coexistence with Skype for Business Server 2019.</span></span> <span data-ttu-id="ede62-113">请确保您已经部署了旧服务器 (业务服务器 2015年的 Skype / Lync Server 2013) XMPP 网关，并配置用户启用旧的 XMPP 网关访问策略。</span><span class="sxs-lookup"><span data-stu-id="ede62-113">Make sure you have already deployed the legacy server (Skype for Business Server 2015 / Lync Server 2013) XMPP Gateway, and configured the access policies to enable users for legacy XMPP Gateway.</span></span> <span data-ttu-id="ede62-114">有关详细信息，请参阅[迁移 XMPP 联盟](migrating-xmpp-federation.md)。</span><span class="sxs-lookup"><span data-stu-id="ede62-114">For details, see [Migrating XMPP Federation](migrating-xmpp-federation.md).</span></span> 
  
### <a name="configure-an-external-access-policy-to-enable-users-for-legacy-xmpp-gateway"></a><span data-ttu-id="ede62-115">旧的 XMPP 网关配置为启用用户外部访问策略</span><span class="sxs-lookup"><span data-stu-id="ede62-115">Configure an External Access Policy to Enable Users for legacy XMPP Gateway</span></span>

1. <span data-ttu-id="ede62-116">打开业务 Server Control Panel 旧 Skype。</span><span class="sxs-lookup"><span data-stu-id="ede62-116">Open the legacy Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="ede62-117">在左侧的导航栏中，单击**联盟和外部访问**，然后单击**外部访问策略**。</span><span class="sxs-lookup"><span data-stu-id="ede62-117">In the left navigation bar, click **Federation and External Access**, and then click **External Access Policy**.</span></span>
    
3. <span data-ttu-id="ede62-118">单击“**新建**”，然后单击“**用户策略**”。</span><span class="sxs-lookup"><span data-stu-id="ede62-118">Click **New**, and then click **User policy**.</span></span>
    
4. <span data-ttu-id="ede62-119">输入外部访问用户策略的名称。</span><span class="sxs-lookup"><span data-stu-id="ede62-119">Enter a name for the external access user policy.</span></span>
    
5. <span data-ttu-id="ede62-120">提供外部访问用户策略的说明。</span><span class="sxs-lookup"><span data-stu-id="ede62-120">Provide a description for external access user policy.</span></span>
    
6. <span data-ttu-id="ede62-121">选择**启用与联盟用户的通信**。</span><span class="sxs-lookup"><span data-stu-id="ede62-121">Select **Enable communications with federated users**.</span></span>
    
7. <span data-ttu-id="ede62-122">选择**启用与 XMPP 联盟通信用户**。</span><span class="sxs-lookup"><span data-stu-id="ede62-122">Select **Enable communications with XMPP federated users**.</span></span>
    
8. <span data-ttu-id="ede62-123">单击**提交**以保存对站点或用户策略所做的更改。</span><span class="sxs-lookup"><span data-stu-id="ede62-123">Click **Commit** to save your changes to the site or user policy.</span></span> 
    

