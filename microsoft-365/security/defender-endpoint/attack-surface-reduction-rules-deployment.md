---
title: 공격 표면 축소 규칙 배포
description: 공격 표면 감소 규칙을 배포하기 위한 지침을 제공합니다.
keywords: 공격 표면 감소 규칙 배포, ASR 배포, asr 규칙 사용, ASR 구성, 호스트 침입 방지 시스템, 보호 규칙, 악용 방지 규칙, 악용 방지 규칙, 감염 방지 규칙, 끝점용 Microsoft Defender, ASR 규칙 구성
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: jweston-1
ms.author: v-jweston
ms.reviewer: oogunrinde, sugamar, jcedola
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: f3ab66236697b52f0b267685be5247b9da88219d
ms.sourcegitcommit: 6dbf879f769a825ed7039363f3a91d676e355ee0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2021
ms.locfileid: "60947928"
---
# <a name="attack-surface-reduction-rules-deployment-guide"></a>공격 표면 감소 규칙 배포 가이드

## <a name="before-you-begin"></a>시작하기 전에

공격 표면은 조직이 사이버 위협 및 공격에 취약한 모든 장소입니다. 조직의 공격 표면에는 공격자가 조직의 장치 또는 네트워크를 손상시킬 수 있는 모든 위치가 포함됩니다. 공격 표면을 줄이면 조직의 장치와 네트워크를 보호하여 공격자가 더 적은 방법으로 공격할 수 있습니다. 끝점용 Microsoft Defender에 있는 많은 보안 기능 중 하나인 ASR(공격 표면 축소) 규칙을 구성하면 도움이 될 수 있습니다.

ASR 규칙은 다음과 같은 특정 소프트웨어 동작을 대상으로 합니다.

- 파일 다운로드 또는 실행을 시도하는 실행 파일 및 스크립트 실행
- 난동 또는 기타 의심스러운 스크립트 실행
- 앱이 일반적으로 일반적인 일과 중에 발생하지 않는 동작

다양한 공격 표면을 줄이면 처음에 공격이 일어나지 않도록 방지할 수 있습니다.

초기 준비 중에 준비할 시스템의 기능을 이해하는 것이 중요합니다. 기능을 이해하면 조직을 보호하는 데 가장 중요한 ASR 규칙을 결정하는 데 도움이 됩니다.

>[!IMPORTANT]
>이 가이드에서는 ASR 규칙을 구성하는 방법을 결정하는 데 도움이 되는 이미지 및 예제를 제공합니다. 이러한 이미지 및 예제는 환경에 가장 적합한 구성 옵션을 반영하지 않을 수 있습니다.

시작하기 전에 공격 표면 감소 개요 [및](overview-attack-surface-reduction.md)공격 표면 감소 규칙의mystifying - 기본 정보에 대한 [1부를](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/demystifying-attack-surface-reduction-rules-part-1/ba-p/1306420) 검토하세요. 적용 범위 및 잠재적인 영향을 이해하기 위해 현재 ASR 규칙 집합에 익숙해지세요. 공격 [표면 감소 규칙을 참조합니다.](attack-surface-reduction-rules.md)

ASR 규칙은 끝점용 Microsoft Defender 내의 공격 범위 축소 기능 중 하나일 뿐입니다. 이 문서에서는 ASR 규칙을 효과적으로 배포하여 사람이 운영하는 랜섬웨어 및 기타 위협과 같은 고급 위협을 중지하는 방법을 자세히 다룰 것입니다.  

### <a name="rules-by-category"></a>범주별 규칙

공격 범위 축소 규칙을 사용하여 맬웨어 감염 방지에 설명된 것 [처럼](attack-surface-reduction.md)조직을 보호하기 위해 사용할 수 있는 MDE 내에 여러 공격 범위 축소 규칙이 있습니다. 다음은 범주별로 구분된 규칙입니다.

<br/>

