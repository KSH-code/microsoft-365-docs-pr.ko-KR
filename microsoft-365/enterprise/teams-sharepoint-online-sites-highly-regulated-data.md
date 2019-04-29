---
title: 높은 규제 대상 데이터에 대한 Microsoft Teams 및 SharePoint Online 사이트
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 04/03/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: 보안 SharePoint Online 팀 사이트 및 Microsoft Teams 팀을 만들어 가장 소중하고 중요한 디지털 자산을 저장합니다.
ms.openlocfilehash: 4342ba5e5d1c83ed0c9d26100afd86afa1e62723
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289809"
---
# <a name="microsoft-teams-and-sharepoint-online-sites-for-highly-regulated-data"></a>높은 규제 대상 데이터에 대한 Microsoft Teams 및 SharePoint Online 사이트

*이 시나리오는 Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*

Microsoft 365 Enterprise에는 높은 규제 대상 데이터를 만들고, 저장하고, 보안을 유지할 수 있도록 하기 위해 전체 클라우드 기반 서비스 제품군이 포함되어 있습니다. 여기에는 다음과 같은 데이터가 포함됩니다.

- 지역 규제를 받는 데이터
- 영업 비밀, 재무 또는 인사 관련 정보와 조직의 전략과 같이 조직에서 가장 중요한 데이터

이러한 비즈니스 요구를 충족하는 Microsoft 365 Enterprise에서는 다음을 요구합니다.

- 디지털 자산(문서, 슬라이드 데크, 스프레드시트 등)을 SharePoint Online 팀 사이트 또는 Microsoft Teams 팀의 **파일** 탭에 저장해야 합니다.
- 사이트 또는 팀의 다음 작업이 방지됩니다.
   - 그룹 멤버 자격을 통해 특정 사용자 계정 집합에만 액세스할 수 있습니다. 특정 사용자 계정 집합에는 임의 권한 수준에서 SharePoint Online 팀 사이트에 액세스할 수 있는 사용자 계정 및 해당 사이트를 관리할 수 있는 사용자 계정이 포함됩니다.
   - 사이트의 멤버가 다른 사람에게 액세스 권한을 부여할 수 없습니다.
   - 사이트의 멤버 이외의 사용자가 다른 사람에게 액세스 권한을 요청할 수 없습니다.
- SharePoint Online 사이트 또는 팀에 대한 Office 365 보존 레이블을 사이트 또는 팀에 있는 문서에 대한 보존 정책을 정의하는 기본 방법으로 구성합니다.
- 사용자가 조직 외부로 파일을 보내지 못하도록 차단합니다.
- 사이트 또는 팀의 가장 중요한 디지털 자산을 암호화합니다.
- 사이트 외부에서 공유되더라도 자산을 열기 위해서는 권한이 있는 사용자 계정의 유효한 자격 증명을 요구하도록 가장 중요한 디지털 자산에 대한 권한을 추가합니다.

다음 표에서는 이러한 솔루션의 요구 사항과 해당하는 Microsoft 365 Enterprise의 기능을 연결해서 보여 줍니다.

|||
|:-------|:-----|
| **요구 사항** | **Microsoft 365 Enterprise 기능** |
| 디지털 자산 저장 | SharePoint Online 팀 사이트 및 Office 365의 팀 |
| 사이트 잠그기 | Azure AD 그룹 및 SharePoint Online 팀 사이트 사용 권한 |
| 사이트의 디지털 자산에 레이블 지정 | Office 365 보존 레이블 |
| 사용자가 조직 외부로 파일을 보내지 못하도록 차단 | Office 365의 DLP(데이터 손실 방지) 정책 |
| 사이트의 모든 디지털 자산 암호화 | EMS(Enterprise Mobility + Security)의 Azure Information Protection 하위 레이블 |
| 사이트의 디지털 자산에 대한 권한 추가 | EMS의 Azure Information Protection 하위 레이블 |
|||

이 솔루션을 사용하려면 다음을 배포했어야 합니다.

- 기본 인프라의 [ID](identity-infrastructure.md) 단계 및 [정보 보호](infoprotect-infrastructure.md) 단계의 1-2단계 
- SharePoint Online 팀 사이트에 있는 높은 규제 대상 데이터의 경우 [SharePoint Online](sharepoint-online-onedrive-workload.md)
- Microsoft Teams 팀에 있는 높은 규제 대상 데이터의 경우 [Microsoft Teams](teams-workload.md)

