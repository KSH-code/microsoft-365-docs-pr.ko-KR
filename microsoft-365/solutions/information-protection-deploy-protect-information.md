---
title: 데이터 개인 정보 보호 규정을 준수하는 정보 보호
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: 보안 Microsoft 365 규정 준수 기능을 배포하고 개인 정보를 보호합니다.
ms.openlocfilehash: d605147b24c4f6ef3a12eedab2243bcaa4c6745b
ms.sourcegitcommit: ab5368888876d8796da7640553fc8426d040f470
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60785933"
---
# <a name="protect-information-subject-to-data-privacy-regulation"></a>데이터 개인 정보 보호 규정을 준수하는 정보 보호

데이터 개인 정보 규정 준수 요구 및 규정을 해결하기 위해 구독에 다양한 정보 보호 컨트롤을 사용할 수 있습니다. 여기에는 GDPR(일반 데이터 보호 규정), HIPAA-HITECH(미국 의료 개인 정보 보호법), 캘리포니아 소비자 보호법(CCPA) 및 브라질 데이터 보호법(LGPD)이 포함됩니다.

이러한 컨트롤은 다음 솔루션 영역 내에 있습니다.

- 민감도 레이블
- DLP(데이터 손실 방지)
- OME(Office 메시지 암호화)
- Teams 및 사이트 액세스 제어

![데이터 개인 정보 보호 규정에 따라 개인 정보를 보호하기 위한 주요 서비스입니다.](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-grid.png)

> [!NOTE]
> 이 솔루션은 데이터 개인 정보 규정을 준수하는 정보를 보호하기 위한 보안 및 규정 준수 기능에 대해 설명합니다. 보안 기능의 전체 목록은 Microsoft 365 [설명서를 Microsoft 365 참조하세요.](../security/index.yml) Microsoft 365 규정 준수 기능의 전체 목록은 Microsoft 365 [참조하세요.](../compliance/index.yml)

## <a name="data-privacy-regulations-that-impact-information-protection-controls"></a>정보 보호 제어에 영향을 미치는 데이터 개인 정보 보호 규정

다음은 정보 보호 제어와 관련이 있을 수 있는 데이터 개인 정보 보호 규정의 샘플 목록입니다.

- GDPR 제5조(1)(f))
- GDPR 문서 (32)(1)(a)
- LGPD 문서 46
- HIPAA-HITECH (45 CFR 164.312(e)(1))
- HIPAA-HITECH (45 C.F.R. 164.312(e)(2)(ii))

위의 각 [항목에 대한](information-protection-deploy-assess.md) 자세한 내용은 데이터 개인 정보 보호 위험 평가 및 중요한 항목 식별 문서를 참조하세요.

정보 보호를 위한 데이터 개인 정보 보호 규정은:

- 손실 또는 무단 액세스, 사용 및/또는 전송으로부터 보호합니다.
- 보호 메커니즘의 위험 기반 적용.
- 적절한 경우 암호화 사용.

조직에서 다른 준수 요구 또는 비즈니스 Microsoft 365 등의 다른 목적으로 콘텐츠의 보호를 원할 수도 있습니다. 데이터 개인 정보 보호를 위한 정보 보호 체계를 설정하는 것이 전체 정보 보호 계획, 구현 및 관리의 일부로 수행됩니다.

Microsoft 365 정보 보호 체계를 시작하는 데 도움이 되는 다음 섹션에는 사용자에 대한 관련 기능 및 개선 Microsoft 365. 이 목록에는 데이터 개인 정보 규정에 적용되는 기능 및 개선 작업이 포함되어 있습니다. 그러나 이전 기술을 대신하는 새로운 기능이 있는 경우 목록에는 이전 기술이 포함되어 없습니다. 예를 들어, SharePoint 및 OneDrive 대한 IRM(정보 권한 관리)은 목록에 포함되지 않지만 민감도 레이블이 포함됩니다.

## <a name="managing-information-protection-in-microsoft-365"></a>2016에서 정보 보호 Microsoft 365

Microsoft [정보 보호 솔루션에는](../compliance/information-protection.md) 다양한 통합 기능이 Microsoft 365, Microsoft Azure 및 Microsoft Windows. 이 Microsoft 365 정보 보호 솔루션에는 다음이 포함됩니다.

