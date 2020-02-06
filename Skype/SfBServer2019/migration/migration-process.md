---
title: 迁移过程
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype for business Server 2019 的推荐和支持的迁移过程是并行迁移。 本主题介绍了应使用并行迁移的原因，还包括有关共存测试的信息。
ms.openlocfilehash: 7d8ce6513535871939894092850ad0526b1b6a63
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813410"
---
# <a name="migration-process"></a>迁移过程

Skype for business Server 2019 的推荐和支持的迁移过程是并行迁移。 本主题介绍了应使用并行迁移的原因，还包括有关共存测试的信息。
  
## <a name="side-by-side-migration"></a>并行迁移

在几乎所有迁移中，都应使用并行迁移路径。 在并行迁移中，你可以使用 Skype for Business Server 2019 与运行早期版本的相应服务器一起部署新的服务器，然后将操作转移到新服务器。 如果需要回滚到以前的版本，你只能将操作转移回原始服务器。 请注意，在这种情况下，使用升级的客户安排的新会议将不起作用，并且客户端也需要降级。
  
## <a name="coexistence-testing"></a>共存测试

在与早期版本并行部署了 Skype for Business Server 2019 后，部署表示 Skype for Business Server 2019 和早期版本的共存测试状态。 在此状态下，测试和确保服务已启动、可管理每个网站，并且客户端可以与当前用户和旧版用户进行通信非常重要。 在迁移所有用户之前，了解每个部署的状态非常重要，并确保每个部署都能正常运行。 通常，共存测试阶段存在于 Skype for business Server 2019 的试点测试中。 旧版用户在一段时间内被移动到 Skype for Business 服务器2019，以确保应用程序兼容性和功能和功能正常工作。 试点测试后，用户和应用程序将移动到 Skype for Business Server 2019 的生产版本，并且旧版本的旧池和应用程序将被停用。
  
