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
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: IT 관리자가 데스크톱, 모바일 및 웹용 Office 앱에서 민감도 레이블을 관리하기 위한 정보입니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9a1d888ceee527960cb8b894b1bc6bcde5c73d9b
ms.sourcegitcommit: e685fafd6dde4901c378685b423883faed7b4fe7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/21/2021
ms.locfileid: "59460043"
---
# <a name="manage-sensitivity-labels-in-office-apps"></a>Office 앱의 민감도 레이블 관리

>*[보안 및 규정 준수에 대한 Microsoft 365 라이선싱 지침](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Microsoft 365 규정 준수 센터 또는 그와 동등한 레이블 지정 센터에서 민감도 레이블을 게시하면 해당 레이블이 [Office 앱](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)에 표시되기 시작하여 사용자가 데이터를 생성하거나 편집한 대로 분류하고 보호할 수 있습니다.

이 문서의 정보를 사용하여 Office 앱에서 민감도 레이블을 성공적으로 관리할 수 있습니다. 예를 들어 기본 제공 레이블을 지원하는 데 필요한 최소 버전의 앱을 식별하고 Azure Information Protection 통합 레이블 지정 클라이언트와의 상호 작용 및 다른 앱 및 서비스와의 호환성을 파악합니다.

## <a name="labeling-client-for-desktop-apps"></a>데스크톱 앱용 클라이언트에 레이블 지정

Windows 및 Mac용 Office 데스크톱 앱에 기본 제공되는 민감도 레이블을 사용하려면 Office 구독판을 사용해야 합니다. 이 레이블 지정 클라이언트는 Office 2016 또는 Office 2019와 같은 독립 실행형 Office 버전은 지원하지 않습니다.

Windows 컴퓨터에서 이러한 독립 실행형 버전의 Office와 함께 민감도 레이블을 사용하려면 [Azure Information Protection 통합 레이블 지정 클라이언트](/azure/information-protection/rms-client/aip-clientv2)를 설치하세요.

## <a name="support-for-sensitivity-label-capabilities-in-apps"></a>앱에서의 민감도 레이블 기능에 대한 지원

다음 표에는 각 기능에 대해 기본 제공 레이블을 사용하여 민감도 레이블을 지원하기 위해 필요한 최소 Office 버전이 나열되어 있습니다. 또는 레이블 기능이 공개 미리 보기 또는 향후 릴리스에 대해 검토 중인 경우입니다. 이후 릴리스에 대한 자세한 내용은 [Microsoft 365 로드맵](https://aka.ms/MIPC/Roadmap)을 이용하세요.

새로운 버전의 Office 앱은 서로 다른 업데이트 채널에 대해 서로 다른 시간에 사용할 수 있습니다. 관심 있는 새 레이블 지정 기능을 테스트할 수 있도록 업데이트 채널을 구성하는 방법을 포함한 자세한 내용은 [ Microsoft 365 앱의 업데이트 채널 개요](/DeployOffice/overview-update-channels)를 참조하세요. 비공개 미리 보기에 있는 새 기능은 표에 포함되지 않지만 [ Microsoft Information Protection 비공개 미리 보기 프로그램 ](https://aka.ms/mip-preview)에 조직을 지정하여 이러한 미리 보기에 참여할 수 있습니다.

> [!NOTE]
> Office 앱의 업데이트 채널 이름이 2020년 5월에 변경되었습니다. 예를 들어 월별 채널은 이제 현재 채널이며 Office 내부자는 베타 채널이 됩니다. 자세한 내용은 [Microsoft 365 앱의 업데이트 채널에 대한 변경 내용](/deployoffice/update-channels-changes)을 참조하세요.

iOS 및 Office for Android: 민감도 레이블은 [Office 앱](https://www.microsoft.com/en-us/microsoft-365/blog/2020/02/19/new-office-app-android-ios-available/)에 내장되어 있습니다.

Windows 컴퓨터에서만 실행되는 Azure Information Protection 통합 레이블 지정 클라이언트를 설치할 때 추가 기능을 사용할 수 있습니다. 자세한 내용은 [Windows 컴퓨터에 대한 레이블 지정 클라이언트 비교](/azure/information-protection/rms-client/use-client#compare-the-labeling-clients-for-windows-computers)를 참조하세요.

> [!TIP]
> 테이블의 최소 버전을 사용 중인 버전과 비교할 때 앞에 오는 0을 생략하는 릴리스 버전의 일반적인 사례를 기억하세요.
> 
> 예를 들어 버전 4.2128.0이 있고 4.7.1+가 최소 버전임을 읽습니다. 보다 쉽게 비교하려면 4.7.1(앞에 오는 0 없음)을 4.**0007**.1(4.**7000**.1)로 읽습니다. 4.2128.0 버전이 4.0007.1보다 높으므로 버전이 지원됩니다.

### <a name="sensitivity-label-capabilities-in-word-excel-and-powerpoint"></a>Word, Excel 및 PowerPoint의 민감도 레이블 기능

나열된 숫자는 각 기능에 필요한 최소 Office 응용 프로그램 버전입니다.

|기능                                                                                                        |Windows<sup>\*</sup> |Mac |iOS    |Android      |웹                                                         |
|------------------------------------------------------------------------------------------------------------------|----------------|------------|-------|-------------|------------------------------------------------------------|
|[수동으로 레이블 적용, 변경 또는 제거](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [예 - 옵트인](sensitivity-labels-sharepoint-onedrive-files.md) |
|새 문서에 [기본 레이블 적용](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [예 - 옵트인](sensitivity-labels-sharepoint-onedrive-files.md)                                                        |
|기존 문서에 [기본 레이블 적용](sensitivity-labels.md#what-label-policies-can-do) | 미리 보기: [베타 채널](https://office.com/insider)에 배포 중           | 미리 보기: [베타 채널](https://office.com/insider)에 배포 중 | 검토 중 | 검토 중 | 배포 중: [예 - 옵트인](sensitivity-labels-sharepoint-onedrive-files.md) |
|[레이블을 변경하기 위한 사유 요구](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [예 - 옵트인](sensitivity-labels-sharepoint-onedrive-files.md) |
|[사용자 지정 도움말 페이지에 도움말 링크 제공](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [예 - 옵트인](sensitivity-labels-sharepoint-onedrive-files.md) |
|[콘텐츠 표시](sensitivity-labels.md#what-sensitivity-labels-can-do)                                              | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [예 - 옵트인](sensitivity-labels-sharepoint-onedrive-files.md) |
|[변수가 있는 동적 표시](#dynamic-markings-with-variables)                                              | 2010+           | 16.42+     | 2.42+ | 16.0.13328+ | [예 - 옵트인](sensitivity-labels-sharepoint-onedrive-files.md) |
|[지금 권한 할당](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+          | 16.21+     | 2.21+ | 16.0.11231+ | [예 - 옵트인](sensitivity-labels-sharepoint-onedrive-files.md) |
|[사용자가 권한을 할당하도록 허용: <br /> - 사용자에게 프롬프트](encryption-sensitivity-labels.md#let-users-assign-permissions)                     |2004+ | 16.35+   | 검토 중   | 검토 중         | 검토 중                                                        |
|[레이블 관련 사용자 활동 감사](data-classification-activity-explorer.md)                      | 2011+ | 16.43+ | 2.46+ | 16.0.13628+ | 예<sup>\*\*</sup>                                                        |
|[사용자가 전자 메일 및 문서에 레이블을 적용하도록 요구](#require-users-to-apply-a-label-to-their-email-and-documents)   | 2101+             | 16.45+         | 2.47+ | 16.0.13628+ | [예 - 옵트인](sensitivity-labels-sharepoint-onedrive-files.md)                                            
|[민감도 레이블을 콘텐츠에 자동으로 적용](apply-sensitivity-label-automatically.md) <br /> - 중요한 정보 유형 사용                    | 2009+                                  | 16.44+ | 검토 중 | 검토 중 | [예 - 옵트인](sensitivity-labels-sharepoint-onedrive-files.md) |
|[민감도 레이블을 콘텐츠에 자동으로 적용](apply-sensitivity-label-automatically.md) <br /> - 학습 가능한 분류자 사용                    | 2009+                                  | 검토 중 | 검토 중 | 검토 중 | [예 - 옵트인](sensitivity-labels-sharepoint-onedrive-files.md) |
|레이블이 지정되고 암호화된 문서에 대한 [공동 작성 및 자동 저장 지원](sensitivity-labels-coauthoring.md) | 2107+ |  16.51+ | 검토 중 | 검토 중 | [예 - 옵트인](sensitivity-labels-sharepoint-onedrive-files.md) |
|

**각주:**

<sup>\*</sup> 버전 번호는 **현재 채널** 에 대한 번호입니다. 새로 릴리스된 기능은 일반적으로 다음 월 단위 기업 채널, 그리고 다음으로 반기 엔터프라이즈 채널로 전달됩니다. 그러나 각 업데이트 채널에 새 기능에 대한 릴리스 기준이 있기 때문에 항상 그렇지는 않습니다. [자세한 정보](/deployoffice/overview-update-channels)
<br /><br />
<sup>\*\*</sup> 현재 레이블을 제거하거나 분류 수준을 낮추기 위한 근거 텍스트를 포함하지 않습니다.

### <a name="sensitivity-label-capabilities-in-outlook"></a>Outlook의 민감도 레이블 기능

나열된 숫자는 각 기능에 필요한 최소 Office 응용 프로그램 버전입니다.

|기능                                                                                                        |Windows용 Outlook<sup>\*</sup> |Outlook for Mac |iOS에서의 Outlook |Android에서의 Outlook |웹용 Outlook |
|------------------------------------------------------------------------------------------------------------------|---------------------------|------------------------|---------------|-------------------|-------------------|
|[수동으로 레이블 적용, 변경 또는 제거](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)| 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | 예               |
|[기본 레이블 적용](sensitivity-labels.md#what-label-policies-can-do)                                         | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | 예               |
|[레이블을 변경하기 위한 사유 요구](sensitivity-labels.md#what-label-policies-can-do)                     | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | 예               |
|[사용자 지정 도움말 페이지에 도움말 링크 제공](sensitivity-labels.md#what-label-policies-can-do)                       | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | 예               |
|[콘텐츠 표시](sensitivity-labels.md#what-sensitivity-labels-can-do)                                              | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | 예               |
|[변수가 있는 동적 표시](#dynamic-markings-with-variables)                                              | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | 예               |
|[지금 권한 할당](encryption-sensitivity-labels.md#assign-permissions-now)                                 | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | 예               |
|[사용자가 권한을 할당하도록 허용: <br /> - 전달하지 않음](encryption-sensitivity-labels.md#let-users-assign-permissions)                     | 1910+                     | 16.21+                 | 4.7.1+         | 4.0.39+           | 예               |
|[사용자가 권한을 할당하도록 허용: <br /> - 암호화 전용](encryption-sensitivity-labels.md#let-users-assign-permissions)  |2011+ | 16.48+ <sup>\*\*</sup> | 4.2112.0+  | 4.2112.0+ | 예 |
|[사용자가 전자 메일 및 문서에 레이블을 적용하도록 요구](#require-users-to-apply-a-label-to-their-email-and-documents)   | 2101+                        | 16.43+ <sup>\*\*</sup>                    | 4.2111+            | 4.2111+                | 예                |
|[레이블 관련 사용자 활동 감사](data-classification-activity-explorer.md) | 2011+ | 16.51+ <sup>\*\*</sup> | 4.2126+ | 4.2126+ | 예 |
|[민감도 레이블을 콘텐츠에 자동으로 적용](apply-sensitivity-label-automatically.md) <br /> - 중요한 정보 유형 사용                    | 2009+                      | 16.44+ <sup>\*\*</sup>                    | 검토 중           | 검토 중               | 예 |
|[민감도 레이블을 콘텐츠에 자동으로 적용](apply-sensitivity-label-automatically.md) <br /> - 학습 가능한 분류자 사용                    | 2009+                      | 검토 중                    | 검토 중           | 검토 중               | 예 |
|[기본 레이블 및 필수 레이블에 대한 다른 설정](#outlook-specific-options-for-default-label-and-mandatory-labeling)                    | 2105+                      | 16.43+ <sup>\*\*</sup>                   | 4.2111+           | 4.2111+               | 예 |
|

**각주:**

<sup>\*</sup> 버전 번호는 **현재 채널** 에 대한 번호입니다. 새로 릴리스된 기능은 일반적으로 다음 월 단위 기업 채널, 그리고 다음으로 반기 엔터프라이즈 채널로 전달됩니다. 그러나 각 업데이트 채널에 새 기능에 대한 릴리스 기준이 있기 때문에 항상 그렇지는 않습니다. [자세한 정보](/deployoffice/overview-update-channels)
<br /><br />
<sup>\*\*</sup> [새로운 Mac용 Outlook](https://support.microsoft.com/office/the-new-outlook-for-mac-6283be54-e74d-434e-babb-b70cefc77439) 필요


## <a name="office-built-in-labeling-client-and-other-labeling-solutions"></a>Office 기본 제공 레이블 지정 클라이언트 및 기타 레이블 솔루션

Office 기본 제공 레이블 지정 클라이언트는 다음 관리 센터에서 민감도 레이블 및 민감도 레이블 정책 설정을 다운로드합니다.

- Microsoft 365 규정 준수 센터
- Office 365 보안 및 준수 센터(이전 관리 포털)

Office 기본 제공 레이블 지정 클라이언트를 사용하려면 나열된 관리 센터 중 하나와 [지원되는 Office 버전](#support-for-sensitivity-label-capabilities-in-apps)에서 사용자에게 하나 이상의 [레이블 정책이 게시](create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy)되어 있어야 합니다.

두 가지 조건이 모두 충족되지만 Office 기본 제공 레이블링 클라이언트를 해제해야 하는 경우 다음 그룹 정책 설정을 사용하세요.

1. **사용자 구성/정책/관리 템플릿/Microsoft Publisher 2016/보안** 으로 이동합니다.

2. **Office의 민감도 기능 사용** 을 설정하여 민감도 레이블을 **0** 에 적용하고 표시합니다. 
 
그룹 정책 또는 [Office 클라우드 정책 서비스](/DeployOffice/overview-office-cloud-policy-service)를 사용하여 이 설정을 배포합니다. 이 설정은 Office 앱이 다시 시작될 때 적용됩니다.

### <a name="office-built-in-labeling-client-and-the-azure-information-protection-client"></a>Office 기본 제공 레이블 지정 클라이언트 및 Azure Information Protection 클라이언트

사용자가 [Azure Information Protection 클라이언트를 설치](/azure/information-protection/rms-client/aip-clientv2)한 경우 기본적으로 Office 앱에서 기본 제공 레이블 지정 클라이언트가 해제됩니다. 

Office 앱용 Azure Information Protection 클라이언트 대신 기본 제공 레이블 지정을 사용하려면 [Office 2013 및 Office 2016 프로그램의 그룹 정책 설정으로 인해 로드된 추가 기능 없음](https://support.microsoft.com/help/2733070/no-add-ins-loaded-due-to-group-policy-settings-for-office-2013-and-off)에 설명된 것처럼 **관리되는 추가 기능 목록** 그룹 정책 설정을 사용하는 것이 좋습니다.

Microsoft Word 2016, Excel 2016, PowerPoint 2016 및 Outlook 2016에서 Azure Information Protection 클라이언트에 대해 다음과 같은 프로그래밍 식별자(ProgID)를 지정하고 옵션을 **0으로 설정합니다. 이 추가 기능은 언제나 사용하지 않도록 설정됩니다(차단).**

|응용 프로그램  |ProgID  |
|---------|---------|
|Word     |     `MSIP.WordAddin`    |
|Excel     |  `MSIP.ExcelAddin`       |
|PowerPoint     |   `MSIP.PowerPointAddin`      |
|Outlook | `MSIP.OutlookAddin` |
| | | 


그룹 정책 또는 [Office 클라우드 정책 서비스](/DeployOffice/overview-office-cloud-policy-service)를 사용하여 이 설정을 배포합니다.

> [!NOTE]
> 그룹 정책 설정 **Office의 민감도 기능을 사용하여 민감도 레이블을 적용하고 보기** 를 사용하고 이 설정을 **1** 로 설정하는 경우 Azure Information Protection 클라이언트가 여전히 Office 앱에 로드 될 수 있는 상황이 몇 가지 있습니다. 각 앱에 추가 기능을 로드하지 못하게 차단하여 이 문제를 방지할 수 있습니다.

또는 Word, Excel, PowerPoint 및 Outlook에서 **Microsoft Azure Information Protection** Office 추가 기능을 사용하지 않도록 설정하거나 제거할 수 있습니다. 이 방법은 단일 컴퓨터 및 임시 테스트에 적합합니다. 자세한 내용은 [Office 프로그램에서 추가 기능 보기, 관리 및 설치](https://support.office.com/article/16278816-1948-4028-91e5-76dca5380f8d)를 참조하세요. 

어떤 메서드를 선택하든 Office 앱이 다시 시작될 때 변경 내용이 적용됩니다. 이 Office 추가 기능을 비활성화하거나 제거하면 Azure Information Protection 클라이언트는 컴퓨터에 설치된 상태로 유지되므로 Office 앱 외부에서 파일에 레이블을 계속 지정할 수 있습니다. 예를 들어, 파일 탐색기 또는 PowerShell을 사용하여 이 작업을 수행할 수 있습니다.

Azure Information Protection 클라이언트 및 Office 내장 레이블 지정 클라이언트에서 지원하는 기능에 대한 자세한 내용은 [Azure Information Protection 문서에서 Windows 레이블 지정 솔루션 선택](/azure/information-protection/rms-client/use-client#choose-your-windows-labeling-solution)을 참조하세요.

## <a name="office-file-types-supported"></a>지원되는 Office 파일 형식

Word, Excel 및 PowerPoint 파일에 대한 레이블이 내장된 Office 앱은 Open XML 형식(.docx 및 .xlx 등)을 지원하지만 Microsoft Office 97-2003 형식(.doc 및 .xls 등), Open Document Format(.odt 및 .ods 등) 또는 기타 형식을 지원하지 않습니다. 기본 제공 레이블 지정에 대해 파일 형식이 지원되지 않는 경우 Office 앱에서 **민감도** 버튼을 사용할 수 없습니다.

Azure Information Protection 통합 레이블 지정 클라이언트는 Open XML 형식과 Microsoft Office 97-2003 형식을 모두 지원합니다. 자세한 내용은 해당 클라이언트 관리 가이드의 [Azure Information Protection 통합 레이블 지정 클라이언트에서 지원되는 파일 형식](/azure/information-protection/rms-client/clientv2-admin-guide-file-types)을 참조하세요.

기타 레이블 지정 솔루션의 경우 해당 문서에서 지원되는 파일 형식을 확인하세요.

## <a name="protection-templates-and-sensitivity-labels"></a>보호 서식 파일 및 민감도 레이블

Office 365 메시지 암호화에 대해 정의하는 경우처럼 [관리자 정의 보호 서식 파일](/azure/information-protection/configure-policy-templates)은 기본 제공 레이블을 사용할 때 Office 앱에 표시되지 않습니다. 이러한 단순화된 환경은 동일한 설정이 암호화를 사용하도록 설정된 민감도 레이블에 포함되어 있기 때문에 보호 템플릿을 선택할 필요가 없음을 나타냅니다.

[New-Label](/powershell/module/exchange/new-label) cmdlet을 *EncryptionTemplateId* 매개 변수와 함께 사용할 때 기존 템플릿을 민감도 레이블로 변환할 수 있습니다.

## <a name="information-rights-management-irm-options-and-sensitivity-labels"></a>IRM(정보 권한 관리) 옵션 및 민감도 레이블

암호화를 적용하도록 구성하는 민감도 레이블은 사용자 자신의 암호화 설정을 지정하기 위해 복잡성을 제거합니다. 대부분의 Office 앱에서 이러한 개별 암호화 설정은 IRM(정보 권한 관리) 옵션을 사용하여 사용자가 수동으로 구성할 수 있습니다. 예를 들어 Windows 앱의 경우:

- 문서: **File** > **정보** > **문서 보호** > **액세스 제한**
- 전자 메일의 경우: **옵션** 탭 > **암호화** 에서 
  
처음에 문서 또는 전자 메일에 레이블을 지정할 때 사용자는 자신의 암호화 설정으로 레이블 구성 설정을 재정의할 수 있습니다. 예를 들면 다음과 같습니다.

- 사용자가 문서에 **기밀 \ 모든 직원** 레이블을 적용하고 이 레이블은 조직의 모든 사용자에 대해 암호화 설정을 적용하도록 구성되어 있습니다. 그런 다음 이 사용자는 조직 외부의 사용자에 대한 액세스를 제한하도록 IRM 설정을 수동으로 구성합니다. 최종 결과로 **비밀 \ 모든 직원** 이라는 레이블이 붙어 있고 암호화되어 있지만 조직의 사용자가 예상하는 것처럼 열 수 없는 문서가 생성됩니다.

- 사용자가 **기밀 \ 수신자 전용** 레이블을 전자 메일에 적용하고 이 전자 메일은 **전달 금지** 의 암호화 설정을 적용하도록 구성되어 있습니다. Outlook 앱에서, 이 사용자는 수동으로 암호화 전용 IRM 설정을 선택합니다. 최종 결과에서는 전자 메일이 암호화된 상태로 유지되는 동안 **기밀 \ 수신자 전용** 레이블이 있음에도 불구하고 수신자가 전자 메일을 전달할 수 있습니다.
    
    예외적으로 웹용 Outlook의 경우 사용자가 현재 선택한 레이블이 **암호화** 를 적용할 때 선택할 수있는 암호화 메뉴의 옵션을 사용할 수 없습니다.

- 사용자가 **일반** 레이블을 문서에 적용하지만 이 레이블이 암호화를 적용하도록 구성되지 않았습니다. 그런 다음 이 사용자는 문서에 대한 액세스를 제한하도록 IRM 설정을 수동으로 구성합니다. 최종 결과로 **일반** 이라는 레이블이 붙어 있지만 일부 사용자가 예상대로 열 수 없도록 암호화도 적용된 문서가 나타납니다.

문서 또는 전자 메일에 이미 레이블이 지정된 경우, 컨텐츠가 아직 암호화되지 않았거나 [사용 권한](/azure/information-protection/configure-usage-rights#usage-rights-and-descriptions) 내보내기 또는 전체 제어가 있는 경우 사용자가 다음 작업 중 하나를 수행할 수 있습니다. 

의미 있는 보고에 대한 보다 일관된 레이블 경험을 위해, 적절한 레이블과 지침을 제공하여 사용자가 레이블만 적용하여 문서 및 전자 메일을 보호할 수 있도록 합니다. 예를 들면 다음과 같습니다.

- 사용자가 자신의 사용 권한을 할당해야 하는 예외 사례의 경우 [사용자가 자신의 사용 권한을 할당할 수 있도록 허용](encryption-sensitivity-labels.md#let-users-assign-permissions)하는 레이블을 제공하세요. 

- 사용자가 암호화를 적용하는 레이블을 선택한 후 수동으로 암호화를 제거하는 대신, 사용자가 동일한 분류의 레이블이 필요하지만 암호화는 필요하지 않은 경우에 하위 레이블 대안을 제공하세요. 예를 들면 다음과 같습니다.
    - **기밀 \ 모든 직원**
    - **기밀 \ 모든 사용자(암호화 없음)**

- 사용자가 설정을 선택하지 못하도록 IRM 설정을 비활성화하는 것이 좋습니다.
    - Windows용 Outlook: 
        - HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Common\DRM의 *DisableDNF* 및 *DisableEO* 레지스트리 키(DWORD:00000001)
        - 그룹 정책 설정 **암호화 단추에 대한 기본 암호화 옵션 구성** 이 구성되지 않았는지 확인합니다.
    - Mac용 Outlook: 
        - [Mac용 Outlook 환경 설정 지정](/DeployOffice/mac/preferences-outlook)에 문서화된 *DisableEncryptOnly* 및 *DisableDoNotForward* 키 보안 설정
    - 웹용 Outlook: 
        - [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration)에 대해 문서화된 매개 변수 *SimplifiedClientAccessDoNotForwardDisabled* 및 *SimplifiedClientAccessEncryptOnlyDisabled*
    - iOS 및 Android 용 Outlook: 이러한 앱은 레이블 없이 암호화를 적용하는 사용자를 지원하지 않으므로 비활성화할 사항이 없습니다.

> [!NOTE]
> 사용자가 SharePoint 또는 OneDrive에 저장된 레이블이 지정된 문서에서 암호화를 수동으로 제거하고 [SharePoint 및 OneDrive의 Office 파일에 대해 민감도 레이블을 사용하도록 설정](sensitivity-labels-sharepoint-onedrive-files.md)한 경우, 레이블 암호화는 다음에 문서에 액세스하거나 다운로드할 때 자동으로 복원됩니다. 


## <a name="apply-sensitivity-labels-to-files-emails-and-attachments"></a>파일, 전자 메일 및 첨부 파일에 민감도 레이블 적용

사용자는 각 문서 또는 전자 메일에 대해 한 번에 하나의 레이블만 적용할 수 있습니다.

첨부 파일이 있는 전자 메일 메시지에 레이블을 지정할 때, 첨부 파일은 전자 메일 메시지에 적용한 레이블이 암호화를 적용하고 첨부 파일이 Office 문서인 경우에만 레이블을 상속합니다. 상속된 레이블이 암호화를 적용하기 때문에 첨부 파일이 새로 암호화됩니다.

전자 메일 메시지에 적용된 레이블이 암호화를 적용하지 않거나 첨부 파일이 이미 암호화되어 있는 경우 첨부 파일은 전자 메일 메시지에서 레이블을 상속하지 않습니다.

**기밀** 레이블은 암호화를 적용하고 **일반** 레이블은 암호화를 적용하지 않는 레이블 상속의 예:

- 사용자가 새 전자 메일 메시지를 생성하고 **기밀 문서** 레이블을 이 메시지에 적용합니다. 그런 다음 레이블이 지정되거나 암호화되지 않은 Word 문서를 추가합니다. 상속으로 인해 문서에 새로 **기밀** 이라는 레이블이 지정되고 해당 레이블에서 암호화가 적용됩니다.

- 사용자가 새 전자 메일 메시지를 생성하고 **기밀 문서** 레이블을 이 메시지에 적용합니다. 그런 다음 **일반** 레이블이 지정된 Word 문서를 추가합니다. 이 파일은 암호화되지 않습니다. 상속으로 인해 문서에 **기밀** 이라는 레이블이 다시 지정되고 해당 레이블에서 암호화가 적용됩니다.

## <a name="sensitivity-label-compatibility"></a>민감도 레이블 호환성

**RMS가 적용된 응용 프로그램**: 민감도 레이블을 지원하지 않는 [RMS가 적용된 응용 프로그램](/azure/information-protection/requirements-applications#rms-enlightened-applications)에서 레이블이 지정되고 암호화된 문서 또는 전자 메일을 여는 경우에도 앱에서 암호화 및 권한 관리를 적용합니다.

**Azure Information Protection 클라이언트 사용**: Azure Information Protection 클라이언트 등을 사용하여 Office 기본 제공 레이블 지정 클라이언트와 함께 문서 및 전자 메일에 적용하는 민감도 레이블을 보고 변경할 수 있습니다.

**다른 버전의 Office**: 모든 인증된 사용자는 다른 버전의 Office에서 레이블이 지정된 문서 및 전자 메일을 열 수 있습니다. 그러나 지원되는 Office 버전 또는 Azure Information Protection 클라이언트를 통해서만 레이블을 보거나 변경할 수 있습니다. 지원되는 Office 앱 버전은 [이전 섹션](#support-for-sensitivity-label-capabilities-in-apps)에 나열되어 있습니다.

## <a name="support-for-sharepoint-and-onedrive-files-protected-by-sensitivity-labels"></a>민감도 레이블로 보호되는 SharePoint 및 OneDrive 파일 지원

SharePoint 또는 OneDrive의 문서에 대해 Office가 웹에 있는 Office 기본 제공 레이블 클라이언트를 사용하려면 [SharePoint 및 OneDrive의 Office 파일에 대해 민감도 레이블을 사용하도록 설정](sensitivity-labels-sharepoint-onedrive-files.md)했는지 확인합니다.

## <a name="support-for-external-users-and-labeled-content"></a>외부 사용자 및 레이블이 있는 콘텐츠에 대한 지원

문서 또는 전자 메일에 레이블을 지정할 때 레이블은 테넌트 및 레이블 GUID를 포함하는 메타데이터로 저장됩니다. 민감도 레이블을 지원하는 Office 앱에서 레이블 지정된 문서 또는 전자 메일을 열면 이 메타데이터가 읽히고 사용자가 동일한 테넌트에 속하는 경우에만 레이블이 해당 앱에 표시됩니다. 예를 들어 Word, PowerPoint 및 Excel에 대한 기본 제공 레이블의 경우 레이블 이름이 상태 표시줄에 표시됩니다. 

즉, 서로 다른 레이블 이름을 사용하는 다른 조직과 문서를 공유하는 경우 각 조직이 해당 문서에 적용된 자체 레이블을 보고 적용할 수 있습니다. 그러나 적용된 레이블의 다음 요소는 조직 외부의 사용자에게 표시됩니다.

- 콘텐츠 표시. 레이블에서 머리글, 바닥글 또는 워터마크를 적용할 때 해당 내용이 내용에 직접 추가되고 사용자가 수정하거나 삭제할 때까지 계속 표시됩니다.

- 암호화를 적용한 레이블의 기본 보호 템플릿 이름 및 설명. 이 정보는 문서 상단에 있는 메시지 표시줄에 표시되어 문서를 열 수 있는 권한과 해당 문서에 대한 사용 권한을 제공합니다.

### <a name="sharing-encrypted-documents-with-external-users"></a>외부 사용자와 암호화된 문서 공유

자신의 조직에서 사용자에 대한 액세스를 제한할 뿐만 아니라 Azure Active Directory에 계정이 있는 다른 모든 사용자에게도 액세스를 확장할 수 있습니다. 그러나 조직에서 조건부 액세스 정책을 사용하는 경우 추가 고려 사항은 [다음 섹션](#conditional-access-policies)을 참조하세요.

사용자가 인증한 후 모든 Office 앱과 기타 [RMS 사용 응용 프로그램](/azure/information-protection/requirements-applications#rms-enlightened-applications)이 암호화된 문서를 열 수 있습니다. 

외부 사용자가 Azure Active Directory에 계정이 없는 경우 테넌트의 게스트 계정을 사용하여 인증할 수 있습니다. [SharePoint 및 OneDrive의 Office 파일에 대해 민감도 레이블을 사용하도록 설정](sensitivity-labels-sharepoint-onedrive-files.md)한 경우 이러한 게스트 계정을 사용하여 SharePoint 또는 OneDrive의 공유 문서에 액세스할 수도 있습니다.

- 한 가지 옵션은 이러한 게스트 계정을 직접 생성하는 것입니다. 이러한 사용자가 이미 사용하는 전자 메일 주소를 지정할 수 있습니다. 예를 들어, Gmail 주소가 해당됩니다.
    
    이 옵션의 이점은 암호화 설정에서 전자 메일 주소를 지정하여 특정 사용자에 대한 액세스 및 권한을 제한할 수 있다는 것입니다. 단점은 계정 생성 및 레이블 구성과의 조정을 위한 관리 오버헤드입니다.

- 또 다른 옵션은 사용자가 링크를 공유할 때 게스트 계정이 자동으로 생성되도록 [Azure AD B2B(미리 보기)가 포함된 SharePoint 및 OneDrive 통합](/sharepoint/sharepoint-azureb2b-integration-preview)을 사용하는 것입니다.
    
    이 옵션의 이점은 계정이 자동으로 생성되고 레이블 구성이 간단하기 때문에 관리 오버헤드가 최소화된다는 것입니다. 이 시나리오에서는 암호화 옵션 [인증된 사용자 추가](encryption-sensitivity-labels.md#requirements-and-limitations-for-add-any-authenticated-users)를 선택해야 합니다. 사용자가 전자 메일 주소를 미리 알 수 없기 때문입니다. 단점은 이 설정으로 특정 사용자에 대한 액세스 및 사용 권한을 제한할 수 없다는 것입니다.

외부 사용자는 Windows 및 Microsoft 365 앱([이전 Office 365 앱](/deployoffice/name-change)) 또는 Office 2019 독립 실행형 버전을 사용할 때 Microsoft 계정을 사용하여 암호화된 문서를 열 수도 있습니다. 다른 플랫폼에서도 최근에 지원되는 Microsoft 계정은 MacOS(Microsoft 365 Apps, 버전 16.42+), Android(버전 16.0.13029+) 및 iOS(버전 2.42+)에서 암호화된 문서를 열 수 있도록 지원합니다. 예를 들어 조직의 사용자는 조직 외부의 사용자와 암호화된 문서를 공유하고 암호화 설정은 외부 사용자의 Gmail 전자 메일 주소를 지정합니다. 이 외부 사용자는 자신의 Gmail 전자 메일 주소를 사용하는 자신의 Microsoft 계정을 만들 수 있습니다. 그런 다음 이 계정으로 로그인한 후 지정된 사용 제한에 따라 문서를 열고 편집할 수 있습니다. 이 시나리오의 자세한 내용은 [보호된 문서 열기 및 편집](/azure/information-protection/secure-collaboration-documents#opening-and-editing-the-protected-document)을 참조하세요.

> [!NOTE]
> Microsoft 계정의 전자 메일 주소는 암호화 설정에 대한 액세스를 제한하도록 지정된 전자 메일 주소와 일치해야 합니다.

Microsoft 계정이 있는 사용자가 암호화된 문서를 열 때 동일한 이름의 게스트 계정이 아직 존재하지 않는 경우 테넌트에 대한 게스트 계정을 자동으로 생성합니다. 게스트 계정이 존재하면 지원되는 데스크톱 및 모바일 Office 앱에서 암호화된 문서를 열 뿐만 아니라 웹에서 Office를 사용하여 SharePoint 및 OneDrive에서 문서를 여는 데 사용할 수 있습니다.

그러나 복제 지연 시간 때문에 이 시나리오에서는 자동 게스트 계정이 즉시 생성되지 않습니다. 레이블 암호화 설정의 일부로 개인 전자 메일 주소를 지정하는 경우 Azure Active Directory에 해당하는 게스트 계정을 생성하는 것이 좋습니다. 그런 다음 이 계정을 사용하여 조직에서 암호화된 문서를 열어야 한다는 사실을 사용자에게 알리세요.

> [!TIP]
> 외부 사용자가 지원되는 Office 클라이언트 앱을 사용할지 확신할 수 없기 때문에, 게스트 계정 생성 후(특정 사용자용) 또는 [Azure AD B2B가 포함된 SharePoint 및 OneDrive 통합](/sharepoint/sharepoint-azureb2b-integration-preview)을 사용할 경우에는 SharePoint 및 OneDrive의 링크를 외부 사용자와 공유하는 것이 안전한 공동 작업을 지원하기 위한 보다 안정적인 방법입니다.

### <a name="conditional-access-policies"></a>조건부 액세스 정책

조직에서 [Azure Active Directory 조건부 액세스 정책 ](/azure/active-directory/conditional-access/overview)을 실행한 경우 해당 정책의 구성을 확인하세요. 정책에 **Microsoft Azure Information Protection** 이 포함되어 있고 정책이 외부 사용자로 확장되는 경우 해당 외부 사용자에게는 자신의 테넌트에 Azure AD 계정이 있더라도 테넌트에 게스트 계정이 있어야 합니다.

이 게스트 계정이 없으면 암호화된 문서를 열 수 없고 오류 메시지를 볼 수 없습니다. 메시지 텍스트는 이 시나리오에서 **다른 Azure Active Directory 사용자 계정으로 다시 로그인** 하는 이 시나리오에 대한 잘못된 지침과 함께 자신의 계정을 테넌트의 외부 사용자로 추가해야 한다고 알릴 수 있습니다.

레이블로 암호화된 문서를 열어야 하는 외부 사용자에 대해 테넌트에 게스트 계정을 생성하고 구성할 수 없는 경우 조건부 액세스 정책에서 Azure Information Protection을 제거하거나 정책에서 외부 사용자를 제외해야 합니다.

민감도 레이블에서 사용하는 암호화 서비스인 조건부 액세스 및 Azure Information Protection에 대한 자세한 내용은 자주 묻는 질문[Azure Information Protection이 조건부 액세스를 위한 사용 가능한 클라우드 앱으로 나열되어 있습니다. -이 작업은 어떻게 수행되나요?](/azure/information-protection/faqs#i-see-azure-information-protection-is-listed-as-an-available-cloud-app-for-conditional-accesshow-does-this-work)를 참조하세요.

## <a name="when-office-apps-apply-content-marking-and-encryption"></a>Office 앱이 콘텐츠 표시 및 암호화를 적용하는 경우

Office 앱은 사용하는 앱에 따라 민감도 레이블을 이용하여 콘텐츠 표시와 암호화를 다르게 적용합니다.

| 앱 | 콘텐츠 표시 | 암호화 |
| --- | --- | --- |
| 모든 플랫폼의 Word, Excel, PowerPoint | 즉시 | 즉시 |
| PC 및 Mac용 Outlook | Exchange Online에서 전자 메일을 보낸 후 | 즉시 |
| Mac, iOS 및 Android용 Outlook | Exchange Online에서 전자 메일을 보낸 후 | Exchange Online에서 전자 메일을 보낸 후 |
|

Office 앱 외부의 파일에 민감도 레이블을 적용하는 솔루션은 파일에 레이블 지정 메타데이터를 적용하여 이 작업을 수행합니다. 이 시나리오에서는 레이블 구성의 콘텐츠 표시가 파일에 삽입되지 않지만 암호화는 적용됩니다. 

Office 데스크톱 앱에서 이러한 파일을 열면 파일을 처음 저장할 때 Azure Information Protection 통합 레이블 지정 클라이언트에서 콘텐츠 표시를 자동으로 적용합니다. 바탕 화면, 모바일 또는 웹 앱에 기본 제공 레이블을 사용할 경우 콘텐츠 표시가 자동으로 적용되지 않습니다.

Office 앱 외부에 민감도 레이블을 적용하는 시나리오에는 다음 항목이 포함됩니다.

- Azure Information Protection 통합 레이블 지정 클라이언트의 스캐너, 파일 탐색기 및 PowerShell 

- SharePoint 및 OneDrive에 대한 자동 레이블 지정 정책

- Power BI에서 레이블 지정 및 암호화된 데이터 내보내기

- Microsoft Cloud App Security

이러한 시나리오의 경우, 내장된 레이블이 있는 사용자는 현재 레이블을 일시적으로 제거 또는 교체한 다음 원래 레이블을 다시 적용함으로써 레이블의 콘텐츠 표시를 적용할 수 있다.

### <a name="dynamic-markings-with-variables"></a>변수가 있는 동적 표시

> [!IMPORTANT]
> 현재 일부 플랫폼의 일부 앱이 머리글, 바닥글 및 워터마크에 대해 지정할 수 있는 동적 콘텐츠 표시를 지원하는 것은 아닙니다. 이 기능을 지원하지 않는 앱의 경우 변수를 해결하는 대신 레이블 구성에 지정된 원래 텍스트로 표시를 적용합니다.
> 
> Azure Information Protection 통합 레이블 지정 클라이언트는 동적 표시를 지원합니다. Office에 기본 제공되는 레이블을 지정하는 경우 지원되는 최소 버전은 이 페이지의 [기능](#support-for-sensitivity-label-capabilities-in-apps) 섹션의 표를 참조하세요.

콘텐츠 표시에 대한 민감도 레이블을 구성할 때 머리말, 바닥글 또는 워터마크에 대해 텍스트 문자열의 다음 변수를 사용할 수 있습니다.

| 변수 | 설명 | 레이블이 적용될 때의 예 |
| -------- | ----------- | ------- |
| `${Item.Label}` | 적용된 레이블의 레이블 표시 이름 | **일반**|
| `${Item.Name}` | 레이블 지정되는 콘텐츠의 파일 이름 또는 전자 메일 제목 | **Sales.docx** |
| `${Item.Location}` | 레이블이 지정된 문서의 경로 및 파일 이름 또는 레이블이 지정된 전자 메일에 대한 전자 메일 제목 | **\\\Sales\2020\Q3\Report.docx**|
| `${User.Name}` | 레이블을 적용하는 사용자의 표시 이름 | **Richard Simone** |
| `${User.PrincipalName}` | 레이블을 적용하는 사용자의 UPN(Azure AD 사용자 이름) | **rsimone\@contoso.com** |
| `${Event.DateTime}` | Microsoft 365 앱에서 레이블을 적용하는 사용자의 로컬 표준시 또는 Office Online 및 자동 레이블 지정 정책에 대한 UTC(협정 세계시)에서 콘텐츠에 레이블을 지정하는 날짜 및 시간입니다. | **8/10/2020 1:30 PM** |

> [!NOTE]
> 이러한 변수의 구문은 대소문자를 구분합니다.

#### <a name="setting-different-visual-markings-for-word-excel-powerpoint-and-outlook"></a>Word, Excel, PowerPoint 및 Outlook에 대한 다양한 시각적 표시 설정

추가 변수로 "If"를 사용하여 Office 응용 프로그램 유형별로 시각적 표시를 구성할 수 있습니다.텍스트 문자열의 앱" 변수 문을 사용하고 **Word**, **Excel**, **PowerPoint** 또는 **Outlook** 값을 사용하여 응용 프로그램 유형을 식별합니다. 또한 동일한 If.App 문에서 둘 이상의 값을 지정하려면 이 값을 약어로 지정할 수도 있습니다.

다음 구문을 사용합니다.

```
${If.App.<application type>}<your visual markings text> ${If.End}
```

다른 동적 시각적 표시와 마찬가지로 구문은 각 응용 프로그램 유형 (WEPO)의 약어를 포함하는 대소문자를 구분합니다.

예제:

- **Word 문서에 대해서만 머리글 텍스트 설정:**

    `${If.App.Word}This Word document is sensitive ${If.End}`

    Word 문서 머리글에서만, 레이블은 "이 Word 문서는 중요합니다" 머리글 텍스트를 적용합니다. 머리글 텍스트는 다른 Office 응용 프로그램에 적용되지 않습니다.

- **Word, Excel 및 Outlook의 바닥글 텍스트 설정 및 PowerPoint의 다른 바닥글 텍스트 설정:**

    `${If.App.WXO}This content is confidential. ${If.End}${If.App.PowerPoint}This presentation is confidential. ${If.End}`

    Word, Excel 및 Outlook에서 레이블은 "이 콘텐츠는 기밀입니다" 바닥글 텍스트를 적용합니다. PowerPoint에서 레이블은 "이 프리젠테이션은 기밀입니다" 바닥글 텍스트를 적용합니다. 

- **Word 및 PowerPoint에 대한 특정 워터마크 텍스트를 설정한 다음 Word, Excel 및 PowerPoint에 대한 워터마크 텍스트를 설정합니다.**

    `${If.App.WP}This content is ${If.End}Confidential`

    Word 및 PowerPoint에서 레이블은 "이 콘텐츠는 기밀입니다" 워터마크 텍스트를 적용합니다. Excel에서 레이블은 "기밀" 워터마크 텍스트를 적용합니다. Outlook에서는 시각적 표시로 워터마크가 지원되지 않으므로 레이블이 워터마크 텍스트를 적용하지 않습니다.

## <a name="require-users-to-apply-a-label-to-their-email-and-documents"></a>사용자가 전자 메일 및 문서에 레이블을 적용하도록 요구

> [!IMPORTANT]
> 
> [Azure Information Protection 통합 레이블 지정 클라이언트](/azure/information-protection/rms-client/install-unifiedlabelingclient-app)는 필수 레이블 지정이라고도 하는 이 구성을 지원합니다. Office 앱에 기본 제공되는 레이블을 지정하는 경우 최소 버전은 이 페이지의 [기능](#support-for-sensitivity-label-capabilities-in-apps) 섹션의 표를 참조하세요.
>
> 문서에는 필수 레이블을 사용하지만 전자 메일은 사용하지 않았다면 다음 섹션에서 Outlook 관련 옵션을 구성하는 방법을 설명하는 지침을 참조하세요.
> 
> Power BI 필수 레이블 지정을 사용하려면 [Power BI 필수 레이블 정책](/power-bi/admin/service-security-sensitivity-label-mandatory-label-policy)을 참조하세요.

**사용자가 전자 메일 및 문서에 레이블을 적용해야 함** 정책 설정을 선택하면 정책이 할당된 사용자는 다음 시나리오에서 민감도 레이블을 선택하고 적용해야 합니다.

- Azure Information Protection 통합 레이블 지정 클라이언트의 경우:
    - 문서(Word, Excel, PowerPoint): 레이블이 없는 문서가 저장되거나 사용자가 문서를 닫는 경우.
    - 전자 메일의 경우(Outlook): 이 때 사용자는 레이블이 없는 메시지를 보냅니다.

- Office 앱에 내장된 레이블 지정의 경우:
    - 문서(Word, Excel, PowerPoint): 레이블이 없는 문서가 열리거나 저장되는 경우.
    - 전자 메일의 경우(Outlook): 이 때 사용자는 레이블이 없는 전자 메일 메시지를 보냅니다.

기본 제공 레이블 지정에 대한 추가 정보:

- 레이블이 없는 문서를 열어서 민감도 레이블을 추가하라는 메시지가 표시되면 레이블을 추가하거나 읽기 전용 모드에서 문서를 열도록 선택할 수 있습니다.

- 필수 레이블 지정이 적용되는 경우 사용자는 문서에서 민감도 레이블을 제거할 수 없지만 기존 레이블을 변경할 수는 있습니다.

이 설정을 사용할 시기에 대한 자세한 내용은 [정책 설정](sensitivity-labels.md#what-label-policies-can-do)에 대한 정보를 참조하세요.

> [!NOTE]
> 필수 레이블 지정 외에도 문서 및 전자 메일에 기본 레이블 정책 설정을 사용하는 경우: 
>
> 기본 레이블은 항상 필수 레이블 지정보다 우선 순위로 지정됩니다. 그러나 문서의 경우 Azure Information Protection 통합 레이블 지정 클라이언트는 레이블이 지정되지 않은 모든 문서에 기본 레이블을 적용하는 반면, 기본 레이블 지정은 레이블이 지정되지 않은 기존 문서가 아닌 새 문서에 기본 레이블을 적용합니다. 이러한 동작의 차이는 기본 레이블 설정과 함께 필수 레이블을 사용할 경우 사용자에게 Azure Information Protection 통합 레이블 클라이언트를 사용할 때보다 기본 제공 레이블을 사용할 때 아마도 민감도 레이블을 더 자주 적용하라는 메시지가 표시될 것을 의미합니다.
> 
> 이제 배포: 기본 제공 레이블 지정을 사용하고 기존 문서에 대한 기본 레이블을 지원하는 Office 앱입니다. 자세한 내용은 Word, Excel 및 PowerPoint의 [기능 표](sensitivity-labels-office-apps.md#sensitivity-label-capabilities-in-word-excel-and-powerpoint)를 참조하세요.

## <a name="outlook-specific-options-for-default-label-and-mandatory-labeling"></a>기본 레이블 및 필수 레이블에 대한 Outlook 관련 옵션

기본 레이블 지정의 경우 이 페이지의 [Outlook 에 대한 기능 테이블](#sensitivity-label-capabilities-in-outlook)과 **기본 레이블 및 필수 레이블 지정** 행의 다른 설정을 사용하여 이러한 기능을 지원하는 최소 버전의 Outlook을 식별합니다. 모든 버전의 Azure Information Protection 통합 레이블 지정 클라이언트는 이러한 Outlook 관련 옵션을 지원합니다.

Outlook 앱이 문서의 기본 레이블 설정과 다른 기본 레이블 설정을 지원하는 경우:

- 레이블 정책 마법사의 **전자 메일에 기본 레이블 적용** 페이지에서 레이블이 지정되지 않은 모든 전자 메일에 적용될 민감도 레이블을 선택하여 지정하거나 기본 레이블을 선택하지 않을 수 있습니다. 이 설정은 마법사의 이전 **문서에 대한 정책 설정** 페이지의 문서에 대한 **기본적으로 이 레이블 적용** 설정과는 별개입니다.

Outlook 앱이 문서의 기본 레이블 설정과 다른 기본 레이블 설정을 지원하지 않는 경우: Outlook은 레이블 정책 마법사의 **문서에 대한 정책 설정** 페이지에서 **문서에 기본적으로 이 레이블 적용** 에 대해 지정한 값을 항상 사용합니다.

Outlook 앱에서 필수 레이블 지정 해제를 지원하는 경우:

- 레이블 정책 마법사의 **정책 설정** 페이지에서 **사용자가 이메일 또는 문서에 레이블을 적용하도록 요구** 를 선택합니다. 그리고 나서 **다음** > **다음** 을 선택하고 **사용자가 이메일에 레이블을 적용하도록 요구** 확인란을 선택 취소합니다. 필수 레이블을 이메일과 문서에 적용하려면 확인란을 선택한 상태로 유지하세요.

Outlook 앱에서 필수 레이블 지정 해제를 지원하지 않는 경우: 정책 설정으로 **사용자에게 이메일 또는 문서에 레이블을 적용하도록 요구** 를 선택하면 Outlook은 항상 사용자에게 레이블이 지정되지 않은 전자 메일의 레이블을 선택하라는 메시지를 표시합니다.

> [!NOTE]
> [Set-LabelPolicy](/powershell/module/exchange/set-labelpolicy) 또는 [New-LabelPolicy cmdlet](/powershell/module/exchange/new-labelpolicy)을 사용하여 PowerShell 고급 설정 **OutlookDefaultLabel** 및 **DisableMandatoryInOutlook** 을 구성한 경우:
> 
> 이러한 PowerShell 설정에 대해 선택한 값은 레이블 정책 마법사에 반영되며 이러한 설정을 지원하는 Outlook 앱에서 자동으로 작동합니다. 다른 PowerShell 고급 설정은 Azure Information Protection 통합 레이블 지정 클라이언트에서만 지원됩니다.

## <a name="end-user-documentation"></a>최종 사용자 설명서

- [Office에서 파일 및 전자 메일에 민감도 레이블 적용](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)
    - [Office의 민감도 레이블과 관련된 알려진 문제점](https://support.microsoft.com/en-us/office/known-issues-with-sensitivity-labels-in-office-b169d687-2bbd-4e21-a440-7da1b2743edc)

- [Office에서 파일 및 전자 메일에 자동으로 민감도 레이블 적용 또는 추천](https://support.office.com/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1)
    - [민감도 레이블 자동 적용 또는 추천에 대한 알려진 문제](https://support.office.com/article/known-issues-with-automatically-applying-or-recommending-sensitivity-labels-451698ae-311b-4d28-83aa-a839a66f6efc)