- [중요한 정보 유형(데이터](../compliance/sensitive-information-type-entity-definitions.md) 개인 정보 보호 위험 평가 및 중요한 항목 식별 문서에서 [설명)](information-protection-deploy-assess.md)
- [민감도 레이블](../compliance/sensitivity-labels.md)
  - 서비스/컨테이너 수준
  - 클라이언트 쪽/콘텐츠 수준
  - 미사용 데이터 및 데이터 저장에 SharePoint OneDrive
- DLP(데이터 손실 방지)
- [Microsoft 365 끝점 데이터 손실 방지](../compliance/endpoint-dlp-learn-about.md)
- [Office 365 메시지 암호화(OME)](../compliance/ome.md) 및 OME [고급 메시지 암호화의](../compliance/ome-advanced-message-encryption.md) 새로운 기능

또한 사이트 및 라이브러리 수준 보호는 모든 보호 체계에 포함하기 위한 중요한 메커니즘입니다.

외부의 다른 정보 보호 기능에 대한 자세한 Microsoft 365 참조하세요.

- [MICROSOFT 클라우드 응용 프로그램 보안(MCAS)](/cloud-app-security/)
- [Azure Information Protection](/azure/information-protection/what-is-information-protection)
- [Microsoft Endpoint Manager ](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)
- [Windows Information Protection](/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip)

## <a name="sensitivity-labels"></a>민감도 레이블

Microsoft Information Protection 프레임워크의 민감도 레이블을 사용하면 사용자의 생산성과 공동 작업 능력에 영향을 주지 않으면서 조직의 데이터를 분류하고 보호할 수 있습니다.

> [!div class="mx-imgBorder"]
> ![2016의 민감도 Microsoft 365.](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-labels.png)

### <a name="prerequisites-for-sensitivity-labels"></a>민감도 레이블의 선행 구성

아래 강조 표시된 민감도 레이블 기반 기능을 구현하기 전에 이러한 활동을 완료합니다.

1. 다음을 이해합니다.
   - **비즈니스 요구 사항.** 기업에서 민감도 레이블을 적용하는 비즈니스 이유를 수립합니다. 예를 들어 정보 보호를 위한 데이터 개인 정보 보호 요구 사항입니다.
   - **민감도 레이블 기능.** 민감도 레이블 지정은 복잡할 수 있으므로 [](../compliance/sensitivity-labels.md) 시작하기 전에 민감도 레이블 설명서를 읽어야 합니다.
   - **기억해야 할 주요 것** 민감도 레이블은 Microsoft 규정 준수 관리 센터에서 관리되지만 대상 지정 및 응용 프로그램 옵션은 크게 다릅니다.
      - 사이트, 그룹 및 Teams 수준에 대한 민감도 레이블이 있습니다(설정은 컨테이너 내부의 콘텐츠에는 적용되지 않습니다). 사이트, 그룹 또는 팀이 프로비전될 때 해당 사용자를 적용하는 사용자 및 그룹에 게시됩니다.
      - 활성 콘텐츠에 대한 민감도 레이블이 있습니다. 이러한 사용자는 수동으로 적용하거나 다음 경우 자동으로 적용되는 사용자 또는 그룹에도 게시됩니다.
        - 파일의 열기/편집/저장은 사용자의 데스크톱 또는 SharePoint 저장됩니다.
        - 전자 메일이 초안으로 작성 및 전송됩니다.
      - 전자 메일을 통해 전송되는 전자 메일 외에도 SharePoint 및 OneDrive 파일에 대한 자동 응용 프로그램에 대한 민감도 레이블이 Exchange. 이러한 사이트는 모든 사이트 또는 특정 사이트를 대상으로 하여 이러한 환경의 휴지 파일에 자동으로 적용됩니다.

