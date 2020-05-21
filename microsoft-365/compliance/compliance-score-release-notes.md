---
title: Microsoft 준수 점수 릴리스 정보
f1.keywords:
- NOCSH
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
description: 위험 평가를 간소화 하 고 자동화 하는 데 도움이 되는 M365 준수 센터의 기능인 Microsoft 준수 점수 (미리 보기)에 대 한 릴리스 정보 및 알려진 문제
ms.openlocfilehash: 1567921b8bd07b0fe4deda0bab6601898eed75a9
ms.sourcegitcommit: 56772bed89516cebc5eb370e292ccfbb4889cb38
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2020
ms.locfileid: "44330782"
---
# <a name="microsoft-compliance-score-preview-release-notes"></a>Microsoft 준수 점수 (미리 보기) 릴리스 정보

Microsoft 준수 점수가 공개 미리 보기를 통해 예정 된 기능 및 업데이트에 빠르게 액세스할 수 있습니다. 새로운 기능을 알아보려면이 페이지를 자주 확인 하세요.

준수 점수는 위험 기반 점수를 계산 하 여 준수 위험을 줄이는 데 도움이 되는 권장 작업을 완료 하는 과정을 측정 하는 [Microsoft 365 준수 센터](microsoft-365-compliance-center.md) 의 새로운 기능입니다.

## <a name="new-templates-for-assessments"></a>평가를 위한 새 서식 파일

평가를 위해 새롭게 미리 구성 된 서식 파일이 출시 되 면 준수 점수 (미리 보기)에 대 한 프로덕션 환경에 릴리스됩니다. 여기에서 [전체 서식 파일 목록을](compliance-score.md#templates)확인 하세요. 최근에 추가 된 서식 파일은 다음과 같습니다.

- 브라질 LGPD (일반 데이터 보호 법)
- DGISR (두바이 Information Security Resolution)
- IRAP/오스트레일리아 정부 ISM (미리 보기)
- ISO 27701:2019
- SOC 1
- SOC 2

## <a name="improvements-in-managing-assessments"></a>평가 관리의 향상 된 기능

2020 년 4 월의 최신 준수 관리자 릴리스에는 평가를 만들고 사용자 지정 하 고 업데이트를 유지 하는 방법을 단순화 하는 업데이트가 포함 되어 있습니다. 자세한 내용은 [준수 관리자 릴리스 정보](compliance-manager-release-notes.md) 를 참조 하세요.

## <a name="language-support"></a>언어 지원

이제 영어, 중국어 (간체), 중국어 (번체), 프랑스어, 독일어, 이탈리아어, 일본어, 한국어, 포르투갈어 (브라질), 러시아어, 스페인어 등의 언어에서 준수 점수를 사용할 수 있습니다.

## <a name="common-actions-will-synch-status-across-groups"></a>일반 작업을 통해 여러 그룹의 상태가 동기화 됨

조직에 여러 평가 그룹이 있는 경우 **기술** 작업의 동작 (즉, 전체 조직에 영향을 주는 작업)이 변경 되었습니다. 그룹 간 중복 된 작업은 하나의 단일 작업으로 결합 됩니다. 이 단일 작업에는 중복 버전의 업로드 된 모든 메모 및 증거가 포함 됩니다. 이렇게 변경 하면 기술 작업은 이제 동일한 그룹에 속해 있는 것 처럼 동작 합니다. 이제 하나의 그룹 또는 평가에서 작업에 대 한 변경 내용이 모든 인스턴스에 반영 됩니다.  **구현 상태**, **구현 날짜**, **테스트 상태**및 **테스트 날짜**에는   최신 업데이트가 반영 됩니다.

## <a name="compliance-score-relationship-to-compliance-manager"></a>준수 관리자와 규정 준수 점수 관계

준수 관리자에서 처리 되는 대부분의 함수는 이제 규정 준수 점수를 받을 수 있습니다. 그러나 일부 기능은 여전히 준수 관리자에 게 있습니다. 공개 미리 보기 동안 준수 점수 및 준수 관리자를 사용할 때는 다음 사항을 염두에 두어야 합니다.

- **평가 관리**: 사용자는 준수 점수에 평가 및 해당 상태 세부 정보를 볼 수 있습니다. 그러나 사용자는 준수 관리자 에서만 평가 관리 작업을 수행할 수 있습니다 ([지침 보기](working-with-compliance-manager.md#assessments)). 이러한 작업의 예는 다음과 같습니다.
    - 평가 만들기 및 복사
    - 평가 내보내기
    - 보관 평가
    - 보관 된 평가 보기
 - **평가를 위한 템플릿 만들기**: 
   - 사용자는 준수 관리자를 방문 하 여 새 템플릿을 만들고 기존 [템플릿을](working-with-compliance-manager.md#templates)수정 해야 합니다. 
   - 서식 파일을 만들 때는 **제품** 및 **인증** 에 대 한 차원을 모두 포함 하 여 서식 파일이 준수 점수에 표시 되도록 해야 합니다.
 - **사용 권한 설정**: 규정 준수 점수 준수 관리자에서 사용 권한을 갖고 있지 않은 사용자는 Microsoft 365 준수 센터에서 사용 권한을 설정 해야 합니다 ([자세한 내용](compliance-score-setup.md#set-user-permissions-and-assign-roles)).
- **데이터 전송**: 준수 관리자의 데이터를 포함 하는 조직에서는 규정 준수 점수에 해당 데이터가 표시 되며, 다른 방식으로도 마찬가지입니다.
- 준수 **관리자에 게 준수 점수**에 로그인: 사용자가 준수 점수에 로그인 되어 있고 준수 관리자에 게 이동 하는 링크를 선택 하는 경우 사용자는 다시 로그인 할 필요가 없습니다. 링크를 클릭 하면 브라우저에서 대화 상자를 표시 하는 새 탭이 열립니다. 머리글이 "이미 Microsoft 클라우드 서비스 고객" 인 최상위 섹션에서 계정에 로그인 하 여 준수 관리자에 게 자동으로 로그인 하는 **로그인** 단추를 선택 합니다.

## <a name="known-issues-in-compliance-score-preview"></a>준수 점수에 알려진 문제 (미리 보기)

다음 섹션에서는 향후 준수 점수에서 해결 해야 할 알려진 문제에 대해 설명 합니다.

### <a name="long-load-times-for-non-admin-users"></a>관리자가 아닌 사용자에 대 한 긴 로드 시간
준수 점수 관리자 역할 이외의 역할을 보유 하는 사용자는 로그인을 시도할 때 로드 시간이 오래 걸릴 수 있습니다. 브라우저를 새로 고치면이 문제가 해결 됩니다. ( [규정 준수 점수 역할](compliance-score-setup.md#set-user-permissions-and-assign-roles)에 대해 자세히 알아보세요.)

### <a name="supported-browsers"></a>지원되는 브라우저

- 최신 버전의 Microsoft Edge, Chrome 및 Safari가 지원 됩니다.
- 업데이트 된 데이터가 브라우저를 새로 고칠 때까지 표시 되지 않는 경우가 있습니다.
- Internet Explorer가 지원 되지 않습니다.
