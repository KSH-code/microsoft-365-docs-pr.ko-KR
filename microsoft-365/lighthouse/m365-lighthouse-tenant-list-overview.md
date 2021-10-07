---
title: Microsoft 365 Lighthouse 목록 개요
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: 테넌트 목록을 사용하는 MSP(관리 Microsoft 365 Lighthouse 공급자)의 경우 테넌트 목록에 대해 자세히 알아보면 됩니다.
ms.openlocfilehash: bff85a523d55cfeeacffc3024bb733a5c3fe2eb5
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60170106"
---
# <a name="microsoft-365-lighthouse-tenant-list-overview"></a>Microsoft 365 Lighthouse 목록 개요

> [!NOTE]
> 이 문서에 설명된 기능은 미리 보기에 있으며, 변경될 수 있으며, 요구 사항을 충족하는 파트너만 사용할 수 [있습니다.](m365-lighthouse-requirements.md) 조직에 등록이 Microsoft 365 Lighthouse 에 [등록을 Microsoft 365 Lighthouse.](m365-lighthouse-sign-up.md)

Microsoft 365 Lighthouse 테넌트 목록은 Lighthouse에 대한 테넌트 온보더링 상태를 포함하여 계약을 체결한 다른 테넌트에 대한 정보를 제공합니다. 또한 테넌트 목록에 테넌트에 태그를 지정하여 Lighthouse 전체에 다양한 필터를 제공하고 드릴다운하여 특정 테넌트 및 배포 계획 상태에 대해 자세히 알아보는 데 사용할 수 있습니다.

테넌트가 [Lighthouse](m365-lighthouse-requirements.md)온보더링 요구 사항을 충족하면 해당 상태가 테넌트 목록에 **활성으로** 표시됩니다.

Lighthouse의 테넌트 목록에 액세스하려면 왼쪽 탐색 창에서 테넌트를 선택하여 테넌트 페이지를 여십시오. 

## <a name="tenant-status"></a>테넌트 상태

다음 표에는 다양한 상태 메시지와 그 의미가 표시됩니다.<br><br>

| 상태 메시지 | 설명 |
|--|--|
| 활성 | 온보더링 및 데이터 흐름이 시작된 경우 |
| In process | 테넌트가 검색되지만 완전히 온보드된 것은 아니며 검색된 테넌트입니다. |
| 부적임, DAP | DAP(위임된 관리자 권한) 설정이 필요합니다. |
| 부적정, 사용자 수 | 테넌트에 허용되는 것보다 많은 사용자가 있습니다. |
| 부적임, 라이선스 | 테넌트에는 필수 라이선스가 없습니다. |
| 부적임, 계약 유형 | CSP(클라우드 솔루션 공급자) 계약이 필요합니다. |
| 비활성 | 테넌트가 더 이상 활성 상태입니다. |

테넌트의 비활성화가 완료되면 Lighthouse가 비활성화 프로세스를 완료하는 동안 테넌트에 대한 작업을 취할 수 없습니다. 비활성화가 완료될 때 최대 48시간이 걸릴 수 있습니다.

테넌트를 다시 활성화하기로 결정한 경우 데이터가 다시 그려지기까지 최대 48시간이 걸릴 수 있습니다.

## <a name="tenant-tags"></a>테넌트 태그

Lighthouse 내에서 사용자 지정 레이블을 사용하여 고객 테넌트에 태그를 지정할 수 있습니다. 이러한 태그를 사용하여 테넌트를 구성할 수 있으며 관련 고객 테넌트 집합에 사용할 수 있는 기존 보기 및 정보를 쉽게 필터링할 수도 있습니다. 테넌트 페이지에서 태그와 태그가 할당된 테넌트도 관리할 수 있습니다.

## <a name="related-content"></a>관련 콘텐츠

[요구 사항](m365-lighthouse-requirements.md) Microsoft 365 Lighthouse(문서)\
[Microsoft 365 Lighthouse FAQ(문서)](m365-lighthouse-faq.yml)