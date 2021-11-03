---
title: Microsoft 365 Defender
description: Microsoft 365 Defender 장치, ID, 데이터 및 응용 프로그램을 보호하도록 설계된 조정된 위협 방지 솔루션입니다.
keywords: MMicrosoft 365 Defender 소개, 사이버 보안, 고급 영구 위협, 엔터프라이즈 보안, 장치, 장치, ID, 사용자, 데이터, 응용 프로그램, 인시던트, 자동화된 조사 및 수정, 고급 헌팅
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: c59b143dafbaf21cc661cc72aaf35009a8a8b665
ms.sourcegitcommit: cfcdb11cc5d39c6c71a34e09c03e8859cd6708d3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2021
ms.locfileid: "60724395"
---
# <a name="microsoft-365-defender"></a>Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

> Microsoft 365 Defender를 경험하고 싶으신가요? [실험실 환경에서 평가](m365d-evaluation.md?ocid=cx-docs-MTPtriallab)하거나 [프로덕션에서 파일럿 프로젝트를 실행](m365d-pilot.md?ocid=cx-evalpilot)할 수 있습니다.
>

Microsoft 365 Defender는 기본적으로 엔드포인트, ID, 전자 메일 및 응용프로그램 전반에서 탐지, 방지, 조사 및 응답을 조정하여 정교한 공격에 대한 통합 보호를 제공하는 통합된 위반 전 및 위반 후 엔터프라이즈 보안 제품군입니다.

통합된 Microsoft 365 Defender 솔루션을 사용하여 보안 전문가는 이러한 각 제품이 수신하는 위협 신호를 통합하고 위협의 전체 범위와 영향을 확인할 수 있습니다. 환경이 환경에 들어오고 있는 방법, 영향을 받는 방법 및 현재 조직에 미치는 영향 Microsoft 365 Defender 공격을 방지하거나 중지하고 영향을 받는 사서함, 끝점 및 사용자 ID를 자동으로 조치를 취합니다.  

<center><h2>Microsoft 365 Defender 서비스</center></h2>
<table><tr><td><center><b><a href="/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint"><b>끝점용 Microsoft Defender</b></center></a></td>
<td><center><b><a href="/microsoft-365/security/office-365-security/overview"><b>Microsoft Defender for Office 365</b></center></a></td>
<td><center><b><a href="/defender-for-identity/"><b>Id용 Microsoft Defender</b></a></center></td>
<td><center><b><a href="/cloud-app-security/"><b>Microsoft Cloud App Security</b></a></center></td>
</tr>
</table>
<br>

## <a name="microsoft-365-defender-interactive-guide"></a>Microsoft 365 Defender 대화형 가이드

이 대화형 가이드에서는 조직을 보호하는 방법을 Microsoft 365 Defender. 보안 위험을 Microsoft 365 Defender 조직에 대한 공격을 조사하고 유해한 활동을 자동으로 방지하는 데 도움이 되는 방법을 알 수 있습니다.

[대화형 가이드 확인](https://aka.ms/M365Defender-InteractiveGuide)

## <a name="microsoft-365-defender-protection"></a>Microsoft 365 Defender 보호

Microsoft 365 Defender 서비스는 다음을 보호합니다. 

- **Endpoint용 Defender가** 있는 끝점 - 끝점용 Defender는 예방적 보호, 위반 후 감지, 자동화된 조사 및 대응을 위한 통합된 끝점 플랫폼입니다. 
- **Defender for Office 365** 전자 메일 및 공동 작업 - Office 365 메시지, 링크(URL) 및 공동 작업 도구로 위협이되는 악의적인 위협에 대해 조직을 보호합니다. 
- ID에 대한 Defender 및 Azure Active Directory **(Azure AD) ID** 보호 - ID에 대한 Defender는 AD DS(Active Directory 도메인 서비스) 신호를 사용하여 조직에 대한 고급 위협, 손상된 ID 및 악의적인 내부자 작업을 식별, 감지 및 조사합니다. Azure AD ID 보호는 클라우드 기반 Azure AD에서 ID 기반 위험을 감지하고 수정합니다.
- 응용 Microsoft Cloud App Security 응용 프로그램 - Microsoft Cloud App **security는** 클라우드 앱에 심층적인 가시성, 강력한 데이터 제어 및 향상된 위협 보호를 도입하는 포괄적인 교차 SaaS 솔루션입니다. 

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4Bzww] 

