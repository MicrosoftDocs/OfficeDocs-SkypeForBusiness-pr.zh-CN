---
title: Skype 会议室系统受信任域
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/4/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9fb63ad4-6eda-4724-be63-10bf5e65cb2b
description: 阅读本主题，了解如何为 Skype 会议室系统和 Skype for Business 配置受信任的域。
ms.openlocfilehash: 83d6e313f8643f593e1e25488e403da448649bd6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-system-trusted-domains"></a><span data-ttu-id="6af23-103">Skype 会议室系统受信任域</span><span class="sxs-lookup"><span data-stu-id="6af23-103">Skype Room System trusted domains</span></span>
 
<span data-ttu-id="6af23-104">阅读本主题，了解如何为 Skype 会议室系统和 Skype for Business 配置受信任的域。</span><span class="sxs-lookup"><span data-stu-id="6af23-104">Read this topic to learn how to configure trusted domains for Skype Room System and Skype for Business.</span></span>
  
## <a name="trusted-domains"></a><span data-ttu-id="6af23-105">受信任的域</span><span class="sxs-lookup"><span data-stu-id="6af23-105">Trusted domains</span></span>

<span data-ttu-id="6af23-106">Skype 业务客户端显示一个对话框，允许用户 SIP 域登录的用户帐户不同的主题或主题 Alt 名称中显示证书上的名称，如果业务服务器接受来自 Skype 的证书。</span><span class="sxs-lookup"><span data-stu-id="6af23-106">The Skype for Business client displays a dialog box that allows users to accept the certificate from the Skype for Business Server if the SIP domain of the user account signing in is different from the name presented in the Subject or Subject Alt Name on the certificate.</span></span> <span data-ttu-id="6af23-107">如果为 Skype 业务服务器的配置，您的组织中的证书没有 Skype 的空间系统帐户在主题或主题 Alt 名称中的 SIP 域的名称，则必须配置这些证书在受信任的域下显示的域Skype 的空间系统控制台的计算机上的注册表项。</span><span class="sxs-lookup"><span data-stu-id="6af23-107">If the certificate configured for Skype for Business Server in your organization does not have SIP domain name of Skype Room System account in Subject or Subject Alt Name, you must configure those domains presented on the certificate under the Trusted Domains registry key on the Skype Room System console machine.</span></span> <span data-ttu-id="6af23-108">Skype 的空间系统厂商提供 Skype 的空间系统管理员的指南说明了如何以及在何处在 Skype 业务客户机中添加受信任的域。</span><span class="sxs-lookup"><span data-stu-id="6af23-108">Your Skype Room System manufacturer-provided Skype Room System Administrator's Guide explains how and where to add trusted domains in the Skype for Business client.</span></span> 
  
<span data-ttu-id="6af23-109">例如，假定在 Skype 上为业务服务器配置的证书有主题/主题 Alt 名称为"CONTOSO。本地"以及分配给用户的 Skype 的空间系统登录地址的 SIP 域之一是"confrm1@contoso.net"。</span><span class="sxs-lookup"><span data-stu-id="6af23-109">For example, assume the certificates configured on Skype for Business Server have a Subject/Subject Alt Name of "CONTOSO.LOCAL" and one of the SIP domains assigned to a user for the Skype Room System sign-in address is "confrm1@contoso.net."</span></span> <span data-ttu-id="6af23-110">因为 contoso.net 是不在证书中，Skype 的空间系统在计算机上，您需要将"contoso.local"配置为在注册表中，受信任的域，您 Skype 的空间系统厂商提供 Skype 的空间系统管理员指南 》 中所述。</span><span class="sxs-lookup"><span data-stu-id="6af23-110">Because contoso.net is not in the certificate, on the Skype Room System machine, you will need to configure "contoso.local" as a trusted domain in the registry, as explained in your Skype Room System manufacturer-provided Skype Room System Administrator's Guide.</span></span> 
  

