---
title: Skype 会议室系统受信任域
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9fb63ad4-6eda-4724-be63-10bf5e65cb2b
description: 阅读本主题，了解如何为 Skype 会议室系统和 Skype for Business 配置受信任域。
ms.openlocfilehash: c7883ed0cbc2e805ee0ba3cddfb3b2cee1163c35
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834112"
---
# <a name="skype-room-system-trusted-domains"></a><span data-ttu-id="97896-103">Skype 会议室系统受信任域</span><span class="sxs-lookup"><span data-stu-id="97896-103">Skype Room System trusted domains</span></span>
 
<span data-ttu-id="97896-104">阅读本主题，了解如何为 Skype 会议室系统和 Skype for Business 配置受信任域。</span><span class="sxs-lookup"><span data-stu-id="97896-104">Read this topic to learn how to configure trusted domains for Skype Room System and Skype for Business.</span></span>
  
## <a name="trusted-domains"></a><span data-ttu-id="97896-105">受信任的域</span><span class="sxs-lookup"><span data-stu-id="97896-105">Trusted domains</span></span>

<span data-ttu-id="97896-106">Skype for Business 客户端显示一个对话框，允许用户接受来自 Skype for Business Server 的证书，如果用户帐户登录的 SIP 域不同于证书上"使用者"或"使用者替代名称"中显示的名称。</span><span class="sxs-lookup"><span data-stu-id="97896-106">The Skype for Business client displays a dialog box that allows users to accept the certificate from the Skype for Business Server if the SIP domain of the user account signing in is different from the name presented in the Subject or Subject Alt Name on the certificate.</span></span> <span data-ttu-id="97896-107">如果组织中为 Skype for Business Server 配置的证书在"主题"或"主题替换名称"中没有 Skype 会议室系统帐户的 SIP 域名，则必须在 Skype 会议室系统控制台计算机上"受信任的域"注册表项下配置证书上呈现的这些域。</span><span class="sxs-lookup"><span data-stu-id="97896-107">If the certificate configured for Skype for Business Server in your organization does not have SIP domain name of Skype Room System account in Subject or Subject Alt Name, you must configure those domains presented on the certificate under the Trusted Domains registry key on the Skype Room System console machine.</span></span> <span data-ttu-id="97896-108">你的 Skype 会议室系统制造商提供的 Skype 会议室系统管理员指南介绍了如何在 Skype for Business 客户端中添加受信任的域以及在何处添加受信任域。</span><span class="sxs-lookup"><span data-stu-id="97896-108">Your Skype Room System manufacturer-provided Skype Room System Administrator's Guide explains how and where to add trusted domains in the Skype for Business client.</span></span> 
  
<span data-ttu-id="97896-109">例如，假定在 Skype for Business Server 上配置的证书的主题/主题替换名称为"CONTOSO"。LOCAL"和分配给用户的 Skype 会议室系统登录地址的 SIP 域之一为"confrm1@contoso.net"。</span><span class="sxs-lookup"><span data-stu-id="97896-109">For example, assume the certificates configured on Skype for Business Server have a Subject/Subject Alt Name of "CONTOSO.LOCAL" and one of the SIP domains assigned to a user for the Skype Room System sign-in address is "confrm1@contoso.net."</span></span> <span data-ttu-id="97896-110">由于contoso.net不在证书中，因此在 Skype 会议室系统计算机上，你需要在注册表中将"contoso.local"配置为受信任的域，如 Skype 会议室系统制造商提供的 Skype 会议室系统管理员指南中介绍。</span><span class="sxs-lookup"><span data-stu-id="97896-110">Because contoso.net is not in the certificate, on the Skype Room System machine, you will need to configure "contoso.local" as a trusted domain in the registry, as explained in your Skype Room System manufacturer-provided Skype Room System Administrator's Guide.</span></span> 
  

