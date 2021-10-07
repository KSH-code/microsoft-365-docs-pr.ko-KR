---
title: eDiscovery의 암호 해독
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: eDiscovery Microsoft 365 전자 메일 메시지에 첨부되고 SharePoint 온라인 및 전자 메일 메시지에 저장된 암호화된 문서를 처리하는 비즈니스용 OneDrive.
ms.openlocfilehash: 351a6c77d1fc0956c83661132f1111897896a724
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60159911"
---
# <a name="decryption-in-microsoft-365-ediscovery-tools"></a>eDiscovery Microsoft 365 암호 해독

암호화는 파일 보호 및 정보 보호 전략의 중요한 부분입니다. 모든 유형의 조직은 암호화 기술을 사용하여 조직 내에서 중요한 콘텐츠를 보호하고 올바른 사용자만 해당 콘텐츠에 액세스할 수 있도록 합니다.

암호화된 콘텐츠에 대해 일반적인 eDiscovery 작업을 실행하기 위해 eDiscovery 관리자는 콘텐츠 검색, 핵심 eDiscovery 사례 및 전자 메일 사례에서 내보낼 때 전자 메일 메시지 콘텐츠를 암호 해독해야 Advanced eDiscovery했습니다. Microsoft 암호화 기술로 암호화된 콘텐츠는 내보낼 때까지 검토할 수 없습니다.

eDiscovery 워크플로에서 암호화된 콘텐츠를 보다 쉽게 관리할 수 있도록 Microsoft 365 eDiscovery 도구에 전자 메일 메시지에 첨부되고 전자 메일 메시지에 전송된 암호화된 파일의 암호 해독이 Exchange Online. <sup>1</sup> 또한 SharePoint Online 및 비즈니스용 OneDrive 암호화된 문서는 Advanced eDiscovery.

이 새로운 기능 이전에는 권한 관리(및 첨부되지 않은 파일)로 보호된 전자 메일 메시지의 콘텐츠만 암호 해독했습니다. eDiscovery 워크플로 SharePoint OneDrive 암호화된 문서의 암호를 해독할 수 없습니다. 이제 Microsoft 암호화 기술로 암호화된 파일은 SharePoint 또는 OneDrive 계정에 있으며, 검색 결과가 미리 보기를 준비하고, Advanced eDiscovery 검토 집합에 추가되고, 내보낼 때 암호가 해독됩니다. 또한 전자 메일 메시지에 SharePoint OneDrive 암호화된 문서도 검색할 수 있습니다. 이 암호 해독 기능을 통해 eDiscovery 관리자는 검색 결과를 미리 볼 때 암호화된 전자 메일 첨부 파일 및 사이트 문서의 콘텐츠를 보고 검색 결과의 검토 집합에 추가된 후 검토할 수 Advanced eDiscovery.

## <a name="supported-encryption-technologies"></a>지원되는 암호화 기술

Microsoft eDiscovery 도구는 Microsoft 암호화 기술로 암호화된 항목을 지원합니다. 이러한 기술은 Azure 권한 관리 및 Microsoft Information Protection(특히 민감도 레이블)입니다. Microsoft 암호화 기술에 대한 자세한 내용은 암호화를 [참조하세요.](encryption.md) 타사 암호화 기술로 암호화된 콘텐츠는 지원되지 않습니다. 예를 들어 Microsoft가 아닌 기술로 암호화된 콘텐츠를 미리 보거나 내보내는 것은 지원되지 않습니다.

> [!NOTE]
> Microsoft eDiscovery 도구에서 [OME(Office 365 메시지 암호화)](add-your-organization-brand-to-encrypted-messages.md) 사용자 지정 브랜징 템플릿을 사용하여 전송된 전자 메일 메시지의 암호 해독은 지원되지 않습니다. OME 사용자 지정 브랜징 템플릿을 사용하는 경우 전자 메일 메시지가 받는 사람의 사서함 대신 OME 포털로 배달됩니다. 따라서 받는 사람의 사서함에서 해당 메시지를 받지 못하므로 eDiscovery 도구를 사용하여 OME로 암호화된 메시지를 검색할 수 없습니다.

## <a name="ediscovery-activities-that-support-encrypted-items"></a>암호화된 항목을 지원하는 eDiscovery 활동

