---
title: Microsoft 365를 사용하여 안전한 공동 작업 설정
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365solution-securecollab
- m365solution-overview
ms.custom:
- M365solutions
- seo-marvel-jun2020
f1.keywords: NOCSH
recommendations: false
description: 민감도에 따라 데이터를 보호하기 위해 Teams 콘텐츠 공동 작업을 설정하는 방법을 알아보겠습니다.
ms.openlocfilehash: f8475cd2f832bf2b634a8e60c819927fb8f2769c
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60158997"
---
# <a name="set-up-secure-collaboration-with-microsoft-365-and-microsoft-teams"></a>보안 및 보안 Microsoft 365 설정 Microsoft Teams

과부하를 방지하면서 올바른 사용자와 정보를 쉽게 공유할 수 있는 것은 조직의 성공에 핵심입니다. 여기에는 중요한 데이터를 액세스 권한이 있는 사용자와만 안전하게 공유할 수 있습니다. 프로젝트에 따라 조직 외부의 사용자와 중요한 데이터를 공유하는 것이 포함됩니다.

이 공동 작업 솔루션 지침에는 다음 두 가지 구성 요소가 포함되어 있습니다.

- 각 Microsoft Teams 대한 올바른 수준의 보호를 통해 배포
- 각 프로젝트에 대해 적절한 보안 설정을 사용하여 외부 공유 구성

![적절한 Teams 사용하여 보안 설정을 배포하고 적절한 보안 설정을 사용하여 외부 공유를 구성합니다.](..\media\solutions-architecture-center\secure-collaboration-overview.png)

다용도 및 사용이 간편한 콘텐츠 공동 작업 도구를 사용할 수 없는 경우 사용자는 문서를 전자 메일로 보내 공동 작업을 하는 경우가 종종 있습니다. 이는 공동 작업의 지우고 오류가 발생할 수 있는 방법일 수 있으며 부적절한 정보 공유의 위험을 증가할 수 있습니다. 정보 공유가 너무 어렵다는 것을 발견하면 IT에서 관리하지 않는 소비자 제품을 사용하게 되찾을 수 있습니다. 이로인하면 위험이 훨씬 커질 수 있습니다.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWxMmL?autoplay=false]

이 Microsoft 365 사용하여 다음을 Teams 구성을 사용하여 배포할 수 있습니다.

- 지적 재산 보호
- 간편한 공동 작업 사용
- 보안과 사용성 간의 균형을 유지하여 사용자 만족도를 향상하고 섀도 IT의 위험을 줄입니다.

대부분의 조직에서는 정보가 부적절하게 공유되는 경우 민감도 및 비즈니스 영향 정도가 다양하며 다양한 정보를 제공합니다. 특정 정보의 민감도에 따라 다음과의 공유를 허용할 수 있습니다.

- 모든 사람(비인식)
- 조직 내부 사용자
- 조직 내부의 특정 사용자
- 조직 내부 및 외부의 특정 사용자

마케팅 브로셔와 같은 정보는 조직 외부에서 광범위하게 공유하기 위한 것입니다. 카페테리아 메뉴와 같은 정보는 외부 공유를 위한 것이 아니라 외부에서 공유된 경우 비즈니스에 영향을 줄 수 없습니다. 이러한 유형의 정보는 보호가 거의 또는 필요하지 않습니다.

개발 중에는 조직 내에서만 동일한 마케팅 브로셔를 공유할 수 있습니다. 이 경우 기본 공유 설정은 Teams 수 있습니다.

개발 중인 새 제품에 대한 정보는 조직 내에서도 중요한 것으로 간주될 수 있습니다. 이 경우 더 높은 수준의 보호가 적절할 수 있습니다. 예를 들어 이 정보에 대한 액세스를 특정 팀의 구성원으로 제한할 수 있습니다. 프로젝트에 따라 공급업체 또는 파트너 조직과 같이 조직 외부의 사용자와 공동 작업을 해야 할 수 있습니다.

조직의 성공에 중요하거나 엄격한 보안 또는 규정 준수 요구 사항이 있는 정보는 훨씬 더 높은 수준의 보호가 필요할 수 있습니다.

