---
title: 데이터 개인 정보 규정의 영향을 받는 정보 보호
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
ms.custom: ''
description: Microsoft 365 보안 및 규정 준수 기능을 배포 하 고 개인 정보를 보호 합니다.
ms.openlocfilehash: 87057d7c823fc9808169efd254300f2b2f5e0487
ms.sourcegitcommit: c76c025fe75cd9c06eccbf9c7fc887b09da36659
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2020
ms.locfileid: "46903898"
---
# <a name="protect-information-subject-to-data-privacy-regulation"></a>데이터 개인 정보 규정의 영향을 받는 정보 보호

데이터 개인 정보 규정 준수 요구 사항 및 규정을 해결 하기 위해 구독에 다양 한 정보 보호 컨트롤을 사용할 수 있습니다. 여기에는 GDPR (일반 데이터 보호 규정), HIPAA-HITECH (미국 의료 보험 개인 정보 보호 act), 캘리포니아 CCPA (소비자 보호 act), LGPD (브라질 Data Protection Act)가 포함 됩니다.

이러한 컨트롤은 다음과 같은 솔루션 영역 내에 있습니다.

- 민감도 레이블
- DLP(데이터 손실 방지)
- OME(Office 메시지 암호화)
- 팀 및 사이트 액세스 제어

![데이터 개인 정보 규정에 따라 개인 정보가 보호 되는 주요 서비스](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-grid.png)

>[!Note]
>이 솔루션은 데이터 개인 정보 규정의 영향을 받는 정보를 보호 하는 보안 및 규정 준수 기능을 설명 합니다. Microsoft 365의 전체 보안 기능 목록에 대 한 자세한 내용은 [microsoft 365 보안 설명서](https://docs.microsoft.com/microsoft-365/security/)를 참조 하십시오. Microsoft 365의 준수 기능에 대 한 전체 목록은 [microsoft 365 준수 설명서](https://docs.microsoft.com/microsoft-365/compliance/)를 참조 하세요.
>

## <a name="data-privacy-regulations-that-impact-information-protection-controls"></a>정보 보호 제어에 영향을 주는 데이터 개인 정보 규정

다음은 정보 보호 컨트롤과 관련이 있을 수 있는 데이터 개인 정보 규정의 예제 목록입니다.

- GDPR 문서 5 (1) (f))
- GDPR 문서 (32) (1) (a)
- LGPD 문서 46
- HIPAA-HITECH (45 CFR 164.312 (1))
- HIPAA-HITECH (45 C.F.R. 164.312 (e) (2) (ii))

위의 각 항목에 대 한 자세한 내용은 [데이터 개인 정보 보호 위험 평가 및 중요 한 항목 식별 문서](information-protection-deploy-assess.md) 를 참조 하세요.

정보 보호에 대 한 데이터 프라이버시 규정은 권장 됩니다.

- 손실 또는 무단 액세스, 사용 및/또는 전송에 대 한 보호
- 보호 메커니즘에 대 한 위험 기반 응용 프로그램
- 해당 하는 경우 암호화 사용

또한 조직에서는 기타 규정 준수 요구 사항이 나 비즈니스 상의 이유로 인해 Microsoft 365 콘텐츠를 다른 용도로 보호 하고자 할 수도 있습니다. 데이터 프라이버시에 대 한 정보 보호 체계 설정은 전체 정보 보호 계획, 구현 및 관리의 일부로 수행 해야 합니다.

Microsoft 365에서 정보 보호 체계를 시작 하는 데 도움이 되도록 다음 섹션에는 Microsoft 365에 대 한 관련 기능 및 향상 작업에 대 한 간단한 목록이 포함 되어 있습니다. 이 목록에는 데이터 개인 정보 규정에 적용할 수 있는 기능 및 개선 작업이 포함 되어 있습니다. 그러나 이전 기술이 많이 대체 되는 최신 기능이 있는 경우에는 목록에 오래 된 기술도 포함 되지 않습니다. 예를 들어 SharePoint 및 OneDrive에 대 한 IRM (정보 권한 관리)은 목록에 포함 되지 않지만 민감도 레이블은 포함 됩니다.

## <a name="managing-information-protection-in-microsoft-365"></a>Microsoft 365에서 정보 보호 기능 관리

Microsoft [information protection 솔루션](../compliance/protect-information.md) 에는 microsoft 365, microsoft Azure 및 microsoft Windows에서 다양 한 기능이 통합 되었습니다. Microsoft 365에서 제공 하는 정보 보호 솔루션은 다음과 같습니다.