2. 과거 또는 대체 방법을 사용하여 현재 민감도 레이블을 합리화

   - Azure Information Protection

      현재 민감도 레이블 지정 체계는 기존 Azure Information [Protection](../compliance/sensitivity-labels.md#sensitivity-labels-and-azure-information-protection) 레이블 구현과 조정해야 할 수 있습니다.
   - OME

      전자 메일 보호에 최신 민감도 레이블 지정을 사용하 고 OME와 같은 기존 전자 메일 암호화 방법이 준비되어 있는 경우 공존할 수 있지만 두 방법 중 하나를 적용해야 하는 시나리오를 이해해야 합니다. 최신 Office 365 메시지 암호화 보호와 OME 기반 보호를 비교하는 표가 포함된 [OME(새로운](#office-365-message-encryption-ome-new-capabilities)기능)를 참조합니다.

3. 더 광범위한 정보 보호 체계로의 통합을 계획합니다. OME와의 공존성에 더하여 민감도 레이블을 DLP(데이터 손실 방지) 및 Microsoft 365 같은 동시 Microsoft Cloud App Security. 데이터 [Microsoft Information Protection 정보](../compliance/information-protection.md) Microsoft 365 보호 목표를 달성하기 위한 자세한 정보를 참조하세요.

4. 민감도 레이블 분류 및 제어 체계를 개발합니다. 데이터 [분류 및 민감도 레이블 분류를 참조합니다.](https://aka.ms/dataclassificationwhitepaper)

### <a name="general-guidance"></a>일반 지침

1. **Schema 정의.** 기술 기능을 사용하여 레이블 및 보호를 적용하기 전에 조직 전체에서 분류표를 정의합니다. 개인 데이터를 더 쉽게 추가할 수 있도록 분류 Schema가 이미 있을 수 있습니다.
2. **시작.** 먼저 구현할 레이블의 수와 이름을 결정해야 합니다. 사용할 기술과 레이블이 적용되는 방식에 대해 걱정하지 않고 이 활동을 합니다. 이 스마마를 조직 전체에 적용합니다(사내 및 다른 클라우드 서비스에 있는 데이터 포함).
3. **추가 권장 사항** 정책, 레이블 및 조건을 디자인하고 구현할 때 다음 권장 사항을 고려하세요.

   - **기존 분류 스마(있는 경우)를 사용 합니다.** 많은 조직에서 이미 어떤 형태로 데이터 분류를 사용하고 있습니다. 기존 레이블 스마마를 신중하게 평가하고 가능한 경우 있는 것으로 사용하세요. 최종 사용자가 인식할 수 있는 친숙한 레이블을 사용하는 것이 채택을 주도합니다.
   - **작게 시작** 만들 수 있는 레이블 수에는 거의 제한이 없습니다. 그러나 많은 수의 레이블과 하위 레이블은 채택 속도가 느려질 수 있습니다.
   - **시나리오 및 사용 사례를 사용 합니다.** 조직 내에서 일반적인 사용 사례를 식별하고 적용 대상 데이터 개인 정보 규정에서 파생된 시나리오를 사용 합니다. 현재의 레이블 및 분류 구성이 실제로 작동할지 여부를 검증합니다.
   - **새 레이블에 대한 모든 요청에 대해 질문합니다.** 모든 시나리오 또는 사용 사례에 새 레이블이 실제로 필요합니까 아니면 이미 있는 레이블을 사용할 수 있나요? 레이블 수를 최소로 유지하여 채택을 향상합니다.
   - **주요 부서에 하위 레이블을 사용 합니다.** 일부 부서에는 특정 레이블이 필요한 특정 요구가 있습니다. 이러한 레이블을 기존 레이블에 대한 하위 레이블로 정의하고 전역이 아닌 사용자 그룹에 할당된 범위 지정 정책을 사용하는 것이 좋습니다.
   - **범위가 지정한 정책을 고려합니다.** 사용자 하위 집합을 대상으로 하는 정책은 레이블 오버로드를 방지합니다. 범위가 지정되어 있는 정책을 사용하면 특정 부서에서 일하는 직원에게만 역할 또는 부서별 레이블 또는 하위 레이블을 할당할 수 있습니다.
   - **의미 있는 레이블 이름을 사용 합니다.** 약어, 표준 또는 약어를 레이블 이름으로 사용하지 않습니다. 최종 사용자에게 공명하는 이름을 사용하여 채택을 향상합니다. PII, PCI, HIPAA, LBI, MBI 및 HBI와 같은 레이블을 사용하는 대신, 업무 외, 공개, 일반, 기밀 및 기밀과 같은 이름을 고려하세요.

### <a name="create-and-deploy-sensitivity-labels-for-sites-groups-and-teams"></a>사이트, 그룹 및 팀에 대한 민감도 레이블 만들기 및 배포

에서 [민감도](../compliance/sensitivity-labels-teams-groups-sites.md) <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">레이블을</a>만들 때 Microsoft 365 규정 준수 센터 컨테이너에 적용할 수 있습니다.

- Microsoft Teams 사이트
- Microsoft 365 그룹(이전 Office 365 그룹)
- SharePoint 사이트

다음 레이블 설정을 사용하여 이러한 컨테이너의 콘텐츠를 보호할 수 있습니다.

- 그룹에 연결된 Microsoft 365 사이트의 개인 정보(공개 또는 Teams)
- 외부 사용자 액세스
- 관리되지 않는 장치에서 액세스

데이터 개인 정보 보호를 위해 중요한 개인 데이터로 콘텐츠를 저장하는 데 사용되는 컨테이너에 대한 외부 공유를 방지하려면 데이터가 포함된 파일을 비공개로 표시하고 관리되는 장치가 필요합니다.

### <a name="create-and-deploy-sensitivity-labels-for-content"></a>콘텐츠에 대한 민감도 레이블 만들기 및 배포

파일에 적용된 민감도 레이블을 사용하면 콘텐츠를 암호화하고, 콘텐츠를 워터마크하고, Office 응용 프로그램 콘텐츠에 대한 기타 컨트롤을 정의할 수 Outlook 웹용 Office.

민감도 레이블을 사용하여 조직의 데이터를 보호하기 시작할 준비가 된 경우:

1. **레이블을 만듭니다.** 다양한 민감도 수준의 컨텐츠에 대한 조직의 분류체계에 따라 민감도 레이블을 작성하고 이름을 지정하십시오. 분류 분류를 개발하는 데 대한 자세한 내용은 데이터 분류 및 민감도 레이블 분류 [백서 를 참조하세요.](https://aka.ms/dataclassificationwhitepaper)
2. **각 레이블이 수행할 수 있는 작업을 정의합니다.** 각 레이블과 연결할 보호 설정을 구성합니다. 예를 들어 민감도가 낮은 콘텐츠(예: "일반" 레이블)에 머리마크나 발자국만 적용하고 민감도가 높은 콘텐츠(예: "기밀" 레이블)에는 워터마크를 적용하고 암호화를 사용하도록 설정해야 할 수 있습니다.
3. **레이블을 게시합니다.** 민감도 레이블이 구성되 면 레이블 정책을 사용하 여 해당 레이블을 게시합니다. 어떤 사용자와 그룹에 레이블과 정책 설정을 사용할지 결정합니다. 단일 레이블을 다시 사용할 수 있습니다. 한 번 정의한 다음 여러 사용자에게 할당된 여러 레이블 정책에 포함할 수 있습니다.

앱의 민감도 레이블을 Microsoft 365 규정 준수 센터 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">사용자가</a>만들거나 편집할 때 콘텐츠를 분류하고 [보호할](../compliance/sensitivity-labels-office-apps.md) 수 있도록 Office 앱에 표시됩니다.

![민감도 레이블 배포 흐름의 Microsoft 365.](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-label-flow.png)

데이터 개인 정보 보호를 위해 중요한 개인 정보를 포함하는 전자 메일 또는 콘텐츠에 암호화 및 기타 규칙을 사용하여 민감도 레이블을 수동으로 적용합니다.

> [!NOTE]
> 전자 메일에 암호화가 적용된 민감도 레이블에는 OME와 일부 겹치는 기능이 있습니다. OME 및 민감도 [레이블과의 보안 전자 메일 시나리오 비교를 참조하세요.](#secure-email-scenarios-comparison-with-ome-and-sensitivity-labels)

### <a name="client-side-auto-labeling-when-users-edit-documents-or-compose-emails"></a>사용자가 문서를 편집하거나 전자 메일을 작성하는 경우 클라이언트 쪽 자동 레이블 지정

민감도 레이블을 만들 때 [](../compliance/apply-sensitivity-label-automatically.md) 지정한 조건과 일치하는 경우 전자 메일을 포함하여 콘텐츠에 해당 레이블을 자동으로 할당할 수 있습니다.

콘텐츠에 자동으로 민감도 레이블을 적용하는 기능도 다음과 같은 이유로 중요합니다.

- 사용자에게 각 분류를 언제 사용할지 교육할 필요가 없습니다.
- 모든 콘텐츠를 올바르게 분류하기 위해 사용자에게 의존할 필요가 없습니다.
- 사용자가 더 이상 정책을 알 필요가 없으며, 대신 업무에 집중할 수 있습니다.

자동 레이블 지정은 레이블을 자동으로 적용하는 것뿐만 아니라 사용자에게 레이블을 권장할 수 있도록 합니다. 그러나 두 경우 모두 사용자가 레이블을 수락할지 또는 거부할지 결정하여 내용에 올바른 레이블을 지정할 수 있도록 합니다.

이 클라이언트 쪽 레이블에는 문서가 저장되기 전에 레이블을 지정할 수 있으므로 문서에 대한 지연 시간이 최소화됩니다. 그러나 일부 클라이언트 앱에서는 자동 레이블 지정을 지원하지 않습니다. 이 기능은 Azure Information Protection 통합 레이블 지정 클라이언트와 일부 버전의 Office [지원됩니다.](../compliance/sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)

구성 지침은 앱에 대한 자동 레이블 지정을 [구성하는 Office 참조하세요.](../compliance/sensitivity-labels-office-apps.md#support-for-sensitivity-label-capabilities-in-apps)

데이터 개인 정보 보호를 위해 중요한 개인 정보를 포함하는 콘텐츠에 대해 민감도 레이블을 자동으로 적용합니다.

### <a name="service-side-auto-labeling-when-content-is-already-saved"></a>콘텐츠가 이미 저장된 경우 서비스 쪽 자동 레이블 지정

이 방법을 민감도 레이블이 있는 자동 분류라고 합니다. 미사용 데이터(SharePoint 및 OneDrive 문서의 경우) 및 전송되는 데이터(Exchange)에 대한 자동 레이블 지정이라고도 들 수 있습니다. 이 Exchange 휴지통의 전자 메일은 포함하지 않습니다.

이 레이블 지정은 사용자 응용 프로그램이 아닌 서비스 자체에서 적용하기 때문에 사용자가 사용하는 앱과 버전에 대해 걱정할 필요가 없습니다. 따라서 이 기능은 조직 전체에서 즉시 사용할 수 있으며 대규모로 레이블을 지정하는 데 적합합니다. 자동 레이블 지정 정책은 사용자가 레이블 지정 프로세스와 상호 작용하지 않기 때문에 권장되는 레이블 지정을 지원하지 않습니다. 대신 관리자가 시뮬레이션 모드에서 정책을 실행하여 실제로 레이블을 적용하기 전에 콘텐츠의 올바른 레이블을 확인합니다.

구성 지침은 에 대한 자동 레이블 지정 정책을 구성하는 [SharePoint,](../compliance/apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange)OneDrive 및 Exchange.

우려되는 사이트 내의 데이터 개인 정보 보호를 위해 중요한 개인 정보를 포함하는 콘텐츠의 자동 암호화를 위해 민감도 레이블을 푸시합니다.

## <a name="data-loss-prevention"></a>데이터 손실 방지

데이터 손실 [방지(DLP)를](../compliance/dlp-learn-about-dlp.md) 사용하여 Microsoft 365, 부적절하거나 부적절한 공유(예: 개인 정보를 포함하는 데이터 공유)를 내부 및 외부적으로 감지, 경고 및 차단할 수 있습니다.

DLP를 사용하면 다음을 할 수 있습니다.

- 위험한 공유 활동을 식별하고 모니터링합니다.
- 사용자에게 컨텍스트 내 지침을 교육하여 올바른 결정을 내릴 수 있도록 합니다.
- 생산성을 저해하지 않고 콘텐츠에 데이터 사용 정책을 적용합니다.
- 분류 및 레이블 지정과 통합하여 데이터를 공유할 때 데이터를 검색하고 보호합니다.

### <a name="supported-workloads-for-dlp"></a>DLP에 지원되는 워크로드

Microsoft 365 규정 준수 센터 DLP 정책을 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank"></a>사용하여 Microsoft 365, SharePoint Exchange Online, OneDrive 및 Microsoft 365의 여러 위치에서 중요한 항목을 식별, 모니터링 및 자동으로 보호할 수 Microsoft Teams.

예를 들어 모든 OneDrive 사이트에 저장된 신용 카드 번호가 포함된 문서를 식별하거나 특정 OneDrive 사이트만 모니터링할 수 있습니다.

또한 로컬로 설치된 버전의 Excel, PowerPoint 및 Word에서 중요한 항목을 모니터링하고 보호할 수 있습니다. 여기에는 중요한 항목을 식별하고 DLP 정책을 적용하는 기능을 포함할 수 있습니다. DLP는 사용자가 이러한 앱의 콘텐츠를 공유할 Office 제공합니다.

> [!div class="mx-imgBorder"]
> ![DLP에 대해 지원되는 워크로드입니다.](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-supported-workloads.png)

이 그림에서는 개인 데이터를 보호하는 DLP의 예를 보여줍니다.

> [!div class="mx-imgBorder"]
> ![DLP를 사용하여 개인 데이터를 보호하는 예입니다.](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-example-use.png)

DLP는 상태 레코드가 포함된 문서 또는 전자 메일을 식별한 다음 해당 문서에 대한 액세스를 자동으로 차단하거나 전자 메일이 전송되지 못하게 차단하는 데 사용됩니다. 그런 다음 DLP는 정책 팁을 통해 받는 사람에게 알리고 최종 사용자 및 관리자에게 알림을 보냅니다.

### <a name="planning-for-dlp"></a>DLP 계획

DLP 정책 계획:

- 비즈니스 요구 사항

- 데이터 개인 정보 보호 위험 평가 및 중요한 항목 식별 문서에 설명된 조직의 위험 기반 [평가입니다.](information-protection-deploy-assess.md)

- 기타 정보 보호 및 거버넌스 메커니즘이 설정되거나 데이터 개인 정보 보호를 계획하는 데 있습니다.

- 데이터 개인 정보 보호 위험 평가 및 중요한 항목 식별 문서에 설명된 평가 작업을 기반으로 개인 데이터에 대해 식별한 중요한 정보 [유형입니다.](information-protection-deploy-assess.md) DLP 정책 조건은 중요한 정보 유형과 보존 레이블을 모두 기반으로 할 수 있습니다.

- DLP 조건을 지정하는 데 필요한 보존 레이블입니다. 자세한 [내용은 조직 문서의](information-protection-deploy-govern.md) 데이터 개인 정보 보호 규정이 적용된 정보 관리 문서를 참조하세요.

- 지속적인 DLP 정책 관리 - 조직의 누군가가 중요한 정보 유형, 보존 레이블, 규정 및 규정 준수 정책의 변경에 대한 정책을 운영하고 조정해야 합니다.

민감도 레이블은 DLP 정책 조건에서 사용할 수 없습니다. 그러나 중요한 정보 유형에 따라 자동으로 적용할 수 있는 민감도 레이블만 사용하여 액세스를 차단하는 특정 보호 시나리오를 사용할 수 있습니다. 강력한 민감도 레이블이 있는 경우 다음과 같은 경우 보호를 강화하는 데 DLP를 사용할지 여부를 고려합니다.

  - DLP는 파일 공유를 방지할 수 있습니다. 민감도 레이블은 액세스를 차단할 수 있습니다.

  - DLP는 규칙, 조건 및 작업 측면에서 더 세부적인 제어 수준을 가집니다.

  - DLP 정책은 채팅 및 채널 메시지에 Teams 수 있습니다. 민감도 레이블은 문서 및 전자 메일에만 적용할 수 있습니다.


### <a name="dlp-policies"></a>DLP 정책

DLP 정책은 Microsoft 준수 관리 센터에서 구성하고 보호 수준, 정책이 찾는 중요한 정보 유형 및 대상 작업을 지정합니다. 기본 구성 요소는 보호 및 데이터 유형을 식별하는 것으로 구성됩니다.

> [!div class="mx-imgBorder"]
> ![DLP 정책 구성의 Microsoft 365.](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-config.png)

다음은 GDPR의 인식을 위한 DLP 정책의 예입니다.

![GDPR에 대한 인식을 위한 DLP 정책 예제.](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-example-policy.png)

DLP [정책을 만들고](../compliance/create-test-tune-dlp-policy.md) 적용하는 데 대한 자세한 내용은 이 문서를 참조하세요.

### <a name="protection-levels-for-data-privacy"></a>데이터 개인 정보 보호를 위한 보호 수준

다음 표에는 DLP를 사용하여 보호를 강화하는 세 가지 구성이 나열되어 있습니다.

![DLP를 사용하여 데이터 개인 정보 보호의 보호 수준.](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-dlp-protection-levels.png)

첫 번째 구성인 인식을 시작점 및 최소 수준의 보호로 사용하여 데이터 개인 정보 보호 규정에 대한 규정 준수 요구 사항을 해결할 수 있습니다.

> [!NOTE]
> 보호 수준이 증가하면 사용자가 정보를 공유하고 액세스할 수 있는 능력이 감소하여 일상적인 작업을 완료하는 생산성이나 능력에 영향을 줄 수 있습니다.

보호 수준을 높이면 직원들이 보다 안전한 환경에서 계속 생산성을 유지하게 도와주기 위해 시간을 내어 새로운 보안 정책 및 절차에 대해 교육하고 교육합니다.

### <a name="example-of-using-sensitivity-labels-with-dlp"></a>민감도 레이블을 DLP와 함께 사용하는 예

민감도 레이블은 DLP와 함께 작동하여 높은 규제 대상 환경에서 데이터 개인 정보를 제공할 수 있습니다. 통합 배포의 주요 단계는 다음과 같습니다.

1. 데이터 개인 정보 보호에 대한 규정 및 기타 비즈니스 요구 사항이 문서화되어 있습니다.
2. 대상 데이터 원본, 유형 및 소유권은 데이터 개인 정보 보호 관련 문제와 관련되어 있습니다.
3. 요구 사항을 해결하고 데이터 개인 정보 보호 핫스팟을 보호하고 관리하기 위한 전반적인 전략이 설정되었습니다.
4. 데이터 개인 정보 제어 전략을 해결하기 위한 단계적 실행 계획이 수립됩니다.

이러한 요소가 결정되면 중요한 정보 유형, 민감도 레이블 분류 및 DLP 정책을 함께 사용할 수 있습니다. 이 그림은 예를 보여줍니다.

> [!div class="mx-imgBorder"]
> ![DLP로 작업하는 민감도 레이블의 예입니다.](../media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-sensitivity-lables-dlp.png)

[이 이미지의 더 큰 버전 참조](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/information-protection-deploy-protect-information/information-protection-deploy-protect-information-sensitivity-lables-dlp.png)

다음은 그림과 같이 DLP 및 민감도 레이블을 함께 사용하는 몇 가지 데이터 보호 시나리오입니다.

| 시나리오 | 프로세스 |
|:-------|:-----|
| A | <ol><li>콘텐츠에 대한 민감도 레이블은 콘텐츠 및 전자 메일에 대한 수동 또는 자동 응용 프로그램용 사용자 및 그룹에 게시됩니다. </li><li>사용자 A는 콘텐츠와 상호 작용할 때 암호화 또는 기타 설정을 적용하여 수동으로 또는 자동으로 레이블을 적용합니다. </li><li>사용자 A는 보호된 전자 메일 또는 파일을 게스트 사용자인 사용자 B에게 전송합니다. </li></ol> |
| B | 관리자가 사용자 A에게 게시한 DLP 정책은 사용자 A가 사용자 B에게 전자 메일 및/또는 파일을 보내지 않습니다. |
| C |  "소유자가 게스트를 초대할 수 없습니다." 설정이 있는 민감도 레이블이 사용자 A에게 게시됩니다. 사용자 A는 Teams 팀 또는 SharePoint 게시됩니다. 사이트의 다른 사용자가 사용자 B와 파일을 선택적으로 공유하지만 DLP는 파일을 차단합니다. |
| D | 사이트 콘텐츠 자동 응용 프로그램에 대한 민감도 레이블은 하나 이상의 사이트에 게시되어 보호된 사이트가 될 수 있는 또 다른 보호 계층을 제공합니다. |
|||

## <a name="office-365-message-encryption-ome-new-capabilities"></a>Office 365 메시지 암호화(OME) 새로운 기능

사람들은 종종 전자 메일을 사용하여 환자 건강 정보 또는 고객 및 직원 정보와 같은 중요한 항목을 교환합니다. 전자 메일 메시지 암호화를 사용하면 받는 사람만 메시지 콘텐츠를 볼 수 있습니다.

[OME를](../compliance/ome.md)사용하면 조직 내부 및 외부의 사용자 간에 암호화된 메시지를 보내고 받을 수 있습니다. OME는 Outlook.com, Yahoo!, Gmail 및 기타 전자 메일 서비스에서 작동합니다. OME는 의도한 받는 사람만 메시지 콘텐츠를 볼 수 있도록 합니다.

데이터 개인 정보 보호를 위해 OME를 사용하여 중요한 항목이 포함된 내부 메시지를 보호합니다. Office 365 메시지 암호화 Azure Information Protection의 일부인 Microsoft Azure 권한 관리(Azure RMS)를 사용하여 구축된 온라인 서비스입니다. 여기에는 전자 메일을 보호하는 데 도움이 되는 암호화, ID 및 권한 부여 정책이 포함됩니다. 권한 관리 템플릿, 전달 금지 옵션 및 암호화 전용 옵션을 사용하여 메시지를 암호화할 수 있습니다.

메일 흐름 규칙을 정의하여 이 보호를 적용할 수도 있습니다. 예를 들어 특정 받는 사람에게 주소가 지정되는 모든 메시지의 암호화가 필요하거나 제목 줄에 특정 키워드 단어가 포함된 규칙을 만들고 받는 사람이 메시지 내용을 복사하거나 인쇄할 수 있도록 지정할 수도 있습니다.

또한 OME [고급](../compliance/ome-advanced-message-encryption.md) 메시지 암호화는 외부 받는 사람에 대한 보다 유연한 제어 및 암호화된 전자 메일에 대한 액세스가 필요한 준수 의무를 충족하는 데 도움이 됩니다. OME 고급 메시지 암호화를 Microsoft 365 중요한 정보 유형을 감지하는 자동 정책을 사용하여 조직 외부에서 공유되는 중요한 전자 메일을 제어할 수 있습니다.

데이터 개인 정보 보호를 위해 외부 사용자와 전자 메일을 공유해야 하는 경우 만료 날짜를 지정하고 메시지를 취소할 수 있습니다. 외부 받는 사람에게 보낸 메시지의 만료 날짜만 해지하고 설정할 수 있습니다.

### <a name="secure-email-scenarios-comparison-with-ome-and-sensitivity-labels"></a>OME 및 민감도 레이블과의 보안 전자 메일 시나리오 비교

암호화가 있는 전자 메일에 적용된 OME 및 민감도 레이블은 몇 가지 겹치기 때문에 이 표에 표시된 것 같이 어떤 시나리오가 적용될 수 있는지 이해하는 것이 중요합니다.

| 시나리오 | 민감도 레이블 | OME |
|:-------|:-----|:-------|
| 내부 + 파트너 <br> 내부 사용자와 신뢰할 수 있는 파트너 간에 안전하게 통신 및 공동 작업 | 권장 - 완전히 사용자 지정된 분류 및 보호가 있는 레이블 | 예 - 분류가 없는 암호화만 또는 보호 전달 안 |
| 외부 당사자 <br> 외부/소비자 사용자와 안전하게 통신 및 공동 작업 | 예 - 레이블의 받는 사람 미리 지정 | 권장 - 받는 사람 기반의 Just-In-Time 보호 |
| 만료/해지가 있는 내부 + 파트너 <br> 만료 및 해지로 내부 사용자 및 신뢰할 수 있는 파트너와 메일 및 콘텐츠에 대한 액세스 제어 | 권장 - 액세스 기간이 있는 완전히 사용자 지정된 보호, 사용자가 파일을 수동으로 추적하고 해지할 수 있습니다. | 아니요 – 내부 메일에 대한 해지 또는 만료 없음 |
| 만료/해지가 있는 외부 당사자 <br> 만료 및 해지로 외부/소비자 사용자와의 메일 및 콘텐츠 액세스 제어 | 예 - 사용자가 파일을 수동으로 추적할 수 있습니다. | 권장(E5) – 관리자가 보안 및 준수 센터에서 & 수 있습니다. |
| 자동 레이블 <br> 조직은 특정 중요한 콘텐츠 및/또는 특정 받는 사람이 있는 메일/첨부 파일을 자동으로 보호하려는 경우 | 권장(E5) - Exchange 및 Outlook 클라이언트의 자동 레이블 지정, 메일 흐름 규칙 및 DLP 정책 보강 | 예 - 암호화만 또는 전달하지 않는 보호를 적용한 메일 흐름 규칙 및 DLP 정책 |
||||

또한 이 두 방법 간에 최종 사용자 및 관리자 환경의 차이점이 있습니다.

## <a name="teams-with-protection-for-highly-sensitive-data"></a>Teams 중요한 데이터를 보호하는 기능 제공

Teams 데이터 개인 정보 보호 규정을 따르는 개인 데이터를 저장하도록 계획하는 조직은 [다음에](secure-teams-security-isolation.md)대한 자세한 지침 및 구성 단계를 제공하는 보안 Teams 팀 구성을 참조하세요.

- ID 및 장치 액세스
- 비공개 팀 만들기
- 팀 사이트 사용 권한의 잠금
- 암호화가 있는 그룹 기반 민감도 레이블