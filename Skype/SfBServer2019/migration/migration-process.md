---
title: 迁移过程
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 为业务服务器 2019 Skype 的建议和受支持的迁移过程是-并行迁移。 本主题介绍原因应使用-并行迁移和还包括有关共存测试信息。
ms.openlocfilehash: 22f503b441bfd6115a63127f9a0b89bc8f5843ab
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028661"
---
# <a name="migration-process"></a>迁移过程

为业务服务器 2019 Skype 的建议和受支持的迁移过程是-并行迁移。 本主题介绍原因应使用-并行迁移和还包括有关共存测试信息。
  
## <a name="side-by-side-migration"></a>并行迁移

在几乎在每个迁移中，您应使用-并行迁移路径。 在-并行迁移中，您将一起运行的是以前版本的相应服务器业务服务器 2019年部署具有 Skype 的新服务器，然后转接到新服务器的操作。 如果需要回滚到以前的版本，您只需要只要将操作切换回原始服务器。 请注意，在此情况下安排与已升级的客户端的任何新会议将不起作用，以及客户端还需要降级。
  
## <a name="coexistence-testing"></a>共存测试

部署 Skype 的业务服务器 2019年与早期版本的并行后，部署代表测试业务服务器 2019年和以前版本的 Skype 状态共存。 在此状态下，务必测试，并确保启动服务，可以管理每个网站，并且客户端可以与当前和旧用户通信。 之前的所有用户的迁移，它是非常重要，您了解每个部署的状态，并确保每个部署为功能且正常工作正常。 通常情况下，测试阶段的共存情况存在整个 Skype 试点测试的业务服务器 2019年。 旧用户移至 Skype 的业务服务器 2019年的一段时间以确保该应用程序兼容性以及特性和功能正常运行。 试点测试之后，用户和应用程序移动到的业务服务器 2019 Skype 和旧池的产品版本和以前版本的应用程序停用。
  