---
title: Office 앱의 민감도 레이블
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
description: 사용자가 데스크톱에 대 한 Office 앱, 모바일 용 Office 앱 및 웹 용 Office 앱에서 민감도 레이블을 사용 하는 방법에 대해 알아봅니다. 민감도 레이블을 지 원하는 앱을 찾습니다.
ms.openlocfilehash: 092c8510acac5cafa6417f93eae19731db5df270
ms.sourcegitcommit: af7950d9674f0eab3aee03f9afccff9ca2f4709a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40970956"
---
# <a name="sensitivity-labels-in-office-apps"></a>Office 앱의 민감도 레이블

이 문서에서는 다음에 대해 설명합니다.

- 전자 메일, 파일 및 첨부 파일에 민감도 레이블을 적용 하기 전 환경의 요구 사항입니다.
- 각 Office 앱에서 지 원하는 민감도 레이블 기능
- 민감도 레이블을 Office 앱에서 작동 하는 다른 Microsoft 보안 및 준수 기술과 결합 하면 어떻게 될까요?
- 조직의 사용자가 Windows 용 Office 앱 및 웹 용 Office 앱으로 작업할 때 민감도 레이블을 사용할 수 있는 방법
- 우편물 민감도 레이블로 시작 하 여 조직의 사용자를 가져올 수 있는 위치입니다.

## <a name="subscription-and-licensing-requirements-for-sensitivity-labels"></a>민감도 레이블의 구독 및 라이선스 요구 사항

사용자에 게 다음 라이선스 중 하나 이상이 할당 되어 있어야 합니다.

- [Microsoft 365 E3](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) 이상

- [Office 365 E3](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e3-business-software) 이상

