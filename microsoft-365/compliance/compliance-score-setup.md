---
title: Microsoft 준수 점수 설정
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
description: 위험 평가를 간소화 하 고 자동화 하는 데 도움이 되는 Microsoft 규정 준수 점수에 대해 로그인 하 고 사용 권한을 설정 하 고 대시보드를 이해 하는 방법을 알아봅니다.
ms.openlocfilehash: 79e93a102107433ed2b493a56381bc60ca544157
ms.sourcegitcommit: 40e83b22b74db8e37d65e0988d4c11de3aa541b2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2020
ms.locfileid: "41021914"
---
# <a name="microsoft-compliance-score-preview-setup"></a>Microsoft 준수 점수 (미리 보기) 설치

## <a name="before-you-begin"></a>시작하기 전에

조직의 Microsoft 365 전역 관리자는 준수 점수에 액세스 하는 첫 번째 사용자가 될 수 있습니다. 다음에 규정 준수 점수를 처음 방문할 때 전역 관리자 로그인 및 아래에 설명 된 대로 사용자 권한을 설정 하는 것이 좋습니다.

## <a name="sign-in"></a>로그인

1. [Microsoft 365 준수 센터로](https://compliance.microsoft.com/) 이동 하 여 microsoft 365 전역 관리자 계정으로 **로그인** 합니다.
2. 왼쪽 탐색 창에서 **규정 준수 점수** 를 선택 합니다. 그런 다음 [준수 점수 대시보드를 점수와 함께](#understand-the-compliance-score-dashboard)확인 해야 합니다.

## <a name="set-user-permissions-and-assign-roles"></a>사용자 권한 설정 및 역할 할당

규정 준수 점수에는 RBAC (역할 기반 액세스 제어) 권한 모델이 사용 됩니다. 역할이 할당 된 사용자만 준수 점수에 액세스할 수 있으며, 각 사용자가 허용한 작업은 역할 유형에 따라 제한 됩니다.

### <a name="where-to-set-permissions"></a>사용 권한을 설정 하는 위치

조직의 전역 관리자는 Microsoft 365 준수 센터 또는 Azure Active Directory (Azure AD)에서 사용자 권한을 설정할 수 있습니다. 이러한 위치 중 하나에서 역할이 설정 되 면 사용자는 준수 관리자 및 준수 점수에 액세스할 수 있습니다.

기존 준수 관리자 역할은 준수 점수로 전송 **되지** 않습니다.  즉, 규정 준수 관리자에서 이전에 역할이 할당 된 경우 해당 역할은 준수 점수에 대 한 액세스 권한을 부여 하지 않습니다. 전역 관리자는 준수 점수에 액세스할 수 있도록 Microsoft 365 준수 센터 또는 Azure AD에서 사용자에 대 한 사용 권한 및 역할을 설정 해야 합니다.

### <a name="role-types"></a>역할 유형

아래 표에는 각 Microsoft 365 준수 센터 역할이 기존 준수 관리자 역할 및 각 역할에서 허용 하는 기능에 매핑되는 방식이 나와 있습니다.


| 사용자는 다음을 수행할 수 있습니다. | Microsoft 365 준수 센터 역할 | 준수 관리자 역할 | 
| :------------- | :-------------: | :------------: |
| **데이터를 읽을 수는 있지만 편집 하지 않음**| Azure AD 전역 읽기 권한자  | Azure AD 전역 읽기 권한자 | 
| **데이터를 읽을 수는 있지만 편집 하지 않음**| 보안 읽기 권한자 | 준수 관리자 읽기 권한자  | 
| **데이터 편집**| 준수 관리자 | 준수 관리자 참가자 | 
| **테스트 결과 편집**| 준수 관리자 | 준수 관리자 평가자 | 
| **평가, 서식 파일 및 테 넌 트 데이터 관리**| 준수 관리자<br>규정 준수 데이터 관리자<br>보안 관리자 | 준수 관리자 관리자 | 
| **사용자 할당**| 전역 관리자 | 포털 관리자 | 

> [!NOTE]
> 규정 준수 점수에서 준수 관리자로 이동 하 여 작업을 완료 하면 (예: 평가 관리) 브라우저가 새 탭을 열고 대화 상자가 표시 됩니다. 머리글이 "이미 Microsoft 클라우드 서비스 고객" 인 최상위 섹션에서 계정에 로그인 하 고 " **로그인** 하 여 액세스 준수 관리자를 선택 합니다. 자격 증명을 다시 입력할 필요가 없습니다.

### <a name="how-to-set-permissions-and-roles-in-the-microsoft-365-compliance-center"></a>Microsoft 365 준수 센터에서 사용 권한 및 역할을 설정 하는 방법

Microsoft 365 준수 센터에서 사용 권한을 설정 하려면 다음을 수행 합니다.

1. [Microsoft 365 준수 센터로](https://compliance.microsoft.com) 이동 하 여 전역 관리자 계정으로 로그인 합니다.
2. 왼쪽 탐색 창에서 **사용 권한을** 선택 합니다. 여기에서 역할을 확인 하 고 사용 권한을 할당할 수 있습니다.

## <a name="understand-the-compliance-score-dashboard"></a>준수 점수 대시보드 이해

준수 점수 대시보드는 현재 준수 상태를 한눈에 파악할 수 있도록 설계 되었습니다.

![준수 점수-대시보드](media/compliance-score-dashboard.png "준수 점수 대시보드")

### <a name="overall-compliance-score"></a>전반적인 준수 점수

주요 데이터 보호 표준 및 규정을 충족 하는 향상 된 작업을 완료 하는 데 필요한 점수를 기준으로 가장 중요 한 규정 준수 점수를 보여 줍니다.

처음으로 준수 점수가 제공 되는 경우 초기 점수는 기본 제공 되는 Microsoft 365 데이터 보호 기준을 기반으로 하며, 일반적인 업계 규정 및 표준을 포함 하는 컨트롤 집합입니다. 규정 준수 점수가 기존 Microsoft 365 솔루션의 시스템을 검사 하기 때문에 조직에서 현재 사용 하 고 있는 개인 정보 및 보안 설정을 기반으로 준수 상태를 초기에 평가할 수 있습니다.

조직과 관련 된 평가를 추가 하면 점수가 더 많이 포함 됩니다. [점수를 계산 하는 방법](compliance-score-methodology.md)에 대해 자세히 알아보세요.

### <a name="key-improvement-actions"></a>주요 개선 작업

이 섹션에서는 전체 준수 점수에 가장 큰 긍정적인 영향을 줄 수 있는 주요 향상 작업을 소개 합니다. 위험도가 높은 평가와 함께 완료 되지 않았거나 실패 한 작업이 나열 됩니다.

### <a name="solutions-that-affect-your-score"></a>점수에 영향을 주는 솔루션

이 섹션에서는 점수에 긍정적인 영향을 줄 수 있는 작업을 포함 하는 솔루션 및 각 솔루션에 포함 된 해결 되지 않은 향상 작업의 수를 보여 줍니다.

### <a name="compliance-score-breakdown"></a>규정 준수 점수 분석

이 섹션에서는 다음과 같은 두 가지 방법으로 점수에 대 한 자세한 내용을 확인할 수 있습니다.

- **범주**: "정보 보호" 또는 "장치 관리"와 같은 데이터 보호 범주 내의 전체 점수 비율을 표시 합니다.
- **평가**: GDPR 또는 NIST 800-53와 같은 특정 준수 및 데이터 보호 표준, 규정 또는 법규에 대 한 평가 관리에서 진행률을 관리할 비율을 보여 줍니다.

### <a name="filtering-your-dashboard-view"></a>대시보드 보기 필터링

대시보드 보기를 필터링 하 여 특정 규정과 표준, 솔루션, 작업 유형, [설정 하는 평가 그룹](working-with-compliance-manager.md#groups)또는 데이터 보호 범주와 관련 된 항목만 볼 수 있습니다. 이 방식으로 보기를 필터링 하면 대시보드의 점수가 필터링 되며, 필터 조건을 기준으로 하 여 총 가능한 점수를 얻은 점의 수를 보여 줍니다.

필터를 적용 하려면

1. 대시보드의 오른쪽 위에 있는 **필터** 를 선택 합니다.
2. 플라이 아웃 **필터** 창에서 필터 조건을 선택한 다음 **적용**을 선택 합니다.

필터가 적용 되 면 점수가 실시간으로 조정 된 것을 볼 수 있습니다. 준수 점수 비율 및 분석 정보 및 개선 작업 및 솔루션은 필터 기준에 포함 된 데이터에만 영향을 받습니다. 규정 준수 점수를 로그 아웃 하는 경우 필터링 된 보기는 다시 로그인 할 때 유지 됩니다.

필터를 제거 하려면

- 준수 점수 위의 **적용 된 필터** 제목에서 제거할 개별 필터 옆에 있는 **X** 를 선택 합니다. 사용자나
- 대시보드의 오른쪽 위에 있는 **필터** 를 선택 하 고 **필터 지우기를**선택 합니다.

## <a name="next-step"></a>다음 단계

[규정 준수 점수 관련 작업](working-with-compliance-score.md) 을 방문 하 여 점수 개선을 위한 작업을 수행 하는 방법에 대 한 워크플로를 파악할 수 있습니다.