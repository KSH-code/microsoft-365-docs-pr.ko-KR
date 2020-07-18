---
title: 앱 컨트롤 시작
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
ms.openlocfilehash: 12df7b074019ea47f2e293b71c6b0b25fe46f66f
ms.sourcegitcommit: 63887d742c59cc660fc85537b335e98a9dc66fbe
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/18/2020
ms.locfileid: "45170712"
---
# <a name="get-started-with-app-control"></a>앱 컨트롤 시작

사용자 환경에서 앱 컨트롤을 사용 하도록 설정 하기 전에 [Microsoft Managed Desktop이이를 구현 하는 방법](../service-description/app-control.md) 및 사용자의 역할과 책임을 검토 하 고 이해 해야 합니다.

Microsoft Managed Desktop은 보안 기본 정책 가져오기에 대 한 보다 까다로운 측면을 고려 하 여 앱 제어를 간소화 합니다. IT 관리자는 여전히 테스트 링에서 앱을 테스트 하 고 경고 또는 오류에 대 한 로그를 검토 해야 합니다. 앱에 제외가 필요한 경우에는 요청을 파일 하거나 먼저 검색 한 데스크톱 작업을 확인할 수 있습니다.

## <a name="initial-deployment-of-apps"></a>초기 앱 배포

앱을 처음 배포할 때 Microsoft Managed Desktop은 현재 동작을 평가 해야 합니다. 앱 컨트롤을 사용 하도록 설정 하는 정확한 단계는 장치를 환경에 이미 배포 했는지 여부에 따라 달라 집니다.

### <a name="devices-already-in-use"></a>장치가 이미 사용 중입니다.

이미 하나 이상의 Microsoft Managed Desktop 장치를 사용 하 고 있는 경우 다음 단계를 수행 합니다.

1. 앱 제어권을 켜시겠습니까 Microsoft Managed Desktop 작업을 사용 하 여 서비스 티켓을 엽니다. 작업은 모든 장치에 [감사 정책을](../service-description/app-control.md#audit-policy) 배포 합니다.
2. [응용 프로그램을 테스트](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) 하 여 차단 된 프로그램이 있는지 확인 합니다. 응용 프로그램이 차단 되 면 [서명자 요청](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer)을 엽니다. 
3. 테스트를 완료 한 후에는 작업을 알리고 보류 중인 서명자 요청을 기록 합니다. 작업에서는 다음 일정에 따라 배포 그룹에 정책을 점진적으로 배포 합니다.

|배포 그룹  |정책 유형  |출시 시기  |
|---------|---------|---------|
|테스트     |  감사       |  일 0       |
|가장     | Enforced        | 1일        |
|신속한     | Enforced        |  3일       |
|폭     | Enforced        |  7일       |

롤아웃 중에 언제 든 지이 배포의 일부를 일시 중지 하거나 롤백하는 다른 서비스 요청을 열 수 있습니다.

### <a name="devices-not-yet-in-use"></a>아직 사용 되지 않은 장치

아직 사용 중인 장치가 없는 경우 앱 제어권을 켜시겠습니까 Microsoft Managed Desktop 작업을 사용 하 여 서비스 티켓을 엽니다. 작업에서는 다음 일정에 따라 배포 그룹에 정책을 점진적으로 배포 합니다.

|배포 그룹  |정책 유형  |출시 시기  |
|---------|---------|---------|
|테스트     |  감사       |  일 0       |
|가장     | Enforced        | 1일        |
|신속한     | Enforced        |  3일       |
|폭     | Enforced        |  7일       |

롤아웃 중에 언제 든 지이 배포의 일부를 일시 중지 하거나 롤백하는 다른 서비스 요청을 열 수 있습니다.

