---
title: Office 앱의 민감도 레이블 관리
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: IT 관리자가 데스크톱, 모바일 및 웹용 Office 앱에서 민감도 레이블을 관리하기 위한 정보입니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1834e1071c56e03ef20ae0e87b63fc4c03a6921b
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/03/2021
ms.locfileid: "50407308"
---
# <a name="manage-sensitivity-labels-in-office-apps"></a>Office 앱의 민감도 레이블 관리

>*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD)*

Microsoft 365 규정 준수 센터 또는 동등한 레이블 지정 센터에서 민감도 레이블을 게시한 경우 사용자가 데이터를 만들거나 편집할 때 데이터를 분류하고 보호할 수 있도록 Office 앱에 표시됩니다. [](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)

이 문서의 정보를 사용하여 Office 앱에서 민감도 레이블을 성공적으로 관리하는 데 도움이 됩니다. 예를 들어 기본 제공 레이블 지정을 지원하는 데 필요한 최소 버전의 앱을 식별하고 Azure Information Protection 통합 레이블 클라이언트와의 상호 작용 및 다른 앱 및 서비스와의 호환성을 이해합니다.

## <a name="labeling-client-for-desktop-apps"></a>데스크톱 앱용 클라이언트 레이블 지정

Windows 및 Mac용 Office 데스크톱 앱에 기본 제공되는 민감도 레이블을 사용하려면 Office 구독 에디션을 사용해야 합니다. 이 레이블 지정 클라이언트는 Office 2016 또는 Office 2019와 같은 독립 실행형 Office 버전은 지원하지 않습니다.

Windows 컴퓨터에서 이러한 독립 실행형 Office 버전에서 민감도 레이블을 사용하려면 Azure Information Protection 통합 레이블 클라이언트 [를 설치합니다.](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2)

## <a name="support-for-sensitivity-label-capabilities-in-apps"></a>앱의 민감도 레이블 기능에 대한 지원

