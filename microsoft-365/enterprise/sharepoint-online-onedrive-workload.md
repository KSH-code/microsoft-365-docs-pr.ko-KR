---
title: Microsoft 365 Enterprise용 SharePoint 및 OneDrive 배포
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/11/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-collaboration
- Strat_O365_Enterprise
- SPO_Content
ms.custom: ''
description: 조직 전체에서 SharePoint를 계획하고 배포하며 가치를 창출하는 프로세스를 안내합니다.
ms.openlocfilehash: cb0cf16df328d667d796008ac7cabfc98c21ad17
ms.sourcegitcommit: 237589a0c8a24510e5c8f3b8b4747d944ad0afbf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/20/2019
ms.locfileid: "39886325"
---
# <a name="deploy-sharepoint-and-onedrive-for-microsoft-365-enterprise"></a>Microsoft 365 Enterprise용 SharePoint 및 OneDrive 배포

*이 작업은 Microsoft 365 Enterprise E3 및 E5 버전에 모두 포함됩니다.*

SharePoint 및 Microsoft Teams는 사용자가 파일 저장 및 공유, 콘텐츠 관리, 공동 작업을 수행하는 방식이며, Microsoft 365 Enterprise가 제공하는 팀 작업을 위한 Office 제품의 핵심 요소입니다. 

또한 SharePoint는 사용 중이거나 미사용 상태일 때 권한 및 암호화를 사용한 액세스 제어를 포함하는 고급 보안 기능도 제공합니다. SharePoint 보안은 Microsoft 365 Enterprise가 제공하는 지능형 보안 가치에서 핵심적인 요소입니다.

