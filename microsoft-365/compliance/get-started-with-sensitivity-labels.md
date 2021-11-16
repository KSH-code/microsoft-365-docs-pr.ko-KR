---
title: 민감도 레이블 시작
f1.keywords:
- CSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- SPO_Content
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: 조직의 데이터를 보호하는 데 도움이 되는 민감도 레이블을 배포할 준비가 되었지만 어디서부터 시작해야 할지 모르겠나요? 레이블 여행에 도움이 되는 몇 가지 실용적인 지침을 읽으세요.
ms.openlocfilehash: ef03bd502b0951416ad9e8be27e6da7281f63811
ms.sourcegitcommit: 542e6b5d12a8d400c3b9be44d849676845609c5f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/15/2021
ms.locfileid: "60962678"
---
# <a name="get-started-with-sensitivity-labels"></a>민감도 레이블 시작

>*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

민감도 레이블이 무엇인지와 조직의 데이터를 보호하는 데 도움이 되는 방법에 대한 자세한 내용은 [민감도 레이블에 대한 자세한 정보](sensitivity-labels.md)를 참조하세요.

[Azure Information Protection](/azure/information-protection/what-is-information-protection)이 있고 Azure Portal에서 관리되는 Azure Information Protection 레이블을 계속 사용하는 경우 이러한 레이블을 [통합 레이블 지정 플랫폼](/azure/information-protection/faqs#how-can-i-determine-if-my-tenant-is-on-the-unified-labeling-platform)으로 마이그레이션해야 합니다. Windows 컴퓨터의 경우 게시된 민감도 레이블에 [사용할 레이블 지정 클라이언트를 선택](/azure/information-protection/rms-client/use-client#choose-which-labeling-client-to-use-for-windows-computers)할 수 있습니다.

민감도 레이블을 사용하여 조직의 데이터를 보호하기 시작할 준비가 되면 다음을 수행합니다.

1. **레이블을 만듭니다.** 다양한 민감도 수준의 컨텐츠에 대한 조직의 분류체계에 따라 민감도 레이블을 작성하고 이름을 지정하십시오. 사용자가 이해할 수 있는 일반적인 이름이나 용어를 사용합니다. 분류 체계가 아직 설정되지 않은 경우 개인, 공개, 일반, 기밀 및 극비와 같은 문구로 레이블 이름으로 시작하는 것이 좋습니다. 그런 다음 하위 레이블을 사용하여 범주별로 비슷한 레이블을 그룹화할 수 있습니다. 레이블을 만들 때 도구 설명 텍스트를 사용하여 사용자가 적절한 레이블을 선택하는 데 도움을 줄 수 있습니다.
    
    분류법 정의에 대한 보다 광범위한 지침을 보려면 [Service Trust Portal](https://aka.ms/DataClassificationWhitepaper)에서 "데이터 분류 및 민감도 레이블 분류법" 백서를 다운로드하세요.

2. **각 레이블이 수행할 수 있는 작업을 정의합니다.** 각 레이블과 연결할 보호 설정을 구성합니다. 예를 들어 민감도가 낮은 콘텐츠(예: "일반"레이블)에 머리글이나 바닥글만 적용하고 민감도가 높은 콘텐츠(예: "기밀" 레이블)에는 워터마크와 암호화가 있어야 합니다.

3. **레이블을 게시합니다.** 민감도 레이블이 구성되 면 레이블 정책을 사용하 여 해당 레이블을 게시합니다. 어떤 사용자와 그룹에 레이블과 정책 설정을 사용할지 결정합니다. 단일 레이블은 다시 사용할 수 있습니다. 한번 정의한 후 다양한 사용자에게 할당된 여러 레이블 정책에 이를 포함시킬 수 있습니다. 예를 들어, 소수의 사용자 에게만 레이블 정책을 할당하여 민감도 레이블을 파일럿 할 수 있습니다. 그런 다음 조직 전체에 레이블을 롤아웃할 준비가되면 레이블에 대한 새 레이블 정책을 작성하고 이번에는 모든 사용자를 지정하십시오.


> 기본 레이블의 자동 생성 및 1-3단계를 처리하는 기본 레이블 정책에 대한 자격이 있을 수 있습니다. 자세한 내용은 [Microsoft Information Protection에 대한 기본 레이블 및 정책](mip-easy-trials.md)을 참조하세요.

민감도 레이블을 배포하고 적용하기 위한 기본 흐름:

![민감도 레이블의 워크플로를 보여 주는 다이어그램.](../media/Sensitivity-label-flow.png)

## <a name="subscription-and-licensing-requirements-for-sensitivity-labels"></a>민감도 레이블에 대한 구독 및 라이선스 요구 사항

다양한 구독 지원 민감도 레이블과 사용자에 대한 라이선스 요구 사항은 사용하는 기능에 따라 다릅니다.

사용자에게 Microsoft 365 규정 준수 기능을 사용하도록 라이선스를 부여하는 옵션을 보려면 [보안 및 규정 준수에 대한 Microsoft 365 라이선스 지침](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)을 참조하세요. 민감도 레이블은 [정보 보호](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection) 섹션 및 기능 수준 라이선스 요구 사항에 대한 관련 PDF 다운로드를 참조하세요.

## <a name="permissions-required-to-create-and-manage-sensitivity-labels"></a>민감도 레이블을 만들고 관리하는 데 필요한 사용 권한

민감도 레이블을 만들 규정 준수 팀의 구성원에게는 Microsoft 365 규정 준수 센터 대한 권한이 필요합니다.

기본적으로 테넌트에 대한 전역 관리자는 이러한 관리 센터에 액세스할 수 있으며, 규정 준수 관리자와 기타 사용자에게 테넌트 관리자의 모든 사용 권한을 부여하지 않고도 액세스 권한을 부여할 수 있습니다. 이러한 위임된 제한적 관리 액세스 권한을 부여하려면 사용자를 **규정 준수 데이터 관리자**, **규정 준수 관리자** 또는 **보안 관리자** 역할 그룹에 추가합니다. 

기본 역할을 사용하는 대신 새 역할 그룹을 만들고 이 그룹에 **민감도 레이블 관리자** 또는 **조직 구성** 역할을 추가할 수 있습니다. 읽기 전용 역할의 경우 **민감도 레이블 리더** 를 사용합니다. 

기본 역할에 사용자를 추가하거나 고유의 역할 그룹을 만드는 방법에 대한 지침은 [Office 365 규정 준수 센터의 사용 권한](microsoft-365-compliance-center-permissions.md)을 참조하세요.

이러한 사용 권한은 민감도 레이블과 해당 레이블 정책을 만들고 구성하는 데만 필요합니다. 앱이나 서비스에서 레이블을 적용하는 것은 필요하지 않습니다. 민감도 레이블과 관련된 특정 구성에 대해 추가 사용 권한이 필요한 경우 해당 사용 권한은 해당하는 문서 지침에 나열되어 있습니다.

## <a name="deployment-strategy-for-sensitivity-labels"></a>민감도 레이블 배포 전략
조직에 민감도 레이블을 배포하는 성공적인 전략은 비즈니스 및 기술 요구사항, 개념 증명 테스트, 내부 체크포인트 및 승인, 프로덕션 환경에 대한 최종 배포를 식별 및 관리하는 가상 팀을 만드는 것입니다.

다음 섹션의 표를 사용하여 가장 영향력 있는 비즈니스 요구사항에 적합한 상위 한두 가지 시나리오를 파악하는 것이 좋습니다. 이러한 시나리오가 배포된 후 목록으로 돌아가 배포의 다음 한두 가지 우선 순위를 식별합니다.

[CAT(고객 가속팀)](https://microsoft.github.io/ComplianceCxE/) 사이트의 리소스 중 하나인 [Microsoft 정보 보호 및 데이터 손실 방지를 위한 배포 가속 가이드](https://microsoft.github.io/ComplianceCxE/dag/mip-dlp/)에서 추가 일반 배포 지침 및 모범 사례를 확인할 수 있습니다.

## <a name="common-scenarios-for-sensitivity-labels"></a>민감도 레이블에 대한 일반적인 시나리오

모든 시나리오에서 [민감도 레이블 및 해당 정책](create-sensitivity-labels.md)을 만들고 구성해야 합니다.

|필요|설명서|
|----------------|---------------|
|Office 앱의 민감도 레이블을 관리하여 컨텐츠가 생성된 대로 레이블이 지정되도록 합니다(모든 플랫폼에서 수동 레이블 지원 포함). |[Office 앱의 민감도 레이블 관리](sensitivity-labels-office-apps.md)|
|사용자가 Office 앱, 파일 탐색기 및 PowerShell을 사용하여 Windows 컴퓨터에서 파일에 레이블을 지정하고 파일을 보호하도록 할 수 있습니다.|[Windows용 Azure Information Protection 통합 레이블 지정 클라이언트](/azure/information-protection/rms-client/aip-clientv2)|
|민감도 레이블이있는 문서 및 이메일을 암호화하고 해당 컨텐츠에 액세스할 수 있는 사람과 사용 방법을 제한합니다. |[민감도 레이블을 사용하여 암호화를 적용하여 콘텐츠 액세스 제한](encryption-sensitivity-labels.md)|
|문서를 암호화한 경우에도 공동 작성, eDiscovery, 데이터 손실 방지, 검색에 대 한 지원을 사용하여 웹용 Office에 대한 민감도 레이블을 사용하도록 설정합니다. | [SharePoint 및 OneDrive에서 Office 파일에 대한 민감도 레이블 사용](sensitivity-labels-sharepoint-onedrive-files.md)
|문서가 암호화된 경우 Office 데스크톱 앱에서 공동 작성 및 자동 저장 사용 | [민감도 레이블로 암호화된 파일에 공동 작성 사용](sensitivity-labels-coauthoring.md)
|문서 및 전자 메일에 자동으로 민감도 레이블 적용 | [민감도 레이블을 콘텐츠에 자동으로 적용](apply-sensitivity-label-automatically.md)|
|민감도 레이블을 사용하여 Teams와 SharePoint에서 콘텐츠 보호 |[Microsoft Teams, Microsoft 365 그룹 및 SharePoint 사이트에서 민감도 레이블 사용하기](sensitivity-labels-teams-groups-sites.md)|
|문서 이해 모델에 민감도 레이블을 적용하여 SharePoint 라이브러리에서 식별된 문서가 자동으로 분류 및 보호되도록 합니다. |[Microsoft SharePoint Syntex에서 모델에 민감도 레이블 적용](/microsoft-365/contentunderstanding/apply-a-sensitivity-label-to-a-model)|
|특정 민감도 레이블로 파일 또는 전자 메일 공유에 대해 사용자 차단 또는 경고 |[DLP 정책에서 민감도 레이블을 조건으로 사용](dlp-sensitivity-label-as-condition.md) |
|보존 레이블을 적용하여 특정 민감도 레이블이 있는 파일 또는 전자 메일을 보존하거나 삭제합니다.|[보존 레이블 자동 적용하여 콘텐츠를 보존 또는 삭제하기](apply-retention-labels-automatically.md) |
|온 프레미스에 있는 데이터 저장소에 저장된 파일 검색, 레이블 지정 및 보호 |[파일을 자동으로 분류하고 보호하는 Azure Information Protection 스캐너 배포](/azure/information-protection/deploy-aip-scanner)|
|클라우드에 있는 데이터 저장소에 저장된 파일 검색, 레이블 지정 및 보호|[클라우드에 저장된 데이터를 검색하고, 분류하고, 레이블을 지정하고, 보호](/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|Power BI에서 레이블을 적용 및 확인하고 서비스 외부에서 데이터를 저장할 때 데이터를 보호합니다.|[Power BI의 민감도 레이블](/power-bi/admin/service-security-sensitivity-label-overview)|
|조직에서 민감도 레이블이 사용되는 방식을 모니터링하고 이해하기|[데이터 분류에 대한 자세한 정보](data-classification-overview.md)|
|타사 앱 및 서비스에 민감도 레이블을 연장|[Microsoft Information Protection SDK](/information-protection/develop/overview#microsoft-information-protection-sdk)|
|Azure Blob Storage, Azure 파일, Azure Data Lake Storage 1세대 및 Azure Data Lake Storage Gen12의 컨텐츠에 걸쳐 민감도 레이블 확장|[Azure Purview에서 내용에 자동으로 레이블을 지정](/azure/purview/create-sensitivity-label) |


## <a name="end-user-documentation-for-sensitivity-labels"></a>민감도 레이블용 최종 사용자 설명서

가장 효과적인 최종 사용자 문서는 선택한 레이블 이름 및 구성에 대한 사용자 지정 안내사항 및 지침입니다. 레이블 정책 설정인 **사용자 정의 도움말 페이지에 대한 링크를 사용자에게 제공** 을 사용하여 이 설명서에 대한 내부 링크를 지정할 수 있습니다. 그러면 사용자는 다음을 수행하여 **민감도** 단추에서 설명서로 쉽게 액세스할 수 있습니다.

- 기본 제공 레이블 지정의 경우: **자세히 알아보기** 메뉴 옵션.
- Azure Information Protection 통합 레이블 지정 클라이언트의 경우: **도움말 및 피드백** 메뉴 옵션 > **자세한 정보** 링크(Microsoft Azure Information Protection 대화 상자).

맞춤식 설명서를 제공할 수 있도록 사용자 교육을 지원하는 데 사용할 수 있는 다음 페이지 및 다운로드를 참조하세요. [민감도 레이블에 대한 최종 사용자 교육](https://microsoft.github.io/ComplianceCxE/enduser/sensitivity/). 

기본 지침으로 다음 리소스를 사용할 수 있습니다.

- [Office에서 파일 및 전자 메일에 민감도 레이블 적용](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)
    - [Office의 민감도 레이블과 관련된 알려진 문제점](https://support.microsoft.com/en-us/office/known-issues-with-sensitivity-labels-in-office-b169d687-2bbd-4e21-a440-7da1b2743edc)

- [Office에서 파일 및 전자 메일에 자동으로 민감도 레이블 적용 또는 추천](https://support.office.com/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1)
    - [민감도 레이블 자동 적용 또는 추천에 대한 알려진 문제](https://support.office.com/article/known-issues-with-automatically-applying-or-recommending-sensitivity-labels-451698ae-311b-4d28-83aa-a839a66f6efc)

- [Azure Information Protection 통합 레이블 사용자 가이드](/azure/information-protection/rms-client/clientv2-user-guide)

민감도 레이블이 PDF 문서에 대해 암호화를 적용하는 경우 Windows 또는 Mac에서 Microsoft Edge를 사용하여 문서를 열 수 있습니다. 자세한 내용과 대체 읽기 프로그램에 대한 자세한 내용은 [보호되는 Pdf에 대해 지원되는 PDF 읽기 프로그램](/azure/information-protection/rms-client/protected-pdf-readers#viewing-protected-pdfs-in-microsoft-edge-on-windows-or-mac)을 참조하세요.
