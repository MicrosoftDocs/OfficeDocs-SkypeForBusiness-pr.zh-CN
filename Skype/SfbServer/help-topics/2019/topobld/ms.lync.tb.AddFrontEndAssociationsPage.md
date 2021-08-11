---
title: 添加前端关联
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndAssociationsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 95620425-defd-47fd-a5c0-e4a283d812a5
ROBOTS: NOINDEX, NOFOLLOW
description: 通过将服务器角色与前端池关联，可以启用对需要部署其他服务器的特定功能的支持。 还可以稍后将服务器角色与前端池关联。 可以与前端池关联的服务器角色包括：
ms.openlocfilehash: 3564457b392e2c122577fb421f5511beb9febd7fbff5ac15bdaec2803263b043
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54285292"
---
# <a name="add-front-end-associations"></a>添加前端关联

通过将服务器角色与前端池关联，可以启用对需要部署其他服务器的特定功能的支持。 还可以稍后将服务器角色与前端池关联。 可以与前端池关联的服务器角色包括：

- A/V 边缘服务器。 有关 A/V 边缘服务器的实现的详细信息，请参阅规划文档中 [的](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-conferencing) 规划会议。

> [!IMPORTANT]
> 如果现在启用对这些功能的任何支持，则发布的拓扑设计将包括实现每个选定功能所需的服务器组件。 若要成功发布拓扑而不出现错误，必须将物理计算机加入域。 例如，如果现在启用存档支持，则必须先部署存档服务器并配置相应的存档选项，然后再开始为组织存档通信。