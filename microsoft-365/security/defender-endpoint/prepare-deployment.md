---
title: 엔드포인트용 Microsoft Defender 배포 준비
description: 끝점용 Microsoft Defender 배포를 위한 이해 관계자 승인, 일정, 환경 고려 사항 및 채택 순서 준비
keywords: 배포, 준비, 관련자, 타임라인, 환경, 끝점, 서버, 관리, 채택
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 0e577108f92abe0c704cd812e61445f8d0f83f13
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60191746"
---
# <a name="prepare-microsoft-defender-for-endpoint-deployment"></a>엔드포인트용 Microsoft Defender 배포 준비

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

끝점용 Defender 배포는 3단계 프로세스입니다.

|![배포 단계 - 준비.](images/phase-diagrams/prepare.png)<br>1 단계: 준비|[![배포 단계 - 설정](images/phase-diagrams/setup.png)](production-deployment.md)<br>[2 단계: 설정](production-deployment.md)|[![배포 단계 - 온보드](images/phase-diagrams/onboard.png)](onboarding.md)<br>[3 단계: 온보딩](onboarding.md)|
|---|---|---|
|*여기 있습니다!*|||

현재 준비 단계에 있습니다.

성공적인 배포의 핵심은 준비입니다. 이 문서에서는 끝점용 Defender 배포를 준비할 때 고려해야 할 지점을 안내합니다.

## <a name="stakeholders-and-approval"></a>이해 관계자 및 승인

다음 섹션에서는 프로젝트에 참여하고 승인, 검토 또는 정보를 제공해야 하는 모든 관련자를 식별하는 데 도움이 됩니다.

조직에 따라 아래 표에 관련자를 추가합니다.

- SO = 프로젝트 승인
- R = 이 프로젝트를 검토하고 입력 제공
- I = 이 프로젝트에 대한 정보

<br>

****

|이름|역할|작업|
|---|---|---|
|이름 및 전자 메일 입력|**CISO(최고 정보 보안 책임자)** 새 기술 배포를 위해 조직 내부의 후원자 역할을 하는 *임원진 대표입니다.*|SO|
|이름 및 전자 메일 입력|**CDOC(Cyber Defense Operations Center)** 책임자 이 변경이 고객 보안 운영 팀의 프로세스와 어떻게 일치할지 정의하는 CDOC 팀의 *담당자입니다.*|SO|
|이름 및 전자 메일 입력|**보안 설계자** 이 변경이 조직의 핵심 보안 아키텍처에 부합하는 방법을 정의하는 보안 팀의 *담당자입니다.*|R|
|이름 및 전자 메일 입력|**작업** 공간 설계자 이 변경이 조직의 핵심 작업 공간 아키텍처에 부합하는 방법을 정의하는 IT 팀의 *담당자입니다.*|R|
|이름 및 전자 메일 입력|**보안 분석가** CDOC 팀의 담당자는 보안 운영 측면에서 이러한 변경의 검색 기능, 사용자 환경 및 전반적인 유용성에 대한 정보를 제공할 *수 있습니다.*|I|
||||

## <a name="environment"></a>환경

이 섹션은 관련자가 환경을 깊이 이해할 수 있도록 하는 데 사용하며, 기술 또는 프로세스에 필요한 잠재적인 종속성 및/또는 변경 사항을 식별하는 데 도움이 됩니다.

<br>

****

|무엇|설명|
|---|---|
|끝점 수|운영 체제의 총 끝점 수입니다.|
|서버 수|운영 체제 버전당 총 서버 수입니다.|
|관리 엔진|관리 엔진 이름 및 버전(예: 현재 System Center Configuration Manager 1803)|
|CDOC 배포|높은 수준의 CDOC 구조(예: Contoso로 아웃소싱되는 계층 1, 계층 2 및 유럽 및 아시아에 분산된 계층 3 사내로 아웃소싱).|
|SIEM(보안 정보 및 이벤트)|사용 중 SIEM 기술입니다.|
|||

## <a name="role-based-access-control"></a>역할 기반 액세스 제어