다음 표에서는 전자 메일 메시지에 첨부된 암호화된 파일과 전자 메일 메시지 및 암호화된 문서에 첨부된 Microsoft 365 eDiscovery 도구에서 수행할 수 있는 지원되는 작업을 SharePoint OneDrive. 이러한 지원되는 작업은 검색 조건과 일치하는 암호화된 파일에 대해 수행할 수 있습니다. 값이면 해당 eDiscovery 도구에서 기능을 사용할 `N/A` 수 없습니다.

|eDiscovery 작업  |콘텐츠 검색  |핵심 eDiscovery  |Advanced eDiscovery  |
|:---------|:---------|:---------|:---------|
|사이트에서 암호화된 파일의 콘텐츠 검색 및 전자 메일 첨부<sup>파일 1</sup>     |아니요      |아니요      |예      |
|전자 메일에 첨부된 암호화된 파일 미리 보기     |예      |예     |예       |
|암호화된 문서를 미리 SharePoint OneDrive|아니요      |아니요    |예       |
|검토 집합에서 암호화된 파일 검토    |해당 없음      |해당 없음        | 예        |
|전자 메일에 첨부된 암호화된 파일 내보내기    |예       |예  |예    |
|암호화된 문서를 SharePoint OneDrive    |아니요       |아니요  |예    |
|||||