![위험 규모는 낮음(릴리스된 브로셔)에서 높은(중요한 비즈니스 데이터)로 확장됩니다.](../media/solutions-architecture-center/SecureCollaboration-SensitivityAndBusinessImpactofSharing-fromVisio.png)

위에서 설명한 모든 시나리오에 대해 팀을 사용하여 정보를 Microsoft Teams, 공유 및 공동 작업을 할 수 있습니다.

보안 공동 작업을 구성하기 위해 이러한 Microsoft 365 기능을 사용하게 합니다.

|제품 또는 구성 요소|기능 또는 특징|라이선싱|
|---|---|---|
|Office 365용 Microsoft Defender|금고 SPO, OneDrive 및 Teams; 금고 문서; 금고 Teams|Microsoft 365 E1, E3 및 E5|
|SharePoint|사이트 및 파일 공유 정책, 사이트 공유 권한, 공유 링크, 액세스 요청, 사이트 게스트 공유 설정|Microsoft 365 E1, E3 및 E5|
|Microsoft Teams|게스트 액세스, 비공개 팀, 비공개 채널|Microsoft 365 E1, E3 및 E5|
|Microsoft 365 규정 준수|민감도 레이블|Microsoft 365 E3 및 E5|

## <a name="collaboration-governance"></a>공동 작업 거버넌스

Microsoft 365 솔루션을 관리하기 위한 다양한 옵션을 제공합니다. 이 배포 콘텐츠를 공동 작업 [](collaboration-governance-overview.md) 거버넌스 콘텐츠와 함께 사용하여 조직에 가장 적합한 공동 작업 솔루션을 만드는 것이 좋습니다.

### <a name="using-teams-for-all-kinds-of-data"></a>모든 Teams 대한 사용자 정보 사용

민감도가 다른 정보에 대한 액세스를 관리하기 위해 에 대한 세 가지 다른 보호 [계층을 Teams.](configure-teams-three-tiers-protection.md) 이러한 계층을 사용자 지정하여 요구 또는 비즈니스를 보다 잘 해결할 수 있습니다.

![사용자에 대한 세 가지 보호 Teams.](../media/solutions-architecture-center/Teams-tiers-of-protection-1.png)

이러한 *계층(기준,* *중요* 및  매우 중요)은 다음 표와 같이 과도하게 공유 및 잠재적인 정보 누출을 방지하는 데 도움이 되는 보호 기능을 점진적으로 늘려나가고 있습니다.

|-|기준 계층|중요 계층|매우 중요한 계층|
|---|---|---|---|
|공개 또는 비공개 팀|둘 중 하나|개인|개인|
|인증되지 않은 공유|차단됨|차단됨|차단됨|
|파일 공유|허용됨|허용됨|팀 소유자만 공유할 수 있습니다.|
|팀 구성원|누구나 공개 팀에 참가할 수 있습니다.<br>비공개 팀에 참가하는 데 팀 소유자 승인이 필요합니다.|팀 소유자 승인에 참여해야 합니다.|팀 소유자 승인에 참여해야 합니다.|
|문서 암호화|||민감도 레이블과 함께 사용 가능|
|게스트 공유|허용됨|허용 또는 차단할 수 있습니다.|허용 또는 차단할 수 있습니다.|
|관리되지 않는 장치|제한 없음|웹 전용 액세스|차단됨|

이러한 계층을 구성하는 과정에는 다음이 수반됩니다.

- 게스트 액세스 및 Teams 채널에 대한 설정 구성
- 팀의 연결된 SharePoint 공유, 액세스 요청 및 공유 링크에 대한 설정 구성
- 중요하고  매우  중요한 계층의 경우 팀을 분류하고, 관리되지 않는 장치에서 게스트 공유 및 액세스를 제어하기 위해 민감도 레이블을 구성합니다.
- 매우 *중요한* 계층의 경우 민감도 레이블을 구성하여 해당 계층이 적용되는 문서를 암호화합니다.

