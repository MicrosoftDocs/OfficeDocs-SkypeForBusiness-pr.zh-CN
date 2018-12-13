---
title: 配置 Azure AD 连接
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: 用于配置混合环境中的 Azure AD 连接的说明。
ms.openlocfilehash: 5d27de4786c588d5d2f2a276dc20c25436bada98
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/13/2018
ms.locfileid: "27244114"
---
# <a name="configure-azure-ad-connect-for-skype-for-business-and-teams"></a>配置 Azure AD 连接 Skype 业务和团队 
 
具有业务服务器 （或 Lync Server） 的 Skype 本地和用户计划业务 online 中使用团队或 Skype 的组织必须在此所述配置其内部部署目录同步与 Office 365 的 Azure AD 连接文档。  这包括直接从移动 Skype 业务本地到团队的组织。 具体而言，与 Skype 的业务本地组织必须确保正确 msRTCSIP 属性保持同步到 Azure AD。 

> [!NOTE]
> 为业务本地还有 Skype 的现有团队用户需要具有其 Skype 业务内部部署帐户移动到云，才能获取完整功能，如业务用户并与 Skype 互操作的功能与联盟组织中的用户进行通信。 即使用户将仅使用团队，此联机 Skype 业务帐户需要由基础结构来提供的其他功能。  若要执行此迁移，必须确保 Azure AD 连接配置正确，以便您可以让混合。
 

## <a name="background-information"></a>背景信息

Azure Active Directory 连接保持内部部署 Active Directory 与 Office 365 持续同步。  您的本地目录保持标识的权威源和内部部署环境中的更改同步到 Azure AD。 有关详细信息，请参阅[Azure AD 连接同步](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/how-to-connect-sync-whatis)。 即使您为不移所有用户从内部部署到云，必须到 Azure AD 以确保在本地和 online 用户之间的通信的内部部署的同步业务 online 使用团队、 业务的本地的 Skype 的所有用户. *您的组织中的用户将显示在您的内部部署和联机目录。*


## <a name="configuring-azure-ad-when-you-have-skype-for-business-server"></a>配置业务服务器具有 Skype 时的 Azure AD 

您有一个内部部署 Active Directory 林或多个林，是否可以在支持的拓扑， [Azure AD 连接的拓扑](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/plan-connect-topologies)中所述的各种使用 Azure AD 连接。  从业务服务器 Skype 的角度来看，有以下三个主要的变体： 

1. 单林，其中包含权威用户标识和业务服务器承载 Skype。 

2. 多个林，其中仅具有一个业务服务器承载 Skype，以及包含权威用户标识 （帐户林） 的一个或多个其他林。 

3. 在多个林中的业务服务器 Skype 的多个部署。 提供满足某些要求时，组织可以合并到单个 Office 365 租户这些多个部署。

### <a name="single-forest"></a>单林 

如果用户帐户和 for Business 的 Skype 所有承载在一个林中，您必须确保 Azure AD 连接被配置为将此林中的用户同步到 Azure AD。  尽管 Azure AD 连接安装向导具有多种选项，将自动到 Azure Active Directory 同步的相应属性。 不要修改内置同步规则和/或连接器进行管理 （这是不可能从安装向导） 的配置建议客户。  

### <a name="multiple-forests-with-one-skype-for-business-deployment"></a>与业务部署一个 Skype 的多个林 

此方案通常称为资源林拓扑中。 在一个或多个帐户林中承载用户的权威标识和 for Business 的 Skype 部署在单独的资源林中 （后者本身可能承载权威用户标识）。 一般情况下，业务用户的权威标识的 Skype 可以是同一个林中 Skype 业务服务器和/或另一个林中，提供： 

- 具有权威性标识帐户林中的用户在资源林中 （Skype 业务服务器部署在何处） 表示为已禁用的用户对象，并在资源林中的 Msrtcsip-originatorsid 属性匹配中的 SID帐户林。 有关详细信息，请参阅[配置混合 for Business 的 Skype 的多林环境](configure-a-multi-forest-environment-for-hybrid.md)。

- 资源林承载 Skype 业务服务器信任帐户林中。  

- 所有相关的用户对象和属性都标识 （从帐户林） 和 Skype for Business （从资源林） 同步到通过 Azure AD 连接的正确值的 Azure AD。  

 若要获得正确的对象和属性同步到 Azure AD[多林部署方案](configure-a-multi-forest-environment-for-hybrid.md)中，Microsoft 强烈建议使用 Azure AD 连接从所有已启用用户帐户的林和域的林同步的包含 for Business 的 Skype。  假定所有林进行都同步，您必须配置 Azure AD 连接合并这些身份并都同步到 Azure AD。 Azure AD 连接旨在处理此方案中，并提供安装向导中的内置选项，此设置，包括设置定位标记加入标识。  选择以下： 跨多个目录存在用户标识。 使用的匹配--> ObjectSID 和 msExchangeMasterAccountSID 属性。


### <a name="multiple-skype-for-business-server-deployments-in-multiple-forests"></a>对于业务服务器部署在多个林中的多个 Skype 

在此方案中，有多个林，对于业务服务器，每个包含 Skype，单个 Office 365 租户。  使用 AAD 连接的租户，可以进行业务服务器包含 Skype 每个林同步到 Azure AD 中。 最多，只有一个林可以配置的 Skype 业务混合在给定时间。 在启用之前的林中的混合，以从所有其他林中的所有 SIP 域都必须使用[禁用 csonlineSipDomain](https://docs.microsoft.com/en-us/powershell/module/skype/disable-csonlinesipdomain)都禁用。 有关如何进行此类将环境整合到 Office 365 的详细信息，请参阅[个团队和 Skype for Business 的云整合](cloud-consolidation.md)。

## <a name="general-requirements"></a>一般要求 

团队和 Skype 业务联机服务需要的正确的 Active Directory 属性存在，并在 Azure AD 中填充。  Microsoft 的常规建议是同步包含用户标识的所有林，以及业务服务器包含 Skype 任何林中。

 如果用户的标识存在跨多级林，Azure AD 连接应执行合并操作。 时遵循此指南，则 Azure AD 连接将自动同步的正确的属性，前提是您不要修改的连接器或在 Azure AD 连接的同步规则。 
  
如果您不从包含用户标识和 Skype Business Server 部署的所有林同步，您仍必须确保相关标识和 Skype 业务属性进行正确填充到使用团队或 Skype 任何用户的 Azure ADfor Business (是否在本地或联机)-该可能需要其他内部部署目录同步。 有关详细信息，请参阅[Azure AD 连接同步： 属性同步到 Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)。

在这种情况下，它是客户的责任，以确保正确配置到 Azure AD 填充属性。 注意以下几项： 

- 使用非标准配置同步到 Azure AD 是危险，因为它可能会导致错误配置，而导致数据损坏联机目录中。

- 在产品发展，Microsoft 将继续验证所有相关林进行同步的标准同步配置。 使用自定义同步配置的客户负责确保其配置到 Azure AD 提供的正确的属性和值。 

## <a name="related-information"></a>相关的信息

- [什么是混合身份](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/whatis-hybrid-identity?toc=%2Fen-us%2Fazure%2Factive-directory%2Fhybrid%2FTOC.json&bc=%2Fen-us%2Fazure%2Fbread%2Ftoc.json)

- [Azure AD 连接同步： 了解和自定义同步](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/how-to-connect-sync-whatis)

- [拓扑的 Azure AD 连接](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/plan-connect-topologies)

- [Azure AD 连接同步： 同步到 Azure Active Directory 的属性](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)