> [!NOTE]
> <sup>1</sup> 로컬 컴퓨터에 있는 암호화된 파일 및 전자 메일 메시지에 복사된 클라우드 첨부 파일은 eDiscovery를 위해 암호 해독 및 인덱싱되지 않습니다. 이러한 시나리오에 대한 자세한 내용은 이 문서의 [](#decryption-limitations-with-email-attachments) 전자 메일 첨부 파일을 사용하여 암호 해독 제한 섹션을 참조하세요.

## <a name="decryption-limitations-with-sensitivity-labels-in-sharepoint-and-onedrive"></a>SharePoint 레이블을 사용하여 암호 해독 OneDrive

eDiscovery는 암호화를 적용한 민감도 레이블이 다음 SharePoint OneDrive 구성될 때 암호화된 파일을 지원하지 않습니다.

- 사용자는 문서에 레이블을 수동으로 적용할 때 사용 권한을 할당할 수 있습니다. 이를 사용자 정의 *권한이라고도 합니다.*

- 문서에 대한 사용자 액세스에는 사용 안 하도록 설정된 만료 설정이 **있습니다.**

이러한 설정에 대한 자세한 내용은 민감도 레이블을 사용하여 암호화를 적용하여 콘텐츠에 대한 액세스 제한의 "암호화 설정 구성" [섹션을 참조하세요.](encryption-sensitivity-labels.md#configure-encryption-settings)

이전 설정으로 암호화된 문서는 eDiscovery 검색에서 반환할 수 있습니다. 제목, 만든 이 또는 수정한 날짜와 같은 문서 속성이 검색 조건과 일치하는 경우 이러한 일이 발생하게 될 수 있습니다. 이러한 문서가 검색 결과에 포함될 수 있는 경우 미리 보거나 검토할 수 없습니다. 이러한 문서는 해당 문서가 암호화된 상태로 유지될 때도 암호화된 상태로 Advanced eDiscovery.

## <a name="decryption-limitations-with-email-attachments"></a>전자 메일 첨부 파일에 대한 암호 해독 제한

다음 시나리오에서는 전자 메일 메시지에 첨부된 파일의 암호 해독에 대한 제한 사항을 설명합니다. 이러한 시나리오 설명에는 이러한 제한을 완화하는 해결 해결 작업도 포함되어 있습니다.

- 로컬 컴퓨터에 있는 파일(SharePoint 사이트 또는 OneDrive 계정에 저장되지 않은)이 전자 메일 메시지에 첨부되어 있으며 암호화를 적용하는 민감도 레이블이 전자 메일 메시지에 적용된 경우 eDiscovery에서 첨부된 파일의 암호를 해독할 수 없습니다. 즉, 받는 사람의 사서함에 대한 키워드 검색 쿼리를 실행하면 암호화된 첨부 파일이 키워드 검색 쿼리에서 반환되지 않습니다.

  이 제한 사항의 해결 해결은 보낸 사람 사서함에서 동일한 첨부 파일을 검색하는 것입니다. 이는 민감도 레이블에 의해 적용된 암호화가 전자 메일 메시지를 전송하는 동안 적용하기 때문에입니다. 즉, 전자 메일 메시지를 보낼 때 첨부 파일이 암호화됩니다. 그 결과 받는 사람의 사서함에 있는 동일한 파일이 암호화되어 있는 경우에도 보낸 사람의 사서함에 첨부된 파일의 인스턴스가 암호화되지 않습니다.

- 마찬가지로 전자 메일 메시지에 복사된 클라우드 첨부 파일(SharePoint 사이트 또는 OneDrive 계정에 저장된 파일)은 eDiscovery에서 암호 해독할 수 Outlook 없습니다.  이는 전자 메일 메시지를 보낼 때 민감도 레이블에 의해 적용된 암호화가 적용될 때도 있기 때문에입니다. 보낸 사람 사서함에서 클라우드 첨부 파일 복사본의 암호화되지 않은 인스턴스를 검색하는 작업도 이 제한 사항의 해결 해결 작업입니다.

이러한 두 시나리오에서 보낸 날짜, 보낸 사람, 받는 사람 또는 제목과 같은 전자 메일 속성이 검색 쿼리와 일치하는 경우 eDiscovery 검색에서 암호화된 첨부 파일이 있는 전자 메일 메시지를 반환할 수 있습니다.

## <a name="requirements-for-decryption-in-ediscovery"></a>eDiscovery의 암호 해독 요구 사항

Microsoft 암호화 기술로 암호화된 파일을 미리 보고 검토하고 내보내기 위해 RMS 암호 해독 역할을 할당해야 합니다. 또한 암호화된 파일을 검토하고 쿼리하기 위해 이 역할을 할당해야 합니다. 이 역할은 해당 역할의 검토 집합에 추가된 암호화된 파일을 Advanced eDiscovery.

이 역할은 이 역할의 사용 권한 페이지에서 eDiscovery 관리자 역할 그룹에 기본적으로 Microsoft 365 규정 준수 센터.  RMS 암호 해독 역할에 대한 자세한 내용은 [eDiscovery](assign-ediscovery-permissions.md#rms-decrypt)사용 권한 할당을 참조하세요.

### <a name="decrypting-rms-protected-email-messages-and-encrypted-file-attachments-using-content-search-or-core-ediscovery"></a>콘텐츠 검색 또는 Core eDiscovery를 사용하여 RMS로 보호된 전자 메일 메시지 및 암호화된 파일 첨부 파일의 암호 해독

콘텐츠 검색 결과에 포함된 권한으로 보호된(RMS로 보호된) 전자 메일 메시지는 내보낼 때 암호가 해독됩니다. 또한 [Microsoft](encryption.md) 암호화 기술로 암호화되고 검색 결과에 포함된 전자 메일 메시지에 첨부된 파일은 내보낼 때 암호가 해독됩니다. 이 암호 해독 기능은 기본적으로 eDiscovery 관리자 역할 그룹의 구성원에 대해 사용하도록 설정됩니다. 이는 기본적으로 RMS 암호 해독 관리 역할이 이 역할 그룹에 할당되어 있기 때문에입니다. 암호화된 전자 메일 메시지 및 첨부 파일을 내보낼 때 다음에 유의하세요.
  
- 앞서 설명한 것 처럼 RMS로 보호된 메시지를 내보낼 때 암호를 해독하기 위해 검색 결과를 개별 메시지로 내보내야 합니다. 검색 결과를 PST 파일로 내보낼 경우 RMS로 보호된 메시지는 암호화된 상태로 유지됩니다.

- 암호 해독된 메시지는 **ResultsLog** 보고서에서 식별됩니다. 이 보고서에는 **Decode Status라는** 열이 포함되어 **있으며, 디코드** 값은 암호 해독된 메시지를 식별합니다.

- 검색 결과를 내보낼 때 첨부 파일의 암호를 해독하는 것 외에도 검색 결과를 미리 볼 때 암호 해독된 파일을 미리 볼 수도 있습니다. 권한으로 보호된 전자 메일 메시지는 내보낼 때만 볼 수 있습니다.

- RMS로 보호되는 메시지 및 암호화된 첨부 파일의 암호를 해독하지 못하도록 해야 하는 경우 기본 제공 eDiscovery 관리자 역할 그룹을 복사하여 사용자 지정 역할 그룹을 만든 다음 사용자 지정 역할 그룹에서 RMS 암호 해독 관리 역할을 제거해야 합니다. 그런 다음 메시지의 암호를 해독하지 않는 사람을 사용자 지정 역할 그룹의 구성원으로 추가합니다.
