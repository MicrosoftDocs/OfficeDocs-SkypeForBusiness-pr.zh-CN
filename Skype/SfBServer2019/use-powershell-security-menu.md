---
title: 对"安全"菜单上的任务使用 PowerShell
ms.reviewer: ''
ms.author: ankum
author: ankum
manager: ravrao
ms.date: 11/03/2021
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: ''
description: 摘要：Skype for Business Server控制面板映射到"安全"菜单的 Cmdlet 映射。
ms.openlocfilehash: 6e726b13b9428b213011126abf5ac0869e6cfbf8
ms.sourcegitcommit: eba9fc680233e9e03773a2942f22afe6247eec41
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60824884"
---
# <a name="security"></a>安全性

本文介绍如何使用 cmdlet 实现与旧版控制面板中的"安全"菜单项类似的结果。

本文介绍了以下子菜单：

- [安全性](#security)
  - [注册器](#registrar)
  - [Web 服务](#web-service)
  - [PIN 策略](#pin-policy)

## <a name="registrar"></a>注册器

**REGISTRAR** 子菜单使管理员可以通过代理服务器配置设置管理代理服务器。 这些设置可在全局范围和服务范围 (但仅应用于边缘服务器和注册器服务) 允许控制客户端终结点可以使用的身份验证协议以及是否将在传入和传出代理服务器连接上使用压缩等内容。

让我们考虑用户在注册器 上可以执行的各种任务，以及Skype for Business映射到的 cmdlet。

---

> **方案 1：** 列出所有代理配置

   ![列出代理配置](./media/proxy-configurations-1.png)

***Cmdlet***

[Get-CsProxyConfiguration](/powershell/module/skype/get-csproxyconfiguration)

***示例***

```powershell
 Get-CsProxyConfiguration
```

---

> **方案 2：** 创建新的代理配置

   ![创建代理配置](./media/proxy-configurations-2.png)

***Cmdlet***

[New-CsProxyConfiguration](/powershell/module/skype/new-csproxyconfiguration)  

***示例***

```powershell
 New-CsProxyConfiguration -Identity "service:EdgeServer:atl-edge-001.litwareinc.com" -RequestServerCompression $True -MaxClientMessageBodySizeKb 256
```

---

> **方案 3：** 获取所选代理配置的详细信息

   ![获取代理配置](./media/proxy-configurations-3.png)

***Cmdlet***

[Get-CsProxyConfiguration](/powershell/module/skype/get-csproxyconfiguration)

***示例***

```powershell
 Get-CsProxyConfiguration -Identity "service:EdgeServer:atl-cs-001.litwareinc.com"
```

---

> **方案 4：** 删除所选的代理配置

   ![删除代理配置](./media/proxy-configurations-4.png)

***Cmdlet***

[Remove-CsProxyConfiguration](/powershell/module/skype/remove-csproxyconfiguration)

***示例***

```powershell
 Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com
```

---

> **方案 5：** 更新代理配置

   ![更新代理配置](./media/proxy-configurations-5.png)

***Cmdlet***

[Set-CsProxyConfiguration](/powershell/module/skype/set-csproxyconfiguration)

***示例***

```powershell
 Set-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-001.litwareinc.com -AcceptServerCompression $True
```

---

## <a name="web-service"></a>Web 服务

通过 **"安全性"下的"WEB 服务** "子 **菜单项，管理员可以** 管理整个组织的 Web 服务配置设置;这包括管理组扩展、证书设置和允许的身份验证方法。 因为管理员可以在全局、站点和服务范围配置不同的设置 (但只能为唯一的 Web 服务) 配置这些设置，因此，管理员可以为不同用户和不同位置自定义 Web 服务功能。

让我们考虑用户可在 **WEB** 服务上执行的各种任务，以及Skype for Business映射到的 cmdlet。

---
> **方案 1：** 列出所有 Web 服务配置

   ![列出 Web 服务配置](./media/web-service-1.png)

***Cmdlet***

[Get-CsWebServiceConfiguration](/powershell/module/skype/get-cswebserviceconfiguration)

***示例***

```powershell
 Get-CsWebServiceConfiguration
```

---

> **方案 2：** 创建新的 Web 服务配置

   ![新的 Web 服务配置](./media/web-service-2.png)

***Cmdlet***

[New-CsWebServiceConfiguration](/powershell/module/skype/new-cswebserviceconfiguration)  

***示例***

```powershell
 New-CsWebServiceConfiguration -Identity site:Redmond -EnableGroupExpansion $False -UseCertificateAuth $True
```

---

> **方案 3：** 获取所选 Web 服务配置的详细信息

   ![获取 Web 服务配置](./media/web-service-3.png)

***Cmdlet***

[Get-CsWebServiceConfiguration](/powershell/module/skype/get-cswebserviceconfiguration)

***示例***

```powershell
 Get-CsWebServiceConfiguration -Identity site:Redmond
```

---

> **方案 4：** 删除所选的 Web 服务配置

   ![删除 Web 服务配置](./media/web-service-4.png)

***Cmdlet***

[Remove-CsWebServiceConfiguration](/powershell/module/skype/remove-cswebserviceconfiguration)

***示例***

```powershell
 Remove-CsWebServiceConfiguration -Identity site:Redmond
```

---

> **方案 5：** 更新 Web 服务配置

   ![更新 Web 服务配置](./media/Web-service-5.png)

***Cmdlet***

[Set-CsWebServiceConfiguration](/powershell/module/skype/set-cswebserviceconfiguration)

***示例***

```powershell
 Set-CsWebServiceConfiguration -Identity site:Redmond -EnableGroupExpansion $True
```

---

## <a name="pin-policy"></a>PIN 策略

管理员可以使用 **PIN 策略** 来管理 PIN 身份验证属性;例如，可以指定 PIN 的最小长度，并确定 PIN 是否允许使用"通用模式"的 PIN，如连续数字 (例如 PIN（如123456) 

让我们考虑用户可在 **PIN 策略** 上执行的各种任务，以及Skype for Business映射到的 cmdlet。

---

> **方案 1：** 列出所有 PIN 策略

   ![列出固定策略](./media/pin-policy-1.png)

***Cmdlet***

[Get-CsPinPolicy](/powershell/module/skype/get-cspinpolicy)

***示例***

```powershell
 Get-CsPinPolicy
```

---

> **方案 2：** 创建新的 PIN 策略

   ![创建固定策略](./media/pin-policy-2.png)

***Cmdlet***

[New-CsPinPolicy](/powershell/module/skype/new-cspinpolicy)  

***示例***

```powershell
 New-CsPinPolicy -Identity "site:Redmond" -MinPasswordLength 10
```

---

> **方案 3：** 获取所选 PIN 策略的详细信息

   ![获取 PIN 策略](./media/pin-policy-3.png)

***Cmdlet***

[Get-CsPinPolicy](/powershell/module/skype/get-cspinpolicy)

***示例***

```powershell
 Get-CsPinPolicy -Identity "site:Redmond"
```

---

> **方案 4：** 删除所选的 PIN 策略

   ![删除 PIN 策略](./media/pin-policy-4.png)

***Cmdlet***

[Remove-CsPinPolicy](/powershell/module/skype/remove-cspinpolicy)

***示例***

```powershell
 Remove-CsPinPolicy -Identity RedmondUsersPinPolicy
```

---

> **方案 5：** 更新 PIN 策略

   ![更新 PIN 策略](./media/pin-policy-5.png)

***Cmdlet***

[Set-CsPinPolicy](/powershell/module/skype/set-cspinpolicy)

***示例***

```powershell
 Set-CsPinPolicy -Identity site:Redmond -MinPasswordLength 10
```

---
