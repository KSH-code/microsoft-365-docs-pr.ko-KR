---
title: Microsoft 준수 점수 릴리스 정보
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
ms.openlocfilehash: d46e8a621b6f4daa1275a78b5cc1e6917e0a997c
ms.sourcegitcommit: 3eae8fe39cea912d29e211a1c9fd035d6b606f91
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2019
ms.locfileid: "38793642"
---
# <a name="microsoft-compliance-score-preview-release-notes"></a>Microsoft 준수 점수 (미리 보기) 릴리스 정보

Microsoft 준수 점수가 공개 미리 보기를 통해 예정 된 기능 및 업데이트에 빠르게 액세스할 수 있습니다.

준수 점수는 위험 기반 점수를 계산 하 여 준수 위험을 줄이는 데 도움이 되는 권장 작업을 완료 하는 과정을 측정 하는 [Microsoft 365 준수 센터](microsoft-365-compliance-center.md) 의 새로운 기능입니다.

## <a name="compliance-score-and-compliance-manager-relationship"></a>준수 점수 및 준수 관리자 관계

준수 관리자에서 처리 되는 대부분의 준수 기능은 이제 규정 준수 점수를 받을 수 있습니다. 그러나 일부 기능은 여전히 준수 관리자 에게만 존재 하며, 공용 미리 보기 기간 동안 준수 관리자의 일부 이전 기능은 변경 되었습니다. 

공개 미리 보기 동안 준수 점수 및 준수 관리자를 사용할 때는 다음 사항을 염두에 두어야 합니다.

- **평가 관리**: 사용자는 준수 점수에 평가 및 해당 상태 세부 정보를 볼 수 있습니다. 그러나 사용자는 준수 관리자의 평가 관리 작업 ([지침 보기](working-with-compliance-manager.md#assessments)) 및 작업을 수행할 수 있으며 다음으로 제한 됩니다.
    - 새 평가를 업로드 하지만 기존 평가는 수정 하지 않습니다. 기존 평가를 수정 해야 하는 경우 새 템플릿을 업로드 해야 합니다.
    - 평가 내보내기
    - 보관 평가
    - 보관 된 평가 보기
 - **평가를 위한 템플릿 만들기**: 
   - 사용자는 준수 관리자를 방문 하 여 새 템플릿을 만들고 기존 템플릿을 내보내야 합니다. 
   - 기존 템플릿은 사용자 지정할 수 없습니다. [준수 관리자의 서식 파일 관리](working-with-compliance-manager.md#templates)에 대 한 지침을 읽으십시오.
   - 서식 파일을 만들 때는 **제품** 및 **인증** 에 대 한 차원을 모두 포함 하 여 서식 파일이 준수 점수에 표시 되도록 해야 합니다.
 - **사용 권한 설정**: 규정 준수 점수 준수 관리자에서 이전에 사용 권한을 부여 받지 않은 사용자는 Microsoft 365 준수 센터에서 사용 권한을 설정 해야 합니다. 규정 준수 관리자에서 역할이 이전에 설정 된 사용자는 준수 점수 작업을 할 때 같은 수준의 액세스를 사용할 수 있습니다.
- **데이터 전송**: 규정 준수 관리자에 데이터가 있는 조직은 규정 준수 점수에 해당 하는 데이터를 확인 하 고 그 반대의 경우도 마찬가지입니다.
- 준수 **관리자에 게 준수 점수**에 로그인: 사용자가 준수 점수에 로그인 되어 있고 준수 관리자에 게 연결 되는 링크를 선택 하는 경우 사용자가 다시 로그인 할 필요가 없습니다. 링크를 클릭 하면 브라우저에서 대화 상자를 표시 하는 새 탭이 열립니다. 머리글이 "이미 Microsoft 클라우드 서비스 고객" 인 최상위 섹션에서 계정에 로그인 하 여 준수 관리자에 게 자동으로 로그인 하는 **로그인** 단추를 선택 합니다.

## <a name="known-issues-in-compliance-score-preview"></a>준수 점수에 알려진 문제 (미리 보기)

다음 섹션에서는 향후 준수 점수에서 해결 해야 할 알려진 문제에 대해 설명 합니다.

### <a name="launch-now-links-in-certain-improvement-actions"></a>특정 개선 작업의 지금 시작 링크

특정 개선 작업에서 구현 명령 아래에 표시 되는 **지금 시작** 링크를 선택 하면 오류가 발생 합니다. SharePoint 관리 센터에 적합 한 대상에 액세스 하려면 다음 단계를 수행 합니다.

1. [Microsoft 365 관리 센터로](https://admin.microsoft.com)이동 합니다.
2. 왼쪽 탐색 메뉴에서 **모두 표시**를 선택 합니다.
3. **관리 센터** 에서 **SharePoint**를 선택 합니다.

다음은 모두 **보호 정보** 범주에 상주 하는 영향을 받는 향상 작업입니다.
  - SharePoint 라이브러리에 암호화 적용
  - SharePoint Online의 데이터 분류
  - 만료 되도록 외부 공유 링크 구성
  - 문서 라이브러리에 대 한 버전 관리 사용

### <a name="long-load-times-for-non-admin-users"></a>관리자가 아닌 사용자에 대 한 긴 로드 시간
준수 점수 관리자 역할 이외의 역할을 보유 하는 사용자는 로그인을 시도할 때 로드 시간이 오래 걸릴 수 있습니다. 브라우저를 새로 고치면이 문제가 해결 됩니다. ( [규정 준수 점수 역할](compliance-score-setup.md#set-user-permissions-and-assign-roles)에 대해 자세히 알아보세요.)

### <a name="supported-browsers"></a>지원되는 브라우저

- 최신 버전의 Microsoft Edge, Chrome 및 Safari가 지원 됩니다.
- 브라우저를 새로 고칠 때까지 업데이트 된 데이터가 표시 되지 않는 경우가 있습니다.
- Microsoft Edge의 preview 버전은 지원 되지 않지만 알려진 문제는 없습니다.
- Internet Explorer가 지원 되지 않습니다.
 
### <a name="language-support"></a>언어 지원

- 준수 점수는 미국 영어로만 제공 됩니다.