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
ms.openlocfilehash: df2ff218e5c62e103661889fc8c66950a4d25cab
ms.sourcegitcommit: 6759e619c45a5f8e775ad456a5dfb18c08f13f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/18/2020
ms.locfileid: "49713269"
---
# <a name="decryption-in-microsoft-365-ediscovery-tools"></a>Microsoft 365 eDiscovery 도구의 암호 해독

암호화는 파일 보호 및 정보 보호 전략의 중요한 부분입니다. 모든 유형의 조직은 암호화 기술을 사용하여 조직 내에서 중요한 콘텐츠를 보호하고 올바른 사용자만 해당 콘텐츠에 액세스할 수 있도록 합니다.

암호화된 콘텐츠에 대한 일반적인 eDiscovery 작업을 실행하기 위해 eDiscovery 관리자는 콘텐츠 검색, Core eDiscovery 사례 및 Advanced eDiscovery 사례에서 내보낼 때 전자 메일 메시지 콘텐츠의 암호를 해독해야 합니다. Microsoft 암호화 기술로 암호화된 콘텐츠는 내보낼 때까지 검토할 수 없습니다.

eDiscovery 워크플로에서 암호화된 콘텐츠를 더 쉽게 관리할 수 있도록 Microsoft 365 eDiscovery 도구에는 이제 전자 메일 메시지에 첨부되고 Exchange Online에서 전송되는 암호화된 파일의 암호 해독이 통합되어 있습니다. 또한 SharePoint Online 및 비즈니스용 OneDrive에 저장된 암호화된 문서는 Advanced eDiscovery에서 암호 해독됩니다. 

이 새 기능 이전에는 권한 관리(및 첨부되지 않은 파일)로 보호된 전자 메일 메시지의 콘텐츠만 암호 해독했습니다. SharePoint 및 OneDrive의 암호화된 문서는 eDiscovery 워크플로 중에 암호를 해독할 수 없습니다. 이제 Microsoft 암호화 기술로 암호화된 파일이 전자 메일 메시지에 첨부되거나 SharePoint 또는 OneDrive 계정에 있는 경우 검색 결과가 미리 보기를 준비하고 Advanced eDiscovery의 검토 집합에 추가되고 내보내면 암호화된 항목의 암호가 해독됩니다. 이를 통해 eDiscovery 관리자는 검색 결과를 미리 볼 때 암호화된 전자 메일 첨부 파일 및 사이트 문서의 콘텐츠를 보고 Advanced eDiscovery의 검토 집합에 추가된 후 검토할 수 있습니다.

## <a name="supported-encryption-technologies"></a>지원되는 암호화 기술

Microsoft eDiscovery 도구는 Microsoft 암호화 기술로 암호화된 항목을 지원합니다. 이러한 기술에는 Office 메시지 암호화, Azure 권한 관리 및 Microsoft Information Protection(특히 민감도 레이블)이 포함됩니다. Microsoft 암호화 기술에 대한 자세한 내용은 [암호화를](encryption.md)참조하십시오. 타사 암호화 기술로 암호화된 콘텐츠는 지원되지 않습니다. 예를 들어 Microsoft가 아닌 기술로 암호화된 콘텐츠를 미리 보거나 내보내는 것은 지원되지 않습니다.

## <a name="ediscovery-activities-that-support-encrypted-items"></a>암호화된 항목을 지원하는 eDiscovery 활동

다음 표에서는 SharePoint 및 OneDrive에서 전자 메일 주소 및 암호화된 문서에 첨부된 암호화된 파일에 대해 Microsoft 365 eDiscovery 도구에서 수행할 수 있는 지원되는 작업을 설명합니다. 이러한 지원되는 작업은 검색 조건과 일치하는 암호화된 파일에서 수행할 수 있습니다. 값이 "N/A"이면 해당 eDiscovery 도구에서 기능을 사용할 수 없습니다.

|eDiscovery 작업  |콘텐츠 검색  |핵심 eDiscovery  |Advanced eDiscovery  |
|:---------|:---------|:---------|:---------|
|전자 메일 및 사이트에서 암호화된 파일의 콘텐츠 검색     |예      |예      |예      |
|전자 메일에 첨부된 암호화된 파일 미리 보기     |예      |예     |예       |
|SharePoint 및 OneDrive에서 암호화된 문서 미리 보기|아니요      |아니요    |예       |
|검토 집합에서 암호화된 파일 검토    |해당 없음      |해당 없음        | 예        |
|전자 메일에 첨부된 암호화된 파일 내보내기    |예       |예  |예    |
|SharePoint 및 OneDrive에서 암호화된 문서 내보내기    |아니요       |아니요  |예    |
|||||

## <a name="requirements-for-decryption-in-ediscovery"></a>eDiscovery의 암호 해독 요구 사항

Microsoft 암호화 기술로 암호화된 파일을 미리 보고 검토하고 내보내기 위해 RMS 암호 해독 역할을 할당해야 합니다. Advanced eDiscovery의 검토 집합에 추가된 암호화된 파일을 검토하고 쿼리하려면 이 역할도 할당해야 합니다.

이 역할은 기본적으로 Office 365 보안 및  준수 센터의 사용 권한 페이지에서 eDiscovery 관리자 & 할당됩니다. RMS 암호 해독 역할에 대한 자세한 내용은 [eDiscovery 권한 할당을 참조하세요.](assign-ediscovery-permissions.md#rms-decrypt)
