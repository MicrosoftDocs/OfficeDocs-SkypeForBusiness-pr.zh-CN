---
title: Skype 会议室系统受信任域
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9fb63ad4-6eda-4724-be63-10bf5e65cb2b
description: 阅读本主题，了解如何为 Skype 会议室系统和 Skype for Business 配置受信任的域。
ms.openlocfilehash: bc025849f56a7257ac3684b9783e551959bd0228
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214889"
---
# <a name="skype-room-system-trusted-domains"></a><span data-ttu-id="28e7c-103">Skype 会议室系统受信任域</span><span class="sxs-lookup"><span data-stu-id="28e7c-103">Skype Room System trusted domains</span></span>
 
<span data-ttu-id="28e7c-104">阅读本主题，了解如何为 Skype 会议室系统和 Skype for Business 配置受信任的域。</span><span class="sxs-lookup"><span data-stu-id="28e7c-104">Read this topic to learn how to configure trusted domains for Skype Room System and Skype for Business.</span></span>
  
## <a name="trusted-domains"></a><span data-ttu-id="28e7c-105">受信任的域</span><span class="sxs-lookup"><span data-stu-id="28e7c-105">Trusted domains</span></span>

<span data-ttu-id="28e7c-106">业务客户端 Skype 显示一个对话框，允许用户接受来自 Skype 的证书 Business Server 如果登录的用户帐户的 SIP 域不同证书上的主题或使用者替代名称中显示的名称。</span><span class="sxs-lookup"><span data-stu-id="28e7c-106">The Skype for Business client displays a dialog box that allows users to accept the certificate from the Skype for Business Server if the SIP domain of the user account signing in is different from the name presented in the Subject or Subject Alt Name on the certificate.</span></span> <span data-ttu-id="28e7c-107">如果您的组织中为 Business Server 配置为 Skype 的证书没有主题或使用者替代名称中的 Skype 会议室系统帐户的 SIP 域名，则必须配置该页上的证书，在受信任域下显示这些域Skype 会议室系统控制台的计算机上的注册表项。</span><span class="sxs-lookup"><span data-stu-id="28e7c-107">If the certificate configured for Skype for Business Server in your organization does not have SIP domain name of Skype Room System account in Subject or Subject Alt Name, you must configure those domains presented on the certificate under the Trusted Domains registry key on the Skype Room System console machine.</span></span> <span data-ttu-id="28e7c-108">Skype 会议室系统提供制造商 Skype 会议室系统管理员的指南介绍了如何以及在哪里业务客户端 Skype 中添加受信任的域。</span><span class="sxs-lookup"><span data-stu-id="28e7c-108">Your Skype Room System manufacturer-provided Skype Room System Administrator's Guide explains how and where to add trusted domains in the Skype for Business client.</span></span> 
  
<span data-ttu-id="28e7c-109">例如，假定为业务服务器配置上 Skype 的证书具有主题/使用者替代名称的"CONTOSO。本地"和 SIP 域分配给用户的登录地址 Skype 会议室系统之一是"confrm1@contoso.net。"</span><span class="sxs-lookup"><span data-stu-id="28e7c-109">For example, assume the certificates configured on Skype for Business Server have a Subject/Subject Alt Name of "CONTOSO.LOCAL" and one of the SIP domains assigned to a user for the Skype Room System sign-in address is "confrm1@contoso.net."</span></span> <span data-ttu-id="28e7c-110">因为 contoso.net 不在该证书，Skype 会议室系统在计算机上，您将需要您 Skype 会议室系统提供制造商 Skype 会议室系统管理员指南 》 中所述作为注册表中的受信任域配置"contoso.local"。</span><span class="sxs-lookup"><span data-stu-id="28e7c-110">Because contoso.net is not in the certificate, on the Skype Room System machine, you will need to configure "contoso.local" as a trusted domain in the registry, as explained in your Skype Room System manufacturer-provided Skype Room System Administrator's Guide.</span></span> 
  

