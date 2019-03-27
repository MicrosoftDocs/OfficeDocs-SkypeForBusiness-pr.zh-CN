---
title: 证书向导
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertsMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6ab661d7-5741-4cad-bbe4-62cf862ded85
ROBOTS: NOINDEX, NOFOLLOW
description: 要“请求”、“分配”、“删除”或“查看”证书，可使用证书向导。 必须以 RTCUniversalServerAdmins 组成员的身份登录。 要向公共证书颁发机构 (CA) 请求证书，无需具备其他任何组成员身份。 若要从您的组织的公钥基础结构 (PKI) 申请证书，您需要确认什么其他 — 如果任何 — 组需要的成员身份。 期间请求任务中，您可以输入备用凭据将用于请求来自 PKI 证书的颁发 CA。
ms.openlocfilehash: afa36085fb4e8a1937facac204d78d5c0c61af9b
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30873399"
---
# <a name="certificate-wizard"></a>证书向导
 
要“**请求**”、“**分配**”、“**删除**”或“**查看**”证书，可使用证书向导。 必须以 RTCUniversalServerAdmins 组成员的身份登录。 要向公共证书颁发机构 (CA) 请求证书，无需具备其他任何组成员身份。 若要从您的组织的公钥基础结构 (PKI) 申请证书，您需要确认什么其他 — 如果任何 — 组需要的成员身份。 期间请求任务中，您可以输入备用凭据将用于请求来自 PKI 证书的颁发 CA。
  
要请求新证书，请单击“**请求**”。
  
要分配尚未分配的证书，请单击“**分配**”。
  
要删除先前分配的证书，请单击“**删除**”。
  
> [!NOTE]
> 仅当先前已分配证书时，“**删除**”按钮才可用。如果“**删除**”按钮不可用（灰显），则表明尚未分配任何证书。
  
要查看已分配的证书，请单击“**查看**”。
  
> [!NOTE]
> 仅当先前已分配证书时，“**查看**”按钮才可用。如果“**查看**”按钮灰显，则表明尚未分配任何证书。
  
要刷新当前证书分配屏幕，请单击“**刷新**”。
  
要导入证书存储中没有的证书，请单击“**导入证书**”。
  
> [!NOTE]
> “**导入证书**”通常用于处理通过某个进程接收而非通过证书向导请求的证书。 例如，KPI 管理员会创建证书，然后提供给您使用。 使用**导入证书**，以将证书导入计算机的证书存储并使其可供业务服务器分配的 Skype。
  
要完成需要 CA 管理员批准的从组织中的 CA 请求证书的过程，请单击“**处理待处理的请求**”。证书请求应该返回待处理状态，并显示待处理请求的标识号。要继续处理待处理状态的证书，请单击“**刷新**”以启用“**处理待处理的请求**”按钮。“**处理待处理的请求**”按钮将变得可用（不再灰显）。然后您就可以尝试检索待处理的请求，但是请求状态仍将保持为待处理，直至 CA 管理员颁发或拒绝该证书。如果不存在证书向导创建的有效的待处理请求，则此按钮将不可用。
  