- [Azure Information Protection Premium P1](https://azure.microsoft.com/pricing/details/information-protection/) 이상

Office 기본 제공 레이블 클라이언트는 Office 구독 버전의 민감도 레이블을 지원 합니다. 이 레이블 클라이언트는 Office 2016 또는 Office 2019과 같은 독립 실행형 Office 버전을 지원 하지 않습니다. Windows 컴퓨터에서 다음 버전의 Office와 함께 민감도 레이블을 사용 하려면 Azure Information Protection 통합 레이블 클라이언트를 설치 합니다.

자동 또는 권장 민감도 레이블을 사용 하려면 사용자에 게 다음 라이선스 중 하나가 필요 합니다.

- [Microsoft 365 E5](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) 이상

- [Office 365 E5](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software) 이상

- [Azure Information Protection Premium P2](https://azure.microsoft.com/pricing/details/information-protection/)

## <a name="support-for-sensitivity-label-capabilities-in-word-excel-and-powerpoint"></a>Word, Excel 및 PowerPoint에서의 민감도 레이블 기능에 대한 지원

다음 표에는 각 기능에 대 한 기본 제공 레이블을 사용 하 여 민감도 레이블을 지원 하기 위해 해당 앱에 필요한 최소 버전이 나와 있습니다.

Windows 컴퓨터 에서만 실행 되는 Azure Information Protection 통합 레이블 클라이언트를 설치할 때 추가 기능을 사용할 수 있습니다. 자세한 내용은 [Windows 컴퓨터에 대 한 레이블 클라이언트 비교](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#compare-the-labeling-clients-for-windows-computers)를 참조 하십시오.

|기능                                                                                                        |Windows 데스크톱 |Mac 데스크톱 |iOS    |Android      |웹                                                         |
|------------------------------------------------------------------------------------------------------------------|----------------|------------|-------|-------------|------------------------------------------------------------|
|[수동으로 레이블 적용, 변경 또는 제거](https://support.office.com/article/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [미리 보기](sensitivity-labels-sharepoint-onedrive-files.md) |
|[기본 레이블 적용](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | 검토 중                                                        |
|[레이블을 변경 하려면 사유 필요](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [미리 보기](sensitivity-labels-sharepoint-onedrive-files.md) |
|[사용자 지정 도움말 페이지에 대 한 도움말 링크 제공](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [미리 보기](sensitivity-labels-sharepoint-onedrive-files.md) |
|[콘텐츠 표시](sensitivity-labels.md#what-label-policies-can-do)                                              | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [미리 보기](sensitivity-labels-sharepoint-onedrive-files.md) |
|[지금 권한 할당](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+          | 16.21 +     | 2.21+ | 16.0.11231+ | [미리 보기](sensitivity-labels-sharepoint-onedrive-files.md) |
|[사용자가 권한을 할당하도록 허용](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | 검토 중            | 검토 중        | 검토 중   | 검토 중         | 검토 중                                                        |
|[레이블 분석을 사용 하 여 레이블 사용을 확인](label-analytics.md) 하 고 관리자를 위해 데이터 보내기                      | 검토 중            | 검토 중        | 검토 중   | 검토 중         | 검토 중                                                        |
|
  [사용자가 전자 메일 및 문서에 레이블을 적용하도록 요구](sensitivity-labels.md#what-label-policies-can-do)   | 검토 중            | 검토 중        | 검토 중   | 검토 중         | 검토 중                                                        |
|[민감도 레이블을 콘텐츠에 자동으로 적용](apply-sensitivity-label-automatically.md)                    | 미리 보기: [Office 참가자](https://office.com/insider)                                  | 검토 중 | 검토 중 | 검토 중 | [미리 보기](sensitivity-labels-sharepoint-onedrive-files.md) |
|레이블이 지정 되 고 보호 된 문서에서 [자동 저장](https://support.office.com/article/6d6bd723-ebfd-4e40-b5f6-ae6e8088f7a5) 및 [공동](https://support.office.com/article/ee1509b4-1f6e-401e-b04a-782d26f564a4) 작성 지원 | 검토 중 | 검토 중 | 검토 중 | 검토 중 | [미리 보기](sensitivity-labels-sharepoint-onedrive-files.md) |
|

## <a name="support-for-sensitivity-label-capabilities-in-outlook"></a>Outlook에서의 민감도 레이블 기능에 대한 지원

다음 표에는 각 기능에 대해 해당 앱에 필요한 최소 버전이 나와 있습니다.

Windows 컴퓨터 에서만 실행 되는 Azure Information Protection 통합 레이블 클라이언트를 설치할 때 추가 기능을 사용할 수 있습니다. 자세한 내용은 [Windows 컴퓨터에 대 한 레이블 클라이언트 비교](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#compare-the-labeling-clients-for-windows-computers)를 참조 하십시오.

|기능                                                                                                        |Windows 데스크톱의 Outlook |Mac 데스크톱 Outlook  |IOS의 Outlook |Android의 Outlook |웹용 Outlook |
|------------------------------------------------------------------------------------------------------------------|---------------------------|------------------------|---------------|-------------------|-------------------|
|[수동으로 레이블 적용, 변경 또는 제거](https://support.office.com/article/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+                     | 16.21 +                 | 4.71 +         | 4.0.39 +           | 예               |
|[기본 레이블 적용](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+                     | 16.21 +                 | 4.71 +         | 4.0.39 +           | 예               |
|[레이블을 변경 하려면 사유 필요](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+                     | 16.21 +                 | 4.71 +         | 4.0.39 +           | 예               |
|[사용자 지정 도움말 페이지에 대 한 도움말 링크 제공](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+                     | 16.21 +                 | 4.71 +         | 4.0.39 +           | 예               |
|[콘텐츠 표시](sensitivity-labels.md#what-label-policies-can-do)                                              | 1910+                     | 16.21 +                 | 4.71 +         | 4.0.39 +           | 예               |
|[지금 권한 할당](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+                     | 16.21 +                 | 4.71 +         | 4.0.39 +           | 예               |
|[사용자가 권한을 할당하도록 허용](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | 1910+                     | 16.21 +                 | 4.71 +         | 4.0.39 +           | 예               |
|[레이블 분석을 사용 하 여 레이블 사용을 확인](label-analytics.md) 하 고 관리자를 위해 데이터 보내기                      | 검토 중                       | 검토 중                    | 검토 중           | 검토 중               | 검토 중               |
|
  [사용자가 전자 메일 및 문서에 레이블을 적용하도록 요구](sensitivity-labels.md#what-label-policies-can-do)   | 검토 중                       | 검토 중                    | 검토 중           | 검토 중               | 검토 중               |
|[민감도 레이블을 콘텐츠에 자동으로 적용](apply-sensitivity-label-automatically.md)                    | 검토 중                       | 검토 중                    | 검토 중           | 검토 중               | 미리 보기: [대상 릴리스로](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide) 롤업 |
|

## <a name="about-the-office-built-in-labeling-client"></a>Office 기본 제공 레이블 클라이언트 정보

Office 기본 제공 레이블 클라이언트는 다음 관리 센터에서 레이블 및 정책 설정을 다운로드 합니다.

- Office 365 보안 및 준수 센터

- Microsoft 365 보안 센터

- Microsoft 365 규정 준수 센터

Office 기본 제공 레이블 클라이언트를 사용 하려면 나열 된 관리 센터 중 하나의 사용자에 게 하나 이상의 [레이블 정책이 게시](sensitivity-labels.md#what-label-policies-can-do) 되어 있어야 합니다.

그러나 사용자에 게 Azure Information Protection 클라이언트 ([통합 레이블 클라이언트](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2) 또는 [클래식 클라이언트](https://docs.microsoft.com/azure/information-protection/rms-client/aip-client)) 중 하나가 설치 되어 있는 경우 기본적으로 Office 앱에서 기본 제공 레이블 클라이언트를 사용 하지 않도록 설정 됩니다. Office 앱의 Azure Information Protection 클라이언트 대신 기본 제공 레이블을 사용 하려면 Azure Information Protection 용 Office 추가 기능을 사용 하지 않도록 설정 하거나 제거 합니다.

1. 다음 옵션 중 하나를 완료 합니다.
    
    - **여러 컴퓨터의 경우:**  **Office의 민감도 기능을 사용 하 여 민감도 레이블 그룹 정책 설정을 적용 하 고 보기를** 구성 합니다. **사용자 구성/관리 템플릿/Microsoft Office 2016/보안 설정**에서이 설정을 찾습니다. 그룹 정책을 통해 또는 [Office 클라우드 정책 서비스](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service)를 사용 하 여이 설정을 배포 합니다.
    
    - **단일 컴퓨터에 대해 다음을 수행 합니다.** 단일 컴퓨터에서 Azure Information Protection 추가 기능을 [영구적으로 사용 하지 않도록 설정 하거나 제거](https://support.office.com/article/16278816-1948-4028-91e5-76dca5380f8d) 하는 방법에 대 한 자세한 내용은 "Office 프로그램에서 추가 기능 보기, 관리 및 설치"를 참조 하세요.

2. 모든 Office 응용 프로그램을 다시 시작합니다.

이 Office 추가 기능을 사용 하지 않도록 설정 하거나 제거 하면 Office 앱 외부에 있는 파일에 계속 레이블을 지정할 수 있도록 Azure Information Protection 클라이언트가 설치 된 상태로 유지 됩니다. 예를 들어 파일 탐색기 또는 PowerShell을 사용 합니다.

Azure Information Protection 클라이언트 및 Office 기본 제공 레이블 클라이언트에서 지 원하는 기능에 대 한 자세한 내용은 Azure Information Protection 설명서에서 [Windows 컴퓨터에 사용할 레이블 지정 클라이언트 선택을](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#choose-which-labeling-client-to-use-for-windows-computers) 참조 하십시오.

## <a name="protection-templates-and-sensitivity-labels"></a>보호 서식 파일 및 민감도 레이블

Office 365 메시지 암호화에 대해 정의 하는 것과 같은 관리자 정의 [보호 템플릿은](https://docs.microsoft.com/azure/information-protection/configure-policy-templates)기본 제공 레이블을 사용 하는 경우 office 앱에 표시 되지 않습니다. 이러한 단순화 된 환경은 암호화를 사용 하도록 설정 된 민감도 레이블에 동일한 설정이 포함 되므로 보호 템플릿을 선택할 필요가 없다는 것을 나타냅니다.

기존 보호 템플릿을 레이블로 변환 해야 하는 경우 Azure portal 및 다음 지침을 사용 [하 여 서식 파일을 레이블로 변환](https://docs.microsoft.com/azure/information-protection/configure-policy-templates#to-convert-templates-to-labels)합니다.

## <a name="apply-sensitivity-labels-to-files-emails-and-attachments"></a>파일, 전자 메일 및 첨부 파일로 민감도 레이블 적용

사용자는 각 문서 또는 전자 메일에 대해 한 번에 하나의 레이블만 적용할 수 있습니다.

첨부 파일이 있는 전자 메일 메시지에 레이블을 지정 하면 첨부 파일이 레이블을 상속 하지 않습니다. 첨부 파일에 레이블이 있으면 별도로 적용 된 레이블을 유지 합니다. 첨부 파일에 레이블이 없으면 첨부 파일은 레이블을 사용 하지 않고 그대로 유지 됩니다. 그러나 전자 메일에 대한 레이블이 보호를 적용하는 경우 해당 보호는 Office 첨부 파일에 적용됩니다.

## <a name="sensitivity-label-compatibility"></a>민감도 레이블 호환성

**RMS-인식 된 Apps를 사용**합니다. 민감도 레이블을 지원 하지 않는 [RMS-인식 된 응용 프로그램](https://docs.microsoft.com/azure/information-protection/requirements-applications#rms-enlightened-applications) 에서 레이블이 지정 되 _고 암호화_ 된 문서 또는 전자 메일을 열면 앱은 여전히 암호화 및 권한 관리를 적용 합니다.

**Azure Information Protection 클라이언트를 사용**합니다. Azure Information Protection 클라이언트를 사용 하는 Office 기본 제공 레이블 클라이언트와 문서 및 전자 메일에 적용 하는 민감도 레이블을 보고 변경할 수 있습니다.

**다른 버전의 Office와 함께 사용**합니다. 권한이 부여 된 모든 사용자는 다른 버전의 Office에서 레이블이 붙은 문서 및 전자 메일을 열 수 있습니다. 그러나 지원 되는 Office 버전 또는 Azure Information Protection 클라이언트 에서만 레이블을 보거나 변경할 수 있습니다. 지원 되는 Office 앱 버전은이 문서의 표에 나와 있습니다.

## <a name="support-for-sharepoint-and-onedrive-files-protected-by-sensitivity-labels"></a>민감도 레이블로 보호 되는 SharePoint 및 OneDrive 파일에 대 한 지원

웹에서 office의 Office 기본 제공 레이블 클라이언트를 사용 하려면 문서가 [SharePoint 및 OneDrive에서 office 파일에 대해 민감도 레이블 사용을 설정](sensitivity-labels-sharepoint-onedrive-files.md)하는 비즈니스용 OneDrive 또는 SharePoint Online 인스턴스에 있어야 합니다.

## <a name="when-office-365-applies-marks-and-encryption-to-content"></a>Office 365에서 콘텐츠에 대 한 표시 및 암호화를 적용 하는 경우

Office 365에서는 사용 하는 응용 프로그램에 따라 민감도 레이블이 있는 콘텐츠 표시 또는 암호화를 다르게 적용 합니다.

| 응용 프로그램 | 콘텐츠 표시 | 암호화 |
| --- | --- | --- |
| 모든 플랫폼의 Word, Excel, PowerPoint | 즉시 | 즉시 |
| PC 및 Mac용 Outlook | Exchange Online이 전자 메일을 보낸 후 | 즉시 |
| Mac, iOS 및 Android용 Outlook | Exchange Online이 전자 메일을 보낸 후 | Exchange Online이 전자 메일을 보낸 후 |
|

## <a name="more-resources"></a>추가 리소스

[Azure Information Protection의 분류 및 레이블링에 대한 질문과 대답](https://docs.microsoft.com/azure/information-protection/faqs-infoprotect)

[Office 내의 문서 및 전자 메일에 민감도 레이블 적용](https://support.office.com/article/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)