SharePoint를 완전히 처음 사용하는 경우 [SharePoint](https://products.office.com/sharepoint/collaboration) 및 [SharePoint 시작](https://support.office.com/article/video-what-is-sharepoint-online-c17b6824-cc22-478f-8757-497cc6b57121)을 참조하세요.

다음 단계에서는 조직에서 SharePoint 역할을 구상하고, 일련의 점진적 배포를 통해 조직을 온보딩하며, 사용 및 가치를 최종 사용자에게 전달하는 프로세스를 안내합니다. 시작하기 전에 SharePoint 사이트에서 필요한 보안 기능을 갖출 수 있도록 적절한 [기초 인프라](deploy-workloads.md#foundation-infrastructure-prerequisites) 단계를 구성했는지 확인합니다. 

Microsoft 365 Enterprise용 OneDrive를 배포하려면 [기업용 OneDrive 가이드](https://docs.microsoft.com/onedrive/plan-onedrive-enterprise)를 참조하세요.

## <a name="phase-1-envision"></a>1단계: 구상
이 단계에서는 SharePoint 배포를 수행할 조직 파트너를 모집하고 조직이 어떤 방식으로 SharePoint를 사용하여 비즈니스 요구를 해결할지를 결정합니다.

### <a name="step-1-gather-your-sharepoint-deployment-members"></a>1단계: SharePoint 배포 구성원 모집

[Microsoft 365 Enterprise 기본 인프라](deploy-foundation-infrastructure.md)에 SharePoint를 성공적으로 배포하려면 입력 및 피드백을 위해 올바른 구성원을 모아야 합니다. 주요 구성원에는 비즈니스 의사 결정권자, IT 담당자(예: 설계자 및 구현자) 및 최종 사용자의 대변자가 포함됩니다. 

이 세 그룹은 배포 시에 일반적인 사용자들이 비즈니스 요구 사항, 폴더 및 문서 마이그레이션의 기술적 측면, 보안과 관련된 사항을 고려할 수 있도록 합니다.

#### <a name="result"></a>결과

조직의 비즈니스, 기술 및 최종 사용자 측면을 대표하는 구성원 목록을 얻을 수 있습니다.

### <a name="step-2-determine-and-prioritize-your-sharepoint-business-scenarios"></a>2단계: SharePoint 비즈니스 시나리오 확인 및 우선 순위 지정

SharePoint는 다양한 용도로 사용할 수 있습니다. 비즈니스 요구에 해당되는 목적을 파악해야 합니다. SharePoint가 팀, 부서 또는 전체 조직이 갖는 문서 저장과 공유, 콘텐츠 관리, 공동 작업 요구 사항을 해결하는 데 사용되도록 해야 합니다. 

시나리오 및 기능 목록은 [SharePoint](https://products.office.com/sharepoint/collaboration )를 참조하세요.

다음과 같은 비즈니스 핵심 요소로 조직의 요구를 처리할 수 있습니다.

|||
|:-----|:-----|
| 공유 및 공동 작업 | 팀 사이트, 커뮤니케이션 사이트 및 동기화를 활용합니다. |
| 정보 전달 및 소통 | 향후 제공될 정보입니다. |
| 변환 | 플로를 사용하여 앱과 서비스 사이에 자동화된 워크플로를 만듭니다. |
| 집단 지성 활용 | 검색을 사용하여 조직 내에서 원하는 결과를 제공합니다. |
| 보호 | 조직이 안전하게 보호되고 올바른 규정을 준수하는지 확인합니다. |
|||

필요에 맞게 SharePoint를 구성하는 방법에 대한 리소스는 [SharePoint 관리자](https://docs.microsoft.com/sharepoint/sharepoint-online)를 참조하세요.

SharePoint의 이점을 알아보는 한 가지 방법은 개인, 팀, 부서 또는 조직 전체가 현재 상호 작용하는 방식을 검토한 후, 파일을 저장 및 공유하는 보다 쉬운 방법을 제공하는 적절한 시나리오를 찾아보는 것입니다. [Microsoft Teams](teams-workload.md)가 일부 시나리오에 적합한 옵션이 될 수 있다는 점에 유의하세요.

#### <a name="sharepoint-site-for-highly-regulated-data"></a>강도 높은 규제 대상 데이터를 위한 SharePoint 사이트

강도 높은 규제 대상 데이터는 해당 지역 규정이 적용되거나, 영업 비밀, 재무 또는 인사 관련 정보와 조직의 전략과 같이 조직에서 가장 중요한 데이터입니다. 이 유형의 데이터에 대한 제한된 액세스, 데이터 분류, 데이터 손실 방지 및 암호화를 위해 SharePoint 사이트를 구성할 수 있습니다. 자세한 내용은 [높은 규제 대상 데이터용 Microsoft Teams 및 SharePoint 사이트](teams-sharepoint-online-sites-highly-regulated-data.md)를 참조하세요.

#### <a name="result"></a>결과
조직의 문서 저장 및 공유, 콘텐츠 관리, 공동 작업 및 보안에 필요한 사항을 충족하는 SharePoint 시나리오 목록을 얻을 수 있습니다.

## <a name="phase-2-onboard"></a>2단계: 온보딩

이 단계에서는 SharePoint 배포의 기술적 측면을 계획하고 선택한 사용자 그룹에 이를 배포하기 시작합니다.

### <a name="prerequisites-identity-and-device-access-configuration"></a>필수 구성 요소: ID 및 장치 액세스 구성

SharePoint 사이트에 대한 액세스를 보호하려면 [ID 및 장치 액세스 정책](identity-access-policies.md) 및 [권장 SharePoint 액세스 정책](sharepoint-file-access-policies.md)을 구성했는지 확인합니다.

### <a name="step-1-complete-your-technical-planning"></a>1단계: 기술 계획 완료

기술 계획을 시작하기 전에 FastTrack을 사용할지를 결정합니다. 조직에 50개가 넘는 좌석이 있고 [적격 요금제](https://docs.microsoft.com/fasttrack/O365-fasttrack-benefit-for-office-365)에 참여하고 있는 경우, 추가 비용 없이 FastTrack 혜택을 사용하여 계획, 마이그레이션, 배포 및 서비스 도입 방법의 안내를 받을 수 있습니다. 또는 Microsoft 365 계정으로 로그인한 후 [FastTrack](https://docs.microsoft.com/fasttrack/m365-fasttrack-benefit-overview)에서 사용할 수 있는 FastTrack 온보딩 마법사를 사용하여 직접 이 작업을 완료할 수 있습니다.

사용자 고유의 계획을 수행하거나 FastTrack과 연계해서 작업하는 경우, 네트워크 및 조직이 SharePoint를 사용할 준비가 되어 있는지 확인해야 합니다.  특히, SharePoint 기반 문서의 추가 트래픽 성능을 극대화하기 위해 인터넷 대역폭, 처리량 및 트래픽 지연에 중점을 두고 기본 인프라의 [네트워킹에 대한 종료 조건](networking-exit-criteria.md)을 충족해야 합니다.

Sharepoint의 출시를 준비하려면 [Migrate to SharePoint](https://docs.microsoft.com/sharepointmigration/migrate-to-sharepoint-online)을 사용합니다. 

SharePoint의 보안을 보다 잘 이해하려면 다음 리소스를 검토하세요.

-   [SharePoint 및 OneDrive가 클라우드에서 데이터를 보호하는 방법](https://docs.microsoft.com/sharepoint/safeguarding-your-data)
-   [OneDrive 및 SharePoint의 데이터 암호화](https://docs.microsoft.com/microsoft-365/compliance/data-encryption-in-odb-and-spo)

#### <a name="result"></a>결과

SharePoint 사이트 및 온-프레미스 폴더 및 문서 마이그레이션과 보안을 이해하고, 조직의 선택한 그룹에 SharePoint의 배포를 시작할 준비를 갖출 수 있습니다.

### <a name="step-2-run-an-it-pilot"></a>2단계: IT 파일럿 실행

대부분의 중간 규모 및 대규모 조직에서는 1단계의 이해 관계자, 얼리어답터 및 기술 전문가와 함께 IT 파일럿을 실행해야 합니다. IT 파일럿 중에 수행하는 작업은 다음과 같습니다.

- IT 파일럿 참가자가 연습해볼 수 있는 SharePoint 비즈니스 시나리오를 선택합니다.
- 파일럿 참가자들에게 SharePoint 문서 저장, 공유, 공동 작업 및 기타 기능을 테스트할 수 있는 일련의 연습을 제공합니다.
- 변경 관리 전략을 결정하고 SharePoint의 조직 전체 사용자 채택을 관리할 수 있도록 자료를 생성합니다. 변경 관리 자료에는 전자 메일 알림 텍스트, 내부 교육 계획, 복도 포스터 및 프레젠테이션이 포함될 수 있습니다. 이 자료는 SharePoint에 대한 정보 및 인식을 높이고 사용을 추진하는 목표의 장점을 조직에 알려줍니다. 시작하려면 [Sharepoint 도입 리소스](https://resources.techcommunity.microsoft.com/resources/SharePoint-adoption/)를 참조 하세요.
- IT 파일럿 참여자가 자신의 경험을 기반으로 변경 관리 자료를 검토하도록 합니다. 이 참여자들이 모범 사례에 대한 팁과 SharePoint의 이점을 가장 잘 설명할 수 있는 방법과 사용 방법에 대한 유용한 정보를 제공할 수 있습니다.

#### <a name="result"></a>결과

SharePoint IT 파일럿이 완료되고 초기 변경 관리 자료가 개발, 검토 및 구체화되었습니다.

### <a name="step-3-roll-out-to-a-business-group"></a>3단계: 비즈니스 그룹에 배포

IT 파일럿을 완료한 후 조직의 비즈니스 그룹 또는 부서에 SharePoint를 배포합니다. 다음은 배포에 포함된 작업입니다.

- 비즈니스 그룹 내에서 SharePoint에 대한 주요 비즈니스 시나리오 식별.
- 부서, 작업 또는 프로젝트 팀에 SharePoint의 사용에 따른 예상 결과 및 일정을 사용자에게 알리는 공지 활동.
- 비즈니스 그룹 구성원의 온-프레미스 폴더 및 문서를 SharePoint로 마이그레이션.
- SharePoint를 도입하기 위한 사용자 교육 및 리소스 링크와 사용 방법 전달. [SharePoint](https://support.office.com/article/sharepoint-online-video-training-cb8ef501-84db-4427-ac77-ec2009fb8e23) 비디오 교육을 참조하세요.
- 비즈니스 그룹의 사용자로부터 의견을 수집하고 문제에 대해 조치를 취하기 위한 피드백 메커니즘(예: 비즈니스 그룹의 모든 사용자를 포함하는 중앙 Microsoft Teams 팀)
 
롤아웃하는 동안 조직 차원의 롤아웃을 준비하려면 변경 관리 자료를 구체화할 수 있습니다.

#### <a name="result"></a>결과

SharePoint를 통해 비즈니스 그룹이 운영되고 변경 관리 자료가 테스트 및 구체화되었습니다.

## <a name="phase-3-drive-value"></a>3단계: 가치 창출

이 단계에서는 SharePoint 배포를 완료하고 사용자가 이점을 실현하도록 도와줍니다.

### <a name="step-1-roll-out-to-the-rest-of-your-organization"></a>1단계: 조직의 나머지 구성원에게 롤아웃

나머지 조직 구성원에게 롤아웃하는 과정에는 다음이 포함되어야 합니다.

- 분리된 비즈니스 그룹 내에서 SharePoint에 대한 주요 비즈니스 시나리오 식별.
- 구체화된 변경 관리 자료를 사용하여 사용에 따른 예상 결과 및 일정을 조직에 알리는 공지 활동.
- 나머지 조직의 폴더 및 문서를 SharePoint로 마이그레이션.
- SharePoint를 도입하기 위한 사용자 교육 및 리소스 링크와 사용 방법 전달.
- 조직의 사용자로부터 의견 및 문제를 수집하기 위한 피드백 메커니즘(예: 모든 사용자를 포함하는 중앙 팀). 조직의 사용자가 2500명 미만인 경우 Teams의 공개 채널을 사용하고, 2500명 이상인 경우 Yammer의 공용 그룹 사용

#### <a name="result"></a>결과
조직이 운영되며, 사용자에게 알림 및 교육을 제공하고 SharePoint를 사용할 수 있도록 하는 변경 관리 전략이 수립되었습니다.

### <a name="step-2-measure-usage-manage-satisfaction-and-drive-adoption"></a>2단계: 사용 현황 측정, 만족도 관리 및 도입 촉진

전체 조직에 롤아웃한 후에는 변경 관리 전략을 계속 실행하여 다음 수행해야 합니다.

- 경영진이 문서를 저장하고 공유하는 기본 도구로 SharePoint를 사용하도록 장려하게 합니다.
- 사용자가 비즈니스 그룹, 부서, 업무 및 프로젝트 팀 간에 문서를 저장하고 공유하는 데 이를 사용할 수 있도록 장려합니다.

다음은 몇 가지 추천 활동입니다.

- [Office 365의 성공 요인](https://aka.ms/successfactors)을 통해 클라우드 서비스 도입에 대한 일반적인 모범 사례를 살펴봅니다. 
- [Office 365 활동 보고서](https://docs.microsoft.com/office365/admin/activity-reports/activity-reports)를 통해 조직 전체의 Office 365 서비스 사용을 이해합니다. 조직의 Office 365 전역 관리자에게 활동 보고서에 액세스할 수 있도록 사용자 계정에 보고서 읽기 권한자 권한을 부여해 달라고 요청합니다(Office 365 전역 관리자가 아닌 경우).
- SharePoint를 사용한 후 사용자가 제공한 문제와 사용자 의견을 확인하기 위해 사용자 의견 장소(중앙 Teams 팀 또는 Yammer의 공개 채널)을 모니터링합니다. 사용자의 불편을 방지하고 배포에 대한 지원을 보여 주기 위해 질문과 문제를 가능한 한 신속하게 해결합니다.
- 각 비즈니스 그룹에서 챔피언를 식별하고 양성하여 SharePoint를 사용할 때 이들의 성과와 모범 사례를 강조합니다. 조직에 성공을 반영하여 프로젝트 성공 및 도입을 보여줍니다. 비즈니스 그룹 내 기술 리더의 지지는 경영진과 동료에게 강력한 영향을 줄 수 있습니다.

#### <a name="result"></a>결과

조직은 문서 저장 및 공동 작업을 지원하기 위해 Microsoft 365 Enterprise를 채택했습니다.

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Microsoft에서 Microsoft 365 Enterprise를 수행하는 방법

Microsoft 내부 상황을 살펴보고 SharePoint를 배포한 방식을 알아보려면 [SharePoint를 클라우드로: Microsoft가 자체 마이그레이션을 수행한 방법 알아보기](https://www.microsoft.com/itshowcase/sharepoint-to-the-cloud-learn-how-microsoft-ran-its-own-migration)를 참조하세요.

## <a name="next-steps"></a>다음 단계

SharePoint의 지속적인 유지 관리에 대한 다음 리소스를 참조하세요. 

- [SharePoint의 권한 수준 이해](https://docs.microsoft.com/sharepoint/understanding-permission-levels)
- [SharePoint 사이트 사용 권한 사용자 지정](https://docs.microsoft.com/sharepoint/customize-sharepoint-site-permissions)
- [SharePoint의 외부 공유 설정 또는 해제](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off)
- [액세스 요청 설정 및 관리](https://support.office.com/article/Set-up-and-manage-access-requests-94B26E0B-2822-49D4-929A-8455698654B3)
