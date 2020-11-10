---
title: EDiscovery에서 암호 해독
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
description: Microsoft 365 eDiscovery 도구에서 전자 메일 메시지에 첨부 되는 암호화 된 문서를 처리 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 3a4a094f1da28c9a017836c099507f5af739b0b9
ms.sourcegitcommit: 9bf6a4f77f9af5fd988f6795bad3b240213a51fc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2020
ms.locfileid: "48951121"
---
# <a name="decryption-in-microsoft-365-ediscovery-tools"></a>Microsoft 365 eDiscovery 도구에서 암호 해독

암호화는 파일 보호 및 정보 보호 전략의 중요 한 부분입니다. 모든 유형의 조직은 암호화 기술을 사용 하 여 조직 내의 중요 한 콘텐츠를 보호 하 고 적절 한 사용자 에게만 해당 콘텐츠에 대 한 액세스 권한이 있는지 확인 합니다.

암호화 된 콘텐츠에 대 한 일반적인 eDiscovery 작업을 실행 하려면 eDiscovery 관리자가 콘텐츠 검색, 핵심 eDiscovery 사례 및 고급 eDiscovery 사례에서 내보낸 것 처럼 전자 메일 메시지 콘텐츠를 해독 해야 했습니다. Microsoft 암호화 기술을 사용 하 여 암호화 된 콘텐츠는 내보낼 때까지 검토에 사용할 수 없습니다.

EDiscovery 워크플로에서 암호화 된 콘텐츠를 보다 쉽게 관리할 수 있도록 하기 위해 Microsoft 365 eDiscovery 도구는 전자 메일 메시지에 첨부 되 고 Exchange Online에서 전송 되는 암호화 된 파일의 암호 해독이 통합 되었습니다. 이 새로운 기능을 수행 하기 전에는 권한 관리로 보호 되는 전자 메일 메시지의 콘텐츠 (연결 된 파일 아님)만 암호 해독 되었습니다. 이제 Microsoft 암호화 기술로 암호화 된 파일이 검색 조건과 일치 하는 전자 메일 메시지에 첨부 되는 경우 검색 결과를 검토할 준비가 되 면 암호화 된 파일의 암호가 해독 됩니다. 이를 통해 eDiscovery 관리자는 검색 결과를 미리 볼 때 암호화 된 전자 메일 첨부 파일의 콘텐츠를 보고 고급 eDiscovery의 검토 집합에 추가한 후 검토를 검토할 수 있습니다.

> [!NOTE]
> 시작 하기 위해 Microsoft 365 eDiscovery 도구는 SharePoint Online 및 비즈니스용 OneDrive에 저장 되어 있는 암호화 된 문서를 지원 합니다.

## <a name="supported-encryption-technologies"></a>지원 되는 암호화 기술

Microsoft eDiscovery 도구는 Microsoft 암호화 기술로 암호화 된 항목을 지원 합니다. 이러한 기술에는 Office 메시지 암호화, Microsoft Information Protection (출시 예정) 및 Azure 권한 관리가 포함 됩니다. Microsoft 암호화 기술에 대 한 자세한 내용은 [encryption](encryption.md)을 참조 하십시오. 타사 암호화 기술로 암호화 된 콘텐츠는 지원 되지 않습니다. 여기에는 Microsoft 제품이 아닌 기술로 암호화 된 콘텐츠를 미리 보거나 내보낼 때 지원 되는 기능이 포함 되지 않습니다.

## <a name="ediscovery-activities-that-support-encrypted-items"></a>암호화 된 항목을 지 원하는 eDiscovery 활동

다음 표에는 전자 메일 massages에 첨부 되어 있는 암호화 된 파일의 암호 해독이 지원 되는 Microsoft 365 eDiscovery 도구에서 수행 하는 작업이 나와 있습니다. 검색 조건과 일치 하는 전자 메일 메시지에 첨부 된 암호화 된 파일에서 지원 작업을 수행할 수 있습니다. 값이 "N/A" 이면 해당 eDiscovery 도구에서 해당 함수를 사용할 수 없습니다.

|eDiscovery 작업  |콘텐츠 검색  |핵심 eDiscovery  |Advanced eDiscovery  |
|:---------|:---------|:---------|:---------|
|암호화 된 파일에서 콘텐츠 검색     |예      |예      |예      |
|암호화 된 파일 미리 보기     |예      |예     |예       |
|검토 집합에서 암호화 된 파일 검토    |해당 없음      |해당 없음        | 예        |
|암호화 된 파일 내보내기    |예       |예  |예    |

## <a name="requirements-for-decryption-in-ediscovery"></a>EDiscovery의 암호 해독 요구 사항

Microsoft 암호화 기술로 암호화 된 첨부 파일을 미리 보고 검토 하 고 내보내려면 RMS 암호 해독 역할을 할당 받아야 합니다. 또한 고급 eDiscovery에서 검토 집합에 추가 된 암호화 된 전자 메일 첨부 파일을 검토 하 고 쿼리 하려면이 역할을 할당 받아야 합니다.

이 역할은 Office 365 보안 & 준수 센터의 eDiscovery 관리자 역할 그룹에 기본적으로 할당 됩니다. RMS 암호 해독 역할에 대 한 자세한 내용은 [eDiscovery 사용 권한 할당](assign-ediscovery-permissions.md#rms-decrypt)을 참조 하십시오.