다음 단계에서는 높은 규제 대상 데이터에 대한 SharePoint Online 사이트 및 팀의 디자인 및 구성 작업과 채택을 유도하는 과정을 안내합니다.

가상의 대표적인 다국적 기업인 Contoso Corporation에서 연구팀을 위해 SharePoint Online 사이트를 설계한 방법을 보려면 이 [예제 구성](contoso-sharepoint-online-site-for-highly-confidential-assets.md)을 참조하세요.

>[!Note]
>높은 규제 대상 데이터에 대한 팀을 사용하려면 먼저 높은 규제 대상 데이터에 대한 SharePoint Online 팀 사이트를 만들어야 합니다. 그런 후 SharePoint Online 팀 사이트의 Office 365 그룹을 사용하는 새 팀을 만듭니다. 자세한 내용은 두 번째 작업 단계, 4단계를 참조하세요.
>

## <a name="identity-and-device-access-prerequisites"></a>ID 및 장치 액세스 필수 구성 요소

팀 또는 SharePoint Online 사이트에 대한 액세스를 보호하려면 [ID 및 장치 액세스 정책](identity-access-policies.md) 및 [권장 SharePoint Online 액세스 정책](sharepoint-file-access-policies.md)을 구성했는지 확인합니다.

## <a name="phase-1-design"></a>첫 번째 작업 단계: 디자인

높은 규제 대상 데이터에 대한 SharePoint Online 사이트 또는 팀을 만들려면 먼저 해당 용도를 식별해야 합니다. 예를 들어, 제조 회사의 연구/개발 부서에는 기존 제품의 최신 디자인 사양을 저장하기 위한 SharePoint Online 사이트와 신제품에 대해 공동 작업을 진행할 장소가 필요합니다. 연구/개발 부서의 구성원과 선택한 임원만 해당 사이트에 액세스할 수 있습니다.

그 용도는 다음과 같은 필수 구성 항목을 파악하는 것입니다.

- SharePoint Online 권한 집합 및 SharePoint 그룹 집합
- 액세스 그룹 집합, Azure AD 보안 그룹 및 SharePoint 그룹에 추가할 구성원
- 사이트에 할당할 Office 365 보존 레이블 및 레이블에 대한 DLP 정책 집합
- 사용자가 사이트에 저장된 높은 규제 대상 디지털 자산에 적용하는 Azure Information Protection 하위 레이블에 대한 설정

일단 결정이 끝나면 이러한 설정을 사용하여 두 번째 작업 단계에서 사이트를 구성합니다. 

### <a name="step-1-an-isolated-sharepoint-online-site"></a>1단계: 격리된 SharePoint Online 사이트

SharePoint Online 팀 사이트의 잠긴 버전을 격리된 사이트라고 합니다. 비공개 팀 사이트의 기본 설정과 달리, 격리된 사이트는 다음을 방지하도록 구성됩니다.

- 지정된 그룹의 구성원이 아닌 사용자에게 액세스 권한 부여
- 액세스 요청
- 지정된 그룹의 현재 구성원이 무단으로 액세스 권한 부여
- 액세스 그룹 구성원에 의한 사이트 관리

높은 규제 대상 자산을 포함하는 SharePoint Online 팀 사이트의 보안은 사이트의 SharePoint 관리자가 아니면 변경할 수 없습니다.

