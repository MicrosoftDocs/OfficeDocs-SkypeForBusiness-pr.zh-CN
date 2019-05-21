---
title: 验证配置设置
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 你可以通过在中央管理存储所在的内部计算机上运行 Skype for Business Server 2019 For CsManagementStoreReplicationStatus cmdlet 验证配置信息到边缘服务器的复制, 或者在任何安装了 Skype for business Server 2019 核心组件 (OcsCore) 的加入域的计算机。
ms.openlocfilehash: 0ea966652972a97dac3e807cef42ddeaa5136322
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34307033"
---
# <a name="verify-configuration-settings"></a>验证配置设置

你可以通过在中央管理存储所在的内部计算机上运行 Skype for Business Server 2019 For **CsManagementStoreReplicationStatus** cmdlet 来验证对边缘服务器的配置信息的复制, 或者在安装了 Skype for Business Server 2019 核心组件 (OcsCore) 的任何加入域的计算机上。 
  
初始结果可能表明状态为 "False", 而不是 "True" 用于复制。 如果是这样, 请运行**CsManagementStoreReplication** cmdlet 并等待复制完成, 然后再再次运行**Get CsManagementStoreReplicationStatus** 。 
  

