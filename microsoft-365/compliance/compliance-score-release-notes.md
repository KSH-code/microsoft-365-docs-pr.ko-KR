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
ms.openlocfilehash: 6678ec03d2cd87a97244acaa55a15483d78dd632
ms.sourcegitcommit: 3ddcf08e8deec087df1fe524147313f1cb12a26d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2020
ms.locfileid: "45022195"
---
# <a name="microsoft-compliance-score-preview-release-notes"></a>Microsoft 준수 점수 (미리 보기) 릴리스 정보

**이 문서의 내용** 이 페이지에는 새로운 기능에 대 한 초기 액세스를 제공 하는 [Microsoft 준수 점수](compliance-score.md)의 **새로운** 공개 미리 보기 기능이 나와 있습니다.

## <a name="assessment-creation-and-management-functionality"></a>평가 만들기 및 관리 기능

6 월 2020 릴리스는 사용자가 규정 준수 점수에서 직접 평가를 만들고 삭제 하 고 관리 하는 기능을 추가 합니다. 이전에는 모든 평가 관리가 준수 관리자에 게 있었습니다. 규정 준수 점수에 대 한 평가를 만들거나 수정 하면 업데이트가 준수 관리자에 게 표시 됩니다. 마찬가지로 준수 관리자에서 수행 하는 모든 평가 작업은 준수 점수를 표시 합니다. [규정 준수 점수 평가를 관리](compliance-score-assessments.md)하는 방법을 알아봅니다. 서식 파일 만들기 및 수정은 여전히 준수 관리자에서 관리 됩니다.

## <a name="new-templates-for-assessments"></a>평가를 위한 새 서식 파일

평가를 위해 새로운 서식 파일을 사용할 준비가 되 면 준수 점수가 제공 됨에 따라 릴리스됩니다. 여기에서 [전체 서식 파일 목록을](compliance-score-templates.md)확인 하세요. 최근에 추가 됨:

- DGISR (두바이 Information Security Resolution)

## <a name="compliance-score-relationship-to-compliance-manager"></a>준수 관리자와 규정 준수 점수 관계

준수 관리자에서 처리 되는 대부분의 함수는 이제 규정 준수 점수를 받을 수 있습니다. 그러나 일부 기능은 여전히 준수 관리자에 게 있습니다. 공개 미리 보기 동안 준수 점수 및 준수 관리자를 사용할 때는 다음 사항을 염두에 두어야 합니다.

 - **평가를 위한 템플릿 만들기**: 
   - 사용자는 준수 관리자를 방문 하 여 [새 템플릿을 만들고 기존 템플릿을 수정](working-with-compliance-manager.md#templates)해야 합니다.
   - 새 템플릿은 **제품** 및 **인증**에 대 한 차원을 모두 포함 해야 합니다.
 - **사용 권한 설정**: 규정 준수 점수 준수 관리자에서 사용 권한을 갖고 있지 않은 사용자는 Microsoft 365 준수 센터에서 사용 권한을 설정 해야 합니다 ([자세한 내용](compliance-score-setup.md#set-user-permissions-and-assign-roles)).
- **데이터 전송**: 준수 관리자의 데이터를 포함 하는 조직에서는 규정 준수 점수에 해당 데이터가 표시 되며, 다른 방식으로도 마찬가지입니다.
- 준수 **관리자에 게 준수 점수**에 로그인: 사용자가 준수 점수에 로그인 되어 있고 준수 관리자에 게 이동 하는 링크를 선택 하는 경우 사용자는 다시 로그인 할 필요가 없습니다. 링크를 클릭 하면 브라우저에서 대화 상자를 표시 하는 새 탭이 열립니다. 머리글이 "이미 Microsoft 클라우드 서비스 고객" 인 최상위 섹션에서 계정에 로그인 하 여 준수 관리자에 게 자동으로 로그인 하는 **로그인** 단추를 선택 합니다.

## <a name="known-issues-in-compliance-score-preview"></a>준수 점수에 알려진 문제 (미리 보기)

다음 섹션에서는 향후 준수 점수에서 해결 해야 할 알려진 문제에 대해 설명 합니다.

### <a name="long-load-times-for-non-admin-users"></a>관리자가 아닌 사용자에 대 한 긴 로드 시간
준수 점수 관리자 역할 이외의 역할을 보유 하는 사용자는 로그인을 시도할 때 로드 시간이 오래 걸릴 수 있습니다. 브라우저를 새로 고치면이 문제가 해결 됩니다. [규정 준수 점수 역할](compliance-score-setup.md#set-user-permissions-and-assign-roles)에 대해 자세히 알아보세요.

### <a name="supported-browsers"></a>지원되는 브라우저

- 최신 버전의 Microsoft Edge, Chrome 및 Safari가 지원 됩니다.
- 업데이트 된 데이터가 브라우저를 새로 고칠 때까지 표시 되지 않는 경우가 있습니다.
- Internet Explorer가 지원 되지 않습니다.