- [고객 키를 사용한 서비스 암호화](../compliance/customer-key-overview.md)
- [중요 한 정보 유형](../compliance/what-the-sensitive-information-types-look-for.md) ( [데이터 개인 정보 보호 위험 평가 및 중요 한 항목 식별 문서](information-protection-deploy-assess.md)참조)
- [민감도 레이블](../compliance/sensitivity-labels.md) 
  - 서비스/컨테이너 수준
  - 클라이언트 쪽/콘텐츠 수준
  - SharePoint 및 OneDrive의 휴지 데이터에 대 한 자동화
- DLP(데이터 손실 방지)
- [Microsoft 365 Endpoint 데이터 손실 방지 (미리 보기)](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about?view=o365-worldwide)
- [Office 365 메시지 암호화 OME (새 기능)](../compliance/ome.md) 및 OME [Advanced Message encryption](../compliance/ome-advanced-message-encryption.md)

또한 사이트 및 라이브러리 수준 보호는 모든 보호 체계에 포함할 중요 한 메커니즘입니다.

Microsoft 365 이외의 다른 정보 보호 기능에 대 한 자세한 내용은 다음 항목을 참조 하십시오.

- [MCAS (Microsoft Cloud Application Security)](https://docs.microsoft.com/cloud-app-security/)
- [Azure Information Protection](https://docs.microsoft.com/azure/information-protection/what-is-information-protection)
- [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)
- [Windows Information Protection](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip)

## <a name="sensitivity-labels"></a>민감도 레이블

Microsoft Information Protection framework의 민감도 레이블을 사용 하면 사용자의 생산성과 공동 작업을 수행 하는 기능을 hindering 않고 조직의 데이터를 분류 및 보호할 수 있습니다.

![Microsoft 365의 민감도 레이블](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-labels.png)

### <a name="prerequisites-for-sensitivity-labels"></a>민감도 레이블의 필수 구성 요소

아래에 강조 표시 된 민감도 레이블 기반 기능을 구현 하기 전에 이러한 활동을 완료 하세요.

1. 다음 사항을 이해 해야 합니다.
   - **비즈니스 요구 사항** 기업에서 민감도 레이블을 적용 하기 위한 비즈니스 이유를 설정 합니다. 정보 보호를 위한 데이터 프라이버시 요구 사항을 예로 들 있습니다.
   - **민감도 레이블 기능** 민감도 레이블은 복잡할 수 있으므로 먼저 [민감도 레이블 설명서](../compliance/sensitivity-labels.md) 를 참조 하세요.
   - **주의할 주요 사항** 민감도 레이블은 Microsoft 준수 관리 센터에서 관리 되지만 대상 및 응용 프로그램 옵션은 매우 다양 합니다.
      - 컨테이너 수준에서 사이트, 그룹 및 팀에 대 한 민감도 레이블이 있습니다 (이 설정은 컨테이너 내의 콘텐츠에는 적용 되지 않음). 이러한 항목은 사이트, 그룹 또는 팀이 프로 비전 될 때 적용 되는 사용자 및 그룹에 게시 됩니다.
      - 활성 콘텐츠에 대 한 민감도 레이블이 있습니다. 이러한 항목은 사용자 또는 그룹에도 게시 되며, 수동으로 적용 하거나 다음 경우에 자동으로 적용 됩니다.
        - 파일이 사용자의 데스크톱 또는 SharePoint 사이트로 열리거나 편집/저장 됩니다.
        - 전자 메일이 초안 되 고 전송 됩니다.
      - 자동 응용 프로그램에 대 한 민감도 레이블은 SharePoint 및 OneDrive의 나머지 파일과 Exchange를 통한 전송 되는 전자 메일에도 제공 됩니다. 이러한 항목은 모든 사이트 또는 특정 위치를 대상으로 하며, 이러한 환경에서 휴지 상태의 파일에 자동으로 적용 됩니다.

2. 합리화 현재 민감도 레이블 (이전의 또는 대체 방법 포함)

   - Azure Information Protection

      현재 민감도 레이블 구성표는 기존의 [Azure Information Protection](../compliance/sensitivity-labels.md#sensitivity-labels-and-azure-information-protection) 레이블 구현과 함께 조정 해야 할 수 있습니다.
   - OME

      전자 메일 보호에 최신 민감도 레이블을 사용 하도록 계획 하는 경우 OME와 같은 기존 전자 메일 암호화 방법을 사용할 수 있지만이를 적용 해야 하는 시나리오를 이해 해야 합니다. OME 기반 보호를 통해 현대 민감도 레이블 유형 보호를 비교 하는 표를 포함 하는 [Office 365 메시지 암호화 OME (새 기능)](#office-365-message-encryption-ome-new-capabilities)를 참조 하세요.

3. 보다 광범위 한 정보 보호 구성표로 통합을 계획 합니다. OME과 함께 사용 하는 경우에는 현재 민감도 레이블을 Microsoft 365 DLP (데이터 손실 방지) 및 Microsoft Cloud App Security와 같은 측면에서 사용할 수 있습니다. 데이터 프라이버시 관련 정보 보호 목표를 달성 하려면 [민감도 레이블 및 Microsoft Cloud App Security](../compliance/sensitivity-labels.md#sensitivity-labels-and-microsoft-cloud-app-security) 를 참조 하세요.

4. 민감도 레이블 분류 및 컨트롤 구성표를 개발 합니다. [데이터 분류 및 민감도 레이블 분류](https://aka.ms/dataclassificationwhitepaper)를 참조 하세요.

### <a name="general-guidance"></a>일반 지침

1. **스키마 정의** 기술 기능을 사용 하 여 레이블과 보호를 적용 하기 전에 조직에서 분류 스키마를 정의 하는 작업을 수행 해야 합니다. 분류 스키마가 이미 있는 경우에는 개인 데이터를 보다 쉽게 추가할 수 있습니다. 
2. **시작 합니다.** 먼저 구현할 레이블 수와 이름을 결정 합니다. 사용할 기술과 레이블 적용 방법을 걱정 하지 않고이 작업을 수행 합니다. 온-프레미스 및 기타 클라우드 서비스에 있는 데이터를 포함 하 여 조직 전체에서이 스키마를 적용 합니다.
3. **추가 권장 사항** 정책, 레이블 및 조건을 디자인 하 고 구현할 때는 다음 권장 사항을 따르는 것이 좋습니다.

   - **기존 분류 스키마 (있는 경우)를 사용 합니다.** 대부분의 조직에서는 특정 양식의 데이터 분류를 이미 사용 하 고 있습니다. 기존 레이블 스키마를 신중 하 게 평가 하 고 가능한 경우 그대로 사용 합니다. 최종 사용자에 게 인식 가능한 익숙한 레이블을 사용 하면 채택이 구동 됩니다.
   - **작은 크기부터 시작 합니다.** 만들 수 있는 레이블 수에는 거의 제한이 없습니다. 그러나 레이블과 하위 레이블의 수가 많으면 채택이 느려질 수 있습니다.
   - **시나리오 및 사용 사례를 사용 합니다.** 조직 내 일반적인 사용 사례를 확인 하 고, 주체가 있는 데이터 개인 정보 규정에서 도출 된 시나리오를 사용 합니다. 구상 중인 레이블과 분류 구성이 실제로 작동 하는지 확인 합니다.
   - **새 레이블을 요청할 때마다 질문 합니다.** 모든 시나리오 또는 사용 사례에 실제로 새 레이블이 필요 합니까? 아니면 이미 갖고 있는 것을 사용할 수 있나요? 최소 채택으로 레이블 수를 유지 하는 것이 향상 되었습니다.
   - **주요 부서에 하위 레이블을 사용 합니다.** 일부 부서에는 특정 레이블이 필요한 특정 요구 사항이 적용 됩니다. 이러한 레이블을 기존 레이블에 대 한 하위 레이블로 정의 하 고, 전역 대신 사용자 그룹에 할당 된 범위 지정 정책을 사용 하는 것이 좋습니다.
   - **범위 지정 정책을 고려 합니다.** 사용자 하위 집합을 대상으로 하는 정책은 레이블 오버 로드를 방지 합니다. 범위 정책을 사용 하면 특정 부서에서 작업 하는 직원 에게만 역할 또는 부서 관련 레이블이나 하위 레이블을 할당할 수 있습니다. 
   - **의미 있는 레이블 이름을 사용 합니다.** 용어, 표준 또는 약어를 레이블 이름으로 사용 하지 마십시오. 최종 사용자에 게 resonate 하는 이름을 사용 하 여 채택을 개선 합니다. PII, PCI, HIPAA, LBI, MBI 및 HBI와 같은 레이블을 사용 하는 대신, 비즈니스, 공용, 일반, 비밀 및 고도의 기밀을 유지 하는 것이 좋습니다.

### <a name="create-and-deploy-sensitivity-labels-for-sites-groups-and-teams"></a>사이트, 그룹 및 팀에 대 한 민감도 레이블 만들기 및 배포

Microsoft 365 준수 센터에서 [민감도 레이블을](../compliance/sensitivity-labels-teams-groups-sites.md) 만들 때 이제 다음 컨테이너에 적용할 수 있습니다.

- Microsoft 팀 사이트
- Microsoft 365 그룹 (이전의 Office 365 그룹)
- SharePoint 사이트

다음 레이블 설정을 사용하여 이러한 컨테이너의 콘텐츠를 보호할 수 있습니다.

- Microsoft 365 그룹에 연결 된 팀 사이트의 개인 정보 보호 (공용 또는 개인)
- 외부 사용자 액세스
- 관리되지 않는 장치에서 액세스

데이터 개인 정보 보호를 위해 중요 한 개인 데이터를 포함 하는 콘텐츠를 저장 하는 데 사용 되는 컨테이너에 대해 외부 공유를 방지 하려면 데이터를 포함 하는 파일을 비공개로 표시 하 고 관리 되는 장치가 필요 합니다

### <a name="create-and-deploy-sensitivity-labels-for-content"></a>콘텐츠에 대 한 민감도 레이블 만들기 및 배포

민감도 레이블을 사용 하 여 콘텐츠를 암호화 하 고, 콘텐츠를 워터 마크로 지정 하 고, 웹용 Outlook 및 Office를 비롯 한 기타 Office 응용 프로그램 콘텐츠 컨트롤을 정의할 수 있습니다.

민감도 레이블로 조직의 데이터를 보호 하기 시작할 준비가 되 면 다음을 수행 합니다.

1. **레이블을 만듭니다.** 다양한 민감도 수준의 컨텐츠에 대한 조직의 분류체계에 따라 민감도 레이블을 작성하고 이름을 지정하십시오. 분류 분류를 개발 하는 방법에 대 한 자세한 내용은 [데이터 분류 및 민감도 레이블 분류 백서](https://aka.ms/dataclassificationwhitepaper)를 참조 하십시오.
2. **각 레이블이 수행할 수 있는 작업을 정의합니다.** 각 레이블과 연결할 보호 설정을 구성합니다. 예를 들어 "일반" 레이블과 같은 낮은 민감도 콘텐츠를 적용 하 여 머리글 또는 바닥글을 적용할 수 있을 뿐 아니라, "기밀" 레이블 같은 더 높은 민감도 콘텐츠는 워터 마크를 사용 하도록 설정 해야 합니다.
3. **레이블을 게시합니다.** 민감도 레이블이 구성되 면 레이블 정책을 사용하 여 해당 레이블을 게시합니다. 어떤 사용자와 그룹에 레이블과 정책 설정을 사용할지 결정합니다. 단일 레이블을 다시 사용할 수 있습니다. 한 번 정의한 다음 서로 다른 사용자에 게 할당 되는 여러 레이블 정책에이를 포함할 수 있습니다.

Microsoft 365 준수 센터에서 민감도 레이블을 게시 한 후에는 사용자가 콘텐츠를 작성 하거나 편집할 때이를 분류 하 고 보호 하기 위해 [Office 앱](../compliance/sensitivity-labels-office-apps.md) 에 표시 되기 시작 합니다.

![Microsoft 365의 민감도 레이블 배포 흐름](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-label-flow.png)

데이터 개인 정보 보호를 위해서는 암호화 및 기타 규칙을 포함 하는 민감도 레이블을 중요 한 개인 정보가 포함 된 전자 메일 또는 콘텐츠에 수동으로 적용 해야 합니다.

>[!Note]
>암호화가 사용 하도록 설정 된 민감도 레이블은 OME에서 약간의 기능이 겹칩니다. [OME 및 민감도 레이블과 보안 전자 메일 시나리오 비교](#secure-email-scenarios-comparison-with-ome-and-sensitivity-labels)를 참조 하세요.

### <a name="client-side-auto-labeling-when-users-edit-documents-or-compose-emails"></a>사용자가 문서를 편집 하거나 전자 메일을 작성할 때 클라이언트 쪽 자동 레이블

민감도 레이블을 만들 때 사용자가 지정한 조건에 맞는 전자 메일을 포함 하 여 [해당 레이블을 콘텐츠에 자동으로 할당할](../compliance/apply-sensitivity-label-automatically.md) 수 있습니다.

콘텐츠에 자동으로 민감도 레이블을 적용하는 기능도 다음과 같은 이유로 중요합니다.

- 사용자에게 각 분류를 언제 사용할지 교육할 필요가 없습니다.
- 모든 콘텐츠를 올바르게 분류하기 위해 사용자에게 의존할 필요가 없습니다.
- 사용자가 더 이상 정책을 알아야 할 필요가 없으며, 그 대신 업무에 집중할 수 있습니다.

자동 레이블 지정은 사용자에 대 한 레이블 권장 및 레이블을 자동으로 적용 하도록 지원 합니다. 그러나 두 경우 모두 사용자가 레이블을 수락할지 또는 거부할지 결정하여 내용에 올바른 레이블을 지정할 수 있도록 합니다.

이 클라이언트 쪽 레이블에는 문서가 저장되기 전에 레이블을 지정할 수 있으므로 문서에 대한 지연 시간이 최소화됩니다. 그러나 일부 클라이언트 앱에서는 자동 레이블 지정을 지원하지 않습니다. 이 기능은 Azure Information Protection 통합 레이블 클라이언트 및 [일부 Office 앱 버전](../compliance/sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)에서 지원 됩니다.

구성 지침에 대해서 [는 Office 앱에 대 한 자동 레이블 구성 방법을](../compliance/sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)참조 하세요.

데이터 개인 정보 보호를 위해 중요 한 개인 정보가 포함 된 콘텐츠에 대 한 민감도 레이블을 자동으로 적용 합니다.

### <a name="service-side-auto-labeling-when-content-is-already-saved"></a>콘텐츠가 이미 저장 된 경우 서비스 쪽 자동 레이블

이 방법을 민감도 레이블이 있는 자동 분류라고 합니다. 또한 rest 데이터 (SharePoint 및 OneDrive의 문서)와 전송 중인 데이터 (Exchange에서 보내거나 받는 전자 메일)에 대해 자동 레이블으로 지칭 한다고 들 수 있습니다. Exchange의 경우 나머지 사서함에는 전자 메일이 포함 되지 않습니다.
 
이 레이블 지정은 사용자 응용 프로그램이 아니라 서비스 자체에 의해 적용 되므로 사용자에 게 어떤 앱과 어떤 버전이 있는지 신경 쓰지 않아도 됩니다. 따라서 이 기능은 조직 전체에서 즉시 사용할 수 있으며 대규모로 레이블을 지정하는 데 적합합니다. 자동 레이블 지정 정책은 사용자가 레이블 지정 프로세스와 상호 작용하지 않기 때문에 권장되는 레이블 지정을 지원하지 않습니다. 대신 관리자가 시뮬레이션 모드에서 정책을 실행하여 실제로 레이블을 적용하기 전에 콘텐츠의 올바른 레이블을 확인합니다.

구성 지침에 대해서 [는 SharePoint, OneDrive 및 Exchange에 대 한 자동 레이블 지정 정책을 구성 하는 방법을](../compliance/apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange)참조 하세요.

중요 한 사이트 내의 데이터 개인 정보 보호를 위해 민감한 개인 정보를 포함 하는 콘텐츠의 자동 암호화에 대 한 푸시 민감도 레이블

## <a name="data-loss-prevention"></a>데이터 손실 방지 

Microsoft 365에서 [DLP (데이터 손실 방지)](../compliance/data-loss-prevention-policies.md) 를 사용 하 여 내부 및 외부에서 개인 정보를 포함 하는 데이터를 공유 하는 것과 같은 위험, 실수로 또는 부적절 한 공유를 감지, 경고 및 부적합 하 게 차단할 수 있습니다.

DLP를 사용 하 여 다음을 수행할 수 있습니다.

- 위험한 공유 활동을 식별 하 고 모니터링 합니다.
- 적절 한 결정을 내릴 수 있도록 컨텍스트 지침을 사용자에 게 교육 합니다.
- 생산성을 유지 하지 않고 콘텐츠를 통해 데이터를 사용 하 여 inhibiting.
- 분류 및 레이블 지정을 통합 하 여 데이터를 공유 하는 경우 검색 하 고 보호 합니다.

### <a name="supported-workloads-for-dlp"></a>DLP에 대해 지원 되는 작업

Microsoft 365 준수 센터의 DLP 정책을 사용 하 여 Exchange Online, SharePoint, OneDrive 및 Microsoft 팀과 같은 Microsoft 365의 여러 위치에서 중요 한 항목을 식별 하 고, 모니터링 하 고, 자동으로 보호할 수 있습니다.

예를 들어 OneDrive 사이트에 저장 된 신용 카드 번호가 포함 된 모든 문서를 식별 하거나 특정 사용자의 OneDrive 사이트만 모니터링할 수 있습니다.

또한 중요 한 항목을 식별 하 고 DLP 정책을 적용 하는 기능이 포함 된 Excel, PowerPoint 및 Word의 로컬로 설치 된 버전의 중요 한 항목을 모니터링 하 고 보호할 수 있습니다. DLP는 사용자가 이러한 Office 앱에서 콘텐츠를 공유 하는 경우 지속적인 모니터링을 제공 합니다.

![DLP에 대해 지원 되는 작업](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-supported-workloads.png)

다음 그림에서는 개인 데이터를 보호 하는 DLP의 예를 보여 줍니다.

![DLP를 사용 하 여 개인 데이터를 보호 하는 예제](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-example-use.png)

DLP는 상태 레코드가 포함 된 문서 또는 전자 메일을 식별 한 다음 해당 문서에 대 한 액세스를 자동으로 차단 하거나 전자 메일이 전송 되지 않도록 차단 하는 데 사용 됩니다. 그러면 DLP는 정책 팁을 사용 하 여 받는 사람에 게 알리고 최종 사용자 및 관리자에 게 경고를 보냅니다.

### <a name="planning-for-dlp"></a>DLP 계획

다음에 대 한 DLP 정책 계획 

- 비즈니스 요구 사항

- [데이터 프라이버시 위험 평가 및 중요 한 항목 식별 문서](information-protection-deploy-assess.md)에 설명 된 대로 조직에 대 한 위험 기반 평가입니다.

- 데이터 개인 정보 보호에 대 한 현재 위치 또는 계획의 기타 정보 보호법 및 거 버 넌 스 메커니즘

- 평가에 따라 개인 데이터에 대해 식별 된 중요 한 정보 유형은 [데이터 개인 정보 보호 위험 평가 및 중요 한 항목 식별 문서](information-protection-deploy-assess.md)에 설명 되어 있습니다. DLP 정책 조건은 중요 한 정보 유형 및 보존 레이블을 기반으로 할 수 있습니다.

- 보존 레이블을 통해 DLP 조건을 지정 해야 합니다. 자세한 내용은 [조직 문서에서 데이터 개인 정보 규정에 대 한 정보 제어를](information-protection-deploy-govern.md) 참조 하세요.

- 지속적인 DLP 정책 관리-조직의 누군가가 중요 한 정보 유형, 보존 레이블, 규정 및 준수 정책의 변경 사항에 대 한 정책을 운영 하 고 조정 해야 합니다.

민감도 레이블은 DLP 정책 조건에서 사용할 수 없지만 중요 한 정보 유형을 기반으로 자동 적용 될 수 있는 민감도 레이블만 사용 하 여 액세스를 차단 하는 특정 보호 시나리오를 사용할 수 있습니다. 강력한 민감도 레이블을 지정 하는 경우에는 다음과 같은 이유로 DLP를 사용 하 여 보호를 강화 해야 하는지 여부를 고려해 야 합니다.

  - DLP는 파일 공유를 방지할 수 있습니다. 민감도 레이블은 액세스를 금지할 수 있습니다.

  - DLP에는 규칙, 조건 및 작업 측면에서 보다 세부적인 제어 수준이 있습니다.

  - DLP 정책은 팀 채팅 및 채널 메시지에 적용할 수 있습니다. 민감도 레이블은 문서 및 전자 메일에만 적용 될 수 있습니다.


### <a name="dlp-policies"></a>DLP 정책

DLP 정책은 Microsoft 준수 관리 센터에서 구성 되며 보호 수준, 정책에서 찾고 있는 중요 한 정보 유형 및 대상 작업을 지정 합니다. 기본 구성 요소는 보호 및 데이터 형식을 식별 하는 것으로 구성 됩니다.

![Microsoft 365의 DLP 정책 구성](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-config.png)

다음은 GDPR에 대 한 인식을 위한 DLP 정책의 예입니다.

![GDPR에 대 한 인식을 위한 DLP 정책 예](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-example-policy.png)

DLP 정책을 만들고 적용 하는 방법에 대 한 자세한 내용은 [이 문서](../compliance/create-test-tune-dlp-policy.md) 를 참조 하세요.

### <a name="protection-levels-for-data-privacy"></a>데이터 개인 정보 보호 수준

다음 표에는 DLP를 사용 하 여 보호를 강화 하는 세 가지 구성이 나와 있습니다.

![DLP를 사용한 데이터 개인 정보 보호 수준](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-protection-levels.png)

첫 번째 구성, 보안 의식을 출발점으로 사용 하 고 데이터 개인 정보 규정 준수 요구를 해결 하기 위한 최소 수준의 보호를 사용할 수 있습니다.

>[!Note]
>보호 수준이 증가 하면 경우에 따라 사용자가 정보를 공유 하 고 액세스 하는 기능이 저하 될 수 있으며 생산성 또는 일상적인 작업을 완료 하는 기능에 영향을 줄 수도 있습니다.
>

보호 수준을 높일 때 직원 들이 보다 안전한 환경에서 계속 해 서 생산성을 유지 하도록 하기 위해 새 보안 정책 및 절차에 대 한 교육을 세우고 교육을 받을 수 있습니다.

### <a name="example-of-using-sensitivity-labels-with-dlp"></a>DLP와 함께 민감도 레이블 사용 예제

민감도 레이블은 DLP와 함께 작동 하 여 높은 규제 환경에서 데이터 개인 정보를 제공할 수 있습니다. 다음은 통합 배포의 주요 단계입니다.

1. 데이터 개인 정보 보호에 대 한 규정 및 기타 비즈니스 요구 사항을 문서화 합니다.
2. 대상 데이터 원본, 유형 및 소유권은 데이터 개인 정보 관련 문제를 기준으로 합니다.
3. 요구 사항을 해결 하 고 데이터 개인 정보 핫스팟을 보호 및 제어 하기 위한 전체 전략이 설정 됩니다.
4. 데이터 개인 정보 제어 전략을 해결 하기 위한 단계별 작업 계획은 현재 위치에 배치 됩니다.

이러한 요소가 결정 되 면 중요 한 정보 유형, 민감도 레이블 분류 및 DLP 정책을 함께 사용할 수 있습니다. 다음 그림에서는 예제를 보여 줍니다.

![DLP로 작업 하는 민감도 레이블의 예](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-sensitivity-lables-dlp.png)

[이 이미지의 더 큰 버전 보기](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-sensitivity-lables-dlp.png)

다음은 그림에 나와 있는 것 처럼 DLP 및 민감도 레이블을 사용 하는 몇 가지 데이터 보호 시나리오입니다.

| 시나리오 | 프로세스 |
|:-------|:-----|
| A | <ol><li>콘텐츠에 대 한 민감도 레이블은 관리자가 수동 또는 자동 응용 프로그램을 위해 콘텐츠 및 전자 메일에 대 한 사용자 및 그룹에 게시 합니다. </li><li>사용자 A는 콘텐츠와 상호 작용할 때 수동 또는 자동으로 레이블을 적용 하며 암호화 또는 기타 설정을 적용할 수 있습니다. </li><li>사용자 A는 보호 된 전자 메일 또는 파일을 사용자 B, 게스트 사용자에 게 보냅니다. </li></ol> |
| B | 관리자가 사용자에 게 게시 한 DLP 정책은 사용자 a가 사용자 B에 게 전자 메일 및/또는 파일을 보내는 것을 차단 합니다. |
| C |  민감도 레이블 "소유자가 게스트를 초대할 수 없습니다." 설정이 사용자 A에 게 게시 되며 팀 팀 또는 SharePoint 사이트를 프로 비전 합니다. 사이트의 다른 사용자가 사용자 B와 파일을 공유 하려고 하지만 DLP가이를 차단 합니다. |
| D | 사이트 콘텐츠에 대 한 자동 응용 프로그램의 민감도 레이블은 하나 이상의 사이트에 게시 되어 보호 된 사이트의 다른 보호 계층을 제공 합니다. |
|||

## <a name="office-365-message-encryption-ome-new-capabilities"></a>Office 365 메시지 암호화 (OME) 새로운 기능

전자 메일을 사용 하 여 환자 건강 정보 또는 고객 및 직원 정보와 같은 중요 한 항목을 교환 하는 경우가 많습니다. 전자 메일 메시지 암호화는 의도 된 받는 사람만 메시지 콘텐츠를 볼 수 있도록 합니다.

[OME](../compliance/ome.md)를 사용 하 여 조직 내부 및 외부의 사용자 간에 암호화 된 메시지를 보내고 받을 수 있습니다. OME는 Outlook.com, Yahoo!, Gmail 및 기타 전자 메일 서비스와 함께 작동 합니다. OME는 의도 된 받는 사람만 메시지 콘텐츠를 볼 수 있도록 합니다.

데이터 개인 정보 보호를 위해 OME를 사용 하 여 중요 한 항목이 포함 된 내부 메시지를 보호할 수 있습니다. Office 365 메시지 암호화는 Azure Information Protection의 일부인 Microsoft Azure RMS (서비스 권한 관리)를 기반으로 작성 된 온라인 서비스가 됩니다. 여기에는 전자 메일을 보호 하는 데 도움이 되는 암호화, id 및 권한 부여 정책이 포함 됩니다. 권한 관리 템플릿, 전달 금지 옵션 및 암호화 전용 옵션을 사용 하 여 메시지를 암호화할 수 있습니다.

메일 흐름 규칙을 정의 하 여이 보호를 적용할 수도 있습니다. 예를 들어 특정 받는 사람에 게 보내는 모든 메시지의 암호화가 필요 하거나 제목 줄에 특정 키워드 단어가 포함 된 규칙을 만들 수 있으며, 받는 사람이 메시지 내용을 복사 하거나 인쇄할 수 없도록 지정 합니다.

또한 OME [Advanced Message Encryption](../compliance/ome-advanced-message-encryption.md) 은 외부 받는 사람에 대 한 보다 유연한 제어 및 암호화 된 전자 메일에 대 한 액세스를 필요로 하는 규정 준수 의무를 충족 하는 데 도움이 됩니다. Microsoft 365에서 OME Advanced Message Encryption을 사용 하 여 조직 외부에서 공유 되는 중요 한 전자 메일을 제어할 수 있습니다 (중요 한 정보 유형을 검색 하는 자동 정책 포함). 

데이터 개인 정보 보호를 위해 외부 사용자와 전자 메일을 공유 해야 하는 경우 만료 날짜를 지정 하 고 메시지를 해지할 수 있습니다. 외부의 받는 사람에 게 보내는 메시지의 만료 날짜만 취소 하 고 설정할 수 있습니다.

### <a name="secure-email-scenarios-comparison-with-ome-and-sensitivity-labels"></a>보안 전자 메일 시나리오 OME 및 민감도 레이블 비교

암호화를 사용한 전자 메일에 적용 되는 OME 및 민감도 레이블은 약간 중복 되므로이 표에 나와 있는 것 처럼 적용할 수 있는 시나리오를 이해 하는 것이 중요 합니다.

| 시나리오 | 민감도 레이블 | OME |
|:-------|:-----|:-------|
| 내부 + 파트너 <br> 내부 사용자와 트러스트 된 파트너 간의 안전한 통신 및 공동 작업 | 권장-완벽 하 게 사용자 지정 된 분류 및 보호를 포함 하는 레이블 | 예 (분류 없이는 암호화만 하거나 전달 하지 않음) |
| 외부 파티 <br> 외부/소비자 사용자와 안전 하 게 통신 및 공동 작업 | 예 (레이블에서 받는 사람 미리 정의) | 받는 사람을 기준으로 just-in-time 보호 권장 |
| 내부 + 파트너 (만료/해지 있음) <br> 내부 사용자 및 만료 및 해지와 함께 트러스트 된 파트너를 사용 하 여 메일 및 콘텐츠 액세스 제어 | 액세스 기간을 사용 하 여 완전히 사용자 지정 된 보호 권장-사용자가 수동으로 파일을 추적 하 고 해지할 수 있음 | No-내부 메일에 대 한 해지 또는 만료 없음 |
| 만료/해지가 적용 된 외부 파티 <br> 만료 및 해지와 함께 외부/소비자 사용자에 게 메일 및 콘텐츠에 대 한 액세스 제어 | 예-사용자가 수동으로 파일을 추적할 수 있습니다. | 권장 (E5)-관리자가 보안 & 준수 센터에서 메일을 해지할 수 있음 |
| 자동 레이블 지정 <br> 조직에서 특정 중요 한 콘텐츠 및/또는 특정 받는 사람에 대 한 메일/첨부 파일을 자동으로 보호 하려고 합니다. | 권장 (E5)-Exchange 및 Outlook 클라이언트에서 자동 레이블 지정, 메일 흐름 규칙 및 DLP 정책 보강 | 예-메일 흐름 규칙 및 암호화만 사용 하는 DLP 정책 및 전달 방지 |
||||

또한 최종 사용자와 관리자가 이러한 두 가지 방법 사이의 차이가 있습니다.

## <a name="teams-with-protection-for-highly-sensitive-data"></a>중요 한 데이터를 보호 하는 팀

팀의 데이터 개인 정보 규정에 따라 개인 데이터를 저장 하려는 조직의 경우에는 다음에 대 한 자세한 지침 및 구성 단계를 제공 하는 [보안 격리를 사용 하 여 팀 구성](secure-teams-security-isolation.md)를 참조 하세요.

- ID 및 장치 액세스
- 비공개 팀 만들기
- 기본 팀 사이트 권한 잠금
- 암호화를 사용 하는 그룹 기반 민감도 레이블