권한 수준, SharePoint 그룹, 액세스 그룹 및 그룹 구성원 집합 결정에 대한 자세한 내용은 [격리된 SharePoint Online 팀 사이트 디자인](https://docs.microsoft.com/office365/enterprise/design-an-isolated-sharepoint-online-team-site)을 참조하세요.

### <a name="step-2-office-365-retention-labels-and-dlp-policies"></a>2단계: Office 365 보존 레이블 및 DLP 정책

SharePoint Online 팀 사이트에 적용된 Office 365 보존 레이블은 사이트에 저장된 모든 디지털 자산에 대한 기본 분류 방법입니다.
 
높은 규제 대상 데이터에 대한 SharePoint Online 사이트에서는 사용할 Office 보존 365 레이블을 결정해야 합니다.

Office 365 레이블의 디자인 고려 사항에 대해서는 [Office 365 분류 및 레이블](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels)을 참조하세요.

중요한 정보를 보호하고 우발적이거나 의도적인 노출을 방지하려면 DLP 정책을 사용합니다. 자세한 내용은 이 [개요](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies)를 참조하세요.

높은 규제 대상 데이터에 대한 SharePoint Online 사이트의 경우, 사용자가 외부 사용자와 디지털 자산을 공유하려고 할 때 사용자를 차단하도록 사이트에 할당된 Office 365 보존 레이블에 대한 DLP 정책을 구성해야 합니다. 

### <a name="step-3-your-azure-information-protection-sub-label"></a>3단계: Azure Information Protection 하위 레이블

가장 중요한 디지털 자산에 암호화 및 권한 집합을 제공하기 위해 사용자는 Azure Information Protection 클라이언트를 사용하여 Azure Information Protection 레이블을 적용해야 합니다. 높은 규제 대상 데이터에 대한 SharePoint Online 사이트에 Azure Information Protection 레이블을 사용하려면 범위가 지정된 정책에서 Azure Information Protection 하위 레이블을 구성해야 합니다. 

하위 레이블은 기존 레이블 아래에 있습니다. 예를 들어 극비 레이블 아래에는 연구/개발 하위 레이블을 만들 수 있습니다. 범위가 지정된 정책은 사용자 하위 집합에만 적용되는 정책입니다. 높은 규제 대상 데이터에 대한 SharePoint Online 사이트에서는 해당 범위가 사이트의 액세스 그룹 구성원인 사용자 집합입니다.

적용된 하위 레이블 설정은 자산을 따라 이동합니다. 사이트 외부에서 다운로드되고 공유되더라도, 권한이 있는 인증된 사용자 계정만 해당 자산을 열 수 있습니다.

### <a name="design-results"></a>디자인 결과

다음 사항이 결정되었습니다.

- SharePoint 그룹 및 권한 수준 집합
- 액세스 그룹 집합 및 각 권한 수준의 구성원
- 해당 Office 365 보존 레이블 및 레이블과 연결된 DLP 정책
- 암호화 및 권한을 포함하는 Azure Information Protection 하위 레이블 설정

## <a name="phase-2-configure"></a>두 번째 작업 단계: 구성

두 번째 작업 단계에서는 첫 번째 작업 단계에서 결정한 설정을 구현하여 높은 규제 대상 데이터에 대한 SharePoint Online 사이트를 만듭니다.

### <a name="step-1-create-and-configure-an-isolated-sharepoint-online-team-site"></a>1단계: 격리된 SharePoint Online 팀 사이트 만들기 및 구성

[격리된 SharePoint Online 팀 사이트 배포](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site)의 지침에 따라 다음을 수행합니다.

- 사이트에서 사용되는 각 SharePoint 권한 수준에 대한 액세스 그룹을 만들고 채웁니다.
- 격리된 팀 사이트를 만들고 구성합니다.

### <a name="step-2-configure-the-site-for-an-office-365-retention-label-dlp-policy"></a>2단계: Office 365 보존 레이블 DLP 정책에 맞게 사이트 구성

[Office 365 레이블 및 DLP를 사용하여 SharePoint Online 파일 보호](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp)의 지침에 따라 다음을 수행합니다.

- Office 365 보존 레이블을 식별하거나 만든 후 격리된 SharePoint Online 사이트에 적용합니다.
- 조직 외부의 SharePoint Online 사이트에서 디지털 자산을 공유하려고 할 경우 사용자를 차단하는 DLP 정책을 만들고 구성합니다.

### <a name="step-3-create-an-azure-information-protection-sub-label-for-the-site"></a>3단계: 사이트에 대한 Azure Information Protection 하위 레이블 만들기

[Azure Information Protection을 사용한 SharePoint Online 파일 보호](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection)의 지침에 따라 다음을 수행합니다. 

- 범위가 지정된 정책에서 Azure Information Protection 하위 레이블을 만들고 구성합니다.
- 사용자 컴퓨터에 Azure Information Protection 클라이언트를 배포합니다.

### <a name="step-4-optional-create-a-team-for-the-highly-regulated-data"></a>4단계(선택 사항): 높은 규제 대상 데이터에 대한 팀 만들기

높은 규제 대상 데이터에 대한 팀을 원하는 경우 먼저 높은 규제 대상 데이터에 대한 SharePoint Online 사이트를 만듭니다. 초기 비공개 SharePoint Online 팀 사이트를 만들 때 Office 365 그룹 이름을 지정합니다.

높은 규제 대상 데이터에 대한 SharePoint Online 사이트가 완전히 구성되면 다음 단계에 따라 높은 규제 대상 데이터에 대한 팀으로 변환합니다.

1. Office 365에 로그인합니다.
2. **Microsoft Office 홈** 탭에서 **Teams**를 클릭합니다.
3. **Microsoft Teams** 탭의 **팀 가입 또는 팀 만들기** 창에서 **팀 만들기**를 클릭합니다.
4. **팀 만들기** 창에서 **기존 Office 365 그룹에서 팀 만들기**를 클릭합니다.
5. Office 365 그룹 목록에서 높은 규제 대상 데이터에 대한 SharePoint Online 사이트에 해당하는 Office 365 그룹의 이름을 선택한 후 **팀 선택**을 클릭합니다.

새 팀의 **파일** 탭에는 해당 SharePoint Online 사이트의 **문서** 영역에 있는 **일반** 폴더의 내용이 표시됩니다. 팀에 대한 SharePoint Online 사이트의 나머지 리소스를 보려면 줄임표를 클릭하고 **SharePoint에서 열기**를 클릭합니다.

### <a name="configuration-results"></a>구성 결과

구성한 항목

- 격리된 SharePoint Online 사이트
- 격리된 SharePoint Online 사이트에 Office 365 보존 레이블 할당
- Office 365 보존 레이블에 대한 DLP 정책
- 사이트에 저장되어 있으며 자산을 암호화하고 권한을 적용하는 가장 중요한 디지털 자산에 사용자가 적용할 수 있는 범위 지정 정책에 대한 Azure Information Protection 하위 레이블
- 필요한 경우, SharePoint Online 사이트를 기준으로 하는 높은 규제 대상 데이터용 팀

## <a name="phase-3-drive-user-adoption"></a>3단계: 사용자 채택 주도

높은 규제 대상 데이터에 대한 SharePoint Online 사이트 또는 팀은 중요한 디지털 자산의 저장 및 액세스에 일관되게 사용되는 경우에만 해당 데이터를 보호할 수 있습니다. 이 단계에서는 사용자가 방식을 변경할 수 있으므로 가장 까다로운 단계에 해당합니다. 

예를 들어 USB 드라이브 또는 개인 클라우드 기반 저장소 솔루션에 중요한 데이터를 저장하던 임원이 이제는 해당 데이터를 높은 규제 대상 데이터에 대한 SharePoint Online 사이트 또는 팀에만 독점적으로 저장해야 합니다.

### <a name="step-1-train-your-users"></a>1단계: 사용자 교육

구성을 완료한 후 사이트 액세스 그룹의 구성원인 사용자 집합에게 다음을 교육합니다.

- 새 사이트 또는 팀을 사용한 귀중한 자산 보호의 중요성과 높은 규제 대상 데이터가 누출되었을 때의 결과(예: 법적 효과, 규제 벌금, 랜섬웨어 또는 경쟁적 우위 박탈)
- 사이트 및 해당 자산에 액세스하는 방법
- 사이트에서 새 파일을 만들고 로컬에 저장된 새 파일을 업로드하는 방법
- DLP 정책으로 외부에서 파일을 공유하지 못하도록 차단하는 방법
- Azure Information Protection 클라이언트를 사용하여 하위 레이블이 구성된 가장 중요한 디지털 자산에 레이블을 지정하는 방법
- 사이트 또는 팀에서 누출된 자산을 Azure Information Protection 하위 레이블을 통해 보호하는 방법

이 교육에는 사용자가 이러한 작업 및 해당 결과를 경험해볼 수 있도록 하기 위해 실무 위주의 연습이 포함되어 있습니다.

### <a name="step-2-conduct-periodic-reviews-of-usage-and-files"></a>2단계: 정기적으로 사용 현황 및 파일 검토 수행

교육이 진행되고 몇 주 후에 SharePoint Online 사이트 또는 팀의 SharePoint 관리자는 다음을 수행할 수 있습니다.

- 사이트 또는 팀의 사용 현황을 분석하고 예상 사용 현황과 비교합니다.
- 매우 중요한 파일에 Azure Information Protection 하위 레이블이 적절히 적용되었는지 확인합니다.

필요에 따라 사용자를 재교육합니다.

### <a name="user-adoption-results"></a>사용자 채택 계획

중요한 디지털 자산은 높은 규제 대상 데이터를 위한 SharePoint Online 사이트 또는 팀에 단독으로 저장되며 가장 중요한 자산은 Azure Information Protection 하위 레이블로 구성됩니다.

## <a name="see-also"></a>참고 항목

[배포 가이드](deploy-microsoft-365-enterprise.md)

[테스트 랩 가이드](m365-enterprise-test-lab-guides.md)

[개발/테스트 환경의 보안 SharePoint Online 사이트](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-in-a-dev-test-environment)
