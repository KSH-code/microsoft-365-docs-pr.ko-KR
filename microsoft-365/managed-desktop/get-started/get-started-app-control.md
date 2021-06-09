---
title: 앱 제어 시작하기
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 431e6cb3b8d7ab7e1dd317918fab4821889c7d4e
ms.sourcegitcommit: 583fd1ac1f385c58b93bda648907a1bd8e0a1950
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2020
ms.locfileid: "45430462"
---
# <a name="get-started-with-app-control"></a>앱 제어 시작하기

환경에서 앱 제어를 사용하도록 설정하기 전에 앱 [](../service-description/app-control.md) 제어를 구현하는 방법과 역할 및 Microsoft Managed Desktop 검토하고 이해해야 합니다.

Microsoft Managed Desktop 기본 정책을 확보하는 데 까다로워진 측면을 관리하여 앱 제어를 간소화합니다. IT 관리자는 테스트 링에서 앱을 계속 테스트하고 경고 또는 오류에 대한 로그를 검토해야 합니다. 앱에 면제가 필요한 경우 요청을 제출하거나, Microsoft Managed Desktop 먼저 검색하는 사람에 따라 Operation을 구성할 수 있습니다.

## <a name="initial-deployment-of-apps"></a>앱의 초기 배포

앱을 처음 배포할 때 Microsoft Managed Desktop 동작을 평가해야 합니다. 앱 제어를 사용하도록 설정하는 정확한 단계는 디바이스가 환경에 이미 배포되어 있는지 여부에 따라 결정됩니다.

### <a name="devices-not-yet-in-use"></a>아직 사용되지 않는 장치

아직 사용 중이지 않은 디바이스가 없는 경우 앱 제어를 켜고 Microsoft Managed Desktop 작업에서 서비스 티켓을 하세요. 작업은 이 일정에 따라 배포 그룹에 정책을 점진적으로 배포합니다.

|배포 그룹  |정책 유형  |출시 시기  |
|---------|---------|---------|
|테스트     |  감사       |  0일       |
|첫 번째     | Enforced        | 1일        |
|빠르기     | Enforced        |  2일       |
|광범위     | Enforced        |  3일       |

언제든지 다른 서비스 요청을 열어 이 배포의 일부를 일시 중지하거나 롤백할 수 있습니다.

### <a name="devices-already-in-use"></a>이미 사용 중인 장치

이미 하나 이상의 Microsoft Managed Desktop 장치를 사용 중이면 다음 단계를 수행합니다.

1. 앱 제어를 Microsoft Managed Desktop Operations를 사용하여 서비스 티켓을 개표합니다. 운영은 모든 장치에 감사 [정책을](../service-description/app-control.md#audit-policy) 배포합니다.
2. [응용 프로그램을](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) 테스트하여 차단된 응용 프로그램이 없는지 테스트합니다. 응용 프로그램이 차단될 경우 서명자 요청을 [열 수 있습니다.](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer) 
3. 테스트(결과)를 완료한 후 보류 중인 서명자 요청에 대해 알리고 Operations에 알릴 수 있습니다. 작업은 이 일정에 따라 배포 그룹에 정책을 점진적으로 배포합니다.

|배포 그룹  |정책 유형  |출시 시기  |
|---------|---------|---------|
|테스트     |  감사       |  0일       |
|첫 번째     | Enforced        | 1일        |
|빠르기     | Enforced        |  일시 중지, 요청에 대한 출시       |
|광범위     | Enforced        |  일시 중지, 요청에 대한 출시       |

언제든지 다른 서비스 요청을 열어 이 배포의 일부를 일시 중지하거나 롤백할 수 있습니다.



