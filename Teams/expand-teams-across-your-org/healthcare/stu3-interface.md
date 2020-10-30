---
title: 患者应用和 EHR 集成 STU3 界面
author: dstrome
ms.author: dstrome
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: 了解如何将电子医疗记录集成到 Microsoft 团队患者应用和 STU3 界面规范中。
ms.custom: seo-marvel-apr2020
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 4e20619badb2509d0a90f396563a98796e718e2f
ms.sourcegitcommit: beaaee10019f4eda746f348888a4a3c2aaa6f196
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2020
ms.locfileid: "48803490"
---
# <a name="stu3-interface-specification"></a>STU3 接口规范

> [!NOTE]
> 2020年10月30日，患者应用已停用，并已由团队中的 " [列表" 应用](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 取代。 患者应用数据存储在支持团队的 Office 365 组的组邮箱中。 与病人应用关联的所有数据都将保留在此组中，但不能再通过用户界面进行访问。 用户可以使用 " [列表" 应用](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)重新创建其列表。
>
>利用 "列表"，医疗保健组织中的 "护理团队" 可以创建各种方案的患者列表，包括从倒圆角和 interdisciplinary 团队会议到常规患者监控。 查看列表中的患者模板以开始使用。 若要了解有关如何管理组织中的列表应用的详细信息，请参阅 [管理列表应用](../../manage-lists-app.md)。

设置或重新配置 FHIR 服务器以处理 Microsoft 团队患者应用需要了解应用需要访问的数据。 FHIR 服务器必须使用以下资源的捆绑包支持发布请求：

