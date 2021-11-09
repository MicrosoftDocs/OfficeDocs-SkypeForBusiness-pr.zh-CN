---
title: 准备 Active Directory
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainADPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: a8c96311-9e1c-4d39-9870-681fd4e272ff
ROBOTS: NOINDEX, NOFOLLOW
description: 若要开始安装Skype for Business Server，您必须准备 Active Directory 域服务架构、林以及将承载服务器和用户的域。 部署Skype for Business Server向导将指导您完成准备 Active Directory 所需的步骤，从架构开始，然后再准备林。 确认 Active Directory 复制成功后，准备将承载用户或服务器的每个域。
ms.openlocfilehash: d0a4bbde9a3dc4bc22a6a709565fe3b1dcf1e009
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60830616"
---
# <a name="prepare-active-directory"></a>准备 Active Directory

若要开始安装Skype for Business Server，您必须准备 Active Directory 域服务架构、林以及将承载服务器和用户的域。 部署Skype for Business Server向导将指导您完成准备 Active Directory 所需的步骤，从架构开始，然后再准备林。 确认 Active Directory 复制成功后，准备将承载用户或服务器的每个域。

> [!IMPORTANT]
> 要成功准备架构，必须以 Enterprise Admins 组和 Schema Admins 组成员身份登录。要准备林，必须以 Enterprise Admins 组成员身份或以林根中的管理员身份登录。对于域准备，必须以 Domain Admins 组成员身份登录。

有关支持的 Active Directory 拓扑的详细信息，请参阅可支持性文档中的 [Active Directory Support](/previous-versions/office/lync-server-2013/lync-server-2013-active-directory-support)。有关 Active Directory 准备的详细信息，请参阅部署文档中的 [Overview of Active Directory Domain Services Preparation](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-active-directory-domain-services-preparation)。