| 다형성 위협 | 측면 이동 & 자격 증명 도난 | 생산성 앱 규칙 |  전자 메일 규칙 | 스크립트 규칙 | 잘못된 규칙 |
|:---|:---|:---|:---|:---|:---|
| 실행 파일이 보전(1000대 컴퓨터), 보존 기한(24시간) 또는 신뢰할 수 있는 목록 기준을 충족하지 않는 한 실행 파일이 실행되지 못하게 차단 | PSExec 및 WMI 명령에서 시작된 프로세스 생성 차단 | 앱에서 Office 콘텐츠를 만들지 차단 | 전자 메일 클라이언트 및 웹 메일에서 실행 가능한 콘텐츠 차단 | 난분된 JS/VBS/PS/매크로 코드 차단 | 악용된 취약한 드라이버의 남용 차단 <sup> [[1]](#fn1)<sup></sup>  |
| USB에서 실행된 무단 및 사인되지 않은 프로세스 차단 | 로컬 보안 기관 하위 Windows(lsass.exe)에서 자격 증명 도용 차단 <sup> [[2]](#fn1)<sup></sup>   | 앱의 Office 프로세스 만들기 차단 |  통신 응용 Office 자식 프로세스 만들기만 차단 | JS/VBS에서 다운로드한 실행 가능 콘텐츠 시작 차단 | |
| 랜섬웨어에 대한 고급 보호 사용 | WMI 이벤트 구독을 통한 지속성 차단 | 앱에서 Office 프로세스에 코드를 삽입하지 차단 | 통신 Office 자식 프로세스를 만들지 차단 | | |
| | | Adobe Reader에서 하위 프로세스를 만들지 차단 | | | |

(<a id="fn1">1)</a> _악용된_ 취약한 드라이버의 남용을 차단하는 것은 현재 MEM 끝점 보안에서 사용할 수 없습니다. [MEM OMA-URI 를](enable-attack-surface-reduction.md#mem)사용하여 이 규칙을 구성할 수 있습니다.

(<a id="fn1">2)</a>일부 ASR 규칙은 상당한 노이즈를 생성하지만 기능을 차단하지 않습니다. 예를 들어 Chrome을 업데이트하는 경우 Chrome은 액세스 lsass.exe. 암호는 장치의 lsass에 저장됩니다. 그러나 Chrome은 로컬 디바이스 디바이스에 액세스하지 lsass.exe. 규칙이 lsass에 대한 액세스를 차단하도록 설정하면 많은 이벤트가 생성됩니다. 이러한 이벤트는 소프트웨어 업데이트 프로세스에서 해당 이벤트에 액세스하지 lsass.exe. 이 규칙을 사용하도록 설정하면 Chrome 업데이트가 lsass에 액세스하지 못하지만 Chrome 업데이트가 차단되지는 않습니다. 이는 응용 프로그램에 대해 불필요한 호출을 하는 다른 응용 lsass.exe. _lsass 규칙에_ 대한 액세스 차단은 lsass에 대한 불필요한 호출을 차단하지만 응용 프로그램의 실행을 차단하지는 않습니다.

### <a name="infrastructure-requirements"></a>인프라 요구 사항

ASR 규칙을 구현하는 여러 방법이 가능하기는 하지만 이 가이드는 다음으로 구성된 인프라를 기반으로 합니다.

- Azure Active Directory
- MEM(Microsoft Endpoint Management)
- Windows 10 및 Windows 11 장치
- Microsoft Defender for Endpoint E5 또는 Windows E5 라이선스

ASR 규칙 및 보고를 전체적으로 활용하기 위해 E5 또는 Microsoft 365 Defender E5 Windows 및 A5를 사용하는 것이 좋습니다. 자세한 정보: [끝점용 Microsoft Defender에 대한 최소 요구 사항.](minimum-requirements.md)

>[!Note]
>ASR 규칙을 구성하는 방법은 여러 가지가 있습니다. ASR 규칙은 MEM(Microsoft Endpoint Manager), PowerShell, 그룹 정책, MICROSOFT SYSTEM CENTER CONFIGURATION MANAGER(SCCM), MEM OMA-URI를 사용하여 구성할 수 있습니다.
>인프라 요구 사항에 나열된 구성과 다른  인프라 구성을 사용하는 경우(위의 경우) 공격 표면 감소 규칙 사용에서 다른 구성을 사용하여 공격 표면 축소 규칙을 배포하는 방법에 대해 자세히 알아보십시오. [](enable-attack-surface-reduction.md)  

### <a name="asr-rules-dependencies"></a>ASR 규칙 종속성

Microsoft Defender 바이러스 백신 및 기본 바이러스 백신 솔루션으로 구성해야 합니다. 다음 모드에 있어야 합니다.

- 기본 바이러스 백신/맬웨어 방지 솔루션  
- 상태: 활성 모드

Microsoft Defender 바이러스 백신 모드 중 하나일 수 없습니다.

- 수동
- 차단 모드에서 끝점 감지 및 응답(EDR)을 EDR 수동 모드
- LPS(제한된 주기적 검사)
- 해제

클라우드 제공 보호 및 [Microsoft Defender 바이러스 백신.](cloud-protection-microsoft-defender-antivirus.md)

### <a name="cloud-protection-maps-must-be-enabled"></a>MAPS(클라우드 보호)를 사용하도록 설정해야 합니다.

Microsoft Defender 바이러스 백신 Microsoft 클라우드 서비스와 원활하게 작동합니다. MICROSOFT MAPS(Advanced Protection Service)라고도 하는 이러한 클라우드 보호 서비스는 표준 실시간 보호를 향상하여 최상의 바이러스 백신 방어를 제공합니다. 클라우드 보호는 맬웨어 및 ASR 규칙의 중요한 구성 요소로부터의 위반을 방지하는 데 중요합니다.
[에서 클라우드 제공 보호를 Microsoft Defender 바이러스 백신.](enable-cloud-protection-microsoft-defender-antivirus.md)

### <a name="microsoft-defender-antivirus-components-must-be-current-versions"></a>Microsoft Defender 바이러스 백신 구성 요소가 현재 버전이 되어야 합니다.

다음 Microsoft Defender 바이러스 백신 구성 요소 버전은 현재 사용 가능한 가장 최근 버전보다 두 개 이전 버전이 아니어도 됩니다.

- **Microsoft Defender 바이러스 백신 버전** - Microsoft Defender 바이러스 백신 플랫폼이 매월 업데이트됩니다.
- **Microsoft Defender 바이러스 백신 버전** - Microsoft Defender 바이러스 백신 엔진이 월별 업데이트됩니다.
- **Microsoft Defender 바이러스 백신** 인텔리전스 사용 - Microsoft는 최신 위협을 해결하고 검색 논리를 구체화하기 위해 Microsoft Defender 보안 인텔리전스(정의 및 서명)를 지속적으로 업데이트합니다.

최신 Microsoft Defender 바이러스 백신 유지하면 ASR 규칙이 가긍적 결과를 줄일 수 있으며 Microsoft Defender 바이러스 백신 기능이 향상됩니다. 현재 버전 및 다양한 Microsoft Defender 바이러스 백신 업데이트하는 방법에 대한 자세한 내용은 Microsoft Defender 바이러스 백신 [플랫폼 지원을 방문하십시오.](manage-updates-baselines-microsoft-defender-antivirus.md)

## <a name="asr-rules-deployment-phases"></a>ASR 규칙 배포 단계

비즈니스 운영에 잠재적으로 영향을 줄 수 있는 새로운 대규모 구현과 함께 계획 및 구현에 의의를 두는 것이 중요합니다. 맬웨어를 방지하는 ASR 규칙의 강력한 기능 때문에 고유한 고객 워크플로에 가장 잘 작동하도록 이러한 규칙을 신중하게 계획하고 배포해야 합니다. 환경에서 작동하려면 ASR 규칙을 신중하게 계획, 테스트, 구현 및 운영해야 합니다.  

> [!div class="mx-imgBorder"]
> ![ASR 규칙 배포 단계](images/asr-rules-deployment-phases.png)

>[!Note]
>Microsoft가 아닌 HIPS를 사용하고 끝점 공격 표면 감소 규칙에 대한 Microsoft Defender로 전환하는 고객의 경우: Microsoft는 감사 모드에서 차단 모드로 전환할 때까지 ASR 규칙 배포와 함께 HIPS 솔루션을 실행해 보라고 고객에게 권고합니다. 제외 권장 사항은 제3자 바이러스 백신 공급업체에 문의해야 합니다.  

## <a name="phase-1-plan"></a>1단계: 계획

ASR 규칙을 테스트하기 시작하면 올바른 사업부부터 시작해야 합니다. 특정 사업부에 소수의 사용자 그룹으로 시작해야 합니다. ASR 규칙에 실제 영향을 줄 수 있는 특정 사업부 내에서 일부 ASR 챔피언을 식별하고 구현을 조정하는 데 도움을 줄 수 있습니다.

> [!div class="mx-imgBorder"]
> ![ASR 규칙 계획 단계](images/asr-rules-planning-steps.png)

### <a name="start-with-the-right-business-unit"></a>올바른 사업부로 시작

ASR 규칙 배포를 배포할 사업부를 선택하는 방법은 다음과 같은 요인에 따라 결정됩니다.

- 사업부 크기
- ASR 규칙 챔피언의 가용성  
- 배포 및 사용:
  - 소프트웨어
  - 공유 폴더
  - 스크립트 사용
  - Office 매크로
  - ASR 규칙의 영향을 받는 기타 엔터티

비즈니스 요구에 따라 여러 사업부를 포함하여 소프트웨어, 공유 폴더, 스크립트, 매크로 등을 광범위하게 샘플링할 수 있습니다. 반대로 첫 번째 ASR 규칙 롤아웃 범위를 단일 사업부로 제한한 다음 전체 ASR 규칙 롤아웃 프로세스를 다른 사업부에 한 번씩 반복할 수 있습니다.

### <a name="identify-asr--rules-champions"></a>ASR 규칙 챔피언 식별

ASR 규칙 챔피언은 예비 테스트 및 구현 단계에서 초기 ASR 규칙 출시에 도움이 되는 조직의 구성원입니다. 챔피언은 일반적으로 기술적으로 더 잘 사용되지 않는 직원으로, 간헐적인 작업 흐름 정전으로 퇴사하지 않는 직원입니다. 챔피언의 참여는 조직에 ASR 규칙 배포의 광범위한 확장 전체에서 계속됩니다. ASR 규칙 챔피언은 먼저 각 수준의 ASR 규칙 롤아웃을 경험합니다.

ASR 규칙 챔피언이 ASR 규칙 관련 작업 중단을 알리고 ASR 규칙 롤아웃 관련 통신을 받을 수 있도록 피드백 및 응답 채널을 제공하는 것이 중요합니다.

### <a name="get-inventory-of-line-of-business-apps-and-understand-the-business-unit-processes"></a>업무용 앱 인벤토리를 파악하고 사업부 프로세스 이해

조직 전체에서 사용되는 응용 프로그램 및 비즈니스 단위 프로세스를 전체적으로 이해하는 것은 성공적인 ASR 규칙 배포에 중요합니다. 또한 조직의 다양한 사업부에서 이러한 앱이 사용되는 방법을 이해해야 합니다.
시작하기 위해 조직 전체에서 사용할 수 있도록 승인된 앱의 인벤토리를 얻게 됩니다. Microsoft 365 앱 관리 센터와 같은 도구를 사용하여 소프트웨어 응용 프로그램을 인벤토리에 게시할 수 있습니다. 자세한 내용은 Microsoft 365 앱 관리 센터의 [인벤토리 개요를 참조하세요.](/deployoffice/admincenter/inventory)

### <a name="define-reporting-and-response-team--roles-and-responsibilities"></a>보고 및 응답 팀 역할 및 책임 정의

ASR 규칙 상태 및 활동을 모니터링하고 통신할 책임이 있는 사람의 역할과 책임을 명확하게 설명하는 것은 ASR 유지 관리의 핵심 활동입니다. 따라서 다음을 확인하는 것이 중요합니다.

- 보고서 수집을 담당하는 사람 또는 팀
- 보고서 공유 방법 및 사용자
- 새로 식별된 위협 또는 ASR 규칙으로 인해 원치 않는 차단에 대해 에스컬레이터가 해결되는 방법

일반적인 역할 및 책임은 다음과 같습니다.

- IT 관리자: ASR 규칙을 구현하고 제외를 관리합니다. 앱 및 프로세스에서 서로 다른 사업부와 함께 작업합니다. 관련자에 대한 보고서 어셈블 및 공유
- CSOC(인증된 보안 운영 센터) 분석가: 우선 순위가 높고 차단된 프로세스를 투자하여 위협이 유효한지 확인할 책임
- CISO(최고 정보 보안 책임자): 조직의 전반적인 보안 상태 및 건강을 담당합니다.

### <a name="ring-deployment"></a>링 배포

대기업의 경우 "링"에 ASR 규칙을 배포하는 것이 좋습니다. 링은 겹치지 않는 트리 링처럼 밖으로 방사되는 동심원으로 시각적으로 표현되는 장치 그룹입니다. 가장 안쪽의 링이 성공적으로 배포되면 다음 링을 테스트 단계로 전환할 수 있습니다. 비즈니스 단위, ASR 규칙 챔피언, 앱 및 프로세스에 대한 철저한 평가는 링을 정의하는 데 필요합니다.
대부분의 경우 조직에서는 업데이트의 단계적 롤아웃을 위한 배포 링을 Windows 있습니다. 기존 링 디자인을 사용하여 ASR 규칙을 구현할 수 있습니다.
자세한 내용은 [Create a deployment plan for Windows](/windows/deployment/update/create-deployment-plan)

## <a name="phase-2-test"></a>2단계: 테스트

링 1로 ASR 규칙 배포를 시작하십시오.

> [!div class="mx-imgBorder"]
> ![ASR 규칙 테스트 단계](images/asr-rules-testing-steps.png)

### <a name="step-1-test-asr-rules-using-audit"></a>1단계: 감사를 사용하여 ASR 규칙 테스트

링 1에서 챔피언 사용자 또는 장치부터 시작하여 규칙이 감사로 설정된 ASR 규칙을 켜서 테스트 단계를 시작하십시오. 일반적으로 테스트 단계에서 트리거되는 규칙을 확인할 수 있도록 모든 규칙을 감사에서 사용하도록 설정하는 것이 좋습니다. Audit로 설정된 규칙은 일반적으로 규칙이 적용되는 엔터티 또는 엔터티의 기능에 영향을 미치는 것이 아니라 평가를 위해 로깅된 이벤트를 생성합니다. 최종 사용자에게는 영향이 없습니다.

#### <a name="configure-asr-rules-using-mem"></a>MEM을 사용하여 ASR 규칙 구성

MEM(Microsoft Endpoint Manager) 끝점 보안을 사용하여 사용자 지정 ASR 규칙을 구성할 수 있습니다.

1. 관리 [Microsoft Endpoint Manager 열기](https://endpoint.microsoft.com/#home)
2. **끝점 보안 공격 표면**  >  **감소로 이동 합니다.**
3. **정책 만들기** 를 선택합니다.
4. **플랫폼에서** Windows 10 **이상을** 선택하고 **프로필에서** 공격 표면 감소 규칙을 **선택합니다.**
  
    > [!div class="mx-imgBorder"]
    > ![ASR 규칙 프로필 구성](images/asr-mem-create-profile.png)

5. **만들기** 를 클릭합니다.
6. 프로필 **만들기 창의** 기본 **탭에** 있는 **이름에** 정책 이름을 추가합니다. **설명에** ASR 규칙 정책에 대한 설명을 추가합니다.
7. 구성 **설정 탭의** **공격 표면 감소 규칙에서** 모든 규칙을 감사 **모드로 설정합니다.**

    > [!div class="mx-imgBorder"]
    > ![ASR 규칙을 감사 모드로 설정](images/asr-mem-configuration-settings.png)

    >[!Note]
    >일부 ASR 규칙 모드 목록에는 변형이 있습니다. _차단 및_ _사용은_ 동일한 기능을 제공합니다.

8. [선택 사항] 범위 **태그 창에서** 특정 장치에 태그 정보를 추가할 수 있습니다. 역할 기반 액세스 제어 및 범위 태그를 사용하여 올바른 관리자가 올바른 Intune 개체에 대한 올바른 액세스 및 표시 권한을 가지게 할 수도 있습니다. 자세한 내용은 [Intune에서 분산 IT에 RBAC(역할](/mem/intune/fundamentals/scope-tags)기반 액세스 제어) 및 범위 태그를 사용 합니다.
9. 할당 **창에서** 사용자 또는 장치 그룹에 프로필을 배포하거나 "할당"할 수 있습니다. 자세한 내용은 [다음을 Microsoft Intune](/mem/intune/configuration/device-profile-assign#exclude-groups-from-a-profile-assignment)
10. 검토 + 만들기 창에서 **설정을** 검토합니다. **만들기를** 클릭하여 규칙을 적용합니다.

   > [!div class="mx-imgBorder"]
   > ![ASR 규칙 정책 활성화](images/asr-mem-review-create.png)

ASR 규칙에 대한 새로운 공격 표면 감소 정책은 끝점 보안 | **공격 표면 감소**.

   > [!div class="mx-imgBorder"]
   > ![나열된 ASR 규칙 정책](images/asr-mem-my-asr-rules.png)

### <a name="step-2-understand-the-attack-surface-reduction-rules-reporting-page-in-the-microsoft-365-defender-portal"></a>2단계: 검색 포털의 공격 표면 감소 규칙 보고 Microsoft 365 Defender 이해

ASR 규칙 보고 페이지는 포털 보고서 **공격 Microsoft 365 Defender** 축소  >    >  **규칙에서 찾을 수 있습니다.** 이 페이지에는 다음 세 개의 탭이 있습니다.

- 검색
- 구성
- 제외 추가

#### <a name="detections-tab"></a>검색 탭

검색된 감사 및 차단된 이벤트의 30일 일정을 제공합니다.

> [!div class="mx-imgBorder"]
> ![공격 표면 감소 규칙 검색 탭](images/asr-defender365-01.png)

공격 표면 감소 규칙 창에서는 규칙에 따라 검색된 이벤트에 대한 개요를 제공합니다.

>[!Note]
>ASR 규칙 보고서에는 몇 가지 변형이 있습니다. Microsoft는 일관된 환경을 제공하기 위해 ASR 규칙 보고서의 동작을 업데이트하고 있습니다.

> [!div class="mx-imgBorder"]
> ![공격 표면 감소 규칙 규칙 검색](images/asr-defender365-01b.png)

검색 **보기를 클릭하여** **검색 탭을 열** 수 있습니다.

> [!div class="mx-imgBorder"]
> [![공격 표면 감소 규칙 감지 ](images/asr-defender365-reports-detections.png) ](images/asr-defender365-reports-detections.png#lightbox)

**GroupBy 및** **Filter** 창에서는 다음 옵션을 제공합니다.

**GroupBy는** 다음 그룹으로 설정된 결과를 반환합니다.

- 그룹화 없음
- 검색된 파일
- 감사 또는 차단
- 규칙
- 원본 앱
- 장치
- 사용자
- 게시자

> [!div class="mx-imgBorder"]
> [![공격 표면 감소 규칙 감지 GroupBy 필터 ](images/asr-defender365-reports-detections.png) ](images/asr-defender365-reports-detections.png#lightbox)

**필터가** **열리면** 결과의 범위를 선택한 ASR 규칙으로만 범위를 지정하는 데 사용할 수 있는 규칙에 대한 필터 페이지가 열립니다.

> [!div class="mx-imgBorder"]
> [규칙에 대한 공격 표면 ![ 감소 규칙 검색 필터 ](images/asr-defender365-filter.png) ](images/asr-defender365-filter.png#lightbox)

>[!Note]
>Microsoft Microsoft 365 Security E5 또는 A5, Windows E5 또는 A5 라이선스가 있는 경우 다음 링크가 Microsoft Defender 365 보고서 > 공격 표면 감소 탭을 > 열립니다. [](https://security.microsoft.com/asr?viewid=detections)

#### <a name="configuration-tab"></a>구성 탭

컴퓨터별로 목록 - ASR 규칙의 집계 상태( 해제, 감사, 차단)입니다.

> [!div class="mx-imgBorder"]
> [![공격 표면 감소 규칙 구성 탭 ](images/asr-defender365-configurations.png) ](images/asr-defender365-configurations.png#lightbox)

구성 탭에서 ASR 규칙을 검토할 장치를 선택하여 장치 기준(사용 가능한 ASR 규칙 및 어떤 모드로 설정되어 있는지)을 확인할 수 있습니다.

> [!div class="mx-imgBorder"]
> [![공격 표면 감소 규칙 사용 및 모드 ](images/asr-defender365-configurations.settings.png) ](images/asr-defender365-configurations.settings.png#lightbox)

시작 **링크가** 열립니다Microsoft Endpoint Manager 관리 센터에서 ASR에 대한 끝점 보호 정책을 만들거나 수정할 수 있습니다.

> [!div class="mx-imgBorder"]
> [![MEM의 공격 표면 감소 규칙 ](images/asr-defender365-05b-mem1.png) ](images/asr-defender365-05b-mem1.png#lightbox)

끝점 보안 | 개요, 공격 **표면 감소를 선택합니다.**

> [!div class="mx-imgBorder"]
> [![MEM의 공격 표면 감소 ](images/asr-defender365-05b-mem2.png) ](images/asr-defender365-05b-mem2.png#lightbox)

끝점 보안 | 공격 표면 축소 창이 열립니다.

> [!div class="mx-imgBorder"]
> [![끝점 보안 Asr 창 ](images/asr-defender365-05b-mem3.png) ](images/asr-defender365-05b-mem3.png#lightbox)

>[!Note]
>Microsoft Defender 365 E5(또는 Windows E5?) 라이선스가 있는 경우 이 링크가 Microsoft Defender 365 보고서 > 구성 [](https://security.microsoft.com/asr?viewid=configuration) 탭에서 공격 표면 > 열립니다.

#### <a name="add-exclusions"></a>제외 추가

이 탭에서는 제외에 대해 검색된 엔터티(예: 가음성)를 선택하는 메서드를 제공합니다. 제외가 추가될 때 보고서는 예상되는 영향에 대한 요약을 제공합니다.

>[!Note]
> Microsoft Defender 바이러스 백신 AV 제외는 ASR 규칙에 따라 준수됩니다.  확장명, 이름 또는 위치에 따라 제외 구성 및 유효성 [검사를 참조하세요.](configure-extension-file-exclusions-microsoft-defender-antivirus.md)

> [!div class="mx-imgBorder"]
> [![끝점 보안 Asr 도구 ](Images/asr-defender365-06d.png) ](Images/asr-defender365-06d.png#lightbox)

> [!Note]
>Microsoft Defender 365 E5(또는 Windows E5?) 라이선스가 있는 경우 이 링크가 Microsoft Defender 365 보고서 > [](https://security.microsoft.com/asr?viewid=exclusions) 공격 표면 감소 > 제외 탭이 열립니다.

### <a name="step-3-assess-impact"></a>3단계: 영향 평가

#### <a name="review"></a>검토

Microsoft 365 Defender 포털의 보고 페이지를 사용하여 비즈니스 단위 프로세스에 영향을 미치는 – ASR 규칙이 있는 경우를 볼 수 있습니다. 이 프로세스의 일부로 ASR 챔피언의 피드백을 포함합니다. 감사 보고서를 검토하여 발생/트리거된 이벤트가 가장 많이 발생하고 이벤트가 가장 적게 있는 규칙을 확인할 수 있습니다.

ASR 규칙은 광범위한 구성 요소를 대상으로 하여 다양한 간격으로 호출될 것이기 때문에 조직 링에서 ASR 규칙 트리거 이벤트의 유용한 샘플링을 얻는 데 걸릴 시간을 예측하기가 어렵습니다. 그러나 Microsoft는 최소 4주를 제안합니다. 예를 들어 Microsoft Office 응용 프로그램에 대한 일부 ASR 규칙은 ASR 규칙보다 더 빨리 자주 "랜섬웨어에 대한 고급 보호 사용"을 트리거할 수 있습니다. 마찬가지로 각 링은 ASR 규칙이 다르게 적용된 응용 프로그램 및 기타 구성 요소를 서로 다른 빈도로 사용할 수 있습니다. 조직의 결과에 따라 테스트가 완료된 경우를 결정해야 합니다. 더 나은 이해를 위해 ASR 규칙을 사용하도록 설정하기 전에 감사 모드에서 ASR 규칙을 테스트해야 하는 기간을 [참조하세요.](attack-surface-reduction-faq.yml#how-long-should-i-test-an-asr-rule-in-audit-mode-before-enabling-it-)

#### <a name="create-exclusions"></a>제외 만들기

대부분의 경우 조직에는 안전한 것으로 알려져 있으며 ASR 규칙을 트리거하는 측면이 포함될 수 있는 파일 또는 파일 폴더가 있습니다. 감사 모드에서는 이러한 파일 및 폴더가 표시됩니다. 예를 들어 조직에 특정 용도의 매크로가 활성화된 Word 또는 Excel 문서 모음이 있을 수 있습니다. 이러한 매크로는 ASR 규칙을 트리거할 수 있습니다. 이러한 경우 감사 모드에서 이러한 파일을 식별하는 경우 ASR 규칙에 의해 이러한 파일이 캡처되지 않도록 이러한 파일 또는 폴더를 제외할 수 있습니다. 파일 [및 폴더 제외 참조](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules)

>[!Note]
>AV 제외 Microsoft Defender 바이러스 백신 ASR 규칙에 따라 준수됩니다. 확장명, 이름 또는 위치에 따라 제외 구성 및 유효성 [검사를 참조하세요.](configure-extension-file-exclusions-microsoft-defender-antivirus.md)

규칙이 치명적인 방식으로 업무 운영에 광범위하게 영향을 미치게 될 경우 계속 캡처할 수 있도록 규칙을 감사에서 그대로 두거나 규칙을 완전히 사용하지 않도록 설정할 수 있습니다. 제외는 보고서 공격 표면 Microsoft 365 Defender 규칙에서 **쉽게**  >    >  **사용할 수 있습니다.** 제외를 만들 엔터티를 선택하기만 합니다.

제외는 보고서 공격 표면 Microsoft 365 Defender 규칙에서 **쉽게**  >    >  **사용할 수 있습니다.** 제외를 만들 엔터티를 선택하기만 합니다.

> [!div class="mx-imgBorder"]
> [![ASR 제외 만들기 ](images/asr-defender365-06d.png) ](images/asr-defender365-06d.png#lightbox)

#### <a name="create-exclusions-after-review"></a>검토 후 제외 만들기

대부분의 경우 조직에는 안전한 것으로 알려져 있으며 ASR 규칙을 트리거하는 측면이 포함될 수 있는 파일 또는 파일 폴더가 있습니다. 감사 모드에서는 이러한 파일 및 폴더가 표시됩니다. 예를 들어 조직에 특정 용도의 매크로가 활성화된 Word 또는 Excel 문서 모음이 있을 수 있습니다. 이러한 매크로는 ASR 규칙을 트리거할 수 있습니다. 이러한 경우 감사 모드에서 이러한 파일을 식별하는 경우 ASR 규칙에 의해 이러한 파일이 캡처되지 않도록 이러한 파일 또는 폴더를 제외할 수 있습니다. 파일 [및 폴더 제외를 참조합니다.](enable-attack-surface-reduction.md#exclude-files-and-folders-from-asr-rules)

>[!Note]
>AV 제외 Microsoft Defender 바이러스 백신 ASR 규칙에 따라 준수됩니다. 확장명, 이름 또는 위치에 따라 제외 구성 및 유효성 [검사를 참조하세요.](configure-extension-file-exclusions-microsoft-defender-antivirus.md)

## <a name="phase-3-implement"></a>3단계: 구현

구현 단계에서는 테스트에서 기능 상태로 링을 이동합니다.

> [!div class="mx-imgBorder"]
> ![ASR 규칙 구현 단계](images/asr-rules-implementation-steps.png)

### <a name="step-1-transition-asr-rules-from-audit-to-block"></a>1단계: 감사에서 차단으로 ASR 규칙 전환

1. 감사 모드에서 모든 제외가 결정되면 트리거된 이벤트가 가장 적게 있는 규칙부터 시작하여 일부 ASR 규칙을 "차단" 모드로 설정하기 시작하세요. "공격 [표면 축소 규칙 사용 을 참조 하도록 설정](enable-attack-surface-reduction.md)합니다.
2. Microsoft 365 Defender 포털에서 보고 페이지를 검토합니다. [끝점용 Microsoft Defender의 위협 방지 보고서를 참조하세요.](threat-protection-reports.md) ASR 챔피언의 피드백도 검토합니다.
3. 제외를 구체화하거나 필요한 경우 새 제외를 만들 수 있습니다.
4. 문제가 있는 규칙을 다시 감사로 전환합니다.

  >[!Note]
  >문제가 있는 규칙(노이즈를 너무 많이 생성하는 규칙)의 경우 규칙을 해제하거나 다시 감사로 전환하는 것보다 제외를 만드는 것이 좋습니다. 환경에 가장 적합한 방법을 결정해야 합니다.

  >[!Tip]
  >사용 가능한 경우 규칙에서 경고 모드 설정을 사용하여 중단을 제한합니다. 경고 모드에서 ASR 규칙을 사용하도록 설정하면 최종 사용자 액세스를 실제로 차단하지 않고 트리거된 이벤트를 캡처하고 잠재적인 중단을 볼 수 있습니다. 자세한 내용은 사용자에 [대한 경고 모드 를 통해 자세히 알아보아야 합니다.](attack-surface-reduction.md#warn-mode-for-users)

#### <a name="how-does-warn-mode-work"></a>경고 모드는 어떻게 작동하나요?

경고 모드는 효과적으로 차단 명령이지만 사용자가 주어진 흐름 또는 앱의 후속 실행을 "차단 해제"하는 옵션을 제공합니다. 장치, 사용자, 파일 및 프로세스 조합에 따라 경고 모드의 차단을 해제합니다. 경고 모드 정보는 로컬에 저장되고 기간은 24시간입니다.

### <a name="step-2-expand-deployment-to-ring-n--1"></a>2단계: n + 1을 링으로 배포 확장

링 1에 대한 ASR 규칙을 올바르게 구성했다고 확신할 경우 배포 범위를 다음 링(링 n + 1)으로 확대할 수 있습니다.

배포 프로세스(1~3단계)는 기본적으로 각 후속 링에서 동일합니다.

1. 감사의 테스트 규칙
2. 웹 사이트 포털에서 ASR로 트리거된 감사 Microsoft 365 Defender 검토
3. 제외 만들기
4. 검토: 필요한 경우 제외 구체화, 추가 또는 제거
5. 규칙을 "차단"으로 설정
6. 웹 사이트 포털에서 보고 Microsoft 365 Defender 검토합니다.
7. 제외를 생성합니다.
8. 문제가 있는 규칙을 사용하지 않도록 설정하거나 다시 감사로 전환합니다.

## <a name="phase-4-operationalize"></a>4단계: 운영화

조직에 ASR 규칙을 완전히 배포한 후 조직에서 ASR 관련 활동을 모니터링하고 대응하기 위한 프로세스를 설정하는 것이 중요합니다.

### <a name="manage-false-positives"></a>가짓 긍정 관리

가짓 긍정/음수는 끝점용 Microsoft Defender를 포함하여 위협 방지 솔루션에서 발생할 수 있습니다. 끝점 보호 솔루션에서 가짓 긍정은 엔터티가 실제로 위협이 아니어도 파일 또는 프로세스와 같은 엔터티가 검색되고 악성으로 식별되는 경우입니다. 반대로 거짓 부정은 위협으로 검색되지는 않지만 실제로 악의적인 엔터티입니다.
가짓 긍정 및 거짓 부정 참석에 대한 자세한 내용은 다음을 참조하세요. [끝점용 Microsoft Defender에서 가긍성/부정 문제 해결을 참조하세요.](defender-endpoint-false-positives-negatives.md)

### <a name="keeping-up-with-reports"></a>보고서 유지

일관되고 정기적인 보고서 검토는 ASR 규칙 배포를 유지 관리하고 새로운 위협에 대한 보안 유지의 필수 요소입니다. 조직에서는 ASR 규칙이 보고된 이벤트를 최신으로 유지하는 케이던스에서 ASR 규칙 이벤트에 대한 검토를 예약해야 합니다. 조직의 규모에 따라 일별, 시간별 또는 지속적인 모니터링이 될 수 있습니다.

### <a name="hunting"></a>헌팅

고급 헌팅의 가장 강력하고 [Microsoft 365 Defender](https://securitycenter.microsoft.com) 기능 중 하나는 고급 헌팅입니다. 고급 헌팅에 익숙하지 않은 경우 다음 문서를 참조하세요. 고급 헌팅을 통해 위협을 사전 [대응적으로 헌팅합니다.](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)

> [!div class="mx-imgBorder"]
> [![Microsoft 365 Defender 고급 헌팅 ](images/asr-defender365-advanced-hunting2.png) ](images/asr-defender365-advanced-hunting2.png#lightbox)

고급 헌팅은 Microsoft Defender ATP 끝점 감지 및 응답(EDR)이 모든 컴퓨터로부터 수집하는 캡처된(원시) 데이터의 최대 30일을 탐색할 수 있는 쿼리 기반(Kusto 쿼리 언어) 위협 헌팅 도구입니다. 고급 헌팅을 통해 이벤트를 사전 검사하여 흥미로운 지표와 엔터티를 찾을 수 있습니다. 데이터에 대한 유연한 액세스는 알려진 위협과 잠재적 위협 모두에 대한 제한없는 헌팅을 용이하게 합니다.

고급 헌팅을 통해 ASR 규칙 정보를 추출하고, 보고서를 만들고, 특정 ASR 규칙 감사 또는 차단 이벤트의 컨텍스트에 대한 자세한 정보를 얻을 수 있습니다.

장치 포털의 고급 헌팅 섹션에 있는 DeviceEvents 테이블에서 ASR 규칙 이벤트를 Microsoft 365 Defender 있습니다. 예를 들어 아래 쿼리와 같은 간단한 쿼리는 지난 30일 동안 ASR 규칙이 있는 모든 이벤트를 데이터 원본으로 보고하고 ActionType 수로 요약하여 요약할 수 있습니다. 이 경우 ASR 규칙의 실제 코드 이름입니다.

> [!div class="mx-imgBorder"]
> ![Microsoft 365 Defender 고급 헌팅 쿼리 명령줄](images/asr-defender365-advanced-hunting3.png)

> [!div class="mx-imgBorder"]
> [![Microsoft 365 Defender 고급 헌팅 쿼리 결과 ](images/asr-defender365-advanced-hunting4.png) ](images/asr-defender365-advanced-hunting4.png#lightbox)

위의 이벤트는 AsrLsassCredentialTheft에 대해 187개 이벤트가 등록된 것으로 나타났습니다(차단된 이벤트는 102개, 감사된 이벤트는 85개), AsrOfficeChildProcess의 이벤트 2개(감사된 경우 1개, 차단의 경우 1개) 및 AsrPsexecWmiChildProcessAudited의 경우 8개 이벤트가 등록되어 있습니다.

AsrOfficeChildProcess 규칙에 중점을 두고 관련된 실제 파일 및 프로세스에 대한 세부 정보를 확인하려면 ActionType에 대한 필터를 변경하고 요약 줄을 원하는 필드의 투영으로 바꿔야 합니다(이 경우 DeviceName, FileName, FolderPath 등).

> [!div class="mx-imgBorder"]
> ![Microsoft 365 Defender 집중된 고급 헌팅 쿼리](images/asr-defender365-advanced-hunting4b.png)

> [!div class="mx-imgBorder"]
> [![Microsoft 365 Defender 고급 헌팅 쿼리 중심 결과 ](images/asr-defender365-advanced-hunting5b.png) ](images/asr-defender365-advanced-hunting5b.png#lightbox)

고급 헌팅의 실질적인 이점은 쿼리를 원하는 내용에 따라 구성할 수 있으므로 개별 컴퓨터의 특정 정보를 정확히 파악하거나 전체 환경에서 정보를 추출하려는지 여부에 관계없이 진행된 일의 정확한 스토리를 볼 수 있습니다.

추가 헌팅 옵션에 대한 자세한 내용은 [Demystifying attack surface reduction rules - Part 3을 참조하십시오.](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/demystifying-attack-surface-reduction-rules-part-3/ba-p/1360968)

## <a name="reference"></a>참조

### <a name="blogs"></a>블로그

[공격 표면 감소 규칙의mystifying 공격 표면 감소 규칙 - 1부](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/demystifying-attack-surface-reduction-rules-part-1/ba-p/1306420)

[공격 표면 감소 규칙의mystifying 공격 표면 감소 규칙 - 2부](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/demystifying-attack-surface-reduction-rules-part-2/ba-p/1326565)

[공격 표면 감소 규칙의mystifying 공격 표면 감소 규칙 - 3부](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/demystifying-attack-surface-reduction-rules-part-3/ba-p/1360968)

[공격 표면 감소 규칙의 비정규화 - 4부](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/demystifying-attack-surface-reduction-rules-part-4/ba-p/1384425)

### <a name="asr-collection"></a>ASR 컬렉션

[공격 표면 감소 개요](overview-attack-surface-reduction.md)

[공격 표면 감소 규칙을 사용하여 맬웨어 감염 방지](attack-surface-reduction.md)

[공격 표면 감소 규칙 사용](enable-attack-surface-reduction.md)

[공격 표면 감소 규칙](attack-surface-reduction-rules.md)

[공격 표면 감소 FAQ](attack-surface-reduction-faq.yml)

### <a name="microsoft-defender"></a>Microsoft Defender

[Endpoint용 Microsoft Defender에서 가양성/가음성 처리](defender-endpoint-false-positives-negatives.md)

[클라우드 제공 보호 및 Microsoft Defender 바이러스 백신](cloud-protection-microsoft-defender-antivirus.md)

[2016년 8월에 클라우드 제공 보호 Microsoft Defender 바이러스 백신](enable-cloud-protection-microsoft-defender-antivirus.md)

[확장명, 이름 또는 위치를 기준으로 제외 구성 및 유효성 검사](configure-extension-file-exclusions-microsoft-defender-antivirus.md)

[Microsoft Defender 바이러스 백신 플랫폼 지원](manage-updates-baselines-microsoft-defender-antivirus.md)

[Microsoft 365 앱 관리 센터의 인벤토리 개요](/deployoffice/admincenter/inventory)

[배포 계획 Windows](/windows/deployment/update/create-deployment-plan)

[Intune에서 분산 IT에 RBAC(역할 기반 액세스 제어) 및 범위 태그 사용](/mem/intune/fundamentals/scope-tags)

[장치에서 장치 프로필 Microsoft Intune](/mem/intune/configuration/device-profile-assign#exclude-groups-from-a-profile-assignment)

### <a name="management-sites"></a>관리 사이트

[Microsoft Endpoint Manager 관리 센터](https://endpoint.microsoft.com/#home)

[공격 표면 감소](https://security.microsoft.com/asr?viewid=detections)

[ASR 규칙 구성](https://security.microsoft.com/asr?viewid=configuration)

[ASR 규칙 제외](https://security.microsoft.com/asr?viewid=exclusions)
