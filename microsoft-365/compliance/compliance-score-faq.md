---
title: Microsoft 준수 점수 FAQ
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
description: 조직에서 위험 평가를 간소화 하 고 자동화 하는 데 도움이 되는 Microsoft 준수 점수에 대 한 질문과 대답을 확인할 수 있습니다.
ms.openlocfilehash: 942de8f8cc9eeb958cb7f8e96c9e7038447ce3f1
ms.sourcegitcommit: ff62dd99fa0d4e780da25dc622f93ddc8f7f95a0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43141563"
---
# <a name="microsoft-compliance-score-preview-frequently-asked-questions"></a>Microsoft 준수 점수 (미리 보기) faq

## <a name="what-is-compliance-score"></a>준수 점수 란?

Microsoft 준수 점수는 조직의 규정 준수 상태를 이해 하는 데 도움이 되는 [microsoft 365 준수 센터](microsoft-365-compliance-center.md) 의 미리 보기 기능입니다. 데이터 보호 및 규정 표준에 대 한 위험을 줄이는 데 도움이 되는 작업 완료의 진행 상태를 측정 하는 위험 기반 점수를 계산 합니다. 준수 점수는 주요 규정 및 표준에 공통 제어를 연결 하는 데 도움이 되는 기본 제공 컨트롤 매핑을 제공 하므로 한 가지 작업을 수행 하 여 동시에 여러 요구 사항을 충족 하 고 준수 프로그램의 규모를 높일 수 있습니다.

## <a name="how-do-i-access-compliance-score"></a>준수 점수에 액세스 하려면 어떻게 해야 합니까?

