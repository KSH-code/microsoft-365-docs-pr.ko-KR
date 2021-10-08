---
title: Microsoft 365에서 민감도 레이블로 암호화된 문서에 공동 작성 사용
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.service: O365-seccomp
ms.date: ''
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
ms.topic: article
description: SharePoint 및 OneDrive의 레이블이 지정되고 암호화된 문서에 대해 데스크톱 앱에서 공동 작성 및 자동 저장을 사용할 수 있도록 설정하세요.
ms.openlocfilehash: fc519ea7a8d76135b4d536a64e6a411844bd3e47
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60151053"
---
# <a name="enable-co-authoring-for-files-encrypted-with-sensitivity-labels"></a>민감도 레이블로 암호화된 파일에 공동 작성 사용

>*[보안 및 규정 준수에 대한 Microsoft 365 라이선싱 지침](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Office 데스크톱 앱에 [공동 작성](https://support.office.com/article/ee1509b4-1f6e-401e-b04a-782d26f564a4)을 지원하도록 설정을 하면, 문서가 [민감도 레이블](sensitivity-labels.md)로 분류되어 암호화될 때 여러 사용자가 동시에 이러한 문서를 편집할 수 있습니다.

테넌트를 위해 이 설정을 사용하지 않으면, 사용자가 Office 데스크톱 앱을 이용할 때 SharePoint 또는 OneDrive에 저장된 암호화 문서를 체크 아웃해야 합니다. 따라서 실시간으로 공동 작업을 하지 못하게 됩니다. 아니면, [SharePoint 및 OneDrive의 Office 파일에 민감도 레이블을 사용](sensitivity-labels-sharepoint-onedrive-files.md)할 경우 사용자는 웹에서 Office를 이용해야 합니다.

또한 이 기능을 사용하도록 설정하면, 레이블이 지정되고 암호화된 파일에 [자동 저장](https://support.office.com/article/what-is-autosave-6d6bd723-ebfd-4e40-b5f6-ae6e8088f7a5) 기능이 지원됩니다.

릴리스 발표를 읽으려면 블로그 게시물[Microsoft Information Protection 암호화 문서에 대한 공동 작성을 이제 일반적으로 사용할 수 있습니다](https://techcommunity.microsoft.com/t5/security-compliance-and-identity/co-authoring-on-microsoft-information-protection-encrypted/ba-p/2693718)를 참조하세요.

## <a name="metadata-changes-for-sensitivity-labels"></a>민감도 레이블의 메타데이터 변경 내용

> [!IMPORTANT]
> 공동 작성 설정을 사용 가능으로 설정한 후에는 암호화되지 않은 파일의 레이블 정보가 더 이상 사용자 지정 속성에 저장되지 않습니다.
> 
> 이전 위치로 레이블 지정 메타데이터를 읽거나 쓰는 앱, 서비스, 스크립트 또는 도구를 사용하고 있다면, 이 설정을 사용하지 마세요.

Office 데스크톱 앱에 공동 작성을 지원하는 설정을 하기 전, 이 작업이 Office 파일에 저장되고 거기에서 읽어오는 레이블 지정 메타데이터를 변경한다는 점을 이해하는 것이 중요합니다.

레이블 지정 메타데이터에는 테넌트 및 적용된 민감도 레이블을 식별하는 정보가 포함됩니다. 이 설정으로 인해 변경되는 사항은 Word, Excel 및 PowerPoint 파일의 메타데이터 형식과 위치입니다. 암호화된 파일 또는 전자 메일에 대해 어떤 조치도 취할 필요가 없습니다. 암호화된 파일에 대한 메타데이터 변경은 이전 버전과 호환되며 전자 메일에 대해 변경 내용은 없습니다. 그러나 암호화된 파일에 대한 메타데이터 변경 내용이 자동으로 업그레이드될 수 있지만 이전 버전과 호환되지 않는다는 것을 명심해야 합니다.

이 변경 내용은 새로 레이블이 지정된 파일과 이미 레이블이 지정된 파일 모두에 영향을 미칩니다. 공동 작성 설정을 지원하는 앱 및 서비스를 사용하는 경우:
- 새로 레이블을 지정한 파일의 경우 레이블 지정 메타데이터에는 새 형식과 위치만 사용합니다.
- 이미 레이블을 지정한 파일의 경우 다음에 파일을 열고 저장할 때 파일에 이전 형식 및 위치의 메타데이터가 있으면 새 형식과 위치로 복사됩니다.

다음 리소스에서 이 메타데이터 변경의 자세한 내용을 살펴볼 수 있습니다.

- 블로그 게시물: [Microsoft Information Protection 메타데이터 저장소의 향후 변경 사항](https://techcommunity.microsoft.com/t5/microsoft-security-and/upcoming-changes-to-microsoft-information-protection-metadata/ba-p/1904418)

- 사양 열기: [2.6.3 LabelInfo와 사용자 지정 문서 속성의 대비](/openspecs/office_file_formats/ms-offcrypto/13939de6-c833-44ab-b213-e0088bf02341)

조직 내에 이전 위치에 레이블 지정 메타데이터를 읽거나 쓰는 앱, 서비스, 스크립트 또는 도구가 있다면, 이러한 변경 때문에 이 설정을 사용하지 마세요. 그럴 경우 다음과 같은 결과가 나타날 수 있습니다.

- 레이블을 지정한 문서가 사용자에게 레이블이 없는 것으로 표시됨

- 문서에서 사용자에게 기간이 지난 레이블을 표시함

- 다른 사용자가 새 레이블 메타데이터를 지원하지 않는 Office 데스크톱 앱에서 문서를 연 경우 공동 작성 및 암호화된 문서에는 공동 작성 및 자동 저장이 작동하지 않습니다.

- [Office 첨부 파일에서 레이블을 사용자 지정 속성으로 식별하는](/azure/information-protection/configure-exo-rules#example-2-rule-that-applies-the-encrypt-only-option-to-emails-when-they-have-attachments-that-are-labeled-confidential--partners-and-these-emails-are-sent-outside-the-organization) Exchange Online 메일 흐름 규칙이 전자 메일 및 첨부 파일을 암호화하지 못하거나 잘못 암호화합니다.

다음 섹션에서 이 설정을 지원하는 앱 및 서비스 목록과 레이블 지정 메타데이터의 변경 내용을 확인하세요.

## <a name="prerequisites"></a>필수 구성 요소

이 기능을 켜기 전에 다음 필수 구성 요소를 이해해야만 합니다.

- 이 기능을 사용하려면 전역 관리자여야 합니다.

- [SharePoint의 Office 파일 및 테넌트의 OneDrive](sensitivity-labels-sharepoint-onedrive-files.md)에 민감도 레이블을 사용해야 합니다. 아직 이 기능을 활성화하지 않은 경우, 민감도 레이블이 있는 파일에 공동 작성 설정을 선택하면 이 기능이 자동으로 활성화됩니다.

- 엔터프라이즈용 Microsoft 365 앱
    - **Windows**: 최소 버전 2107
    - **macOS**: 최소 버전 16.51
    - **iOS**: 아직 지원되지 않음
    - **Android**: 아직 지원되지 않음

- 테넌트의 모든 앱, 서비스 및 운영 도구는 새 [레이블 지정 메타데이터](#metadata-changes-for-sensitivity-labels)를 지원해야 합니다. 다음을 사용하고 있는 경우 필수 최소 버전을 확인하세요.
    
    - **Azure Information Protection 통합 레이블 지정 클라이언트 및 스캐너:**
        - [Microsoft 다운로드 센터](https://www.microsoft.com/en-us/download/details.aspx?id=53018)에서 설치할 수 있는 최소 버전 [2.12.62.0](/information-protection/rms-client/unifiedlabelingclient-version-release-history#version-212620)
    
    - **Windows 또는 MacOS용 OneDrive 동기화 앱:**
        - 19.002.0121.0008 최소 버전
    
    - **엔드포인트 데이터 손실 방지(Endpoint DLP):**
        - Windows 10 1809, KB 4601383 포함
        - Windows 10 1903 및 1909, KB 4601380 포함
        - Windows 10 2004, KB 4601382 포함
    
    - **Microsoft Information Protection SDK를 사용하는 앱 및 서비스:** 
        - 1.7 최소 버전 

이 기능을 사용하면 Microsoft 365 서비스가 자동으로 새 레이블 지정 메타데이터를 지원합니다. 다음은 그 예시입니다.

- [자동 레이블 지정 정책](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-policies-for-sharepoint-onedrive-and-exchange)
- [민감도 레이블을 조건으로 사용하는 DLP 정책](dlp-sensitivity-label-as-condition.md)
- [민감도 레이블을 적용하도록 구성한 Microsoft Cloud App Security](/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)

## <a name="limitations"></a>제한 사항

민감도 레이블로 암호화된 파일에 공동 작성을 위한 테넌트 설정을 사용하기 전, 이 기능의 다음과 같은 제한 사항을 이해해야 합니다.

- [레이블 지정 메타데이터의 변경](#metadata-changes-for-sensitivity-labels) 때문에 테넌트의 모든 앱, 서비스 및 운영 도구는 일관되고 안정적인 레이블 지정 환경을 위해 새 레이블 지정 메타데이터를 지원해야 합니다.
    
    Excel에만 해당: 다른 사용자가 민감도 레이블의 메타데이터 변경 내용을 지원하지 않는 Excel 버전을 사용하여 해당 파일을 편집하고 저장한 경우, 암호화를 적용하지 않는 민감도 레이블의 메타데이터를 파일에서 삭제할 수 있습니다.

- iOS 및 Android용 Office 앱은 현재 지원되지 않습니다.

- 공동 작성 및 자동 저장을 지원하지 않으며, 다음 [구성을 암호화](encryption-sensitivity-labels.md#configure-encryption-settings)하는 데 사용하는 레이블 지정 및 암호화된 Office 문서에서는 작동하지 않습니다.
    - **사용자가 레이블을 적용할 때 권한을 할당하도록 허용** 및 **Word, PowerPoint 및 Excel에서 사용자에게 권한 지정 메시지 표시** 확인란이 선택되어 있습니다. 이 구성을 "사용자 정의 권한"이라고도 합니다.
    - **콘텐츠에 대한 사용자 액세스 만료** 가 **만료 안 함** 이외의 값으로 설정됩니다.
    - **이중 키 암호화** 가 선택됩니다.
    
    이러한 암호화 구성이 있는 레이블이면, 레이블은 Office 앱에 표시됩니다. 하지만 사용자가 이러한 레이블을 선택해도 문서를 편집하는 다른 사용자가 없으면, 공동 작성 및 자동 저장을 사용할 수 없다는 경고가 표시됩니다. 다른 사용자가 문서를 편집한다면, 레이블을 적용할 수 없다는 메시지가 나타납니다.

- Azure Information Protection 통합 레이블 지정 클라이언트를 사용하는 경우: 이 레이블 지정 클라이언트에 대한 설명서 [추가 요구 사항 또는 제한](/azure/information-protection/known-issues#known-issues-for-co-authoring)에서 참조하세요.

## <a name="how-to-enable-co-authoring-for-files-with-sensitivity-labels"></a>민감도 레이블이 있는 파일에 공동 작성을 사용하는 방법

> [!CAUTION]
> 이 설정은 한 번 켜고 나면 다시 끌 수 없습니다. 이 페이지에서 설명하는 메타데이터 변경 내용, 필수 구성 요소, 제한 사항 및 알려진 문제를 읽고 이해한 후에만 사용해 주세요.

미리 보기 기간 동안 이 설정을 이미 켠 경우 추가 작업이 필요하지 않으며 이 절차를 건너뛸 수 있습니다.

1. 테넌트의 전역 관리자로서 [Microsoft 365 규정 준수 센터](https://compliance.microsoft.com)에 로그인합니다.

2. 탐색 창에서 **설정** > **민감도 레이블이 있는 파일 공동 작성** 을 선택합니다.

2. **민감도 레이블이 있는 파일 공동 작성** 페이지에서 요약 설명과 필수 구성 요소, 예상 내용, 이 설정을 켠 후에는 해제할 수 없다는 경고를 읽습니다.
    
    그런 다음 **민감도 레이블이 있는 파일에 공동 작성을 사용** 하도록 설정을 선택하여 **적용** 합니다.
    
    ![민감도 레이블이 있는 파일에 공동 작성을 사용하는 옵션](../media/co-authoring-tenant-option-for-sensitivity-labels.png)

3. 공동 작성을 위한 새 기능을 사용하기 전에 24시간 동안 이 설정이 환경 전체에 복제되기를 기다립니다.

## <a name="contact-support-if-you-need-to-disable-this-feature"></a>이 기능을 실행 중지해야 한다면, 고객 지원에 문의하세요.

> [!IMPORTANT]
> 이 기능을 실행 중지해야 하는 경우 레이블 지정 정보가 손실될 수 있습니다.

테넌트에 대한 민감도 레이블이 있는 파일에 공동 작성을 사용한 후에는 이 설정을 직접 실행 중지할 수 없습니다. 따라서 이 설정을 사용하기에 앞서 필수 구성 요소, 결과 및 한계를 확인하고 이해하는 것이 중요합니다.

![민감도 레이블에 공동 작성 사용을 설정한 것을 나타내는 옵션](../media/co-authoring-tenant-option-set-for-sensitivity-labels.png)

이 설정을 사용할 때의 스크린샷에서 볼 수 있듯이, [Microsoft 지원](../business-video/get-help-support.md)에 연락하여 이 설정의 해제를 요청할 수 있습니다. 이 요청에는 수일이 소요될 수 있으며, 사용자가 테넌트의 전역 관리자임을 입증해야 합니다. 일반적인 지원 요금이 적용될 것입니다. 

지원 엔지니어가 테넌트에 이 설정을 실행 중지하는 경우:

- 새 레이블링 메타데이터를 지원하는 앱과 서비스의 경우 레이블을 읽거나 저장할 때 원래 메타데이터 형식 및 위치로 돌아갑니다.

- 설정이 가능한 동안에 사용한 Office 문서의 새 메타데이터 형식 및 위치는 원래의 형식 및 위치로 복사되지 않습니다. 결과적으로, 암호화되지 않은 Word, Excel 및 PowerPoint 파일의 이 레이블 지정 정보가 손실됩니다.

- 레이블이 지정되고 암호화된 문서에 대한 공동 작성 및 자동 저장이 더는 지원되지 않습니다.

- 민감도 레이블은 OneDrive 및 SharePoint의 Office 파일에 사용 가능한 상태로 유지됩니다.