Microsoft 365 Defender 제품 간 계층은 개별 서비스 구성 요소를 다음으로 향상합니다.

- 신호 공유 및 자동화된 작업을 통해 공격으로부터 보호하고 서비스 전체에서 방어 대응을 조정합니다.
- 경고, 의심스러운 이벤트 및 영향을 미치는 자산에 '인시던트'에 데이터를 가입하여 보안 팀을 위한 제품 경고, 동작 및 컨텍스트 전반에 걸쳐 공격의 전체 스토리를 내레이션합니다.
- 자동화된 수정을 통해 영향을 미치는 자산에 대한 자동 복구를 트리거하여 손상에 대한 대응을 자동화합니다.
- 보안 팀이 끝점 및 데이터 전체에서 상세하고 효과적인 위협 헌팅을 Office 수 있습니다.

다음은 Microsoft 365 Defender 포털이 제품 전체에 관련된 모든 경고를 단일 인시던트로 연관하는 방법의 예입니다.

:::image type="content" source="../../media/overview-incident.png" alt-text="인시던트 개요 페이지 예" lightbox="../../media/overview-incident.png":::

다음은 인시던트에 대한 관련 경고 목록의 예입니다.

:::image type="content" source="../../media/incident-list.png" alt-text="인시던트에 대한 경고 목록의 예" lightbox="../../media/incident-list.png":::

다음은 전자 메일 및 끝점 원시 데이터 위에 있는 쿼리 기반 헌팅의 예입니다.

:::image type="content" source="../../media/advanced-hunting.png" alt-text="고급 헌팅 및 쿼리의 예" lightbox="../../media/advanced-hunting.png":::

Microsoft 365 Defender 제품 간 기능에는 다음이 포함됩니다. 

