---
title: 迁移过程
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 建议和支持的 2019 Skype for Business Server迁移过程是并行迁移。 本主题介绍为什么应使用并行迁移，并包括有关共存测试的信息。
ms.openlocfilehash: e1d89dc2081918d87f73cd3c6908fff0c388e6700d00af6dcd72161a2ccc9ece
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54303406"
---
# <a name="migration-process"></a>迁移过程

建议和支持的 2019 Skype for Business Server迁移过程是并行迁移。 本主题介绍为什么应使用并行迁移，并包括有关共存测试的信息。
  
## <a name="side-by-side-migration"></a>并行迁移

在几乎每个迁移中，都应该使用并行迁移路径。 在并行迁移中，将 Skype for Business Server 2019 的新服务器与运行早期版本的相应服务器一起部署，然后将操作转移到新服务器。 如果需要回滚到以前的版本，只需将操作切换回原始服务器。 请注意，在此情况下，使用升级的客户端安排的任何新会议将不会工作，并且客户端也将需要降级。
  
## <a name="coexistence-testing"></a>共存测试

在将 Skype for Business Server 2019 与以前版本并行部署后，部署表示 Skype for Business Server 2019 和早期版本的共存测试状态。 在此状态下，必须测试和确保服务已启动，可以管理每个站点，并且客户端可以与当前用户和旧用户通信。 在迁移所有用户之前，必须了解每个部署的状态并确保每个部署正常运行。 通常，共存测试阶段存在于 2019 年 2019 年Skype for Business Server测试中。 将旧用户移至 Skype for Business Server 2019 一段时间，以确保应用程序兼容性和功能正常工作。 在试点测试之后，用户和应用程序将移至 Skype for Business Server 2019 的生产版本，并且早期版本的旧池和应用程序将停用。
  
