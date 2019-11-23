---
title: Microsoft 준수 관리자 릴리스 정보
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 준수 관리자는 Microsoft Service Trust Portal의 무료 워크플로 기반 위험 평가 도구입니다. 준수 관리자를 사용 하면 Microsoft 클라우드 서비스와 관련 된 규정 준수 활동을 추적, 할당 및 확인할 수 있습니다.
ms.openlocfilehash: 1f233a6bc19f4a7afa495f49ad77e39e496c1dc5
ms.sourcegitcommit: fb3815ee186b2b3ec790ee32a9d7b1628d623b0b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "39202169"
---
# <a name="release-notes-for-compliance-manager-preview"></a>준수 관리자를 위한 릴리스 정보 (미리 보기)

준수 관리자의 공개 미리 보기는 예정 된 기능과 업데이트에 빠르게 액세스할 수 있도록 합니다.

[서비스 트러스트 포털](https://servicetrust.microsoft.com) 에서 업데이트 된 [준수 관리자](https://servicetrust.microsoft.com/ComplianceManager) 도구를 사용 하 여 Microsoft 클라우드 서비스와 관련 된 규정 준수 활동을 추적, 할당 및 확인할 수 있습니다.

## <a name="whats-new-in-compliance-manager-preview"></a>준수 관리자의 새로운 기능 (미리 보기)

- **준수 관리자에 대 한 역할 기반 액세스:** 기본 **게스트 액세스** 역할이 제거 되었습니다. 사용자가 준수 관리자에 액세스 하려면 전역 관리자가 각 사용자에 게 [권한을 할당](compliance-manager-overview.md#permissions)해야 합니다.

- **업데이트 된 준수 점수**: 준수 점수가 이제 Microsoft 관리 작업에 대 한 점수를 포함 합니다. 결과적으로 점수가 증가 합니다.

- **작업 항목:** 작업 항목은 이제 개별 항목이 며 Microsoft 보안 점수 그래프 API의 많은 원격 분석 컬렉션을 포함 합니다. 가능한 경우 기술 작업 권장 사항에는 이제 Office 365 서비스의 해당 구성 페이지에 대 한 링크가 포함 되어 있습니다.

- **테 넌 트 관리:** 준수 관리자의 새 데이터 요소를 관리 하기 위한 새 인터페이스 (미리 보기):
    - **차원:** 필터의 사용자 지정 피벗을 만들 수 있는 템플릿, 평가 및 작업 항목에 대 한 메타 데이터를 보고, 추가 하 고, 사용자 지정 합니다.
    - **소유자:** 각 작업 항목의 소유자를 지정 합니다.
    - **고객 작업:** 준수 관리자 (미리 보기)에 포함 된 작업 항목의 전체 목록과 보안 점수와 통합 된 작업 항목에 대 한 보안 점수 모니터링 사용/사용 안 함을 관리 합니다.

## <a name="known-issues-in-compliance-manager-preview"></a>준수 관리자의 알려진 문제 (미리 보기)

다음 섹션에서는 이후의 준수 관리자 릴리스에서 해결 해야 할 알려진 문제에 대해 설명 합니다.

### <a name="compliance-score"></a>준수 점수

- **범위 내에 없는**것으로 표시 된 작업 항목의 경우에는 작업 항목에 할당 되는 점수가 준수 점수 계산에서 제외 되지 않습니다. **범위에 없는** 것으로 표시 된 작업 항목은 준수 점수가 증가 하지 않습니다.

### <a name="secure-score"></a>보안 점수

- 특정 Microsoft 365 및 Office 365 구독의 일부 작업 항목에는 보안 점수 결과를 사용할 수 없습니다. 이러한 경우에는 보안 점수 결과를 **검색할** 수 없습니다.
- 경우에 따라 해당 정책에 대 한 보안 점수 결과가 반환 되 고 작업 항목이 완료 되지 않을 수 있습니다.
- 새 테 넌 트의 경우 모든 작업에 대 한 보안 점수 업데이트가 자동으로 켜 집니다. 전역 관리자는 보안 점수 연속 업데이트 스위치를 off로 설정 하 여 모든 작업에 대 한 업데이트를 해제할 수 있습니다.
  - **참고**: 조직에서 Microsoft 365 또는 Office 365를 처음 배포 하는 경우 보안 점수가 약 7 일인 경우에만 데이터를 완벽 하 게 수집 하 고 해당 점수를 요소에 활용할 수 있습니다. 이 시간 동안에는 보안 점수 연속 업데이트 스위치를 **Off** 로 설정 하 고, 수동으로 작업을 수행 하도록 **설정 하면 점수를 받을 수** 있습니다. 초기 7 일이 지나면 보안 점수 연속 업데이트를 다시 설정 하면 해당 시점부터의 지속적인 모니터링이 가능 합니다.
- 보안 점수 업데이트가 설정 되 면 작업의 테스트 날짜가 모니터링을 반영 하도록 업데이트 되지 않지만 작업은 보안 점수에 의해 적극적으로 모니터링 됩니다.
- 새 평가를 만들 때 점수에는 Microsoft가 관리 하는 제어 점수와 보안 점수 통합이 자동으로 포함 됩니다.
- 보안 점수 통합에서 지원 되지 않는 모든 작업은 수동으로 구현할 수 있습니다. 수동 구현은 해당 작업 그룹의 점수를 발생 시키는 기능을 합니다.

### <a name="microsoft-managed-controls"></a>Microsoft 관리 컨트롤

- Microsoft 관리 컨트롤에 대 한 테스트 날짜는 평가에 포함 된 경우에도 UI에 나타나지 않습니다. 테스트 날짜 정보를 보려면 평가를 내보내야 합니다.

### <a name="customization"></a>사용자 지정

- 사용자 지정 컨트롤을 추가 하면 기존 컨트롤 패밀리에 새 컨트롤을 추가할 수 있지만 새 컨트롤 패밀리를 추가할 수는 없습니다.
- 이 릴리스는 작업 항목을 연결 하거나 평가에 작업 항목 또는 컨트롤을 추가 하는 것을 지원 하지 않습니다.
- 사용자 지정 동작을 만드는 경우에는 편집 하거나 삭제할 수 없습니다.

### <a name="control-families-not-shown-in-assessments"></a>평가에 표시 되지 않는 컨트롤 패밀리

- 템플릿을 가져올 때 해당 서식 파일을 기반으로 하는 모든 평가는 서식 파일에 포함 된 모든 컨트롤 패밀리를 반영 합니다. 그러나 서식 파일에 새 컨트롤 패밀리를 추가 하는 경우 기존 평가에 변경 내용이 반영 되지 않습니다. 업데이트 된 서식 파일에서 만든 새 평가에만 변경 내용이 적용 됩니다.

### <a name="templates"></a>템플릿

- 서식 파일을 만들 때는 **제품** 및 **인증** 에 대 한 차원을 모두 포함 하 여 서식 파일이 준수 점수에 표시 되도록 해야 합니다.
- 보관 된 템플릿은 편집이 가능 하 고 편집이 불가능 합니다.
- 잠긴 템플릿을 사용 하면 평가를 수행 하지 않아야 할 때 평가할 수 있습니다. 템플릿을 잠그면 평가를 만드는 데 사용 되는 것을 방지 하기 위한 것입니다.

### <a name="export"></a>내보내기

- 서식 파일 내보내기가 **가져오기** 또는 **보류 중인 승인**으로 설정 된 경우 JSON으로 내보내기 작업이 실패 합니다.

### <a name="supported-browsers"></a>지원되는 브라우저

- 최신 버전의 Microsoft Edge, Chrome 및 Safari가 지원 됩니다.
- 브라우저를 새로 고칠 때까지 업데이트 된 데이터가 표시 되지 않는 경우가 있습니다.
- Microsoft Edge의 preview 버전은 지원 되지 않지만 알려진 문제는 없습니다.
- Internet Explorer가 지원 되지 않습니다.

### <a name="session-timeout"></a>세션 제한 시간

- 세션 시간이 초과 되 면 "문제가 발생 했습니다." 오류가 나타날 수 있습니다. 문제를 해결 하려면 [준수 관리자로](https://servicetrust.microsoft.com/ComplianceManager) 이동 하 여 다시 로그인 합니다.
 
### <a name="language-support"></a>언어 지원

- 모든 언어는 일부 웹 페이지에서 지원 되지 않습니다. 로컬 언어가 지원 되지 않으면 영어 (미국)로 확인 합니다.