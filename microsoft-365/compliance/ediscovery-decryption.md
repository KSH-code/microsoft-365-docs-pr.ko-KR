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
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: eDiscovery Microsoft 365 전자 메일 메시지에 첨부되고 SharePoint 온라인 및 전자 메일 메시지에 저장된 암호화된 문서를 처리하는 비즈니스용 OneDrive.
ms.openlocfilehash: 9d3bee507d2add2a6ad1dedadf64c47298ecbab6
ms.sourcegitcommit: 346c1332e1e9eebb5c90d6b8553dd70fcabf530a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/23/2021
ms.locfileid: "53567311"
---
# <a name="decryption-in-microsoft-365-ediscovery-tools"></a>eDiscovery Microsoft 365 암호 해독

암호화는 파일 보호 및 정보 보호 전략의 중요한 부분입니다. 모든 유형의 조직은 암호화 기술을 사용하여 조직 내에서 중요한 콘텐츠를 보호하고 올바른 사용자만 해당 콘텐츠에 액세스할 수 있도록 합니다.

암호화된 콘텐츠에 대해 일반적인 eDiscovery 작업을 실행하기 위해 eDiscovery 관리자는 콘텐츠 검색, 핵심 eDiscovery 사례 및 전자 메일 사례에서 내보낼 때 전자 메일 메시지 콘텐츠를 암호 해독해야 Advanced eDiscovery했습니다. Microsoft 암호화 기술로 암호화된 콘텐츠는 내보낼 때까지 검토할 수 없습니다.

eDiscovery 워크플로에서 암호화된 콘텐츠를 보다 쉽게 관리할 수 있도록 Microsoft 365 eDiscovery 도구에 전자 메일 메시지에 첨부되고 전자 메일 메시지에 전송된 암호화된 파일의 암호 해독이 Exchange Online. <sup>1</sup> 또한 SharePoint Online 및 비즈니스용 OneDrive 암호화된 문서는 Advanced eDiscovery.

이 새로운 기능 이전에는 권한 관리(및 첨부되지 않은 파일)로 보호된 전자 메일 메시지의 콘텐츠만 암호 해독했습니다. eDiscovery 워크플로 SharePoint OneDrive 암호화된 문서의 암호를 해독할 수 없습니다. 이제 Microsoft 암호화 기술로 암호화된 파일은 SharePoint 또는 OneDrive 계정에 있으며, 검색 결과가 미리 보기를 준비하고, Advanced eDiscovery 검토 집합에 추가되고, 내보낼 때 암호가 해독됩니다. 또한 전자 메일 메시지에 SharePoint OneDrive 암호화된 문서도 검색할 수 있습니다. 이 암호 해독 기능을 통해 eDiscovery 관리자는 검색 결과를 미리 볼 때 암호화된 전자 메일 첨부 파일 및 사이트 문서의 콘텐츠를 보고 검색 결과의 검토 집합에 추가된 후 검토할 수 Advanced eDiscovery.

## <a name="supported-encryption-technologies"></a>지원되는 암호화 기술

Microsoft eDiscovery 도구는 Microsoft 암호화 기술로 암호화된 항목을 지원합니다. 이러한 기술은 Azure 권한 관리 및 Microsoft Information Protection(특히 민감도 레이블)입니다. Microsoft 암호화 기술에 대한 자세한 내용은 암호화를 [참조하세요.](encryption.md) 타사 암호화 기술로 암호화된 콘텐츠는 지원되지 않습니다. 예를 들어 Microsoft가 아닌 기술로 암호화된 콘텐츠를 미리 보거나 내보내는 것은 지원되지 않습니다.

> [!NOTE]
> OME(Office 365 메시지 암호화)로 암호화된 전자 메일 메시지의 암호 해독은 Microsoft eDiscovery 도구에서 지원되지 않습니다.

## <a name="ediscovery-activities-that-support-encrypted-items"></a>암호화된 항목을 지원하는 eDiscovery 활동