최소 권한의 개념을 사용하는 것이 좋습니다. Endpoint용 Defender는 기본 제공 역할을 Azure Active Directory. Microsoft는 사용 [가능한 다양한](/azure/active-directory/roles/permissions-reference) 역할을 검토하고 이 응용 프로그램의 각 사용자에 대한 요구 사항을 해결하기 위한 올바른 역할을 선택하는 것이 좋습니다. 배포가 완료된 후 일부 역할을 일시적으로 적용하고 제거해야 할 수 있습니다.

<br>

****

|개인|역할|Azure AD 역할(필요한 경우)|다음에 할당|
|---|---|---|---|
|보안 관리자||||
|보안 분석가||||
|끝점 관리자||||
|인프라 관리자||||
|비즈니스 소유자/이해 관계자||||
|

Microsoft는 디렉터리 [Privileged Identity Management](/azure/active-directory/active-directory-privileged-identity-management-configure) 사용자에 대한 추가 감사, 제어 및 액세스 검토를 제공하기 위해 역할을 관리하는 것이 좋습니다.

Endpoint용 Defender는 사용 권한을 관리하는 두 가지 방법을 지원합니다.

- **기본 사용 권한 관리:** 모든 권한 또는 읽기 전용으로 사용 권한을 설정합니다. 보안 읽기 권한자 역할이 읽기 전용인 동안 Azure Active Directory 관리자 또는 보안 관리자 역할이 있는 기본 권한 관리 사용자의 경우 모든 권한이 있습니다.

- **RBAC(역할** 기반 액세스 제어) : 역할을 정의하고, 역할에 Azure AD 사용자 그룹을 할당하고, 사용자 그룹에 장치 그룹에 대한 액세스 권한을 부여하여 세분화된 사용 권한을 설정할 수 있습니다. 자세한 내용은 역할 [기반 액세스 제어를 사용하여 포털 액세스 관리를 참조합니다.](rbac.md)

비즈니스 사유가 있는 사용자만 끝점용 Defender에 액세스할 수 있도록 RBAC를 활용하는 것이 좋습니다.