기준 계층으로 시작한 다음, 필요한 경우  중요하고 매우 중요한 계층을 사용하여 조직의 정보를 보호하는 팀을 추가합니다.  시작을 위해 다음 리소스를 참조합니다.

- [기본 보호 기능으로 팀 구성](configure-teams-baseline-protection.md)
- [중요한 데이터를 보호하는 팀 구성하기](configure-teams-sensitive-protection.md)
- [매우 중요한 데이터를 보호하는 팀 구성하기](configure-teams-highly-sensitive-protection.md)

조직 내에서도 공유로부터 추가 보호가 필요한 매우 중요한 프로젝트가 있는 경우 팀 구성원만 읽을 수 있도록 자체 민감도 레이블을 사용하여 파일을 암호화하는 팀을 구성할 수 있습니다. 자세한 [내용은 보안으로 팀 구성을](secure-teams-security-isolation.md) 참조합니다.

### <a name="sharing-with-people-outside-your-organization"></a>조직 외부의 사용자와 공유

조직 외부의 사용자와 민감도 정보를 [공유해야 할 수 있습니다.](collaborate-with-people-outside-your-organization.md) 단일 사용자와 단일 문서를 공유하는 것부터 대규모 파트너 조직 또는 전 세계의 프리랜서와 주요 프로젝트 공동 작업까지 다양한 작업을 할 수 있습니다. 이 Microsoft 365 중요한 정보를 보호하는 데 도움이 되는 적절한 보호책을 사용하여 이 범위의 외부 공유를 쉽게 할 수 있습니다.

이러한 리소스는 조직 외부의 사용자와 공동 작업을 위한 환경을 설정하는 데 도움이 됩니다.

- [개별 폴더 파일을](collaborate-on-documents.md) 공유하기 위해 문서에 대해 공동 작업을 합니다.
- [사이트 내](collaborate-in-site.md) 게스트와 공동 작업을 할 수 있는 사이트에서 공동 작업을 SharePoint 있습니다.
- [팀에서](collaborate-as-team.md) 게스트와 공동 작업을 할 수 있는 팀으로 공동 작업을 합니다.

공유되는 정보의 민감도에 따라 과도하게 공유되지 않도록 보호 장치를 추가할 수 있습니다. 이러한 리소스는 조직에 필요한 보호를 설정하는 데 도움이 됩니다.

- [인증되지 않은 사용자와 파일 및 폴더를 공유하는 최우수 사례](best-practices-anonymous-sharing.md)
- [파일을 조직 외부의 사람들과 공유할 때 실수로 발생하는 정보 노출 제한하기](share-limit-accidental-exposure.md)
- [보안 게스트 공유 환경 만들기](create-secure-guest-sharing-environment.md)

파트너 조직과 함께 주요 프로젝트가 있는 경우 Azure 권리 관리 를 사용하여 프로젝트에 대해 설정한 팀에서 해당 조직의 게스트를 관리할 수 있습니다. 자세한 [내용은 관리되는 게스트를 사용하여 B2B 엑스트라넷](b2b-extranet.md) 만들기를 참조합니다.

## <a name="training-for-administrators"></a>관리자 교육

Microsoft Learn의 이러한 교육 모듈은 사용자 및 서비스에서 공동 작업, 거버넌스 및 ID 기능을 Teams SharePoint.

### <a name="teams"></a>Teams

|교육:|Microsoft 팀과 팀 공동 작업 관리|
|---|---|
|![Teams 교육 아이콘입니다.](../media/manage-team-collaboration-with-microsoft-teams.svg)|Microsoft 팀과 팀 공동 작업 관리는 microsoft 365에서 팀 공동 작업을 위한 중앙 허브인 Microsoft 팀의 기능을 소개 합니다. 팀을 사용하여 조직의 팀워크와 커뮤니케이션을 촉진하는 방법에 대해 배워보겠습니다. Office 365의 다양한 기능을 활용하는 동시에 다양한 장치 데스크톱 그리고 태블릿에서 휴대폰까지 온-프레미스와 오프-프레미스 모두에 대해 알아보겠습니다. 응용 프로그램 및 장치 전반에 걸쳐 팀이 공동 작업에 어떻게 포괄적이고 융통성있는 환경을 제공 하는지 이해하게 될 것입니다. 이 학습 경로를 통해 Microsoft 365 인증: Teams 관리자 학위 인증서 준비를 할 수 있습니다.<p>2시간 17분 - Learning 경로 - 5개 모듈|

