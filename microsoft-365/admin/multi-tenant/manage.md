---
title: 여러 테넌트 관리
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- admindeeplinkMAC
search.appverid:
- BCS160
- MET150
- MOE150
description: 단일 위치에서 테넌트를 관리할 수 있는 기능을 제공 하는 테넌트 전환기 및 다중 테넌트 보기를 사용하는 방법을 학습합니다.
ms.openlocfilehash: d30d352376bb10e142d478e21ddd550577f536ca
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60195176"
---
# <a name="multi-tenant-management"></a>다중 테넌트 관리

다중 테넌트 관리는 파트너 Microsoft 365 한 위치에서 관리하는 모든 테넌트를 관리할 수 있도록 하는 통합된 관리 형식을 제공합니다. 여러 테넌트를 관리하는 파트너인 경우 다음을 할 수 있습니다.

- 관리하는 테넌트 간에 빠르게 이동할 수 있습니다.
- 여러 테넌트에서 서비스 상태, 제품 및 청구를 평가합니다.
- 모든  테넌트 페이지에서 모든 테넌트의 서비스 상태, 열려 있는 서비스 요청, 제품 및 청구, 해당 테넌트의 사용자 수를 빠르게 볼 수 있습니다.

## <a name="move-between-tenants"></a>테넌트 간 이동

1. 에서 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 관리 센터</a>를 선택합니다.

    :::image type="content" source="../../media/macorgswitcher.png" alt-text="다중 테넌트 전환기.":::

- **테넌트 전환기 에서** 관리하는 테넌트 간에 빠르게 이동할 수 있습니다.

    :::image type="content" source="../../media/yourtenantslist.png" alt-text="검색 기능이 있는 테넌트 목록":::

## <a name="view-all-tenants-page"></a>모든 테넌트 보기 페이지

1. 왼쪽 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 관리 센터</a>에서 모든 **테넌트 를 선택합니다.**
- 모든 **테넌트 페이지에서** 다음을 할 수 있습니다.
  - 서비스 상태 평가
  - 라이선스 사용 검토
  - 관리하려는 테넌트 검색 또는 선택
  - 가장 자주 방문하는 테넌트도 목록 맨 위에 고정할 수 있습니다.

테넌트가 즐겨찾기로 표시된 경우 상태 세부 정보를 즉시 볼 수 있도록 자동으로 확장됩니다.

## <a name="view-service-health-for-all-accounts"></a>모든 계정에 대한 서비스 상태 보기

서비스 상태 보기에는 인시던트 또는 권고가 테넌트에 영향을 주는지가 표시됩니다. 관리되는 테넌트의 수가 영향을 받는지 알 수 있습니다.

1. 다중 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 관리 센터</a>보기에서 서비스 상태 를 **선택합니다.**
2. 서비스 상태 **페이지** 집계 보기에서 총 인시던트 수, 관리되는 테넌트에 영향을 주는 총 권고 수 및 활성 인시던트가 있는 서비스 수를 볼 수 있습니다. 인시던트 및 권고의 영향을 받는 테넌트의 수를 볼 수도 있습니다.

    - 필터 옵션을 사용하여 문제 유형 또는 서비스별로 문제를 볼 수 있습니다.

    - 모든 서비스 또는 **모든** 문제 탭에서 문제를 **검토할** 수 있습니다.

    :::image type="content" source="../../media/multitenant-servicehealth.png" alt-text="다중 테넌트 서비스 상태 페이지.":::
1. 개요 탭에서  인시던트에 대한 자세한 정보를 확인하려면 모든 서비스 또는 모든 문제 탭에서 인시던트 **선택**  영향을 **받는 테넌트 탭을** 선택하여 영향을 받는 테넌트 목록을 얻습니다.

    :::image type="content" source="../../media/tenantsaffected.png" alt-text="서비스 상태 문제의 영향을 받는 테넌트 목록입니다.":::

영향을 받는 테넌트 목록은 관리자가 지원 팀과 공유할 수 있도록 CSV 형식으로 내보낼 수 있습니다.

## <a name="view-a-single-tenant-in-the-microsoft-365-admin-center"></a>테넌트에서 단일 테넌트 Microsoft 365 관리 센터

모든 테넌트 Microsoft 365 관리 센터 테넌트에 대한 목록으로 **돌아올 수** 있습니다.

1. 모든 **테넌트 페이지에서** 관리 센터를 볼 테넌트 이름을 선택합니다.
2. 해당 테넌트의 관리 센터로 연결됩니다.