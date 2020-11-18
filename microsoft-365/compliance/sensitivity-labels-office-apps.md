---
title: Office 앱의 민감도 레이블 사용
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
description: 사용자가 데스크톱, 모바일 및 웹의 Office 앱에서 민감도 레이블을 사용 하는 방법 및 민감도 레이블을 지 원하는 앱에 대해 알아봅니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: de005e40cf346c8dd6e02e0394272a97b186920f
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "49131111"
---
# <a name="use-sensitivity-labels-in-office-apps"></a>Office 앱의 민감도 레이블 사용

>*[보안 및 규정 준수를 위한 Microsoft 365 라이선싱 지침](https://aka.ms/ComplianceSD)*

Microsoft 365 준수 센터 또는 동등한 레이블 센터에서 민감도 레이블을 [게시](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) 한 경우 사용자가 만들거나 편집할 때 데이터를 분류 하 고 보호 하기 위해 Office 앱에 표시 되기 시작 합니다.

이 문서의 정보를 사용 하 여 Office 앱에서 민감도 레이블을 올바르게 관리 하는 데 도움을 받을 수 있습니다. 예를 들어 기본 제공 레이블을 지원 해야 하는 최소 버전의 앱을 식별 하 고 Azure Information Protection 통합 레이블 클라이언트 및 다른 앱 및 서비스와의 호환성을 이해 합니다.

## <a name="labeling-client-for-desktop-apps"></a>데스크톱 앱에 대 한 레이블 클라이언트

Windows 및 Mac 용 Office 데스크톱 앱에 기본으로 제공 되는 민감도 레이블을 사용 하려면 Office 구독 버전을 사용 해야 합니다. 이 레이블 클라이언트는 Office 2016 또는 Office 2019과 같은 독립 실행형 Office 버전을 지원 하지 않습니다.

Windows 컴퓨터에서 이러한 독립 실행형 버전의 Office와 함께 민감도 레이블을 사용 하려면 [Azure Information Protection 통합 레이블 클라이언트](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2)를 설치 합니다.

## <a name="support-for-sensitivity-label-capabilities-in-apps"></a>앱의 민감도 레이블 기능 지원

다음 표에는 각 기능에 대 한 기본 제공 레이블을 사용 하 여 민감도 레이블을 지원 하기 위해 해당 앱에 필요한 최소 Office 버전이 나와 있습니다. 또는 레이블 기능이 공개 미리 보기에 있거나 이후 릴리스에 대 한 검토 중에 있습니다. 향후 릴리스에 대 한 자세한 내용을 보려면 [Microsoft 365 로드맵을](https://aka.ms/MIPC/Roadmap) 사용 합니다.

새 버전의 Office 앱은 다양 한 업데이트 채널에 대해 서로 다른 시간에 사용할 수 있습니다. 관심 있는 새 레이블 기능을 테스트할 수 있도록 업데이트 채널을 구성 하는 방법을 비롯 한 자세한 내용은 [Microsoft 365 용 업데이트 채널 개요](https://docs.microsoft.com/DeployOffice/overview-update-channels)를 참조 하세요. 개인 미리 보기에 있는 새로운 기능은 표에는 포함 되어 있지 않지만 이러한 미리 보기에 참여 하려면 먼저 조직에서 [Microsoft Information Protection nominating 미리 보기 프로그램](https://aka.ms/mip-preview)을 사용할 수 있습니다.

> [!NOTE]
> Office 앱에 대 한 업데이트 채널의 이름이 최근에 변경 되었습니다. 예를 들어 이제 월별 채널이 현재 채널 이며 Office 참가자가 이제 베타 채널입니다. 자세한 내용은 [업데이트 채널의 Microsoft 365 앱 변경 사항을](https://docs.microsoft.com/deployoffice/update-channels-changes)참조 하세요.

Windows 컴퓨터 에서만 실행 되는 Azure Information Protection 통합 레이블 클라이언트를 설치할 때 추가 기능을 사용할 수 있습니다. 자세한 내용은 [Windows 컴퓨터에 대 한 레이블 클라이언트 비교](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#compare-the-labeling-clients-for-windows-computers)를 참조 하십시오.

### <a name="sensitivity-label-capabilities-in-word-excel-and-powerpoint"></a>Word, Excel 및 PowerPoint의 민감도 레이블 기능

IOS 및 Android의 경우: 나열 되는 최소 버전은 [Office 앱](https://www.microsoft.com/en-us/microsoft-365/blog/2020/02/19/new-office-app-android-ios-available/)에서도 민감도 레이블 기능을 지원 합니다.

|기능                                                                                                        |Windows 데스크톱 |Mac 데스크톱 |iOS    |Android      |웹                                                         |
|------------------------------------------------------------------------------------------------------------------|----------------|------------|-------|-------------|------------------------------------------------------------|
|[수동으로 레이블 적용, 변경 또는 제거](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [예-옵트인](sensitivity-labels-sharepoint-onedrive-files.md) |
|[기본 레이블 적용](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [예-옵트인](sensitivity-labels-sharepoint-onedrive-files.md)                                                        |
|[레이블을 변경 하려면 사유 필요](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [예-옵트인](sensitivity-labels-sharepoint-onedrive-files.md) |
|[사용자 지정 도움말 페이지에 대 한 도움말 링크 제공](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [예-옵트인](sensitivity-labels-sharepoint-onedrive-files.md) |
|[콘텐츠 표시](sensitivity-labels.md#what-sensitivity-labels-can-do)                                              | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [예-옵트인](sensitivity-labels-sharepoint-onedrive-files.md) |
|[변수가 있는 동적 표식](#dynamic-markings-with-variables)                                              | 2010 +           | 16.42 +     | 2.42 + | 16.0.13328 + | 검토 중 |
|[지금 권한 할당](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [예-옵트인](sensitivity-labels-sharepoint-onedrive-files.md) |
|[사용자가 권한을 할당하도록 허용](encryption-sensitivity-labels.md#let-users-assign-permissions)                     |2004 + | 16.35 +   | 검토 중   | 검토 중         | 검토 중                                                        |
|[레이블 분석을 사용 하 여 레이블 사용을 확인](label-analytics.md) 하 고 관리자를 위해 데이터 보내기                      | 검토 중            | 검토 중        | 검토 중   | 검토 중         | 검토 중                                                        |
|[사용자가 전자 메일 및 문서에 레이블을 적용 해야 합니다.](sensitivity-labels.md#what-label-policies-can-do)   | 검토 중            | 검토 중        | 검토 중   | 검토 중         | 검토 중                                                        |
|[민감도 레이블을 콘텐츠에 자동으로 적용](apply-sensitivity-label-automatically.md)                    | 2009 +                                  | Word 및 PowerPoint에 대 한 미리 보기: [현재 채널로 롤백 (미리 보기)](https://office.com/insider) | 검토 중 | 검토 중 | [예-옵트인](sensitivity-labels-sharepoint-onedrive-files.md) |
|레이블이 지정 되 고 보호 된 문서에서 [자동 저장](https://support.office.com/article/6d6bd723-ebfd-4e40-b5f6-ae6e8088f7a5) 및 [공동](https://support.office.com/article/ee1509b4-1f6e-401e-b04a-782d26f564a4) 작성 지원 | 검토 중 | 검토 중 | 검토 중 | 검토 중 | [예-옵트인](sensitivity-labels-sharepoint-onedrive-files.md) |
|

### <a name="sensitivity-label-capabilities-in-outlook"></a>Outlook의 민감도 레이블 기능

|기능                                                                                                        |Windows 데스크톱의 Outlook |Mac 데스크톱 Outlook  |IOS의 Outlook |Android의 Outlook |웹용 Outlook |
|------------------------------------------------------------------------------------------------------------------|---------------------------|------------------------|---------------|-------------------|-------------------|
|[수동으로 레이블 적용, 변경 또는 제거](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | 예               |
|[기본 레이블 적용](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | 예               |
|[레이블을 변경 하려면 사유 필요](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | 예               |
|[사용자 지정 도움말 페이지에 대 한 도움말 링크 제공](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | 예               |
|[콘텐츠 표시](sensitivity-labels.md#what-label-policies-can-do)                                              | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | 예               |
|[변수가 있는 동적 표식](#dynamic-markings-with-variables)                                              | 검토 중                     | 검토 중                 | 검토 중         | 검토 중           | 검토 중               |
|[지금 권한 할당](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | 예               |
|[사용자가 권한을 할당하도록 허용](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | 1910+                     | 16.21 +                 | 4.7.1 +         | 4.0.39 +           | 예               |
|[레이블 분석을 사용 하 여 레이블 사용을 확인](label-analytics.md) 하 고 관리자를 위해 데이터 보내기                      | 검토 중                       | 검토 중                    | 검토 중           | 검토 중               | 검토 중               |
|[사용자가 전자 메일 및 문서에 레이블을 적용 해야 합니다.](sensitivity-labels.md#what-label-policies-can-do)   | 검토 중                       | 검토 중                    | 검토 중           | 검토 중               | 검토 중               |
|[민감도 레이블을 콘텐츠에 자동으로 적용](apply-sensitivity-label-automatically.md)                    | 2009 +                      | 검토 중                    | 검토 중           | 검토 중               | 예 |
|

## <a name="office-built-in-labeling-client-and-other-labeling-solutions"></a>Office 기본 제공 레이블 클라이언트 및 기타 레이블 솔루션

클라이언트에서 다음 관리 센터 로부터 민감도 레이블 및 민감도 레이블 정책 설정을 다운로드 하는 Office 기본 제공 레이블:

- Microsoft 365 규정 준수 센터
- Microsoft 365 보안 센터
- Office 365 보안 및 준수 센터

Office 기본 제공 레이블 클라이언트를 사용 하려면 나열 된 관리 센터와 [office의 지원 되는 버전](#support-for-sensitivity-label-capabilities-in-apps)중 하나에서 사용자에 게 하나 이상의 [레이블 정책이 게시](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) 되어 있어야 합니다.

이러한 두 조건을 충족 하지만 Office 기본 제공 레이블 클라이언트를 해제 해야 하는 경우에는 다음 그룹 정책 설정을 사용 합니다.

1. **사용자 구성/관리 템플릿/Microsoft Office 2016/보안 설정** 으로 이동 합니다.

2. 설정 **민감도 레이블을 적용 하 고 0으로 표시 하려면 Office의 민감도 기능을 사용** 합니다. **0** 
 
그룹 정책을 사용 하거나 [Office 클라우드 정책 서비스](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service)를 사용 하 여이 설정을 배포 합니다. Office 앱을 다시 시작 하면 설정이 적용 됩니다.

### <a name="office-built-in-labeling-client-and-the-azure-information-protection-client"></a>Office 기본 제공 레이블 클라이언트 및 Azure Information Protection 클라이언트

사용자가 Azure Information Protection 클라이언트 ([통합 레이블 클라이언트](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2) 또는 [클래식 클라이언트](https://docs.microsoft.com/azure/information-protection/rms-client/aip-client)) 중 하나를 사용 하는 경우 기본적으로 Office 앱에서 기본 제공 레이블 클라이언트를 사용할 수 없게 됩니다. 

Office 앱의 Azure Information Protection 클라이언트 대신 기본 제공 레이블을 사용 하려면 이전 섹션의 지침을 사용 하 되, 그룹 정책 설정을 사용 하 여 민감도 레이블을 **1** 로 **적용 하 고 확인** 합니다. 

또는 Office 추가 기능을 사용 하지 않도록 설정 하거나 제거 **합니다.** 이 메서드는 단일 컴퓨터 및 임시 테스트에 적합 합니다. 자세한 내용은 [Office 프로그램에서 추가 기능 보기, 관리 및 설치](https://support.office.com/article/16278816-1948-4028-91e5-76dca5380f8d)를 참조 하세요. 

이 Office 추가 기능을 사용 하지 않도록 설정 하거나 제거 하면 Office 앱 외부에 있는 파일에 계속 레이블을 지정할 수 있도록 Azure Information Protection 클라이언트가 설치 된 상태로 유지 됩니다. 예를 들어 파일 탐색기 또는 PowerShell을 사용 합니다.

Azure Information Protection 클라이언트 및 Office 기본 제공 레이블 클라이언트에서 지 원하는 기능에 대 한 자세한 내용은 Azure Information Protection 설명서에서 [Windows 컴퓨터에 사용할 레이블 지정 클라이언트 선택을](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#choose-which-labeling-client-to-use-for-windows-computers) 참조 하십시오.

## <a name="office-file-types-supported"></a>지원 되는 Office 파일 형식

Word, Excel 및 PowerPoint 파일에 대 한 기본 제공 레이블을 지정 하는 Office 앱은 Open XML 형식 (예: .docx 및 .xlsx)을 지원 하지만 Microsoft Office 97-2003 형식 (예: .doc 및 .xls)이 아닙니다. 기본 제공 레이블 지정에 지원 되지 않는 파일 형식을 사용 하는 경우 Office 앱에서 **민감도** 단추를 사용할 수 없습니다.

Azure Information Protection 통합 레이블 클라이언트는 Open XML 형식과 Microsoft Office 97-2003 형식을 모두 지원 합니다. 자세한 내용은 해당 클라이언트의 관리 가이드에서 [Azure Information Protection 통합 레이블 클라이언트에서 지 원하는 파일 형식을](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-file-types) 참조 하세요.

다른 레이블 솔루션의 경우 지원 되는 파일 형식에 대 한 설명서를 확인 하세요.

## <a name="protection-templates-and-sensitivity-labels"></a>보호 서식 파일 및 민감도 레이블

Office 365 메시지 암호화에 대해 정의 하는 것과 같은 관리자 정의 [보호 템플릿은](https://docs.microsoft.com/azure/information-protection/configure-policy-templates)기본 제공 레이블을 사용 하는 경우 office 앱에 표시 되지 않습니다. 이러한 단순화 된 환경은 암호화를 사용 하도록 설정 된 민감도 레이블에 동일한 설정이 포함 되므로 보호 템플릿을 선택할 필요가 없다는 것을 나타냅니다.

기존 보호 템플릿을 레이블로 변환 해야 하는 경우 Azure portal 및 다음 지침을 사용 [하 여 서식 파일을 레이블로 변환](https://docs.microsoft.com/azure/information-protection/configure-policy-templates#to-convert-templates-to-labels)합니다.

## <a name="information-rights-management-irm-options-and-sensitivity-labels"></a>IRM (정보 권한 관리) 옵션 및 민감도 레이블

민감도 레이블 암호화를 적용 하도록 구성한 사용자의 복잡도를 제거 하 여 고유한 암호화 설정을 지정 합니다. 대부분의 Office 앱에서 이러한 개별 암호화 설정은 IRM (정보 권한 관리) 옵션을 사용 하 여 사용자가 수동으로 구성할 수 있습니다. 예를 들어 Windows 앱에 대해 다음을 수행 합니다.

- 문서의 경우: **파일**  >  **정보**  >  **보호 문서**  >  **제한 액세스**
- 전자 메일의 경우: **Options** 탭에서 **Encrypt** > 합니다. 
  
처음에 문서 또는 전자 메일에 레이블을 지정 하면 사용자는 레이블 구성 설정을 자체 암호화 설정으로 무시할 수 있습니다. 예시:

- 사용자가 문서에 **기밀 \ 모든 직원** 레이블을 적용 하며,이 레이블은 조직의 모든 사용자에 대해 암호화 설정을 적용 하도록 구성 됩니다. 이 사용자는 조직 외부의 사용자에 대 한 액세스를 제한 하도록 IRM 설정을 수동으로 구성 합니다. 최종 결과는 **기밀 \ 모든 직원** 및 암호화 됨 이라는 레이블이 지정 된 문서이 고 조직의 사용자가 예상 대로 열 수 없습니다.

- 사용자가 **기밀 \ 받는 사람 전용** 레이블을 전자 메일에 적용 하 고이 전자 메일은 **전달 하지** 않음에 대 한 암호화 설정을 적용 하도록 구성 됩니다. 이 사용자는 전자 메일이 무제한으로 표시 되도록 IRM 설정을 수동으로 구성 합니다. 최종 결과는 **기밀 \ 받는 사람 전용** 레이블을 갖고 있더라도 받는 사람이 전자 메일을 전달할 수 있습니다.

- 사용자가 문서에 **일반** 레이블을 적용 하며이 레이블은 암호화를 적용 하도록 구성 되지 않습니다. 이 사용자는 문서에 대 한 액세스를 제한 하기 위해 IRM 설정을 수동으로 구성 합니다. 최종 결과는 레이블이 **일반** 이지만 일부 사용자가 예상 대로 열 수 없도록 암호화도 적용 되는 문서입니다.

문서 또는 전자 메일에 이미 레이블이 지정 되어 있는 경우에는 콘텐츠가 아직 암호화 되지 않았거나 [사용 권한](https://docs.microsoft.com/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions) 내보내기 또는 모든 권한이 있는 경우 사용자가 이러한 작업을 수행할 수 있습니다. 

의미 있는 보고를 사용 하 여 보다 일관성 있는 레이블 환경을 제공 하려면 문서 보호에 레이블을 적용 하는 데 사용할 수 있는 적절 한 레이블과 지침을 제시 합니다. 예시:

- 사용자가 자신의 사용 권한을 할당 해야 하는 경우 사용자에 [게 고유한 사용 권한을 할당](encryption-sensitivity-labels.md#let-users-assign-permissions)하는 데 사용할 수 있는 레이블을 제공 합니다. 

- 사용자가 암호화를 적용 하는 레이블을 선택한 후 수동으로 암호화를 제거 하는 대신, 사용자에 게 동일한 분류의 레이블이 필요한 경우에는 암호화를 사용 하지 않는 sublabel 대체 방법을 제공 합니다. 예:
    - **기밀 \ 모든 직원**
    - **기밀 \ 모든 사용자 (암호화 안 함)**

> [!NOTE]
> 사용자가 SharePoint 또는 OneDrive에 저장 되어 있는 레이블이 지정 된 문서에서 암호화를 수동으로 제거 하 고 [sharepoint 및 onedrive에서 Office 파일에 대 한 민감도 레이블을 사용 하도록 설정한](sensitivity-labels-sharepoint-onedrive-files.md)경우 다음에 문서를 액세스 하거나 다운로드할 때 레이블 암호화가 자동으로 복원 됩니다. 

## <a name="apply-sensitivity-labels-to-files-emails-and-attachments"></a>파일, 전자 메일 및 첨부 파일로 민감도 레이블 적용

사용자는 각 문서 또는 전자 메일에 대해 한 번에 하나의 레이블만 적용할 수 있습니다.

첨부 파일이 포함 된 전자 메일 메시지에 레이블을 지정 하면 첨부 파일은 다음과 같은 한 가지 예외를 제외 하 고 레이블을 상속 하지 않습니다.

- 이 첨부 파일은 암호화를 적용 하지 않는 레이블이 있는 Office 문서 이며 전자 메일 메시지에 적용 하는 레이블은 암호화를 적용 합니다. 이 경우 이메일로 받은 Office 문서는 해당 암호화 설정으로 전자 메일의 레이블을 상속 받습니다.

방법 

- 첨부 파일에 레이블이 있으면 원래 적용 된 레이블을 유지 합니다.
- 레이블을 사용 하지 않고 첨부 파일을 암호화 하면 암호화는 유지 되지만 레이블이 지정 되지 않습니다.
- 첨부 파일에 레이블이 없는 경우에는 레이블이 없는 상태로 유지 됩니다.

## <a name="sensitivity-label-compatibility"></a>민감도 레이블 호환성

**Rms-인식 된 앱을 사용** 하는 경우: 민감도 레이블을 지원 하지 않는 [rms-인식 된 응용 프로그램](https://docs.microsoft.com/azure/information-protection/requirements-applications#rms-enlightened-applications) 에서 레이블이 지정 되 고 암호화 된 문서 또는 전자 메일을 열면 앱에서 여전히 암호화 및 권한 관리를 적용 합니다.

**Azure Information protection 클라이언트** 를 사용 하 여 Azure information protection 클라이언트를 사용 하 여 Office 기본 제공 레이블 클라이언트와 문서 및 전자 메일에 적용 하는 민감도 레이블을 보고 변경할 수 있습니다.

**다른 버전의 office**: 권한 있는 사용자는 다른 버전의 office에서 레이블이 지정 된 문서와 전자 메일을 열 수 있습니다. 그러나 지원 되는 Office 버전에서 또는 Azure Information Protection 클라이언트를 사용 하는 경우에만 레이블을 보거나 변경할 수 있습니다. 지원 되는 Office 앱 버전은 [이전 섹션](#support-for-sensitivity-label-capabilities-in-apps)에 나와 있습니다.

## <a name="support-for-sharepoint-and-onedrive-files-protected-by-sensitivity-labels"></a>민감도 레이블로 보호 되는 SharePoint 및 OneDrive 파일에 대 한 지원

SharePoint 또는 OneDrive의 문서를 웹에 있는 office 기본 제공 레이블 클라이언트를 사용 하려면 [sharepoint 및 onedrive에서 office 파일에 대 한 민감도 레이블을 사용 하도록 설정](sensitivity-labels-sharepoint-onedrive-files.md)했는지 확인 합니다.

## <a name="support-for-external-users-and-labeled-content"></a>외부 사용자 및 레이블이 지정 된 콘텐츠 지원

문서나 전자 메일에 레이블을 지정 하면 해당 레이블은 테 넌 트와 레이블 GUID를 포함 하는 메타 데이터로 저장 됩니다. 민감도 레이블을 지 원하는 Office 앱에서 레이블이 지정 된 문서 또는 전자 메일을 열면이 메타 데이터를 읽고 사용자가 같은 테 넌 트에 속해 있는 경우에만 레이블이 앱에 표시 됩니다. 예를 들어 Word, PowerPoint 및 Excel의 기본 제공 레이블에서는 상태 표시줄에 레이블 이름이 표시 됩니다. 

즉, 다른 레이블 이름을 사용 하는 다른 조직과 문서를 공유 하는 경우 각 조직이 적용 되며 문서에 적용 된 자체 레이블이 표시 될 수 있습니다. 그러나 적용 된 레이블에서 다음 요소는 조직 외부의 사용자에 게 표시 됩니다.

- 콘텐츠 표식입니다. 레이블이 머리글, 바닥글 또는 워터 마크를 적용 하는 경우 이러한 항목은 콘텐츠에 직접 추가 되며 사용자가 수정 하거나 삭제할 때까지 계속 표시 됩니다.

- 암호화를 적용 한 레이블에서 기본 보호 서식 파일의 이름과 설명을 입력 합니다. 이 정보는 문서 위쪽의 메시지 표시줄에 표시 되며, 문서를 열 수 있는 사용자에 대 한 정보 및 해당 문서에 대 한 사용 권한을 제공 합니다.

### <a name="sharing-encrypted-documents-with-external-users"></a>암호화 된 문서를 외부 사용자와 공유

자신의 조직에 있는 사용자에 대 한 액세스를 제한 하는 것 외에도 Azure Active Directory에 계정을 가진 다른 모든 사용자에 대 한 액세스를 확장할 수 있습니다. 사용자가 인증 된 후 모든 Office 앱 및 기타 [RMS-인식 된 응용 프로그램](https://docs.microsoft.com/azure/information-protection/requirements-applications#rms-enlightened-applications) 에서 암호화 된 문서를 열 수 있습니다.

외부 사용자가 Azure Active Directory에 계정이 없는 경우 테 넌 트에서 guest 계정을 만들 수 있습니다. 전자 메일 주소에 대해 이미 사용 중인 전자 메일 주소를 지정할 수 있습니다. 예를 들면 Gmail 주소입니다. [Sharepoint 및 onedrive에서 Office 파일에 대 한 민감도 레이블을 사용 하도록 설정한](sensitivity-labels-sharepoint-onedrive-files.md)경우이 게스트 계정을 사용 하 여 Sharepoint 또는 onedrive의 공유 문서에 액세스할 수도 있습니다.

또한 외부 사용자가 Windows에서 Microsoft 365 앱 ([이전 Office 365 앱](https://docs.microsoft.com/deployoffice/name-change))을 사용 하는 경우, 이제 Android (버전 13029 +) 및 iOS (버전 1385219 +)와 함께 암호화 된 문서에 microsoft 계정을 사용할 수 있습니다. MacOS에 대해서는이 기능이 아직 지원 되지 않습니다. 예를 들어, 사용자는 암호화 된 문서를 함께 공유 하 고, 암호화 설정은 Gmail 전자 메일 주소를 지정 합니다. 이 사용자는 Gmail 전자 메일 주소를 사용 하는 자신의 Microsoft 계정을 만들 수 있습니다. 그런 다음이 계정으로 로그인 한 후 해당 사용자에 대해 지정 된 사용 제한에 따라 문서를 열고 편집할 수 있습니다. 이 시나리오의 연습 예제를 보려면 보호 된 [문서 열기 및 편집](https://docs.microsoft.com/azure/information-protection/secure-collaboration-documents#opening-and-editing-the-protected-document)을 참조 하십시오.

> [!NOTE]
> Microsoft 계정의 전자 메일 주소는 암호화 설정에 대 한 액세스를 제한 하기 위해 지정 된 전자 메일 주소와 일치 해야 합니다.

Microsoft 계정이 있는 사용자가이 방법으로 암호화 된 문서를 열면 이름이 같은 게스트 계정이 없는 경우 테 넌 트에 대 한 게스트 계정이 자동으로 만들어집니다. 게스트 계정이 있으면 Windows 데스크톱 앱에서 암호화 된 문서를 열 뿐 아니라 브라우저 (웹에서 Office)를 사용 하 여 SharePoint 및 OneDrive에서 문서를 여는 데 사용할 수 있습니다. 

그러나 자동 게스트 계정은 복제 대기 시간으로 인해 즉시 만들어지지 않습니다. 레이블 암호화 설정의 일부로 개인 전자 메일 주소를 지정 하는 경우 Azure Active Directory에서 해당 하는 게스트 계정을 만드는 것이 좋습니다. 그런 다음 이러한 사용자에 게이 계정을 사용 하 여 조직에서 암호화 된 문서를 여는 것을 알리는 것을 허용 합니다.

> [!TIP]
> 외부 사용자가 지원 되는 Office 클라이언트 앱을 사용 하 고 있는지 확실 하지 않으므로, 게스트 계정을 만든 후 SharePoint 및 OneDrive에서 링크를 공유 하는 것은 외부 사용자와의 안전한 공동 작업을 지원 하기 위한 보다 안정적인 방법입니다.

## <a name="when-office-apps-apply-content-marking-and-encryption"></a>Office 앱에서 콘텐츠 표시 및 암호화를 적용 하는 경우

Office 앱은 사용 하는 앱에 따라 콘텐츠 표시 및 암호화를 민감도 레이블과 다르게 적용 합니다.

| 앱 | 콘텐츠 표시 | 암호화 |
| --- | --- | --- |
| 모든 플랫폼의 Word, Excel, PowerPoint | 즉시 | 즉시 |
| PC 및 Mac용 Outlook | Exchange Online이 전자 메일을 보낸 후 | 즉시 |
| Mac, iOS 및 Android용 Outlook | Exchange Online이 전자 메일을 보낸 후 | Exchange Online이 전자 메일을 보낸 후 |
|

Office 앱 외부의 파일에 민감도 레이블을 적용 하는 솔루션은 레이블 메타 데이터를 파일에 적용 하 여이를 수행 합니다. 이 시나리오에서는 레이블의 구성에서 콘텐츠 표시가 파일에 삽입 되지 않지만 암호화가 적용 됩니다. 

Office 데스크톱 앱에서 해당 파일을 열면 콘텐츠 표시가 Azure Information Protection 통합 레이블 클라이언트에 의해 자동으로 적용 됩니다. 데스크톱, 모바일 또는 웹 앱에 대 한 기본 제공 레이블을 사용 하는 경우에는 콘텐츠 표시가 자동으로 적용 되지 않습니다.

Office 앱 외부에 민감도 레이블을 적용 하는 경우 다음이 포함 됩니다.

- Azure Information Protection 통합 레이블 클라이언트의 스캐너, 파일 탐색기 및 PowerShell 

- SharePoint 및 OneDrive에 대 한 자동 레이블 지정 정책

- Power BI에서 레이블이 지정 되 고 암호화 된 데이터 내보내기

- Microsoft Cloud App Security

이러한 시나리오에서 Office 앱을 사용 하는 경우 기본 제공 레이블이 지정 된 사용자는 현재 레이블을 일시적으로 제거 하거나 바꾼 다음 원래 레이블을 다시 적용 하 여 레이블의 내용 표시를 적용할 수 있습니다.

### <a name="dynamic-markings-with-variables"></a>변수가 있는 동적 표식

> [!IMPORTANT]
> 현재 모든 플랫폼의 모든 앱이 머리글, 바닥글 및 워터 마크에 대해 지정할 수 있는 동적 콘텐츠 표식을 지 원하는 것은 아닙니다. 이 기능을 지원 하지 않는 앱에서는 변수를 확인 하는 대신 레이블 구성에 지정 된 원래 텍스트로 표시를 적용 합니다.
> 
> Azure Information Protection 통합 레이블 클라이언트는 동적 표시를 지원 합니다. Office에 기본 제공 되는 레이블을 지정 하려면이 페이지의 [기능](#support-for-sensitivity-label-capabilities-in-apps) 섹션에 있는 표를 참조 하세요.

콘텐츠 표시에 대 한 민감도 레이블을 구성할 때 머리글, 바닥글 또는 워터 마크에 대 한 텍스트 문자열에 다음 변수를 사용할 수 있습니다.

| 변수 | 설명 | 레이블이 적용 된 경우의 예 |
| -------- | ----------- | ------- |
| `${Item.Label}` | 현재 레이블 표시 이름 | **일반**|
| `${Item.Name}` | 현재 파일 이름 또는 전자 메일 제목 | **Sales.docx** |
| `${Item.Location}` | 문서의 현재 경로 및 파일 이름 또는 전자 메일에 대 한 전자 메일 제목입니다. | **\\\Sales\2020\Q3\Report.docx**|
| `${User.Name}` | 현재 사용자 표시 이름  | **Richard a 1** |
| `${User.PrincipalName}` | 현재 사용자의 Azure AD UPN (사용자 계정 이름) | **rcontoso.com 1 \@** |
| `${Event.DateTime}` | 현지 표준 시간대의 현재 날짜 및 시간입니다. | **오후 8/10/2020 1:30** |

> [!NOTE]
> 이러한 변수에 대 한 구문은 대/소문자를 구분 합니다.

## <a name="end-user-documentation"></a>최종 사용자 설명서

- [Office 내의 문서 및 전자 메일에 민감도 레이블 적용](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)

- [Office 파일에 민감도 레이블을 적용할 때의 알려진 문제](https://support.microsoft.com/en-us/office/known-issues-with-sensitivity-labels-in-office-b169d687-2bbd-4e21-a440-7da1b2743edc)