[Microsoft 365 준수 센터로](https://compliance.microsoft.com/) 이동한 후 microsoft 365 전역 관리자, 준수 관리자 또는 준수 데이터 관리자 역할로 **로그인** 합니다. 왼쪽 탐색 창에서 **규정 준수 점수** 를 선택 합니다. 그런 다음 [준수 점수 대시보드를 점수와 함께](compliance-score-setup.md#understand-the-compliance-score-dashboard)확인 해야 합니다. 적절 한 역할 액세스가 없는 경우 조직의 전역 관리자가 권한을 부여할 수 있습니다.

## <a name="what-roles-or-permissions-are-needed-to-use-compliance-score"></a>준수 점수를 사용 하는 데 필요한 역할 또는 사용 권한

준수 점수는 RBAC (역할 기반 액세스 제어) 권한 모델을 사용 하며, 사용자에 게 할당 된 역할 유형에 따라 수행할 수 있는 작업이 달라 집니다. 조직의 Microsoft 365 전역 관리자는 규정 준수 점수에 설치 기능을 수행 하 고 역할을 관리할 수 있는 사용자입니다. 최소한 준수 점수가 규정 된 데이터를 읽기 위해서는 사용자가 **AZURE AD 전역 독자** 역할을 수행 해야 합니다. [준수 점수 설정](compliance-score-setup.md)에서 사용 권한, 역할 및 설정 절차에 대해 자세히 알아보세요.

## <a name="what-is-the-difference-between-compliance-score-and-compliance-manager"></a>준수 점수와 준수 관리자의 차이점은 무엇 인가요?

준수 점수 및 준수 관리자는 동일한 백 엔드를 공유 하지만 두 가지 다른 위치 (준수 점수가 Microsoft 365 준수 센터에 있고 준수 관리자는 Microsoft Service Trust Portal에 있음)에 있습니다. 규정 준수 점수를 준수 관리자의 단순화 된 버전으로 생각 하면 조직의 현재 준수 상태와이를 개선 하기 위해 수행할 수 있는 단계를 보다 완벽 하 게 확인할 수도 있습니다. 규정 준수 점수 내에서 많은 작업을 직접 수행할 수 있지만 일부 기능은 현재 준수 관리자에 게 있습니다. [준수 점수와 준수 관리자 간의 관계](compliance-score.md#relationship-to-compliance-manager)에 대 한 자세한 내용을 읽으십시오.

## <a name="who-should-use-compliance-score-and-who-should-use-compliance-manager"></a>준수 점수를 사용 해야 하는 사용자 및 준수 관리자를 사용 해야 하는 사용자

규정 준수 점수는 규정 준수를 모니터링 하는 역할을 담당 하는 조직의 모든 사용자에 게 유용한 기능 표준을 준수 하는 데 도움이 됩니다. 규정 준수 점수가 있으면 조직의 데이터 보호를 향상 시키는 규정 및 표준을 익혀야 할 필요가 없습니다. 규정 준수 점수가 모든 사용자에 게 적합 한 시작 위치입니다. 여기에서 준수 점수를 확인 하 고, 위험을 최소화 하는 데 도움이 되는 권장 작업을 알아보고, 대부분의 경우 이러한 작업을 수행 하기 위한 솔루션을 즉시 시작할 수 있습니다.

지금은 준수 관리자는 평가를 관리 하 고 사용자 지정 템플릿을 만들어 평가를 작성할 수 있는 위치입니다. 공개 미리 보기 중에는 [준수 관리자만 지 원하는 작업](compliance-score-release-notes.md#compliance-score-relationship-to-compliance-manager) 에 대해 자세히 알아보세요.

## <a name="if-i-have-a-high-score-does-it-mean-im-fully-compliant"></a>높은 점수를 받은 경우 완벽 한 규격을 의미 하나요?

아니요. 준수 점수는 데이터 보호 및 규정 표준에 대 한 위험을 줄이는 데 도움이 되는 권장 작업을 완료 하는 과정을 측정 합니다. 이는 특정 표준 또는 규정에 대 한 조직의 규정 준수를 절대적으로 측정 하는 것이 아닙니다. 규정 준수 점수가 보장 되는 방식으로 해석 되어서는 안 됩니다.

## <a name="what-regulations-and-standards-does-compliance-score-monitor"></a>준수 점수가 어떻게 지는 규정 및 표준은 무엇 인가요?

규정 준수 점수는 일반적인 업계 규정 및 표준을 포함 하는 컨트롤 집합인 Microsoft 365 데이터 보호 기준을 기반으로 초기 점수를 제공 합니다. 이 기준은 기본적으로 NIST CSF (표준 및 기술 Cybersecurity 프레임 워크) 및 ISO (국제 표준화 기구)를 비롯 하 여 FedRAMP (연방 위험 및 권한 부여 관리 프로그램) 및 GDPR (유럽 연합의 일반 데이터 보호 규정)의 요소를 그립니다.

조직은 조직과 관련성이 높은 사용자 지정 평가를 만들고 추가할 수 있습니다. 준수 점수 점수가 [미리 구성 된 서식 파일](compliance-score.md#templates)중 하나를 사용 하거나, 자신만의 컨트롤 및 작업을 사용 하 여 Microsoft 템플릿을 사용자 지정 하거나, 자신만의 서식 파일을 만듭니다. [서식 파일](working-with-compliance-manager.md#templates)사용 방법에 대 한 세부 정보를 읽어보십시오.

[규정 준수 점수가 점수를 계산](compliance-score-methodology.md)하는 방법을 알아봅니다.

## <a name="what-is-the-difference-between-compliance-score-and-secure-score"></a>규정 준수 점수와 보안 점수 간의 차이점

규정 준수 점수는 조직의 데이터 보호 및 준수 상황을 광범위 하 게 보여 줍니다. 규정 준수 점수에는 워크플로 도구도 기본적으로 제공 됩니다. 조직에서 사용자에 게 작업을 할당 하 고, 컨트롤 구현 및 테스트 상태를 추적 하 고, 증거를 업로드 하 고 감사 보고서를 만들 수 있습니다.

Microsoft 보안 점수는 보안 상황을 이해 하는 데 도움이 되는 보안 분석 도구입니다. [보안 점수 및 작동 방식에 대해 자세히 알아보세요](../security/mtp/microsoft-secure-score.md).

## <a name="which-cloud-services-are-covered-by-compliance-score"></a>준수 점수가 포함 된 클라우드 서비스는 무엇 인가요?

준수 점수는 현재 Office 365 및 Intune에 대 한 평가를 제공 합니다. 확장 된 검사는 향후 릴리스에서 기대 되며 [준수 점수 릴리스 정보](compliance-score-release-notes.md)에 기록 됩니다.

## <a name="can-i-use-compliance-score-for-non-microsoft-products"></a>타사 제품에 대해 준수 점수를 사용할 수 있나요?

준수 점수가 Microsoft 클라우드 서비스에 대 한 지속적인 모니터링 및 권장 작업만 제공 하는 반면, 온-프레미스, 타사 서비스에 대 한 준수 관리자에는 사용자 지정 평가를 추가할 수 있습니다. 이러한 방식으로 Microsoft 준수 점수를 SaaS 준수 관리 도구로 사용 하 여 디지털 자산에서 모든 컨트롤을 관리할 수 있습니다.

규정 준수 점수의 [미리 구성 된 서식 파일](compliance-score.md#templates) 중 하나를 사용 하 여 특정 표준에 대 한 평가를 만들거나 [고유한 서식 파일을 만들](working-with-compliance-manager.md#create-a-template)수 있습니다.

## <a name="how-do-i-delete-a-template-or-assessment-i-no-longer-need"></a>더 이상 필요 하지 않은 템플릿이나 평가를 삭제 하려면 어떻게 해야 하나요?

평가 또는 서식 파일을 삭제할 수는 없지만 보기에서 숨길 수는 있습니다. [평가를 숨기는 방법에 대 한 지침을](working-with-compliance-manager.md#hide-a-template-or-an-assessment)검토 합니다.

## <a name="what-test-procedures-does-microsoft-follow-for-controls"></a>컨트롤에 대해 Microsoft에서 어떤 테스트 절차가 수행 됩니까?

Microsoft는 컨트롤에 대 한 연간 감사에 참여 합니다. [Microsoft 서비스 보안 포털](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuideV3)에서 다운로드할 수 있는 감사자의 감사 보고서를 검토할 수 있습니다.

## <a name="why-are-some-controls-tested-annually-and-others-tested-every-three-years"></a>일부 컨트롤은 매년 테스트 되 고 나머지는 3 년 마다 테스트 되는 이유는 무엇 인가요?

FedRAMP 평가는 이러한 상황이 발생 하는 이유를 예로 들 수 있습니다. 이는 매년 수행 되며 주요 컨트롤 패밀리 사이에 있는 컨트롤의 횡단면을 테스트 합니다. 연간 테스트를 필요로 하는 데 충분히 중요 한 경우 FedRAMP에서 컨트롤을 **핵심** 으로 분류 합니다. 코어가 아닌 것으로 지정 된 컨트롤은 3 년 마다 테스트 됩니다. 모든 주요 컨트롤 패밀리에서 확장 되는 컨트롤의 하위 집합은 매년 테스트 됩니다. 이러한 방식으로 각 연간 감사는 솔루션의 안정성을 보장 하기 위해 보드에서 시나리오를 조사 합니다. [FedRAMP 연간 평가 프로세스](https://www.fedramp.gov/annual-assessment-guidance/)에 대 한 자세한 내용을 읽으십시오.