> [!div class="nextstepaction"]
> [시작 >](/learn/modules/m365-teams-collab-prepare-deployment/introduction/)

### <a name="sharepoint"></a>SharePoint

|교육:|Microsoft 365에서 SharePoint를 이용한 공동 작업|
|---|---|
|![SharePoint 아이콘입니다.](../media/collaborate-with-sharepoint-in-microsoft-365.svg)|Microsoft SharePoint를 사용하여 공유 콘텐츠를 관리함으로서 SharePoint의 기능 및 특성 그리고 Microsoft 365에서 작동하는 방식에 대해 알게됩니다. 허브 사이트, 정보 보호, 보고, 모니터링을 비롯 한 다양한 유형의 SharePoint 사이트에 대해 배우게 될 것입니다. 또한 SharePoint 파일 및 폴더 공유를 활용하여 공동 작업을 최적화 하는 방법, 외부로 파일을 공유하는 방법 그리고 SharePoint 관리 센터에서 SharePoint 사이트를 관리하는 방법에 대해 배우게 될 것입니다. 이 학습 경로를 통해 Microsoft 365 인증: 팀워크 관리자 학위 인증서 준비를 할 수 있습니다.<p>1시간 14분 - Learning 경로 - 4개 모듈|

> [!div class="nextstepaction"]
> [시작 >](/learn/modules/m365-teams-sharepoint-plan-sharepoint/introduction/)

### <a name="information-protection"></a>정보 보호

|교육:|Microsoft 365를 사용하여 엔터프라이즈 정보 보호|
|---|---|
|![Teams 보호 교육 아이콘입니다.](../media/protect-enterprise-information-microsoft-365.svg)|조직의 정보를 보호하고 보안을 유지하는 것이 어느 때보다 어려워졌습니다. Microsoft 365로 엔터프라이즈 정보 보호 학습 경로는 우발적인 과도한 공유 또는 오용으로부터 중요한 정보를 보호하는 방법, 데이터를 검색하고 분류하는 방법, 민감도 레이블을 사용하여 중요한 정보를 보호하는 방법 및 중요한 정보가 손실되지 않도록 보호하기 위해 모니터링하고 분석하는 방법에 대해 설명합니다. 이 학습 경로를 통해 인증된 Microsoft 365: 보안 관리자 연결 및 인증: Microsoft 365 인증: 관리 전문가 인증을 Enterprise 수 있습니다.<p>1 hr - Learning 경로 - 5개 모듈|

> [!div class="nextstepaction"]
> [시작 >](/learn/modules/m365-security-info-overview/introduction/)

### <a name="identity-and-access"></a>ID 및 액세스

|교육:|Azure Active Directory로 ID 및 엑세스 권한 보호|
|---|---|
|![ID 및 액세스 교육 아이콘.](../media/protect-identity-and-access-with-microsoft-365.svg)|ID 및 Access 학습 경로에는 최신 ID 및 액세스 기술, 인증 강화 도구 및 조직 내 ID 보호에 대한 지침이 포함되어 있습니다. Microsoft의 액세스 및 ID 기술을 사용하면 온-프레미스 또는 클라우드에 있는 조직의 ID를 보호할 수 있으며, 사용자가 어느 위치에서나 안전하게 작업하도록 할 수 있습니다. 이 학습 경로를 통해 Microsoft 365 인증: 보안 관리자 학위 및 Microsoft 365 인증: 엔터프라이즈 관리 전문가 인증서를 준비할 수 있습니다.<p>2시간 52분 - Learning 경로 - 6개 모듈|

> [!div class="nextstepaction"]
> [시작 >](/learn/modules/m365-identity-overview/introduction/)

## <a name="training-for-end-users"></a>최종 사용자를 위한 교육

