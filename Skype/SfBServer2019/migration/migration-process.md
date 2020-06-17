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
description: Skype for Business Server 2019 的推荐和受支持的迁移过程是并行迁移。 本主题介绍为什么应使用并行迁移，并包括有关共存测试的信息。
ms.openlocfilehash: 2343e3d6dd7eadbcfbf2b900d51594253e22f933
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752634"
---
# <a name="migration-process"></a>迁移过程

Skype for Business Server 2019 的推荐和受支持的迁移过程是并行迁移。 本主题介绍为什么应使用并行迁移，并包括有关共存测试的信息。
  
## <a name="side-by-side-migration"></a>并行迁移

在几乎每个迁移中，都应该使用并行迁移路径。 在并行迁移中，使用 Skype for Business Server 2019 和运行早期版本的相应服务器一起部署新的服务器，然后将操作转移到新服务器。 如果有必要回滚到以前的版本，则只需将操作转移回原始服务器。 请注意，在此情况下，使用升级的客户端安排的任何新会议将不会工作，并且客户端也将需要降级。
  
## <a name="coexistence-testing"></a>共存测试

在将 Skype for Business Server 2019 与以前的版本并行部署后，该部署表示 Skype for Business Server 2019 和以前版本的共存测试状态。 在此状态下，必须测试和确保服务已启动，可以管理每个站点，并且客户端可以与当前用户和旧用户通信。 在迁移所有用户之前，必须了解每个部署的状态并确保每个部署正常运行。 通常情况下，共存测试阶段在 Skype for business Server 2019 的试点测试过程中存在。 旧版用户在一段时间内被移动到 Skype for Business Server 2019，以确保应用程序兼容性和功能和功能正常运行。 完成试点测试后，用户和应用程序将移至 Skype for Business Server 2019 的生产版本，旧版本的旧池和应用程序将停用。
  
