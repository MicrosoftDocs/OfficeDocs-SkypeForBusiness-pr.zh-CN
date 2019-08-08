---
title: Skype 会议室系统受信任域
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9fb63ad4-6eda-4724-be63-10bf5e65cb2b
description: 阅读本主题，了解如何为 Skype 会议室系统和 Skype for Business 配置受信任的域。
ms.openlocfilehash: 2b2aeb98e3b1b6efe585e565c1e288d635fdb26e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235011"
---
# <a name="skype-room-system-trusted-domains"></a><span data-ttu-id="1a9c3-103">Skype 会议室系统受信任域</span><span class="sxs-lookup"><span data-stu-id="1a9c3-103">Skype Room System trusted domains</span></span>
 
<span data-ttu-id="1a9c3-104">阅读本主题，了解如何为 Skype 会议室系统和 Skype for Business 配置受信任的域。</span><span class="sxs-lookup"><span data-stu-id="1a9c3-104">Read this topic to learn how to configure trusted domains for Skype Room System and Skype for Business.</span></span>
  
## <a name="trusted-domains"></a><span data-ttu-id="1a9c3-105">受信任的域</span><span class="sxs-lookup"><span data-stu-id="1a9c3-105">Trusted domains</span></span>

<span data-ttu-id="1a9c3-106">Skype for Business 客户端将显示一个对话框, 允许用户从 Skype for Business 服务器接受证书 (如果登录的用户帐户的 SIP 域与证书上的主题或使用者替换名称中显示的名称不同)。</span><span class="sxs-lookup"><span data-stu-id="1a9c3-106">The Skype for Business client displays a dialog box that allows users to accept the certificate from the Skype for Business Server if the SIP domain of the user account signing in is different from the name presented in the Subject or Subject Alt Name on the certificate.</span></span> <span data-ttu-id="1a9c3-107">如果为组织中的 Skype for Business 服务器配置的证书没有使用主题或主题替换名称中的 Skype 会议室系统帐户的 SIP 域名, 则必须在受信任域下的证书上配置这些域。Skype 会议室系统控制台计算机上的注册表项。</span><span class="sxs-lookup"><span data-stu-id="1a9c3-107">If the certificate configured for Skype for Business Server in your organization does not have SIP domain name of Skype Room System account in Subject or Subject Alt Name, you must configure those domains presented on the certificate under the Trusted Domains registry key on the Skype Room System console machine.</span></span> <span data-ttu-id="1a9c3-108">Skype 会议室系统制造商-提供的 Skype 会议室系统管理员指南介绍如何在 Skype for Business 客户端中添加受信任域和在何处添加受信任域。</span><span class="sxs-lookup"><span data-stu-id="1a9c3-108">Your Skype Room System manufacturer-provided Skype Room System Administrator's Guide explains how and where to add trusted domains in the Skype for Business client.</span></span> 
  
<span data-ttu-id="1a9c3-109">例如, 假设在 Skype for Business 服务器上配置的证书具有主题/主题的 "CONTOSO" 替换名称。本地 "和为 Skype 会议室系统登录地址分配给用户的 SIP 域之一是" confrm1@contoso.net "。</span><span class="sxs-lookup"><span data-stu-id="1a9c3-109">For example, assume the certificates configured on Skype for Business Server have a Subject/Subject Alt Name of "CONTOSO.LOCAL" and one of the SIP domains assigned to a user for the Skype Room System sign-in address is "confrm1@contoso.net."</span></span> <span data-ttu-id="1a9c3-110">由于 contoso.net 不在证书中, 在 Skype 会议室系统计算机上, 你需要在注册表中将 "contoso" 配置为受信任域, 如 Skype 会议室系统制造商提供的 Skype 会议室系统管理员指南中所述。</span><span class="sxs-lookup"><span data-stu-id="1a9c3-110">Because contoso.net is not in the certificate, on the Skype Room System machine, you will need to configure "contoso.local" as a trusted domain in the registry, as explained in your Skype Room System manufacturer-provided Skype Room System Administrator's Guide.</span></span> 
  

