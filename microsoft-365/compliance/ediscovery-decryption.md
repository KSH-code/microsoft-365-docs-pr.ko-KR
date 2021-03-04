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
description: Microsoft 365 eDiscovery 도구가 전자 메일 메시지에 첨부되고 SharePoint Online 및 비즈니스용 OneDrive에 저장된 암호화된 문서를 처리하는 방법에 대해 자세히 알아보습니다.
ms.openlocfilehash: 4ddc66d595b9d2129a7ba1b75e69586ccbd130f7
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423821"
---
# <a name="decryption-in-microsoft-365-ediscovery-tools"></a>Microsoft 365 eDiscovery 도구의 암호 해독

암호화는 파일 보호 및 정보 보호 전략의 중요한 부분입니다. 모든 유형의 조직은 암호화 기술을 사용하여 조직 내에서 중요한 콘텐츠를 보호하고 올바른 사용자만 해당 콘텐츠에 액세스할 수 있도록 합니다.

암호화된 콘텐츠에 대한 일반적인 eDiscovery 작업을 실행하려면 eDiscovery 관리자가 콘텐츠 검색, 핵심 eDiscovery 사례 및 Advanced eDiscovery 사례에서 내보낼 때 전자 메일 메시지 콘텐츠의 암호를 해독해야 합니다. Microsoft 암호화 기술로 암호화된 콘텐츠는 내보낼 때까지 검토할 수 없습니다.

eDiscovery 워크플로에서 암호화된 콘텐츠를 더 쉽게 관리할 수 있도록 Microsoft 365 eDiscovery 도구에는 이제 전자 메일 메시지에 첨부되고 Exchange Online에서 전송되는 암호화된 파일의 암호 해독이 통합되어 있습니다. 또한 SharePoint Online 및 비즈니스용 OneDrive에 저장된 암호화된 문서는 Advanced eDiscovery에서 암호 해독됩니다. 

이 새로운 기능 이전에는 권한 관리(및 첨부되지 않은 파일)로 보호된 전자 메일 메시지의 콘텐츠만 암호 해독했습니다. SharePoint 및 OneDrive의 암호화된 문서는 eDiscovery 워크플로 중에 암호를 해독할 수 없습니다. 이제 Microsoft 암호화 기술로 암호화된 파일이 전자 메일 메시지에 첨부되거나 SharePoint 또는 OneDrive 계정에 있는 경우 검색 결과가 미리 보기를 준비하고 Advanced eDiscovery의 검토 집합에 추가되고 내보내면 암호화된 항목의 암호가 해독됩니다. 이를 통해 eDiscovery 관리자는 검색 결과를 미리 볼 때 암호화된 전자 메일 첨부 파일 및 사이트 문서의 콘텐츠를 보고 Advanced eDiscovery의 검토 집합에 추가된 후 검토할 수 있습니다.

## <a name="supported-encryption-technologies"></a>지원되는 암호화 기술

Microsoft eDiscovery 도구는 Microsoft 암호화 기술로 암호화된 항목을 지원합니다. 이러한 기술은 Azure 권한 관리 및 Microsoft Information Protection(특히 민감도 레이블)입니다. Microsoft 암호화 기술에 대한 자세한 내용은 암호화를 [참조하세요.](encryption.md) 타사 암호화 기술로 암호화된 콘텐츠는 지원되지 않습니다. 예를 들어 Microsoft가 아닌 기술로 암호화된 콘텐츠를 미리 보거나 내보내는 것은 지원되지 않습니다.

## <a name="ediscovery-activities-that-support-encrypted-items"></a>암호화된 항목을 지원하는 eDiscovery 활동

다음 표에서는 SharePoint 및 OneDrive에서 전자 메일 주소 및 암호화된 문서에 첨부된 암호화된 파일에 대해 Microsoft 365 eDiscovery 도구에서 수행할 수 있는 지원되는 작업을 설명합니다. 이러한 지원되는 작업은 검색 조건과 일치하는 암호화된 파일에 대해 수행할 수 있습니다. 값이면 해당 eDiscovery 도구에서 기능을 사용할 `N/A` 수 없습니다.

|eDiscovery 작업  |콘텐츠 검색  |핵심 eDiscovery  |Advanced eDiscovery  |
|:---------|:---------|:---------|:---------|
|전자 메일 및 사이트에서 암호화된 파일의 콘텐츠 검색     |예      |예      |예      |
|전자 메일에 첨부된 암호화된 파일 미리 보기     |예      |예     |예       |
|SharePoint 및 OneDrive에서 암호화된 문서 미리 보기|아니요      |아니요    |예       |
|검토 집합에서 암호화된 파일 검토    |해당 없음      |해당 없음        | 예        |
|전자 메일에 첨부된 암호화된 파일 내보내기    |예       |예  |예    |
|SharePoint 및 OneDrive에서 암호화된 문서 내보내기    |아니요       |아니요  |예    |
|||||

**참고:** eDiscovery는 암호화를 적용한 민감도 레이블이 다음 설정 중 하나를 사용하여 구성된 경우 SharePoint 및 OneDrive에서 암호화된 파일을 지원하지 않습니다.

- 사용자는 문서에 레이블을 수동으로 적용할 때 사용 권한을 할당할 수 있습니다. 이를 사용자 정의 *권한이라고도 합니다.*<br/>

- 문서에 대한 사용자 액세스에는 사용 안 하도록 설정된 만료 설정이 **있습니다.**

이러한 설정에 대한 자세한 내용은 민감도 레이블을 사용하여 암호화를 적용하여 콘텐츠에 대한 액세스 제한의 "암호화 설정 구성" [섹션을 참조하세요.](encryption-sensitivity-labels.md#configure-encryption-settings)

이전 설정으로 암호화된 문서는 eDiscovery 검색에서 반환할 수 있습니다. 제목, 만든 이 또는 수정한 날짜와 같은 문서 속성이 검색 조건과 일치하는 경우 이러한 일이 발생하게 될 수 있습니다. 이러한 문서가 검색 결과에 포함될 수 있는 경우 미리 보거나 검토할 수 없습니다. 이러한 문서는 Advanced eDiscovery에서 내보낼 때도 암호화된 상태로 유지됩니다.

## <a name="requirements-for-decryption-in-ediscovery"></a>eDiscovery의 암호 해독 요구 사항

Microsoft 암호화 기술로 암호화된 파일을 미리 보고 검토하고 내보내기 위해 RMS 암호 해독 역할을 할당해야 합니다. Advanced eDiscovery의 검토 집합에 추가된 암호화된 파일을 검토하고 쿼리하려면 이 역할을 할당해야 합니다.

이 역할은 기본적으로 Office 365 보안 및  준수 센터의 사용 권한 페이지에서 eDiscovery 관리자 역할 & 할당됩니다. RMS 암호 해독 역할에 대한 자세한 내용은 [eDiscovery](assign-ediscovery-permissions.md#rms-decrypt)사용 권한 할당을 참조하세요.