다음 표에서는 전자 메일 메시지에 첨부된 암호화된 파일과 전자 메일 메시지 및 암호화된 문서에 첨부된 Microsoft 365 eDiscovery 도구에서 수행할 수 있는 지원되는 작업을 SharePoint OneDrive. 이러한 지원되는 작업은 검색 조건과 일치하는 암호화된 파일에 대해 수행할 수 있습니다. 값이면 해당 eDiscovery 도구에서 기능을 사용할 `N/A` 수 없습니다.

|eDiscovery 작업  |콘텐츠 검색  |핵심 eDiscovery  |Advanced eDiscovery  |
|:---------|:---------|:---------|:---------|
|전자 메일 및 사이트<sup>1에서</sup> 암호화된 파일의 콘텐츠 검색     |예      |예      |예      |
|전자 메일에 첨부된 암호화된 파일 미리 보기     |예      |예     |예       |
|암호화된 문서를 미리 SharePoint OneDrive|아니요      |아니요    |예       |
|검토 집합에서 암호화된 파일 검토    |해당 없음      |해당 없음        | 예        |
|전자 메일에 첨부된 암호화된 파일 내보내기    |예       |예  |예    |
|암호화된 문서를 SharePoint OneDrive    |아니요       |아니요  |예    |
|||||

> [!NOTE]
> <sup>1</sup> 로컬 컴퓨터에 있으며 SharePoint 또는 OneDrive 사이트에 저장되지 않은 암호화된 파일은 eDiscovery에 대해 인덱싱되지 않습니다. 즉, 암호화된 로컬 파일이 전자 메일 메시지에 첨부된 경우 파일에 검색 쿼리와 일치하는 키워드가 포함되어 있는 경우에도 키워드 검색 쿼리에서 해당 파일이 반환되지 않습니다. 그러나 보낸 날짜, 보낸 사람, 받는 사람 또는 제목과 같은 전자 메일 속성이 검색 쿼리와 일치하는 경우 eDiscovery 검색에서 로컬 암호화된 파일이 있는 전자 메일 메시지를 반환할 수 있습니다.

### <a name="decryption-limitations-with-sensitivity-labels"></a>민감도 레이블을 사용하여 암호 해독 제한

eDiscovery는 암호화를 적용한 민감도 레이블이 다음 SharePoint OneDrive 구성될 때 암호화된 파일을 지원하지 않습니다.

- 사용자는 문서에 레이블을 수동으로 적용할 때 사용 권한을 할당할 수 있습니다. 이를 사용자 정의 *권한이라고도 합니다.*

- 문서에 대한 사용자 액세스에는 사용 안 하도록 설정된 만료 설정이 **있습니다.**

이러한 설정에 대한 자세한 내용은 민감도 레이블을 사용하여 암호화를 적용하여 콘텐츠에 대한 액세스 제한의 "암호화 설정 구성" [섹션을 참조하세요.](encryption-sensitivity-labels.md#configure-encryption-settings)

이전 설정으로 암호화된 문서는 eDiscovery 검색에서 반환할 수 있습니다. 제목, 만든 이 또는 수정한 날짜와 같은 문서 속성이 검색 조건과 일치하는 경우 이러한 일이 발생하게 될 수 있습니다. 이러한 문서가 검색 결과에 포함될 수 있는 경우 미리 보거나 검토할 수 없습니다. 이러한 문서는 해당 문서가 암호화된 상태로 유지될 때도 암호화된 상태로 Advanced eDiscovery.

## <a name="requirements-for-decryption-in-ediscovery"></a>eDiscovery의 암호 해독 요구 사항

Microsoft 암호화 기술로 암호화된 파일을 미리 보고 검토하고 내보내기 위해 RMS 암호 해독 역할을 할당해야 합니다. 또한 암호화된 파일을 검토하고 쿼리하기 위해 이 역할을 할당해야 합니다. 이 역할은 해당 역할의 검토 집합에 추가된 암호화된 파일을 Advanced eDiscovery.

이 역할은 기본적으로 Office 365 보안 및 준수 센터의  사용 권한 페이지에서 eDiscovery 관리자 역할 & 할당됩니다. RMS 암호 해독 역할에 대한 자세한 내용은 [eDiscovery](assign-ediscovery-permissions.md#rms-decrypt)사용 권한 할당을 참조하세요.