- [档案](#patient)
- [知识产权](#observation)
- [条件](#condition)
- [产生](#encounter)
- [过敏症 Intolerance](#allergyintolerance)
- [内](#coverage)
- [药物报表](#medication-request) (替换 PATIENTSAPP 的 DSTU2 版本中的 MedicationOrder) 
- 位置 (此资源所需的信息可以包含在 "遇到") 

> [!NOTE]
> 患者资源是唯一必需的资源 (不会在所有) 加载的应用;但是，建议合作伙伴针对 Microsoft 团队患者应用的最佳最终用户体验，针对以下提供的针对以上提及的所有资源提供支持。

来自 Microsoft 团队患者应用的来自多个资源的查询将发布 (批处理) FHIR 服务器 URL 的捆绑包。 服务器应对每个请求进行处理，并返回每个请求所匹配的资源的捆绑包。 有关详细信息和示例，请参阅 [https://www.hl7.org/fhir/STU3/http.html#transaction](https://www.hl7.org/fhir/STU3/http.html#transaction) 。

## <a name="capability-statement"></a>功能陈述

以下是最少的必填字段：

 - 余下

    - 众
    - 相交
    - 资源：类型
    - 安全性： [OAuth uri 的扩展](https://hl7.org/fhir/extension-oauth-uris.html)
    
 - FhirVersion (我们的代码需要此内容才能了解应将数据透视到哪个版本。 ) 

[https://www.hl7.org/fhir/stu3/capabilitystatement.html](https://www.hl7.org/fhir/stu3/capabilitystatement.html)有关此字段集的其他详细信息，请参阅。

## <a name="patient"></a>档案

下面是 "Argonaut" 患者档案字段子集的最少必填字段：

 - 名称。给定
 - 名称。家庭
 - 性别
 - BirthDate
 - MRN (标识符) 

除了 [Argonaut 字段](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-patient.html)外，还可以为患者应用提供出色的用户体验，还可以读取以下字段：

 - 名称。使用
 - 名称。前缀
 - [GeneralPractitioner]-GeneralPractitioner 参考应包含在患者资源 (仅限显示字段中) 

资源搜索在/Patient/_search 使用 POST 方法，并使用以下参数：

 - 标识号
 - 系列 = (搜索其系列名称包含该值的所有患者) 
 - 给定 =\<substring>
 - 出生日期 = (完全匹配) 
 - 性别 = (值是一个管理性别) 
 - \_计数 (应返回的最大结果数)  <br> 该响应应包含作为搜索和计数的结果返回的记录总数， \_ PatientsApp 将使用该计数来限制返回的记录数。
 - 标识符 =\<mrn>

目标是能够搜索和筛选患者，如下所示：

- ID：这是 FHIR 中的每个资源具有的资源 ID。
- MRN：这是临床人员将知道的患者的实际标识符。 我们理解此 MRN 基于 FHIR 中的标识符资源内的标识符类型。
- 名称
- Birthdate

请参阅下面的通话示例：

```
Request:
POST <fhir-server>/Patient/_search
Request Body:
given=ruth&family=black

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "meta": {
    "lastUpdated": "2019-01-14T23:44:45.052+00:00"
  },
  "type": "searchset",
  "total": 1,
  "link": [
    {
      "relation": "self",
      "url": <fhir-server>/Patient/_search"
    }
  ],
  "entry": [
    {
      "fullUrl": <fhir-server>/Patient/<patient-id>",
      "resource": {
        "resourceType": "Patient",
        "id": "<patient-id>",
        "meta": {
          "versionId": "1",
          "lastUpdated": "2017-10-18T18:32:37.000+00:00"
        },
        "text": {
          "status": "generated",
          "div": "<div>\n        <p>Ruth Black</p>\n      </div>"
        },
        "identifier": [
          {
            "use": "usual",
            "type": {
              "coding": [
                {
                  "system": "https://hl7.org/fhir/v2/0203",
                  "code": "MR",
                  "display": "Medical record number",
                  "userSelected": false
                }
              ],
              "text": "Medical record number"
            },
            "system": "http://hospital.smarthealthit.org",
            "value": "1234567"
          }
        ],
        "active": true,
        "name": [
          {
            "use": "official",
            "family": "Black",
            "given": [
              "Ruth",
              "C."
            ]
          }
        ],
        "telecom": [
          {
            "system": "phone",
            "value": "800-599-2739",
            "use": "home"
          },
          {
            "system": "phone",
            "value": "800-808-7785",
            "use": "mobile"
          },
          {
            "system": "email",
            "value": "ruth.black@example.com"
          }
        ],
        "gender": "female",
        "birthDate": "1951-08-23",
        "address": [
          {
            "use": "home",
            "line": [
              "26 South RdApt 22"
            ],
            "city": "Sapulpa",
            "state": "OK",
            "postalCode": "74066",
            "country": "USA"
          }
        ]
      },
      "search": {
        "mode": "match"
      }
    }
  ]
}
```

```
Request:
GET <fhir-server>/Patient/<patient-id>

Response:
{
  "resourceType": "Patient",
  "id": "<patient-id>",
  "identifier": [
    {
      "use": "usual",
      "type": {
        "coding": [
          {
            "system": "https://hl7.org/fhir/v2/0203",
            "code": "MR",
          }
        ],
        "text": "Medical record number"
      },
      "value": "1234567"
    }
  ],
  "name": [
    {
      "use": "official",
      "family": "Adams",
      "given": [ "Daniel", "X." ]
    }
  ],
  "gender": "male",
  "birthDate": "1925-12-23",
}
```

[https://hl7.org/fhir/stu3/patient.html](https://hl7.org/fhir/stu3/patient.html)有关此字段集的其他详细信息，请参阅。

## <a name="observation"></a>知识产权

以下是最少的必填字段，它们是 [Argonaut Vital-Signs 个人资料](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-vitalsigns.html)的子集。

 - 有效 (日期时间或期间) 
 - 编码代码
 - ValueQuantity 值

除了 Argonaut 字段外，还可以为患者应用提供出色的用户体验，还可以读取以下字段：

 - 代码编码。显示
 - ValueQuantity 单位

资源搜索使用 GET 方法和以下参数：

 - 患者 =\<patient id>
 - _sort =-日期
 - 类别 (我们将查询 "category = 重要标志" ) 以检索关键签名列表。

请参阅此通话示例：

```
Request:
GET <fhir-server>/Observation?patient=<patient-id>&category=vital-signs

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 20,
  "entry": [
    {
      "resource": {
        "resourceType": "Observation",
        "id": "<resource-id>",
        "category": [
          {
            "coding": [
              {
                "system": "https://hl7.org/fhir/observation-category",
                "code": "vital-signs"
              }
            ],
          }
        ],
        "code": {
          "coding": [
            {
              "system": "http://loinc.org",
              "code": "8867-4",
              "display": "heart_rate"
            }
          ]
        },
        "effectiveDateTime": "2009-04-08T00:00:00-06:00",
        "valueQuantity": {
          "value": 72.0,
          "unit": "{beats}/min",
          "system": "http://unitsofmeasure.org",
        }
      }
    },
    .
    .
    .
  ]
}
```

[https://www.hl7.org/fhir/stu3/observation.html](https://www.hl7.org/fhir/stu3/observation.html)有关此字段集的其他详细信息，请参阅。

## <a name="condition"></a>条件

下面是 [Argonaut 条件配置文件](http://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-condition.html)子集的最少必填字段。

 - 代码。编码 [0]。画面

除了 Argonaut 字段外，还可以为患者应用提供出色的用户体验，还可以读取以下字段：

 - AssertedDate
 - 严重性

资源搜索使用 GET 方法和以下参数：

 - 患者 =\<patient id>
 - _count =\<max results>

请参阅下面的此呼叫示例：

```
Request:
GET <fhir-server>/Condition?patient=<patient-id>&_count=10

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 2,
  "entry": [
    {
      "resource": {
        "resourceType": "Condition",
        "id": "<resource-id>",
        "code": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": "185903001",
              "display": "Needs influenza immunization",
            }
          ]
        },
        "severity": {
          "coding": [
            {
              "system": "http://snomed.info/sct",
              "code": "24484000",
              "display": "Severe"
            }
          ]
        },
        "assertedDate": "2018-04-04"
      }
    },
    .
    .
    .
  ]
}
```

[https://hl7.org/fhir/stu3/condition.html](https://hl7.org/fhir/stu3/condition.html)有关此字段集的其他详细信息，请参阅。

## <a name="encounter"></a>产生

以下是最少必填字段，这些字段是 [US Core](https://hl7.org/fhir/us/core/2018Jan/StructureDefinition-us-core-encounter.html) "必须有" 字段) 的一个子集。

 - 状态栏
 - 键入 [0]。编码 [0]。画面

此外，美国核心的以下字段会遇到配置文件的 "必须支持" 字段：

 - 句号。开始
 - 位置 [0]。位置。显示

资源搜索使用 GET 方法和以下参数：

 - 患者 =\<patient id>
 - _sort： desc =\<field ex. date>
 - _count =\<max results>

目标是能够检索患者的最后一个已知位置。 每个遇到的都引用一个位置资源。 该引用还应包含位置的显示字段。

[https://hl7.org/fhir/stu3/encounter.html](https://hl7.org/fhir/stu3/encounter.html)有关此字段集的其他详细信息，请参阅。

## <a name="allergyintolerance"></a>AllergyIntolerance

以下是最少的必填字段，它们是 [Argonaut AllergyIntolerance](https://www.fhir.org/guides/argonaut/r2/StructureDefinition-argo-allergyintolerance.html) 配置文件的子集：

 - 代码。文本
 - 代码。编码 [0]。画面
 - ClinicalStatus/VerificationStatus (我们同时阅读) 

除了 Argonaut 字段外，还可为患者应用提供出色的用户体验，还可以读取以下字段：

 - AssertedDate
 - 备注。文本
 - 被动
    -  (一个编码元素) 的物质
    -  (一个编码元素的表现形式) 

资源搜索使用 GET 方法和以下参数：

 - 患者 =  \<patient id>

请参阅下面的通话示例： 

```
Request:
GET <fhir-server>/AllergyIntolerance?patient=<patient-id>

Response:
{
  "resourceType": "Bundle",
  "id": "<bundle-id>",
  "type": "searchset",
  "total": 1,
  "entry": [
    {
      "resource": {
        "resourceType": "AllergyIntolerance",
        "id": "<resource-id>",
        "clinicalStatus": "active",
        "verificationStatus": "confirmed",
        "code": {
          "coding": [
            {
              "system": "http://rxnav.nlm.nih.gov/REST/Ndfrt",
              "code": "N0000175503",
              "display": "sulfonamide antibacterial",
            }
          ],
          "text": "sulfonamide antibacterial"
        },
        "assertedDate": "2018-01-01T00:00:00-07:00",
        "reaction": [
          {
            "manifestation": [
              {
                "coding": [
                  {
                    "system": "http://snomed.info/sct",
                    "code": "271807003",
                    "display": "skin rash",
                  }
                ],
                "text": "skin rash"
              }
            ],
          }
        ]
      }
    }
  ]
}
```

[https://hl7.org/fhir/stu3/allergyintolerance.html](https://hl7.org/fhir/stu3/allergyintolerance.html)有关此字段集的其他详细信息，请参阅。

## <a name="medication-request"></a>药物请求

以下是最少的必填字段，这些字段是 [美国核心药物请求档案](http://www.hl7.org/fhir/us/core/StructureDefinition-us-core-medicationrequest.html)的子集：

 - 药物。如果引用) ，则显示 (
 - 如果 CodableConcept) ，则为文本 (
 - AuthoredOn
 - 请求者代理。显示

除了 US 核心字段外，还可为患者应用提供出色的用户体验，还可以读取以下字段：

 - DosageInstruction[..].文本
 - 文本

资源搜索使用 GET 方法和以下参数：

 - 患者 =\<patient id>
 - _count =\<max results>

[https://www.hl7.org/fhir/medicationrequest.html](https://www.hl7.org/fhir/medicationrequest.html)有关此字段集的其他详细信息，请参阅。

## <a name="coverage"></a>内

以下是 "最少必填字段"，不包含在美国 Core 或 Argonaut 配置文件中：

 - 组合，至少一个元素具有
    - GroupDisplay
    - PlanDisplay
 - 试用期
 - SubscriberId

资源搜索使用 GET 方法和以下参数：

 - 患者 = \<patient id>

[https://hl7.org/fhir/stu3/coverage.html](https://www.hl7.org/fhir/medicationrequest.html)有关此字段集的其他详细信息，请参阅。
