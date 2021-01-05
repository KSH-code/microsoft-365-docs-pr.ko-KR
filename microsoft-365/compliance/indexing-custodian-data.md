---
title: 보유자 데이터의 고급 인덱싱
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 고급 eDiscovery 사례에 상주하는 경우 부분적으로 인덱싱된 것으로 확인된 모든 콘텐츠는 완전히 검색할 수 있도록 다시 처리됩니다.
ms.openlocfilehash: 908d01cacc103639e1f9efe965240c33a5296ba9
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750759"
---
# <a name="advanced-indexing-of-custodian-data"></a>보유자 데이터의 고급 인덱싱

고급 eDiscovery 사례에 보안 주체가 추가된 경우 부분적으로 인덱싱된 것으로 확인된 모든 콘텐츠는 완전히 검색할 수 있도록 다시 처리됩니다.  이 프로세스를 고급 *인덱싱이라고 합니다.* 이미지가 존재하거나, 지원되지 않는 파일 형식이나 인덱싱 파일 크기 제한이 발생하는 경우를 비롯한 다양한 이유로 콘텐츠를 부분적으로 인덱싱할 수 있습니다.

지원 및 부분적으로 인덱싱된 항목 처리에 대한 자세한 내용은 다음을 참조합니다.

- [Advanced eDiscovery에서 지원되는 파일 형식](supported-filetypes-ediscovery20.md)

- [Office 365의 콘텐츠 검색에서 부분적으로 인덱싱된 항목](partially-indexed-items-in-content-search.md)

- [Exchange 검색에서 인덱싱하는 파일 형식](https://docs.microsoft.com/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [SharePoint Server의 크롤링되는 기본 파일 이름 확장명 및 구문 분석되는 파일 형식](https://docs.microsoft.com/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a>고급 인덱싱 결과 보기

고급 인덱싱 프로세스가 완료되면 다시 처리의 효율성을 이해할 수 있습니다.  사례에 대한 처리 탭의  고급 인덱싱 결과 보기에서 그래프에는 하이브리드 인덱스에 추가된 항목 *수가 나열됩니다.*  하이브리드 인덱스는 Advanced eDiscovery가 다시 처리된 콘텐츠를 저장하는 위치입니다.

이 보기에는 수정이 필요한 항목 수와 파일 형식별로 다른 오류 그래프도 포함됩니다. 자세한 내용은 다음을 참조하세요.

- [데이터를 처리할 때 오류 수정](error-remediation-when-processing-data-in-advanced-ediscovery.md)

- [단일 항목 오류 수정](single-item-error-remediation.md)

## <a name="updating-the-advanced-index-for-custodians"></a>양도자에 대한 고급 인덱스 업데이트

고급 eDiscovery 사례에 custodian을 추가하면 부분적으로 인덱싱된 모든 항목이 다시 처리됩니다. 그러나 시간이 지나면 부분적으로 인덱싱된 항목이 사용자의 사서함 또는 OneDrive 계정에 추가될 수 있습니다.  필요한 경우 특정 정보주에 대한 인덱스를 업데이트할 수 있습니다. 자세한 내용은 Advanced eDiscovery 사례의 보호자 [관리(Manage custodians)를 참조하세요.](manage-new-custodians.md#re-index-custodian-data) 처리 탭에서 업데이트 인덱스를 클릭하여 사례의 모든 보전자에 대한 **인덱스를** 업데이트할 **수** 있습니다.

> [!NOTE]
> 양도자 인덱스 업데이트는 오랫동안 실행되는 프로세스입니다. 경우에 한해 하루 두 번 이상 인덱스를 업데이트하지 않는 것이 좋습니다.