사용 권한 지침에 대한 자세한 내용은 역할 만들기 및 역할 할당에서 Azure Active Directory [있습니다.](/microsoft-365/security/defender-endpoint/user-roles#create-roles-and-assign-the-role-to-an-azure-active-directory-group)

다음 예제 표는 환경에 필요한 RBAC 구조를 확인하는 데 도움이 되는 환경의 Cyber Defense Operations Center 구조를 식별하는 데 도움이 됩니다.

<br>

****

|계층|설명|필요한 사용 권한|
|---|---|---|
|계층 1|**로컬 보안 운영 팀/IT 팀** <p> 이 팀은 일반적으로 지리적 위치 내에 포함된 경고를 조사하고 활성 수정이 필요한 경우 계층 2로 에스컬레이터합니다.||
|계층 2|**지역 보안 운영 팀** <p> 이 팀은 해당 지역의 모든 장치를 보고 수정 작업을 수행할 수 있습니다.|데이터 보기|
|계층 3|**글로벌 보안 운영 팀** <p> 이 팀은 보안 전문가로 구성하며 포털에서 모든 작업을 보고 수행할 수 있는 권한이 있습니다.|데이터 보기 <p> 경고 조사 활성 수정 작업 <p> 경고 조사 활성 수정 작업 <p> 포털 시스템 설정 관리 <p> 보안 설정 관리|
||||

## <a name="adoption-order"></a>채택 순서

대부분의 경우 조직에는 기존 끝점 보안 제품이 있습니다. 모든 조직이 최소한 바이러스 백신 솔루션이 됐을 것입니다. 그러나 경우에 따라 조직에서 이미 솔루션 솔루션을 이미 EDR 있습니다.

지금까지는 응용 프로그램 계층 및 인프라 종속성에 대한 엄격한 후크로 인해 시간이 많이 걸려서 달성하기 어려운 보안 솔루션을 교체했습니다. 그러나 Endpoint용 Defender는 운영 체제에 기본 제공되어 있기 때문에 이제 타사 솔루션을 바꾸는 것이 쉽습니다.

사용할 끝점용 Defender의 구성 요소를 선택하고 적용되지 않는 구성 요소를 제거합니다. 아래 표에는 끝점 보안 제품군을 사용하도록 설정하는 방법에 대해 Microsoft에서 권장하는 순서가 표시됩니다.

<br>

****

|구성 요소|설명|채택 순서 순위|
|---|---|---|
|끝점 검색 & 응답(EDR)|Endpoint 끝점 감지 및 응답 기능에 대한 Defender는 거의 실시간으로 실행 가능한 고급 공격 감지를 제공합니다. 보안 분석가는 알림에 효과적으로 우선 순위를 지정하고, 침해의 전체 범위에 대한 가시성을 확보하고 위협을 수정하기 위한 응답 조치를 취할 수 있습니다. <p> [더 알아보세요.](/windows/security/threat-protection/windows-defender-atp/overview-endpoint-detection-response)|1|
|위협 & 취약성 관리(TVM)|위협 & 취약성 관리는 끝점용 Microsoft Defender의 구성 요소로, 다음을 비롯한 고유한 가치를 보안 관리자 및 보안 운영 팀에 제공합니다. <ul><li>엔드포인트 취약점과 관련된 실시간 EDR(엔드포인트 탐지 및 대응) 인사이트</li><li>인시던트 조사 중에 평가할 수 있는 장치 취약성 컨텍스트</li><li>Microsoft Intune Microsoft 2013을 통한 기본 System Center Configuration Manager</li></ul> <p> [자세히 알아보기](https://techcommunity.microsoft.com/t5/Windows-Defender-ATP/Introducing-a-risk-based-approach-to-threat-and-vulnerability/ba-p/377845).|2|
|NGP(차세대 보호)|Microsoft Defender 바이러스 백신 맬웨어 방지 솔루션으로, 데스크톱, 휴대용 컴퓨터 및 서버에 대한 차세대 보호 기능을 제공합니다. Windows Defender 바이러스 백신은 다음을 포함합니다. <ul><li>새로 등장하는 위협의 거의 즉각적인 탐지 및 차단을 위한 클라우드 전달 보호 기능. 기계 학습 및 Intelligent Security Graph와 함께 클라우드 전달 보호 기능은 Microsoft Defender 바이러스 백신을 지원하는 차세대 기술의 일부입니다.</li><li>고급 파일 및 프로세스 동작 모니터링 및 기타추론("실시간 보호"라고도 알려지기)을 사용하여 항상 검사합니다.</li><li>기계 학습, 인간 및 자동화된 대규모 데이터 분석, 심층 위협 저항 연구를 기반으로 하는 전용 보호 업데이트.</li></ul> <p> [자세히 알아보기](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10).|3 |
|ASR(공격 표면 축소)|Microsoft Defender for Endpoint의 공격 표면 감소 기능은 새로운 위협으로부터 조직의 장치 및 응용 프로그램을 보호하는 데 도움이 됩니다. <br> [더 알아보세요.](/windows/security/threat-protection/windows-defender-atp/overview-attack-surface-reduction)|4 |
|자동 조사 & 재구성(AIR)|Microsoft Defender for Endpoint는 자동화된 조사를 사용하여 개별적으로 조사해야 하는 경고의 양을 크게 줄입니다. 자동화된 조사 기능은 다양한 검사 알고리즘과 분석가가 사용하는 프로세스(예: 플레이북)를 활용하여 경고를 검사하고 위반을 해결하기 위해 즉시 수정 조치를 취합니다. 이렇게 하면 경고 수량이 많이 줄어들기 때문에 보안 운영 전문가가 더 복잡한 위협과 기타 높은 가치의 이니셔티브에 집중할 수 있습니다. <p> [더 알아보세요.](/windows/security/threat-protection/windows-defender-atp/automated-investigations-windows-defender-advanced-threat-protection)|해당 없음|
|Microsoft 위협 전문가(MTE)|Microsoft 위협 전문가 센터는 SOC(보안 운영 센터)에 전문가 수준의 모니터링 및 분석을 제공하는 관리되는 헌팅 서비스로, 고유한 환경에서 중요한 위협이 누락되지 않도록 합니다. <p> [더 알아보세요.](/windows/security/threat-protection/windows-defender-atp/microsoft-threat-experts)|해당 없음|

## <a name="next-step"></a>다음 단계

![2단계: 설치.](images/setup.png) <br> [2 단계: 설정](production-deployment.md)

끝점 배포를 위한 Microsoft Defender를 설치합니다.