- Microsoft 365 Defender 포털의 제품 간 단일 창 **-** 단일 큐 및 단일 큐의 단일 창에서 감지, 영향을 미치는 자산, 수행된 자동화된 작업 및 관련 증거에 대한 모든 정보를 볼 수 있는 [security.microsoft.com.](https://security.microsoft.com) 
- **결합된** 인시던트 큐 - 전체 공격 범위를 보장하여 보안 전문가가 중요한 작업에 집중할 수 있도록 영향을 미치는 자산 및 자동화된 수정 작업이 그룹화되어 시기적합한 방식으로 표시됩니다. 
- **위협에 대한** 자동 대응 - 위험 위협 정보는 공격의 진행을 Microsoft 365 Defender 제품 간에 실시간으로 공유됩니다. 

   예를 들어 끝점용 Defender로 보호되는 끝점에서 악성 파일이 감지되면 Defender에 모든 전자 메일 메시지에서 파일을 Office 365 파일을 검사하고 제거합니다. 이 파일은 전체 보안 제품군에 의해 Microsoft 365 차단됩니다.

- **손상된 장치,** 사용자 ID 및 사서함에 대한 자체 복구 - Microsoft 365 Defender AI 기반 자동 작업 및 플레이북을 사용하여 영향을 받는 자산을 안전한 상태로 다시 수정합니다. Microsoft 365 Defender 제품군 제품의 자동 수정 기능을 활용하여 인시던트와 관련된 모든 영향을 미치는 자산이 가능한 경우 자동으로 수정되도록 합니다.
- **제품** 간 위협 헌팅 - 보안 팀은 다양한 보호 제품에서 수집한 원시 데이터에 대해 자체 사용자 지정 쿼리를 만들어 고유한 조직 지식을 활용하여 손상 징후를 찾을 수 있습니다. Microsoft 365 Defender 30일 동안의 기록된 원시 신호에 대한 쿼리 기반 액세스 권한을 제공하며, 끝점에서 경고 데이터를 보내고 Office 365 데이터를 제공합니다. 

## <a name="get-started"></a>시작

Microsoft 365 Defender 라이선스 요구 사항을 충족해야 Microsoft 365 Defender 포털에서 서비스를 사용하도록 설정할 [수 security.microsoft.com.](https://security.microsoft.com) 자세한 내용은 다음을 참조하세요.

- [라이선스 요구사항](prerequisites.md#licensing-requirements)
- [Microsoft 365 Defender 켜기](m365d-enable.md)


## <a name="the-microsoft-365-defender-portal"></a>Microsoft 365 Defender 포털

Microsoft 365 Defender 포털( )은 전자 메일, 공동 **작업, ID,** 장치 및 앱 위협에 대한 보호, 검색, 조사 및 응답을 중앙 장소에 [https://security.microsoft.com](https://security.microsoft.com) 결합합니다.    

이 단일 창은 Microsoft 365 Defender 포털 및 Office 365 보안 및 규정 준수 센터와 같은 기존 Microsoft 보안 포털의 & 통합합니다. Microsoft 365 Defender 포털에서는 정보에 빠르게 액세스하고, 레이아웃을 단순화하고, 관련 정보를 함께 모아 보다 쉽게 사용할 수 있도록 합니다. 이 목록에는 다음과 같은 내용이 포함됩니다.

- **[Microsoft Defender for Office 365](/microsoft-365/security/office-365-security/defender-for-office-365)** Microsoft Defender for Office 365 보호, 검색, 조사 및 헌팅 기능 집합을 통해 조직의 엔터프라이즈 보안을 유지하여 전자 메일 및 전자 메일 리소스를 Office 365 있습니다.
- **[끝점용 Microsoft Defender는](/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection)** 조직의 장치에 대한 예방 보호, 위반 후 감지, 자동화된 조사 및 응답을 제공합니다.
- **[Microsoft 365 Defender](microsoft-365-defender.md)** 보안 포트폴리오를 활용하여 도메인 전체의 위협 데이터를 자동으로 분석하고 단일 대시보드에 대한 공격 그림을 작성하는 Microsoft의 XDR(Extended *Detection and Response* Microsoft 365) 솔루션에 속합니다.
- Microsoft Cloud App Security 클라우드 앱에 심층적인 **[가시성,](/cloud-app-security/)** 강력한 데이터 제어 및 향상된 위협 보호를 도입하는 포괄적인 교차 SaaS 및 PaaS 솔루션입니다. 

Office 365 보안 및 준수 센터 또는 & 포털에서 변경된 Microsoft 365 Defender 필요한 경우 다음을 참조하세요.

- [Microsoft 365 Defender의 Office 365용 Defender](microsoft-365-security-center-mdo.md)
- [Microsoft 365 Defender의 엔드포인트용 Defender](microsoft-365-security-center-mde.md)

> [!NOTE]
> Microsoft 365 Defender 포털은 기존 역할 기반 액세스를 사용 및 적용하며, 각 보안 모델을 통합 포털로 이동합니다. 수렴형 워크로드마다 자체 역할 기반 액세스 권한이 있습니다. 제품에 이미 있는 역할은 자동으로 Microsoft 365 Defender 수렴됩니다. 그러나 역할 및 사용 권한은 Microsoft Cloud App Security 역할에 의해 Microsoft Cloud App Security.

### <a name="what-to-expect"></a>예상할 일

Office 365 보안 및 준수 센터(protection.office.com) 및 Microsoft 365 Defender 포털(securitycenter.microsoft.com)에서 사용하는 모든 보안 콘텐츠를 Microsoft 365 Defender 포털에서 찾을 *수* 있습니다.

Microsoft 365 Defender 포털을 사용하면 보안 팀이 여러 워크로드의 신호를 다음에 대한 통합 환경 집합으로 가져와 공격을 조사하고 대응할 수 있습니다.

- 인시던트 및 경고
- 헌팅
- 알림 센터 
- 위협 분석

Microsoft 365 Defender Microsoft Defender  for Office 365 끝점용 Microsoft Defender를 병합할 때 단합, 명확성 및 공통 목표를 강조합니다. 병합은 아래에 나열된 우선 순위를 기반으로 하여 각 보안 제품군이 다음과 같은 조합으로 가져온 기능을 만족하지 않고도 이행됩니다.

- 일반적인 구성 요소
- 일반적인 용어
- 일반 엔터티
- 다른 워크로드와의 기능 패리티

> [!NOTE]
> 고객이 Microsoft 365 Defender 새 라이선스를 구매하거나 마이그레이션 단계를 수행하지 않고도 사이트 포털에 액세스할 수 있습니다. 예를 들어 E3 구독이 있는 관리자는 이 새 포털에 액세스할 수 있습니다. 이 포털은 Office 365 계획 1 및 계획 2에 대한 Microsoft Defender를 Office 365 있습니다. 그러나 Exchange Online Protection 또는 Office 365 요금제 1 고객에게는 구독 라이선스가 지원하는 보안 기능만 볼 수 있습니다. 포털의 목표는 보안을 중앙 집중화하는 것입니다.

### <a name="unified-investigations"></a>통합 조사

보안 정보를 중앙 집중화하면 여러 보안 정보에서 보안 인시던트 조사를 위한 단일 Microsoft 365. 기본 예로  인시던트 및 인시던트 & 빠른 실행에 대한 알림이 Microsoft 365 Defender. 

:::image type="content" source="../../media/converged-incidents-2.png.png" alt-text="2016년 8월의 인시던트 Microsoft 365 Defender" lightbox="../../media/converged-incidents-2.png.png":::

:::image type="content" source="../../media/converged-incidents-2.png.png" alt-text="2016의 인시던트 Microsoft 365 Defender.":::

인시던트 이름을 선택하면 보안 정보의 중앙 집중화 값을 보여줄 수 있는 페이지가 표시됩니다.

:::image type="content" source="../../media/converged-incident-info-3.png" alt-text="문서의 인시던트에 대한 요약 Microsoft 365 Defender" lightbox="../../media/converged-incident-info-3.png":::

인시던트 페이지 위쪽에는 요약, **경고,** 장치, 사용자,  **사서함,** **조사,** 증거  **및** 응답 및 Graph 표시됩니다. 자세한 내용을 확인하려면 이 탭을 선택합니다. 예를 들어  사용자 탭에는 수렴형 워크로드(끝점용 Microsoft Defender, ID용 Microsoft Defender 및 Microsoft Cloud App Security) 및 다양한 원본(예: AD DS(Active Directory 도메인 서비스), Azure AD 및 타사 ID 공급자)의 사용자에 대한 정보가 표시됩니다. 자세한 내용은 사용자 [조사를 참조하세요.](investigate-users.md)

시간을 내어 환경의 인시던트 검토, 이러한 탭으로 드릴다운, 다양한 종류의 위협에 대해 인시던트에 제공된 정보에 액세스하는 방법을 파악하는 방법을 연습하세요.

자세한 내용은 에서 [인시던트 Microsoft 365 Defender.](incidents-overview.md)

### <a name="improved-processes"></a>향상된 프로세스

공용 컨트롤과 콘텐츠는 같은 장소에 표시되거나 한 데이터 피드로 압축되어 찾기가 더 쉽습니다. 예를 들어 통합 설정이 있습니다.

#### <a name="unified-settings"></a>통합 설정

:::image type="content" source="../../media/converged-add-role-9.png" alt-text="웹 사이트 포털의 Microsoft 365 Defender 페이지" lightbox="../../media/converged-add-role-9.png":::

#### <a name="permissions--roles"></a>역할에 & 사용 권한

:::image type="content" source="../../media/converged-roles-5.png" alt-text="사용 권한 & 그룹, 역할 및 장치 & 끝점 역할을 보여 주는 역할 페이지" lightbox="../../media/converged-roles-5.png":::

액세스 Microsoft 365 Defender Azure AD 전역 역할 또는 사용자 지정 역할을 사용하여 구성됩니다. 끝점용 Defender에 대한 자세한 내용은 Microsoft 365 Defender 포털에 대한 [사용자 액세스 할당을 참조합니다.](/microsoft-365/security/defender-endpoint/assign-portal-access) For Defender for Office 365, see [Permissions in the Microsoft 365 규정 준수 센터 and Microsoft 365 Defender.](../office-365-security/permissions-microsoft-365-compliance-security.md)

- 액세스 권한을 관리하는 방법에 대해 자세히 [Microsoft 365 Defender](m365d-permissions.md)
- 자세한 내용은 2013에서 사용자 지정 역할을 만드는 [방법을](custom-roles.md) Microsoft 365 Defender

> [!NOTE]
> Microsoft 365 Defender Microsoft Defender for Endpoint는 Microsoft 365 Defender 포털에서 액세스 권한을 부여하는 방법과 동일한 방식으로 관리되는 보안 서비스 [공급자(MSSP)에](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) 대한 액세스 권한을 [부여할 Microsoft 365 Defender 지원합니다.](./mssp-access.md)

#### <a name="integrated-reports"></a>통합 보고서

보고서도 통합되어 Microsoft 365 Defender. 관리자는 일반 보안 보고서로 시작하여 끝점, 전자 메일 및 공동 작업과 관련한 특정 보고서로 & 있습니다. 여기에 있는 링크는 작업 구성에 따라 동적으로 생성됩니다.

#### <a name="quickly-view-your-microsoft-365-environment"></a>사용자 환경의 Microsoft 365 빠르게 보기

홈 **페이지에는** 보안 팀에 필요한 많은 공통 카드가 표시됩니다. 카드와 데이터의 구성은 사용자 역할에 따라 달라집니다. 포털에서 Microsoft 365 Defender 액세스 제어를 사용하게 됐기 때문에 각 역할에 따라 매일 작업하는 데 더 의미 있는 카드가 표시될 수 있습니다.  

이 정보를 한눈에 확인하면 조직의 최신 활동을 유지하는 데 도움이 됩니다. Microsoft 365 Defender 소스의 신호를 함께 모아 사용자 환경의 전체적인 Microsoft 365 제공합니다.

카드는 다음 범주로 분류됩니다.

- **ID**- 조직의 ID를 모니터링하고 의심스거나 위험한 동작을 추적합니다. [ID 보호에 대해 자세히 알아보시다.](/azure/active-directory/identity-protection/overview-identity-protection)
- **데이터** - 무단 데이터 공개로 이어질 수 있는 사용자 활동을 추적하는 데 도움이 됩니다.
- **장치** - 장치의 경고, 위반 활동 및 기타 위협에 대한 최신 정보를 얻습니다.
- **앱** - 조직에서 클라우드 앱이 어떻게 사용되는지 파악합니다. [검색된 앱의 Cloud App Security 자세히 알아보아야 합니다.](/cloud-app-security/discovered-apps)

### <a name="threat-analytics-with-better-data-coverage"></a>더 나은 데이터 범위를 제공하는 위협 분석
다음과 같은 위협 분석 통합 환경을 Microsoft 365 Defender 새로운 위협을 추적하고 대응합니다.

- 엔드포인트용 Microsoft Defender와 Microsoft Defender for Office 365 통합된 인시던트 관리, 자동 조사, 수정 및 사전 또는 사후 위협 헌팅을 도메인 전체에서 사용할 수 있도록 합니다. 
- 끝점용 Microsoft Defender에서 이미 사용할 수 있는 끝점 데이터 외에 Office 365 Microsoft Defender의 전자 메일 관련 검색 및 완화 기능
- Microsoft Defender for Endpoint 및 Microsoft Defender for Office 365 전반에 걸쳐 종합적인 공격 사례로 경고를 집계하여 작업 큐를 줄이고 조사를 단순화하고 빠르게 하는 위협 관련 인시던트 보기입니다.
- 보안 솔루션에 의해 검색되고 차단된 공격 Microsoft 365 Defender 있습니다. 추가 노출 및 탄력성 증가 위험을 완화하는 예방 조치를 구동하는 데 사용할 수 있는 데이터도 있습니다. 
- 실행 가능한 정보를 스포트라이트에 저장하여 보고서를 긴급하게 집중하고 조사하고 활용하기 위해 데이터를 빠르게 식별할 수 있도록 하는 향상된 디자인입니다.

### <a name="a-centralized-learning-hub"></a>중앙 집중식 Learning 허브

Microsoft 365 Defender 포털에는 Microsoft 보안 블로그, YouTube의 Microsoft 보안 커뮤니티 및 공식 설명서와 같은 리소스의 공식 지침을 버블업하는 학습 허브가 docs.microsoft.com.

학습 허브 내에서 Email & Collaboration (Microsoft Defender for Office 365) 지침은 Endpoint(Endpoint용 Microsoft Defender) 및 Microsoft 365 Defender 리소스와 함께 제공됩니다.

학습 허브는 "Learning 사용하여 조사하는 방법"과 같은 주제에 대해 구성되는 Microsoft 365 Defender 경로로 열립니다. 및 "Microsoft Defender for Office 365 모범 사례". 이 섹션은 현재 Microsoft 내부의 보안 제품 그룹에서 큐레이터합니다. 각 Learning 경로는 개념을 통과하는 데 걸리는 시간을 반영합니다. 예를 들어 'Office 365 사용자 계정이 손상될 때 수행되는 단계'는 8분 정도 소요될 것으로 예정되어 있으며, 중요한 학습이 진행됩니다.

콘텐츠를 클릭한 후 이 사이트를 책갈피로 지정하고 책갈피를 '보안' 또는 '중요' 폴더로 구성하는 것이 유용할 수 있습니다. 모든 Learning 보려면 주 패널에서 모두 표시 링크를 클릭합니다.

> [!NOTE]
> 제품(현재  Microsoft 365 Defender Microsoft 365 Defender, 끝점용 Microsoft Defender 및 Microsoft Defender for Office 365) 간에 선택할 수 있는 유용한 필터가 Microsoft 365 Defender 있습니다. 각 섹션의 학습 리소스 수가 나열되어 있으며, 이는 학습하는 사람이 교육 및 학습을 위해 얼마나 많은 리소스를 준비해야 하는지 추적하는 데 도움이 될 수 있습니다.
>
> 제품 필터, 현재 항목, 리소스 유형(비디오에서 웨비나까지), 보안 영역, 보안 역할 및 제품 기능에 대한 익숙하거나 경험 수준이 나열됩니다.

> [!TIP]
> Microsoft Learn 에는 다른 많은 학습 [기회가 있습니다.](/learn/) [Ms-500T02-A:](/learn/certifications/courses/ms-500t02)보안 위협 방지 구현과 같은 인증 Microsoft 365 있습니다.

### <a name="send-us-your-feedback"></a>피드백 보내기

피드백이 필요합니다. We're always looking to improve, so if there's something you're like to see, [send us your Microsoft 365 Defender feedback.](https://www.microsoft.com/videoplayer/embed/RE4K5Ci)

이 문서에서 피드백을 남길 수 있습니다. '피드백 제출 및 보기' 아래 끝에 있는 '피드백' 섹션에서 옵션은 이 제품 또는 *이 페이지입니다.*

제품 **피드백을 위해 이** 제품 *단추를* 사용하세요.

1. 문서 *아래쪽에서* 이 제품을 선택합니다.
    1. 단추를 마우스 오른쪽 단추로 클릭하고 다음 길안을 계속 읽으려면 '새 탭에서 열기'를 클릭합니다.
2. 그러면 **UserVoice 포럼으로 이동합니다.**
3. 다음과 같은 두 가지 옵션이 있습니다.
    1. 텍스트 상자까지 아래로 스크롤하여 규정 준수를 개선하거나 사용자를 보다 잘 보호할 수 *Office 365?를* 입력하고 *Microsoft 365 Defender.* 결과에서 사용자와 같은 아이디어를 검색하여 투표하거나 새 아이디어 게시 **단추를 사용할 수 있습니다.**
    1. 이 문제가 이미 보고된 것으로 생각되고 해당 프로필을 투표(또는 투표)로  올리고 싶은 경우 UserVoice의 오른쪽에 있는 피드백 보내기 상자를 사용하세요. 에서 *Microsoft 365 Defender* **검색하고,** 투표 단추를 사용하여 상태를 올렸다.

문서 *자체에* 대한 피드백을 위해 이 페이지를 사용하세요. 사용자 의견을 보내 주셔서 감사합니다. 음성은 제품을 개선하는 데 도움이 됩니다.

### <a name="explore-what-the-microsoft-365-defender-portal-has-to-offer"></a>포털에서 Microsoft 365 Defender 정보를 탐색합니다.

다음과 같은 기능에 대해 계속 Microsoft 365 Defender.

- [인시던트 및 경고 관리](manage-incidents.md)
- [위협 분석을 사용하여 새로운 위협 추적 및 대응](threat-analytics.md)
- [알림 센터](m365d-action-center.md)
- [장치, 전자 메일, 앱 및 ID에 대한 위협 검색](./advanced-hunting-query-emails-devices.md)
- [사용자 지정 검색 규칙](./custom-detection-rules.md)
- [전자 메일 및 공동 작업 경고](../../compliance/alert-policies.md#default-alert-policies)
- [피싱 공격 시뮬레이션을](../office-365-security/attack-simulation-training.md) 만들고 팀 교육을 위한 [페이로드 만들기](/microsoft-365/security/office-365-security/attack-simulation-training-payloads)
 
## <a name="training-for-security-analysts"></a>보안 분석가를 위한 교육

Microsoft Learn의 이 학습 경로를 통해 보안 위협을 식별, Microsoft 365 Defender 및 수정하는 방법에 대해 이해할 수 있습니다.

|교육:|Microsoft 365 Defender를 통한 사이버 공격 감지 및 대응|
|---|---|
|![Microsoft 365 Defender 교육 아이콘입니다.](../../media/microsoft-365-defender/m365-defender-secure-organization.svg)|Microsoft 365 Defender는 엔드포인트, ID, 전자 메일, 애플리케이션 전체의 위협 신호를 통합하여 정교한 사이버 공격에 대한 통합된 보호를 제공합니다. Microsoft 365 Defender는 인시던트를 조사하고 이에 대응하고, 적극적으로 현재 진행 중인 악성 사이버 보안 활동을 조사하기 위한 중앙 집중식 환경입니다.<p> 1 hr 38분 - Learning 경로 - 5개 모듈|

> [!div class="nextstepaction"]
> [시작 >](/learn/paths/defender-detect-respond/)


## <a name="see-also"></a>참고 항목

- [Microsoft 365 Defender의 새로운 기능](whats-new.md)
- [Microsoft Defender for Office 365 Microsoft 365 Defender](microsoft-365-security-center-mdo.md)
- [Microsoft Defender for Endpoint in Microsoft 365 Defender](microsoft-365-security-center-mde.md)
