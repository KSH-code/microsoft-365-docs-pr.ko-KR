---
title: Microsoft 365 보안 센터 개요
description: MDO(Microsoft Defender for Office 365) 및 MDE(Microsoft Defender for Endpoint)를 MDI(Microsoft Defender for Identity) 및 MCAS(Microsoft Cloud App Security)와 결합하여 Microsoft 365 보안 센터의 이점 이 문서에서는 관리자를 위한 Microsoft 365 보안 센터에 대해 간략하게 설명했습니다.
keywords: 보안, 맬웨어, Microsoft 365, M365, 보안 센터, 모니터링, 보고서, ID, 데이터, 장치, 앱
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.date: 02/02/2021
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: 89e72d703bd70647d6c2b00732315b8e5f015cc7
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167221"
---
# <a name="the-unified-microsoft-365-security-center-overview"></a>통합 Microsoft 365 보안 센터 개요

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

**적용 대상:**

- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Office 365용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2148715)

> Microsoft 365 Defender를 경험하고 싶나요? 랩 [환경에서 평가하거나](https://aka.ms/mtp-trial-lab) 프로덕션 환경에서 파일럿 프로젝트를 [실행할 수 있습니다.](https://aka.ms/m365d-pilotplaybook)

향상된 **Microsoft 365** 보안 센터()는 중앙 포털에서 전자 메일, 공동 작업, ID 및 장치 위협에 대한 보호, 검색, 조사 및 응답을 [https://security.microsoft.com](https://security.microsoft.com) 결합합니다.    

Microsoft 365 보안 센터는 Microsoft Defender 보안 센터 및 Office 365 보안 및 규정 준수 센터와 같은 기존 Microsoft 보안 포털의 & 제공합니다. 보안 센터에서는 정보에 빠르게 액세스하고, 더 간단한 레이아웃을 사용하며, 관련 정보를 함께 사용하여 보다 쉽게 사용할 수 있도록 합니다. 이 센터에는 다음이 포함됩니다.

- **[Office 365용 Microsoft Defender](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)** Office 365용 Microsoft Defender는 조직이 전자 메일 및 Office 365 리소스를 보호하기 위해 방지, 검색, 조사 및 헌팅 기능 집합을 통해 엔터프라이즈를 보호하는 데 도움이 됩니다.
- **[끝점용 Microsoft Defender는](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)** 조직의 장치에 대한 예방 보호, 위반 후 감지, 자동화된 조사 및 대응을 제공합니다.
- **[Microsoft 365 Defender는](microsoft-threat-protection.md)** Microsoft 365 보안 포트폴리오를 활용하여 도메인 전체의 위협 데이터를 자동으로 분석하고 단일 대시보드에 대한 공격의 그림을 작성하는 Microsoft의 XDR(Extended *Detection and Response)* 솔루션의 일부입니다.

Office 365 보안 및 준수 센터 또는 Microsoft Defender 보안 센터에서 변경된 & 필요한 경우 다음을 참조하세요.

- [Microsoft 365 보안 센터의 Office 365용 Defender](microsoft-365-security-center-mdo.md)
- [Microsoft 365 보안 센터의 끝점용 Defender](microsoft-365-security-center-mde.md)

## <a name="what-to-expect"></a>예상할 일

Office 365 보안 및 준수 센터(protection.office.com) 및 Microsoft Defender 보안 센터(securitycenter.microsoft.com)에서 사용하는 모든 보안 콘텐츠는 *이제 Microsoft 365* 보안 센터에서 찾을 수 있습니다.

Microsoft 365 보안 센터는 보안 팀이 서로 다른 워크로드의 신호를 통합된 단일 환경으로 통합하여 공격을 조사하고 대응할 수 있도록 합니다.

- 인시던트 & 경고
- 헌팅
- 알림 센터 
- 위협 분석

Microsoft 365 보안 센터는 Office 365용 Microsoft Defender와 끝점용 Microsoft Defender를 병합할 때 단합, 명확성 및 공통 목표를 강조합니다.  병합은 아래에 나열된 우선 순위를 기반으로 하여 각 보안 제품군이 조합에 가져온 기능을 만족하지 않고 만들어 졌다.

- 일반적인 구성 요소
- 일반적인 용어
- 일반 엔터티
- 다른 워크로드와의 기능 패리티

## <a name="unified-investigations"></a>통합 조사

보안 센터를 간소화하면 Microsoft 365 조직 전체의 인시던트 조사를 위한 단일 창이 생성됩니다. 기본 예로는  Microsoft 365 보안 센터를 빠르게 실행하기 위한 인시던트 노드가 있습니다.

:::image type="content" source="../../media/converged-incidents-2.png.png" alt-text="MDO의 인시던트 페이지입니다.":::

예를 들어 심각도 높은 인시던트  이름을 두 번 클릭하면 수렴 센터의 이점을 보여줄 수 있는 페이지로 이동됩니다.

![여러 끝점에서 권한 에스컬레이터가 관련된 다단계 인시던트. 영향을 16개 디바이스와 9명에게 영향을 미치는 사용자를 보여 줄 수 있습니다.](../../media/converged-incident-info-3.png)

> [!TIP]
> 수렴형 사용자  탭은 문의를 시작하는 데 좋은 장소입니다. 이 단일 페이지는 수렴된 워크로드(이를 활용하는 경우 끝점용 Microsoft Defender, ID용 Microsoft Defender 및 MCAS)의 사용자 및 다양한 원본(예: On-premises Active Directory, Azure Active Directory, 동기화된, 로컬 및 타사 사용자)의 정보를 제공합니다. 새 사용자 [경험에 대해 자세히 알아보는 것이 있습니다.](investigate-users.md)

인시던트 정보에는 영향을 받는 사서함 외에 사용자/ID 관련 및 위험에 노출된 장치가 표시됩니다. 또한 모든 조사 **정보** 및 수집된 증거와 **관련이 있습니다.** 이렇게 하면 관리자와 보안 운영 팀이 위험에 노출된 사용자 및 사서함으로 한 번의 고위험 경고에서 더 쉽게 피벗할 수 있습니다. 이 페이지의 **맨** 위에 있는 인시던트 탭에는 이 단일 위치에서 사용할 수 있는 다른 주요 보안 피벗이 있습니다.

> [!IMPORTANT]
> 특정 인시던트에 대한 페이지 위쪽에는 **요약,** **경고,** 장치, **사용자,** **사서함,** 조사 및  증거 탭이 표시됩니다.  

조사를 **선택하면** 진행 중인 분석 그래픽이 있는 페이지가 열리며 수정을 위한 상태(예: 승인 보류 **중)가** 나열됩니다. 작업 환경에서 특정 인시던트 선택, 이러한 탭으로 드릴다운 및 다양한 종류의 위협에 대한 프로필을 작성하는 방법을 알아보세요. 익숙은 이후의 모든 압박 조사에 도움이 됩니다.

## <a name="improved-processes"></a>향상된 프로세스

공용 컨트롤과 콘텐츠가 같은 장소에 표시되거나 한 데이터 피드로 압축되어 쉽게 찾을 수 있습니다. 예를 들어 통합 설정이 있습니다.

### <a name="unified-settings"></a>통합 설정

!['역할'을 클릭하고 일반 설정, 사용 권한, API 및 규칙이 포함된 설정 페이지를 열했습니다. 사용 권한을 연 다음 역할을 열 수 있습니다. 모든 역할을 표시](../../media/converged-add-role-9.png)

### <a name="permissions--roles"></a>역할에 & 사용 권한

![사용 &, 역할 및 장치 그룹에서 끝점 역할을 & 역할 페이지를 참조하세요.](../../media/converged-roles-5.png)

 Microsoft 365 보안 센터에 액세스하는 것은 Azure Active Directory 전역 역할 또는 사용자 지정 역할을 사용하여 구성됩니다. 끝점용 Defender에 대한 자세한 내용은 Microsoft Defender 보안 센터에 대한 사용자 액세스 [할당을 참조합니다.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/assign-portal-access) Office 365용 Defender의 경우 Microsoft 365 규정 준수 센터 및 [Microsoft 365](../office-365-security/permissions-microsoft-365-compliance-security.md)보안 센터의 사용 권한을 참조합니다.

- [Microsoft 365 Defender에](mtp-permissions.md) 대한 액세스를 관리하는 방법에 대해 자세히 알아보시고
- Microsoft 365 보안 센터에서 사용자 지정 역할을 만드는 방법에 대한 자세한 정보 [](custom-roles.md)

### <a name="integrated-reports"></a>통합 보고서

보고서는 Microsoft 365 보안 센터에서도 통합됩니다. 관리자는 일반 보안 보고서로 시작하여 끝점, 전자 메일 및 공동 작업과 관련한 특정 & 수 있습니다. 여기에 있는 링크는 작업 구성에 따라 동적으로 생성됩니다.

### <a name="quickly-view-your-microsoft-365-environment"></a>Microsoft 365 환경 빠르게 보기

홈 **페이지에는** 보안 팀이 필요로 하는 많은 공통 카드가 표시됩니다. 카드와 데이터의 구성은 사용자 역할에 따라 달라집니다. Microsoft 365 보안 센터는 역할 기반 액세스 제어를 사용하기 때문에 다양한 역할은 매일의 작업에서 더 의미 있는 카드를 볼 수 있습니다.  

이 정보를 한눈에 확인하면 조직의 최신 활동을 유지하는 데 도움이 됩니다. Microsoft 365 보안 센터는 다양한 소스의 신호를 모아 Microsoft 365 환경의 전체적인 보기를 제공합니다.

카드는 다음 범주로 분류됩니다.

- **ID**- 조직의 ID를 모니터링하고 의심스거나 위험한 동작을 추적합니다. [ID 보호에 대해 자세히 알아보습니다.](https://docs.microsoft.com/azure/active-directory/identity-protection/overview-identity-protection)
- **데이터** - 무단 데이터 공개로 이어질 수 있는 사용자 활동을 추적하는 데 도움이 됩니다.
- **장치** - 장치에서 경고, 위반 활동 및 기타 위협에 대한 최신 정보를 얻습니다.
- **앱** - 조직에서 클라우드 앱이 어떻게 사용되는지 파악합니다. [Cloud App Security 검색된 앱에 대해 자세히 알아보습니다.](https://docs.microsoft.com/cloud-app-security/discovered-apps)

## <a name="threat-analytics-with-better-data-coverage"></a>더 나은 데이터 범위를 제공하는 위협 분석
다음 Microsoft 365 Defender 위협 분석 통합 환경을 사용하여 새로운 위협을 추적하고 대응합니다.

- 엔드포인트용 Microsoft Defender와 Office 365용 Microsoft Defender 사이의 데이터 범위가 향상되어 인시던트 관리, 자동 조사, 수정 및 사전 대응 또는 사후 위협 헌팅이 가능해지며, 
- 끝점용 Microsoft Defender에서 이미 사용할 수 있는 끝점 데이터 외에도 Office 365용 Microsoft Defender의 전자 메일 관련 검색 및 완화 기능
- 경고를 엔드포인트용 Microsoft Defender 및 Office 365용 Microsoft Defender에서 종합적인 공격 사례로 집계하여 작업 큐를 줄이고 조사를 단순화하고 속도를 향상하는 위협 관련 인시던트 보기입니다.
- Microsoft 365 Defender 솔루션에서 공격을 감지하고 차단합니다. 추가 노출 위험을 완화하고 탄력을 높이는 예방 조치를 구동하는 데 사용할 수 있는 데이터도 있습니다. 
- 보고서에 집중하고 조사하고 보고서에서 활용하기 위해 데이터를 빠르게 식별할 수 있도록 스포트라이트에 실행 가능한 정보를 저장하는 향상된 디자인입니다.

## <a name="a-centralized-learning-hub"></a>중앙 집중식 학습 허브

Microsoft 365 보안 센터에는 Microsoft 보안 블로그, YouTube의 Microsoft 보안 커뮤니티 및 공식 문서와 같은 리소스의 공식 지침을 버블업하는 학습 허브가 docs.microsoft.com.

학습 허브 내에서 전자 메일 & 공동 작업(Office 365 또는 MDO용 Microsoft Defender) 지침은 Endpoint(Endpoint 또는 MDE용 Microsoft Defender) 및 Microsoft 365 Defender 학습 리소스와 함께 제공됩니다.

학습 허브는 "Microsoft 365 Defender를 사용하여 조사하는 방법"과 같은 주제에 대해 구성한 학습 경로로 열립니다. "Microsoft Defender for Office 365 모범 사례". 이 섹션은 현재 Microsoft 내부의 보안 제품 그룹에서 큐레이터합니다. 각 학습 경로는 개념을 통과하는 데 소요되는 시간을 반영합니다. 예를 들어 'Office 365용 Microsoft Defender 사용자 계정이 손상된 경우 취할 단계'는 8분 정도 걸릴 것으로 예정된 것이고 중요한 정보를 제공합니다.

콘텐츠를 클릭한 후 이 사이트를 책갈피로 지정하고 책갈피를 '보안' 또는 '중요' 폴더로 구성하는 것이 유용할 수 있습니다. 모든 학습 경로를 보려면 주 패널에서 모든 링크 표시를 클릭합니다.

> [!NOTE]
> 제품(현재  Microsoft 365 Defender, 끝점용 Microsoft Defender 및 Office 365용 Microsoft Defender) 중 선택할 수 있는 Microsoft 365 보안 센터 학습 허브 위쪽에 유용한 필터가 있습니다. 각 섹션에 대한 학습 리소스의 수가 나열되어 있으며, 학습자는 교육 및 학습을 위해 준비된 리소스의 수를 추적하는 데 도움이 될 수 있습니다.
>
> 제품 필터, 현재 항목, 리소스 유형(비디오에서 웨비나로), 보안 영역, 보안 역할 및 제품 기능에 대한 익숙하거나 경험 수준이 나열됩니다.

## <a name="send-us-your-feedback"></a>피드백 보내기

사용자 의견이 필요합니다. We're always looking to improve, so if there's something you're like to see, [send us your Microsoft 365 Defender feedback.](https://www.microsoft.com/videoplayer/embed/RE4K5Ci)

이 문서에서 피드백을 남길 수 있습니다. '제출 및 피드백 보기'의 끝에 있는 '피드백' 섹션에서 옵션은 이 제품 *또는* *이 페이지입니다.*

제품 **피드백에 이 제품** *단추를* 사용하세요.

1. 문서 *아래쪽에서* 이 제품을 선택합니다.
    1. 단추를 마우스 오른쪽 단추로 클릭하고 이러한 길안을 계속 읽으려면 '새 탭에서 열기'를 클릭합니다.
2. 그러면 **UserVoice** 포럼으로 이동합니다.
3. 다음 두 가지 옵션이 있습니다.
    1. 텍스트 상자까지 아래로 스크롤하여 *Office 365에서* 규정 준수를 개선하거나 사용자를 더 잘 보호할 수 있나요? *Microsoft 365* 보안 센터에서 붙여넣습니다. 결과에서 사용자와 같은 아이디어를 검색하여 투표하거나 새 아이디어 게시 **단추를 사용할 수 있습니다.**
    1. 이 문제가 이미 보고된 것으로 생각되고 해당 프로필을 투표(또는 투표)로  올리고 싶은 경우 UserVoice 오른쪽의 피드백 보내기 상자를 사용하세요. Microsoft *365* 보안 센터를 검색하고, 문제를 **찾고,** 투표 단추를 사용하여 상태를 올렸다.

이 *페이지를 사용하여* 문서 자체에 대한 피드백을 제공합니다. 사용자 의견을 보내 주셔서 감사합니다. 음성은 제품을 개선하는 데 도움이 됩니다.

### <a name="explore-what-the-security-center-has-to-offer"></a>보안 센터에서 제공하는 것을 살펴보기

Microsoft 365 보안 센터에서 기능을 계속 탐색합니다.

- [인시던트 및 경고 관리](manage-incidents.md)
- [위협 분석을 사용하여 새로운 위협 추적 및 대응](threat-analytics.md)
- [알림 센터](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
- [장치, 전자 메일, 앱 및 ID 전반의 위협 헌트](https://docs.microsoft.com/microsoft-365/security/mtp/advanced-hunting-query-emails-devices)
- [사용자 지정 검색 규칙](https://docs.microsoft.com/microsoft-365/security/mtp/custom-detection-rules)
- [전자 & 공동 작업 알림](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies)
- [피싱 공격 시뮬레이션을 만들고](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulation-training) 팀 교육을 위한 [페이로드 만들기](https://docs.microsoft.com/microsoft-365/security/office-365-security/attack-simulation-training-payloads)
 
### <a name="related-information"></a>관련 정보
- [Microsoft 365 보안 센터](overview-security-center.md)
- [Microsoft 365 보안 센터의 Office 365용 Microsoft Defender](microsoft-365-security-center-mdo.md)
- [Microsoft 365 보안 센터의 끝점용 Microsoft Defender](microsoft-365-security-center-mde.md)
- [끝점용 Microsoft Defender에서 Microsoft 365 보안 센터로 계정 리디렉션](microsoft-365-security-mde-redirection.md)