다음 표에는 각 기능에 대해 기본 제공 레이블 지정을 사용하여 민감도 레이블을 지원하는 데 필요한 최소 Office 버전이 나열되어 있습니다. 또는 레이블 기능이 공개 미리 보기에 있는 경우 또는 향후 릴리스에 대한 검토 중입니다. 향후 릴리스에 대한 자세한 내용은 [Microsoft 365](https://aka.ms/MIPC/Roadmap) 로드맵을 사용 하시기 바랍니다.

새 버전의 Office 앱은 다른 업데이트 채널에 대해 다른 시간으로 사용할 수 있습니다. 관심 있는 새 레이블 지정 기능을 테스트할 수 있도록 업데이트 채널을 구성하는 방법을 비롯한 자세한 내용은 [Microsoft 365 앱](https://docs.microsoft.com/DeployOffice/overview-update-channels)업데이트 채널 개요를 참조하세요. 비공개 미리 보기의 새로운 기능은 표에 포함되지 않지만 Microsoft Information Protection 개인 미리 보기 프로그램에 대한 조직을 지명하여 이러한 미리 보기에 참가할 수 [있습니다.](https://aka.ms/mip-preview)

> [!NOTE]
> 최근에 Office 앱의 업데이트 채널 이름이 변경되었습니다. 예를 들어 월별 채널은 현재 채널이 이며 Office Insider는 이제 베타 채널이 됩니다. 자세한 내용은 [Microsoft 365 앱의](https://docs.microsoft.com/deployoffice/update-channels-changes)채널 업데이트 변경을 참조하세요.

iOS 및 Android용 Office: 민감도 레이블은 [Office 앱에 기본 제공됩니다.](https://www.microsoft.com/en-us/microsoft-365/blog/2020/02/19/new-office-app-android-ios-available/)

추가 기능은 Windows 컴퓨터에서만 실행되는 Azure Information Protection 통합 레이블 지정 클라이언트를 설치할 때 사용할 수 있습니다. 이러한 세부 정보는 Windows 컴퓨터용 레이블 [지정 클라이언트 비교를 참조합니다.](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#compare-the-labeling-clients-for-windows-computers)

### <a name="sensitivity-label-capabilities-in-word-excel-and-powerpoint"></a>Word, Excel 및 PowerPoint의 민감도 레이블 기능

나열된 번호는 각 기능에 필요한 최소 Office 응용 프로그램 버전입니다.

|기능                                                                                                        |Windows |Mac |iOS    |Android      |웹                                                         |
|------------------------------------------------------------------------------------------------------------------|----------------|------------|-------|-------------|------------------------------------------------------------|
|[레이블을 수동으로 적용, 변경 또는 제거](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [예 - 옵트인](sensitivity-labels-sharepoint-onedrive-files.md) |
|[기본 레이블 적용](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [예 - 옵트인](sensitivity-labels-sharepoint-onedrive-files.md)                                                        |
|[레이블을 변경하기 위한 사당성 필요](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [예 - 옵트인](sensitivity-labels-sharepoint-onedrive-files.md) |
|[사용자 지정 도움말 페이지에 대한 도움말 링크 제공](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [예 - 옵트인](sensitivity-labels-sharepoint-onedrive-files.md) |
|[콘텐츠 표시](sensitivity-labels.md#what-sensitivity-labels-can-do)                                              | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [예 - 옵트인](sensitivity-labels-sharepoint-onedrive-files.md) |
|[변수가 있는 동적 표시](#dynamic-markings-with-variables)                                              | 2010+           | 16.42+     | 2.42+ | 16.0.13328+ | 검토 중 |
|[지금 권한 할당](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [예 - 옵트인](sensitivity-labels-sharepoint-onedrive-files.md) |
|[사용자가 권한을 할당하도록 허용](encryption-sensitivity-labels.md#let-users-assign-permissions)                     |2004+ | 16.35+   | 검토 중   | 검토 중         | 검토 중                                                        |
|[데이터 분류 시작](data-classification-overview.md) 및 관리자를 위한 데이터 보내기                      | 2011+ | 16.43+ | 미리 보기: [현재 채널(미리 보기)](https://office.com/insider) | 미리 보기: [현재 채널(미리 보기)](https://office.com/insider) | 예 <sup>\*</sup>                                                        |
|[사용자가 전자 메일 및 문서에 레이블을 적용해야 합니다.](#require-users-to-apply-a-label-to-their-email-and-documents)   | 미리 보기: [현재 채널(미리 보기)](https://office.com/insider)             | 미리 보기: [현재 채널(미리 보기)](https://office.com/insider)         | 검토 중   | 롤아웃: 16.0.13628+ | 검토 중                                            
|[민감도 레이블을 콘텐츠에 자동으로 적용](apply-sensitivity-label-automatically.md)                    | 2009+                                  | 롤아웃: 16.44+ | 검토 중 | 검토 중 | [예 - 옵트인](sensitivity-labels-sharepoint-onedrive-files.md) |
|[레이블이 지정되고](sensitivity-labels-coauthoring.md) 암호화된 문서에 대한 공동 작성 및 자동 저장 지원 | 미리 보기: [현재 채널(미리 보기)](https://office.com/insider) | 미리 보기: [베타 채널](https://office.com/insider) | 검토 중 | 검토 중 | [예 - 옵트인](sensitivity-labels-sharepoint-onedrive-files.md) |
|

**각주:**

<sup>\*</sup> 현재, 레이블을 제거하거나 분류 수준을 낮추기 위한 사명 텍스트를 포함하지 않습니다.

### <a name="sensitivity-label-capabilities-in-outlook"></a>Outlook의 민감도 레이블 기능

나열된 번호는 각 기능에 필요한 최소 Office 응용 프로그램 버전입니다.

|기능                                                                                                        | Windows용 Outlook |Outlook for Mac |iOS의 Outlook |Android의 Outlook |웹용 Outlook |
|------------------------------------------------------------------------------------------------------------------|---------------------------|------------------------|---------------|-------------------|-------------------|
|[레이블을 수동으로 적용, 변경 또는 제거](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | 예               |
|[기본 레이블 적용](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | 예               |
|[레이블을 변경하기 위한 사당성 필요](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | 예               |
|[사용자 지정 도움말 페이지에 대한 도움말 링크 제공](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | 예               |
|[콘텐츠 표시](sensitivity-labels.md#what-sensitivity-labels-can-do)                                              | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | 예               |
|[변수가 있는 동적 표시](#dynamic-markings-with-variables)                                              | 검토 중                     | 검토 중                 | 검토 중         | 검토 중           | 검토 중               |
|[지금 권한 할당](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | 예               |
|[사용자가 권한을 할당하도록 허용](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | 예               |
|[사용자가 전자 메일 및 문서에 레이블을 적용해야 합니다.](#require-users-to-apply-a-label-to-their-email-and-documents)   | 미리 보기: [현재 채널(미리 보기)](https://office.com/insider))                        | 16.43+ <sup>\*</sup>                    | 검토 중            | 검토 중                | 예                |
|[데이터 분류 시작](data-classification-overview.md) 및 관리자를 위한 데이터 보내기                      | 2011+ | 검토 중 | 검토 중           | 검토 중               | 검토 중 |
|[민감도 레이블을 콘텐츠에 자동으로 적용](apply-sensitivity-label-automatically.md)                    | 2009+                      | 16.44+ <sup>\*</sup>                    | 검토 중           | 검토 중               | 예 |
|

**각주:**

<sup>\*</sup> 새 [Mac용 Outlook 필요](https://support.microsoft.com/office/the-new-outlook-for-mac-6283be54-e74d-434e-babb-b70cefc77439)


## <a name="office-built-in-labeling-client-and-other-labeling-solutions"></a>Office 기본 제공 레이블 클라이언트 및 기타 레이블 솔루션

Office 기본 제공 레이블 클라이언트는 다음 관리 센터에서 민감도 레이블 및 민감도 레이블 정책 설정을 다운로드합니다.

- Microsoft 365 규정 준수 센터
- Microsoft 365 보안 센터
- Office 365 보안 및 준수 센터

Office 기본 제공 레이블 클라이언트를 사용하려면 나열된 [](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) 관리 센터와 지원되는 Office 버전 중 하나에서 사용자에게 하나 이상의 레이블 정책을 [게시해야 합니다.](#support-for-sensitivity-label-capabilities-in-apps)

이러한 조건이 모두 충족되지만 Office 기본 제공 레이블 클라이언트를 해제해야 하는 경우 다음 그룹 정책 설정을 사용 합니다.

1. 사용자 **구성/관리 템플릿/2016/Microsoft Office 설정으로 이동합니다.**

2. Office의 **민감도** 기능을 사용하여 민감도 레이블을 적용하고 **0으로 설정** 
 
그룹 정책 또는 Office 클라우드 정책 서비스를 사용하여 이 [설정을 배포합니다.](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service) 이 설정은 Office 앱이 다시 시작될 때 적용됩니다.

### <a name="office-built-in-labeling-client-and-the-azure-information-protection-client"></a>Office 기본 제공 레이블 클라이언트 및 Azure Information Protection 클라이언트

사용자에게 Azure Information Protection 클라이언트 중[](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2) 하나(통합 레이블 지정 클라이언트 또는 클래식 [클라이언트)가](https://docs.microsoft.com/azure/information-protection/rms-client/aip-client)설치되어 있는 경우 기본적으로 Office 앱에서 기본 제공 레이블 클라이언트가 꺼집니다. 

Office 앱용 Azure Information Protection 클라이언트가 아닌 기본 제공 레이블 지정을 사용하기 위해 이전 섹션의 지침을 사용하지만 그룹 정책 설정 **Office의** 민감도 기능을 사용하여 민감도 레이블을 적용하고 **1로** 설정하세요. 

또는 Office 추가 기능인 Azure Information Protection을 사용하지 않도록 **설정하거나 제거합니다.** 이 방법은 단일 컴퓨터 및 ad-hoc 테스트에 적합합니다. 자세한 내용은 Office 프로그램에서 추가 기능 보기, 관리 및 [설치를 참조하세요.](https://support.office.com/article/16278816-1948-4028-91e5-76dca5380f8d) 

이 Office 추가 기능을 사용하지 않도록 설정하거나 제거하면 Azure Information Protection 클라이언트가 설치된 상태로 유지되어 Office 앱 외부의 파일에 계속 레이블을 지정합니다. 예를 들어 파일 탐색기 또는 PowerShell을 사용합니다.

Azure Information Protection 클라이언트 및 Office 기본 제공 레이블 클라이언트에서 지원하는 기능에 [](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#choose-which-labeling-client-to-use-for-windows-computers) 대한 자세한 내용은 Azure Information Protection 설명서에서 Windows 컴퓨터에 사용할 레이블 클라이언트 선택을 참조하세요.

## <a name="office-file-types-supported"></a>지원되는 Office 파일 형식

Word, Excel 및 PowerPoint 파일에 대한 기본 제공 레이블 지정이 있는 Office 앱은 Open XML 형식(예: .docx 및 .xlsx)을 지원하지만 Microsoft Office 97-2003 형식(예: .doc 및 .xls), Open Document Format(예: .odt 및 .ods) 또는 기타 형식은 지원하지 않습니다. 파일 형식이 기본 제공 레이블 지정에 지원되지 않는 경우 Office 앱에서 민감도 단추를 사용할 수 없습니다. 

Azure Information Protection 통합 레이블 지정 클라이언트는 Open XML 형식과 97-Microsoft Office 형식을 모두 지원합니다. 자세한 내용은 해당 클라이언트의 관리 가이드에서 [Azure Information Protection](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-file-types) 통합 레이블 지정 클라이언트에서 지원하는 파일 형식을 참조하세요.

다른 레이블 지정 솔루션의 경우 해당 설명서에서 지원되는 파일 형식을 참조하세요.

## <a name="protection-templates-and-sensitivity-labels"></a>보호 템플릿 및 민감도 레이블

Office 365 메시지 암호화에 대해 정의하는 템플릿과 같은 관리자 정의 보호 템플릿은 기본 제공 레이블 지정을 사용하는 경우 Office 앱에서 표시되지 않습니다. [](https://docs.microsoft.com/azure/information-protection/configure-policy-templates) 이 간소화된 환경은 암호화를 사용하도록 설정된 민감도 레이블에 동일한 설정이 포함되어 있기 때문에 보호 템플릿을 선택할 필요가 없음을 반영합니다.

기존 보호 템플릿을 레이블로 변환해야 하는 경우 Azure Portal 및 다음 지침을 사용하여 템플릿을 레이블로 [변환합니다.](https://docs.microsoft.com/azure/information-protection/configure-policy-templates#to-convert-templates-to-labels)

## <a name="information-rights-management-irm-options-and-sensitivity-labels"></a>IRM(정보 권한 관리) 옵션 및 민감도 레이블

암호화를 적용하도록 구성한 민감도 레이블은 사용자가 자체 암호화 설정을 지정하기 위한 복잡성을 제거합니다. 대부분의 Office 앱에서는 사용자가 IRM(정보 권한 관리) 옵션을 사용하여 이러한 개별 암호화 설정을 수동으로 구성할 수 있습니다. 예를 들어 Windows 앱의 경우:

- 문서의 경우: **파일**  >  **정보**  >  **보호 문서 액세스**  >  **제한**
- 전자 메일의 경우: 옵션 **탭에서** >  
  
사용자가 처음에 문서 또는 전자 메일에 레이블을 지정하면 항상 자체 암호화 설정으로 레이블 구성 설정을 의회할 수 있습니다. 예를 들면 다음과 같습니다.

- 사용자가 문서에 **기밀 \ 모든** 직원 레이블을 적용하고 이 레이블은 조직의 모든 사용자에 대해 암호화 설정을 적용하도록 구성됩니다. 그런 다음 이 사용자는 조직 외부의 사용자에 대한 액세스를 제한하도록 IRM 설정을 수동으로 구성합니다. 최종 결과로 기밀 **\ 모든** 직원으로 레이블이 지정되고 암호화된 문서가 되지만 조직의 사용자가 예상대로 열 수 없습니다.

- 사용자가 전자 메일에 **기밀 \ 받는** 사람만 레이블을 적용하고 이 전자 메일은 전달 금지의 암호화 설정을 **적용하도록 구성됩니다.** 그런 다음 이 사용자는 전자 메일에 제한이 없는 IRM 설정을 수동으로 구성합니다. 최종 결과 전자 메일은 기밀 \ 받는 사람만 레이블이 지정되어도 받는 사람이 전자 메일을 **전달할 수** 있습니다.

- 사용자가 문서에 **일반** 레이블을 적용하며 이 레이블은 암호화를 적용하도록 구성되지 않습니다. 이 사용자는 문서에 대한 액세스를 제한하도록 IRM 설정을 수동으로 구성합니다. 최종 결과로 일반 레이블이 지정되지만 일부 사용자가 예상대로 열 수 없는 암호화도 적용됩니다. 

문서 또는 전자 메일에 이미 레이블이 지정되어 있는 경우 사용자는 콘텐츠가 암호화되지 않은 경우 [](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions) 또는 사용권 내보내기 또는 모든 사용권이 있는 경우 이러한 작업을 수행할 수 있습니다. 

의미 있는 보고를 통해 보다 일관된 레이블 환경을 위해 사용자가 문서를 보호하기 위해 레이블만 적용할 수 있는 적절한 레이블과 지침을 제공합니다. 예를 들면 다음과 같습니다.

- 사용자가 고유한 사용 권한을 할당해야 하는 예외의 경우 사용자가 자신의 권한을 할당할 수 있는 [레이블을 제공합니다.](encryption-sensitivity-labels.md#let-users-assign-permissions) 

- 사용자가 암호화를 적용하는 레이블을 선택한 후 암호화를 수동으로 제거하는 대신 동일한 분류를 사용하지만 암호화가 없는 레이블이 필요한 경우 하위 레이블 대안을 제공합니다. 예:
    - **기밀 \ 모든 직원**
    - **기밀 \ 모든 사람(암호화 없음)**

> [!NOTE]
> 사용자가 SharePoint 또는 OneDrive에 저장된 레이블이 있는 문서에서 암호화를 수동으로 제거하고 SharePoint 및 [OneDrive에서 Office](sensitivity-labels-sharepoint-onedrive-files.md)파일에 대해 민감도 레이블을 사용하도록 설정한 경우 다음에 문서에 액세스하거나 다운로드할 때 레이블 암호화가 자동으로 복원됩니다. 


## <a name="apply-sensitivity-labels-to-files-emails-and-attachments"></a>파일, 전자 메일 및 첨부 파일에 민감도 레이블 적용

사용자는 각 문서 또는 전자 메일에 대해 한 번씩 하나의 레이블만 적용할 수 있습니다.

첨부 파일이 있는 전자 메일 메시지에 레이블을 지정하면 전자 메일 메시지에 적용하는 레이블이 암호화를 적용하고 첨부 파일이 Office 문서가 아직 암호화되지 않은 경우 첨부 파일에서만 레이블을 상속합니다. 상속된 레이블은 암호화를 적용하기 때문에 첨부 파일이 새로 암호화됩니다.

전자 메일 메시지에 적용된 레이블이 암호화를 적용하지 못하거나 첨부 파일이 이미 암호화되어 있는 경우 첨부 파일은 전자 메일 메시지에서 레이블을 상속하지 않습니다.

레이블 기밀이 암호화를 적용하고 **일반** 레이블은 암호화를 적용하지 않는 레이블 상속의 예: 

- 사용자가 새 전자 메일 메시지를 만들고 이 메시지에 **기밀** 레이블을 적용합니다. 그런 다음 레이블이 지정되거나 암호화되지 않은 Word 문서를 추가합니다. 상속의 결과로 문서에 기밀 레이블이  새로 지정되고 이제 해당 레이블에서 암호화가 적용됩니다.

- 사용자가 새 전자 메일 메시지를 만들고 이 메시지에 **기밀** 레이블을 적용합니다. 그런 다음 일반 레이블이 지정되어 있으며 이 파일은 암호화되지 않은 Word 문서를 추가합니다.  상속의 결과로 문서는 기밀로 레이블이  지정되고 이제 해당 레이블에서 암호화가 적용되었습니다.

## <a name="sensitivity-label-compatibility"></a>민감도 레이블 호환성

**RMS** 지원 앱 사용: 민감도 레이블을 지원하지 않는 [RMS](https://docs.microsoft.com/azure/information-protection/requirements-applications#rms-enlightened-applications) 지원 응용 프로그램에서 레이블이 지정되고 암호화된 문서 또는 전자 메일을 여는 경우 앱에서 여전히 암호화 및 권한 관리를 적용합니다.

**Azure Information Protection** 클라이언트: Azure Information Protection 클라이언트를 사용하여 Office 기본 제공 레이블 클라이언트를 사용하여 문서 및 전자 메일에 적용하는 민감도 레이블을 보고 변경할 수 있습니다.

**다른 버전의 Office** 사용: 권한이 부여된 사용자는 다른 버전의 Office에서 레이블이 붙은 문서 및 전자 메일을 열 수 있습니다. 그러나 지원되는 Office 버전에서 또는 Azure Information Protection 클라이언트를 사용하여 레이블을 보거나 변경할 수만 있습니다. 지원되는 Office 앱 버전은 이전 [섹션에 나열되어 있습니다.](#support-for-sensitivity-label-capabilities-in-apps)

## <a name="support-for-sharepoint-and-onedrive-files-protected-by-sensitivity-labels"></a>민감도 레이블로 보호되는 SharePoint 및 OneDrive 파일 지원

SharePoint 또는 OneDrive의 문서에 대해 웹용 Office에서 Office 기본 제공 레이블 지정 클라이언트를 사용하려면 SharePoint 및 [OneDrive에서 Office](sensitivity-labels-sharepoint-onedrive-files.md)파일에 대한 민감도 레이블을 사용하도록 설정해야 합니다.

## <a name="support-for-external-users-and-labeled-content"></a>외부 사용자 및 레이블이 붙은 콘텐츠 지원

문서 또는 전자 메일에 레이블을 지정하면 레이블은 테넌트 및 레이블 GUID를 포함하는 메타데이터로 저장됩니다. 민감도 레이블을 지원하는 Office 앱에서 레이블이 지정한 문서 또는 전자 메일을 열면 이 메타데이터가 읽기 전용으로, 사용자가 동일한 테넌트에 속하는 경우 레이블이 앱에 표시됩니다. 예를 들어 Word, PowerPoint 및 Excel에 대한 기본 제공 레이블 지정의 경우 레이블 이름이 상태 표시줄에 표시됩니다. 

즉, 다른 레이블 이름을 사용하는 다른 조직과 문서를 공유하는 경우 각 조직에서 해당 문서에 적용되는 자체 레이블을 적용하고 볼 수 있습니다. 그러나 적용된 레이블의 다음 요소는 조직 외부의 사용자에게 표시됩니다.

- 콘텐츠 표시. 레이블이 머리더, 발자국 또는 워터마크를 적용하면 콘텐츠에 직접 추가되고 누군가가 이를 수정하거나 삭제할 때까지 계속 표시됩니다.

- 암호화를 적용한 레이블의 기본 보호 템플릿 이름 및 설명입니다. 이 정보는 문서 맨 위에 있는 메시지 표시줄에 표시되어 문서를 열 권한이 있는 사용자와 해당 문서에 대한 사용 권한에 대한 정보를 제공합니다.

### <a name="sharing-encrypted-documents-with-external-users"></a>외부 사용자와 암호화된 문서 공유

조직 내 사용자에 대한 액세스를 제한하는 것 외에도 Azure Active Directory에 계정이 있는 다른 사용자에 대한 액세스를 확장할 수 있습니다. 그러나 조직에서 조건부 액세스 정책을 사용하는 [](#conditional-access-policies) 경우 다음 섹션에서 추가 고려 사항을 참조하세요.

사용자가 인증된 후 모든 Office 앱 및 [기타 RMS](https://docs.microsoft.com/azure/information-protection/requirements-applications#rms-enlightened-applications) 지원 응용 프로그램에서 암호화된 문서를 열 수 있습니다. 

외부 사용자가 Azure Active Directory에 계정이 없는 경우 테넌트에서 게스트 계정을 사용하여 인증할 수 있습니다. SharePoint 및 [OneDrive에서 Office](sensitivity-labels-sharepoint-onedrive-files.md)파일에 대해 민감도 레이블을 사용하도록 설정한 경우 이러한 게스트 계정을 사용하여 SharePoint 또는 OneDrive의 공유 문서에 액세스할 수도 있습니다.

- 한 가지 옵션은 이러한 게스트 계정을 직접 만드는 것입니다. 이러한 사용자가 이미 사용하는 모든 전자 메일 주소를 지정할 수 있습니다. 예를 들어 Gmail 주소입니다.
    
    이 옵션의 장점은 암호화 설정에서 전자 메일 주소를 지정하여 특정 사용자에 대한 액세스 및 권한을 제한할 수 있습니다. 단점은 계정 만들기 및 레이블 구성과의 조정에 대한 관리 오버헤드입니다.

- 또 다른 옵션은 사용자가 링크를 공유할 때 게스트 계정이 자동으로 만들어지기 위해 Azure AD B2B(미리 보기)와 SharePoint 및 [OneDrive](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview) 통합을 사용하는 것입니다.
    
    계정이 자동으로 만들어지며 레이블 구성이 간단하기 때문에 이 옵션의 장점은 최소 관리 오버헤드입니다. 이 시나리오에서는 전자 메일 주소를 [](encryption-sensitivity-labels.md#requirements-and-limitations-for-add-any-authenticated-users) 미리 알 수 없는 인증된 사용자 추가 암호화 옵션을 선택해야 합니다. 단점은 이 설정을 통해 액세스 및 사용 권한을 특정 사용자로 제한할 수 없습니다.

또한 외부 사용자는 Windows 및 Microsoft 365 앱(이전의[Office 365](https://docs.microsoft.com/deployoffice/name-change)앱) 또는 Office 2019 독립 실행형 버전에서 암호화된 문서를 열 때 Microsoft 계정을 사용하여 암호화된 문서를 열 수도 있습니다. 기타 플랫폼에서 더 최근에 지원되는 Microsoft 계정은 macOS(Microsoft 365 앱, 버전 16.42+), Android(버전 16.0.13029+) 및 iOS(버전 2.42+)에서 암호화된 문서를 여는 데도 지원됩니다. 예를 들어 조직의 사용자가 암호화된 문서를 조직 외부의 사용자와 공유하고 암호화 설정은 외부 사용자의 Gmail 전자 메일 주소를 지정합니다. 이 외부 사용자는 Gmail 전자 메일 주소를 사용하는 자체 Microsoft 계정을 만들 수 있습니다. 그런 다음 이 계정으로 로그인한 후 문서에 대해 지정된 사용 제한에 따라 문서를 열고 편집할 수 있습니다. 이 시나리오의 예제는 보호된 문서 [열기 및 편집을 참조합니다.](https://docs.microsoft.com/azure/information-protection/secure-collaboration-documents#opening-and-editing-the-protected-document)

> [!NOTE]
> Microsoft 계정의 전자 메일 주소는 암호화 설정에 대한 액세스를 제한하기 위해 지정된 전자 메일 주소와 일치해야 합니다.

Microsoft 계정이 있는 사용자가 이러한 방식으로 암호화된 문서를 열면 동일한 이름의 게스트 계정이 없는 경우 테넌트에 대한 게스트 계정이 자동으로 생성됩니다. 게스트 계정이 있는 경우 지원되는 데스크톱 및 모바일 Office 앱에서 암호화된 문서를 여는 것 외에도 웹용 Office를 사용하여 SharePoint 및 OneDrive에서 문서를 여는 데 사용할 수 있습니다.

그러나 이 시나리오에서는 복제 대기 시간 때문에 자동 게스트 계정이 즉시 만들어지지 않습니다. 레이블 암호화 설정의 일부로 개인 전자 메일 주소를 지정하는 경우 Azure Active Directory에서 해당 게스트 계정을 만드는 것이 좋습니다. 그런 다음 이러한 사용자가 이 계정을 사용하여 조직에서 암호화된 문서를 열 수 있어야 하다는 것을 알립니다.

> [!TIP]
> 외부 사용자가 지원되는 Office 클라이언트 앱을 사용하게 될지 확신할 수 없는 경우 게스트 계정을 만들고(특정 사용자용) 또는 [SharePoint 및 OneDrive와 Azure AD B2B(인증된 사용자)와의 SharePoint 및 OneDrive](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview) 통합을 사용하는 경우 외부 사용자와의 보안 공동 작업을 지원하는 보다 안정적인 방법입니다.

### <a name="conditional-access-policies"></a>조건부 액세스 정책

조직에서 [Azure Active Directory 조건부 액세스](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)정책을 구현한 경우 해당 정책의 구성을 확인합니다. 정책에 Azure Information Protection이 포함되어 있으며 정책이 외부 사용자로 확장되는 경우 해당 외부 사용자는 자신의 테넌트에 Azure AD 계정이 있는 경우에도 테넌트에 게스트 계정이 있어야 합니다.

이 게스트 계정이 없는 경우 암호화된 문서를 열 수 없습니다. 오류 메시지가 표시됩니다. 이 시나리오에서 다른 **Azure Active Directory** 사용자 계정으로 다시 로그인하려면 해당 계정을 테넌트의 외부 사용자로 추가해야 하도록 알리는 메시지 텍스트가 표시될 수 있습니다.

레이블로 암호화된 문서를 열 필요가 있는 외부 사용자에 대해 테넌트에서 게스트 계정을 만들고 구성할 수 없는 경우 조건부 액세스 정책에서 Azure Information Protection을 제거하거나 정책에서 외부 사용자를 제외해야 합니다.

민감도 레이블에 사용되는 암호화 서비스인 조건부 액세스 및 Azure Information Protection에 대한 자세한 내용은 Azure Information Protection이 조건부 액세스에 사용할 수 있는 클라우드 앱으로 나열되어 있습니다. 어떻게 작동하나요? 질문과 대답을 [참조하세요.](https://docs.microsoft.com/azure/information-protection/faqs#i-see-azure-information-protection-is-listed-as-an-available-cloud-app-for-conditional-accesshow-does-this-work)

## <a name="when-office-apps-apply-content-marking-and-encryption"></a>Office 앱에서 콘텐츠 표시 및 암호화를 적용하는 경우

Office 앱은 사용하는 앱에 따라 민감도 레이블을 사용하여 콘텐츠 표시 및 암호화를 다르게 적용합니다.

| 앱 | 콘텐츠 표시 | 암호화 |
| --- | --- | --- |
| 모든 플랫폼의 Word, Excel, PowerPoint | 즉시 | 즉시 |
| PC 및 Mac용 Outlook | Exchange Online에서 전자 메일을 보낸 후 | 즉시 |
| Mac, iOS 및 Android용 Outlook | Exchange Online에서 전자 메일을 보낸 후 | Exchange Online에서 전자 메일을 보낸 후 |
|

Office 앱 외부의 파일에 민감도 레이블을 적용하는 솔루션은 파일에 레이블 지정 메타데이터를 적용합니다. 이 시나리오에서는 레이블 구성의 콘텐츠 표시가 파일에 삽입되지 않지만 암호화가 적용됩니다. 

이러한 파일이 Office 데스크톱 앱에서 열리면 콘텐츠 표시가 Azure Information Protection 통합 레이블 지정 클라이언트에 의해 자동으로 적용됩니다. 데스크톱, 모바일 또는 웹앱에 기본 제공 레이블 지정을 사용하는 경우 콘텐츠 표시가 자동으로 적용되지 않습니다.

Office 앱 외부에 민감도 레이블을 적용하는 것이 포함된 시나리오는 다음과 같습니다.

- Azure Information Protection 통합 레이블 지정 클라이언트의 스캐너, 파일 탐색기 및 PowerShell 

- SharePoint 및 OneDrive에 대한 자동 레이블 지정 정책

- Power BI에서 레이블이 지정되고 암호화된 데이터 내보내기

- Microsoft Cloud App Security

이러한 시나리오에서 Office 앱을 사용하는 경우 기본 제공 레이블이 있는 사용자는 현재 레이블을 일시적으로 제거하거나 바꾸고 원래 레이블을 다시 적용하여 레이블의 콘텐츠 표시를 적용할 수 있습니다.

### <a name="dynamic-markings-with-variables"></a>변수가 있는 동적 표시

> [!IMPORTANT]
> 현재 일부 플랫폼의 모든 앱은 머리더, 머리마크 및 워터마크에 대해 지정할 수 있는 동적 콘텐츠 표시를 지원하지 않습니다. 이 기능을 지원하지 않는 앱의 경우 변수를 확인하지 않고 레이블 구성에 지정된 원래 텍스트로 표시를 적용합니다.
> 
> Azure Information Protection 통합 레이블 지정 클라이언트는 동적 표시를 지원합니다. Office에 기본 제공되는 레이블 지정은 이 페이지의 기능 섹션에 [있는](#support-for-sensitivity-label-capabilities-in-apps) 표를 참조하세요.

콘텐츠 표시에 대한 민감도 레이블을 구성할 때 머리더, 머리 글자 또는 워터마크에 대해 텍스트 문자열에 다음 변수를 사용할 수 있습니다.

| 변수 | 설명 | 레이블이 적용된 경우의 예 |
| -------- | ----------- | ------- |
| `${Item.Label}` | 적용된 레이블의 레이블 표시 이름입니다.| **일반**|
| `${Item.Name}` | 레이블이 지정되는 콘텐츠의 파일 이름 또는 전자 메일 제목 | **Sales.docx** |
| `${Item.Location}` | 레이블을 지정하는 문서의 경로 및 파일 이름 또는 레이블이 지정되는 전자 메일의 전자 메일 제목 | **\\\Sales\2020\Q3\Report.docx**|
| `${User.Name}` | 레이블을 적용하는 사용자의 표시 이름| **Richard Simone** |
| `${User.PrincipalName}` | 레이블을 적용하는 사용자의 AZURE AD UPN(사용자 계정 이름) | **rsimone \@ contoso.com** |
| `${Event.DateTime}` | 레이블을 적용하는 사용자의 로컬 표준 시간대에서 콘텐츠에 레이블이 지정되는 날짜 및 시간 | **2020/8/10 오후 1:30** |

> [!NOTE]
> 이러한 변수의 구문은 대소문자 구분입니다.

#### <a name="setting-different-visual-markings-for-word-excel-powerpoint-and-outlook"></a>Word, Excel, PowerPoint 및 Outlook에 대해 서로 다른 시각적 표시 설정

추가 변수로 텍스트 문자열에서 "If.App" 변수 문을 사용하여 Office 응용 프로그램 유형별로 시각적 표시를 구성하고 **Word,** **Excel,** **PowerPoint** 또는 **Outlook** 값을 사용하여 응용 프로그램 유형을 식별할 수 있습니다. 동일한 If.App 문에서 두 개 이상 지정하려는 경우 필요한 이러한 값을 약어로 지정할 수도 있습니다.

> [!NOTE]
> 완전한 기능을 위해 현재 Azure Information Protection 통합 레이블 지정 클라이언트에서만 지원되고 있는 Outlook에 대한 지침이 포함되어 있습니다.

다음 구문을 사용합니다.

```
${If.App.<application type>}<your visual markings text> ${If.End}
```

다른 동적 시각적 표시와 함께 구문은 대소문자 구분입니다.

예제:

- **Word 문서에 대한 헤더 텍스트만 설정:**

    `${If.App.Word}This Word document is sensitive ${If.End}`

    Word 문서 헤더에서만 레이블은 "This Word document is sensitive"라는 헤더 텍스트를 적용합니다. 다른 Office 응용 프로그램에는 헤더 텍스트가 적용되지 않습니다.

- **Word, Excel 및 Outlook에 대한 발자국 텍스트와 PowerPoint에 대해 다른 발자국어 텍스트를 설정할 수 있습니다.**

    `${If.App.WXO}This content is confidential. ${If.End}${If.App.PowerPoint}This presentation is confidential. ${If.End}`

    Word, Excel 및 Outlook에서 레이블은 "이 콘텐츠는 기밀입니다."라는 글자 텍스트를 적용합니다. PowerPoint에서 레이블은 "이 프레젠테이션은 기밀입니다."라는 글자 텍스트를 적용합니다.

- **Word 및 PowerPoint에 대해 특정 워터마크 텍스트를 설정한 다음 Word, Excel 및 PowerPoint에 대해 워터마크 텍스트를 지정합니다.**

    `${If.App.WP}This content is ${If.End}Confidential`

    Word 및 PowerPoint에서 레이블은 워터마크 텍스트 "This content is Confidential"을 적용합니다. Excel에서 레이블은 워터마크 텍스트 "Confidential"을 적용합니다. Outlook에서는 워터마크를 시각적 표시로 사용할 수 없는 워터마크 텍스트가 Outlook에서 적용되지 않습니다.

## <a name="require-users-to-apply-a-label-to-their-email-and-documents"></a>사용자가 전자 메일 및 문서에 레이블을 적용해야 합니다.

> [!IMPORTANT]
> 필수 레이블 지정으로도 알려져 있으며, 모든 플랫폼의 모든 앱이 현재 사용자의 전자 메일 및 문서에 레이블을 적용해야 의 정책 설정을 **지원하지는 않습니다.**
> 
> Azure Information Protection 통합 레이블 지정 [클라이언트는](https://docs.microsoft.com/azure/information-protection/rms-client/install-unifiedlabelingclient-app) 필수 레이블 지정을 지원하고 Office 앱에 [](#support-for-sensitivity-label-capabilities-in-apps) 기본 제공된 레이블 지정을 위해 이 페이지의 기능 섹션에 있는 표를 참조하세요.

이 정책 설정을 선택하면 정책이 할당된 사용자가 다음 시나리오에서 민감도 레이블을 선택하고 적용해야 합니다.

- Azure Information Protection 통합 레이블 지정 클라이언트의 경우:
    - 문서(Word, Excel, PowerPoint): 문서가 저장되거나 사용자가 문서를 닫을 때
    - 전자 메일(Outlook): 사용자가 당시에 사용자가 표시되지 않은 메시지를 보낼 때입니다.

- Office 앱에 기본 제공되는 레이블 지정:
    - 문서((Word, Excel, PowerPoint): 표시되지 않은 문서를 열거나 저장할 때
    - 전자 메일(Outlook): 사용자가 당시에 사용자가 표시되지 않은 전자 메일 메시지를 보낼 때

기본 제공 레이블 지정에 대한 추가 정보:

- 레이블이 지정되지 않은 문서를 열기 때문에 민감도 레이블을 추가하라는 메시지가 표시될 경우 레이블을 추가하거나 읽기 전용 모드로 문서를 열 수 있습니다.

- 필수 레이블 지정이 적용된 경우 사용자는 문서에서 민감도 레이블을 제거할 수 없지만 기존 레이블을 변경할 수 있습니다.

이 설정을 사용하는 경우에 대한 지침은 정책 설정에 대한 [정보를 참조하세요.](sensitivity-labels.md#what-label-policies-can-do)

## <a name="end-user-documentation"></a>최종 사용자 설명서

- [Office 내의 문서 및 전자 메일에 민감도 레이블 적용](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)

- [Office 파일에 민감도 레이블을 적용할 때의 알려진 문제](https://support.microsoft.com/en-us/office/known-issues-with-sensitivity-labels-in-office-b169d687-2bbd-4e21-a440-7da1b2743edc)