이러한 교육 모듈은 사용자가 사용자들이 Teams, 그룹 및 SharePoint 사용하여 공동 작업을 하는 데 도움이 Microsoft 365.

|Teams|SharePoint|
|---|---|
|![팀 교육 아이콘을 설정하고 사용자 지정합니다.](../media/set-up-customize-team-training.png)<br>**[팀 설정 및 사용자 지정](https://support.microsoft.com/office/702a2977-e662-4038-bef5-bdf8ee47b17b)**|![SharePoint 공유 및 동기화 교육 아이콘](../media/sharepoint-share-sync-training.png)<br>**[공유 및 동기화](https://support.microsoft.com/office/98cb2ff2-c27e-42ea-b055-c2d895f8a5de)**|
|![Teams 파일 교육 아이콘을 업로드하고 찾을 수 있습니다.](../media/smc-teams-upload-find-files-training.png)<br>**[업로드 파일 찾기](https://support.microsoft.com/office/57b669db-678e-424e-b0a0-15d19215cb12)**||
|![팀 및 채널 아이콘으로 공동 작업합니다.](../media/teams-collaborate-channels-training.png)<br>**[팀 및 채널에서 공동 작업](https://support.microsoft.com/office/c3d63c10-77d5-4204-a566-53ddcf723b46)**||

## <a name="illustrations"></a>그림

다음 그림은 그룹 및 팀이 조직의 다른 서비스와 상호 작용하는 방법과 Microsoft 365 조직에서 이러한 서비스를 관리하는 데 도움이 되는 거버넌스 및 규정 준수 기능을 이해하는 데 도움이 됩니다.

### <a name="groups-in-microsoft-365-for-it-architects"></a>IT 설계자용 Microsoft 365의 그룹

IT 설계자가 Microsoft 365의 그룹에 대해 알아야 하는 점

|**항목**|**설명**|
|---|---|
|[![그룹 정보 그래픽의 축소판 이미지입니다.](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) <br/> [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx) <br> 2019년 6월에 업데이트됨|이러한 일러스트레이션은 다양한 그룹의 종류, 그룹을 만들고 관리하는 방법, 몇 가지 관리 권장 사항에 대해 자세한 설명을 제공합니다.|

### <a name="microsoft-teams-and-related-productivity-services-in-microsoft-365-for-it-architects"></a>IT 설계자용 Microsoft 365의 Microsoft Teams 및 관련 생산성 서비스

Microsoft Teams로 시장을 선도하는 Microsoft 365 생산성 서비스의 논리적 아키텍처입니다.

|**항목**|**설명**|
|---|---|
|[![논리 아키텍처 Teams 포스터의 축소판 이미지입니다.](../downloads/msft-teams-logical-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-teams-logical-architecture.pdf) <br/> [PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-teams-logical-architecture.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-teams-logical-architecture.vsdx)  <br>2019년 4월에 업데이트됨|Microsoft는 생산성 서비스 제품군을 제공하여 데이터 관리, 보안 및 규정 준수 기능이 포함된 공동 작업 환경을 제공합니다. <p>이 일러스트레이션 시리즈는 엔터프라이즈 설계자를 위해 Microsoft Teams로 시장을 선도하는 생산성 서비스의 논리 아키텍처를 보여줍니다.|

## <a name="deploy-the-secure-collaboration-solution"></a>보안 공동 작업 솔루션 배포

이 솔루션을 배포할 준비가 되면 다음 단계를 계속 진행합니다.

1. 에 대한 세 가지 서로 다른 보호 [계층을 Teams.](configure-teams-three-tiers-protection.md)
2. 조직 외부의 사용자와 민감도 [정보를 공유하기 위한 설정을 구성합니다.](collaborate-with-people-outside-your-organization.md)

## <a name="see-also"></a>참고 항목

[Microsoft 365 보안 설명서](../security/index.yml)

[Microsoft 365 규정 준수 설명서](../compliance/index.yml)

[Microsoft Teams에 오신 것을 환영합니다.](/MicrosoftTeams/Teams-overview)
