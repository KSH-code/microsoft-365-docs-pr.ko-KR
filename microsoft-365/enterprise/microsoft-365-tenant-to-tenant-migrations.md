---
title: Microsoft 365 테넌트와 테넌트 마이그레이션
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-collaboration
- M365-subscription-management
- SPO_Content
search.appverid:
- MET150
- MOE150
ms.assetid: eb45fd8b-1d5d-4b0c-9c5a-479dbb176e7d
f1.keywords:
- NOCSH
description: Microsoft 365 테넌트 마이그레이션 방법에 대해 자세히 알아보습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f6e8277a7ca768db3a4a4acd2488859b7764a40c
ms.sourcegitcommit: 8b1bd7ca8cd81e4270f0c1e06d2b6ca81804a6aa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "50819717"
---
# <a name="microsoft-365-tenant-to-tenant-migrations"></a>Microsoft 365 테넌트와 테넌트 마이그레이션

합병, 인수, 매입 및 기타 시나리오에 대한 몇 가지 아키텍처 접근 방식이 있으며, 기존 Microsoft 365 테넌트는 새 테넌트로 마이그레이션할 수 있습니다. 대부분의 고객은 타사 도구를 사용하여 콘텐츠를 마이그레이션하는 등 Microsoft 컨설팅 서비스 또는 Microsoft 파트너와 협력하여 테넌트 마이그레이션을 진행합니다. 

테넌트 [대 테넌트](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf) 마이그레이션 아키텍처 모델을 사용하여 Microsoft 365 테넌트-테넌트 마이그레이션을 계획하는 방법과 마이그레이션 단계를 이해합니다.

[![테넌트와 테넌트 마이그레이션 모델](../media/solutions-architecture-center/msft-tenant-to-tenant-migration-thumb.png)](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf) 

이 모델을 PDF 형식으로 [다운로드하여](https://download.microsoft.com/download/b/a/1/ba19dfe7-96e2-4983-8783-4dcff9cebe7b/microsoft-365-tenant-to-tenant-migration.pdf) 편지형, 법률형 또는 타블로이드(11 x 17) 크기 용지에 인쇄합니다.

이 모델은 다음에 대한 섹션을 사용하여 계획하기 위한 지침과 시작 지점을 제공합니다.

- 비즈니스 시나리오를 아키텍처 접근 방식에 매핑
- 디자인 고려 사항

이 모델에는 다음에 대한 자세한 예제도 포함되어 있습니다.

- 단일 이벤트 마이그레이션 흐름
- 단계적 마이그레이션 흐름
- 테넌트 이동 또는 분할 흐름
