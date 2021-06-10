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
description: Advanced eDiscovery 경우, 부분적으로 인덱싱된 것으로 확인된 모든 콘텐츠는 완전히 검색할 수 있도록 다시 처리됩니다.
ms.openlocfilehash: 904c8fe626ce8ece8f4b48bd5504e4011e9f4fb2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911212"
---
# <a name="advanced-indexing-of-custodian-data"></a>보유자 데이터의 고급 인덱싱

Advanced eDiscovery 경우, 부분적으로 인덱싱된 것으로 확인된 모든 콘텐츠는 완전히 검색할 수 있도록 다시 처리됩니다.  이 프로세스를 고급 *인덱싱이라고 합니다.* 이미지가 존재하거나, 지원되지 않는 파일 형식이나 인덱싱 파일 크기 제한이 발생하는 경우를 포함하여 여러 가지 이유로 콘텐츠를 부분적으로 인덱싱할 수 있습니다.

지원 및 부분적으로 인덱싱된 항목 처리에 대한 자세한 내용은 다음을 참조합니다.

- [지원되는 Advanced eDiscovery](supported-filetypes-ediscovery20.md)

- [Office 365의 콘텐츠 검색에서 부분적으로 인덱싱된 항목](partially-indexed-items-in-content-search.md)

- [Exchange 검색에서 인덱싱하는 파일 형식](/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [SharePoint Server의 크롤링되는 기본 파일 이름 확장명 및 구문 분석되는 파일 형식](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a>고급 인덱싱 결과 보기

고급 인덱싱 프로세스가 완료되면 다시 처리의 효율성을 이해할 수 있습니다.  사례에 대한 처리 탭의  고급 인덱싱 결과 보기에서 하이브리드 인덱스에 추가된 항목 수를 *그래프에 나열합니다.*  하이브리드 인덱스는 다시 Advanced eDiscovery 콘텐츠를 저장하는 위치입니다.

이 보기에는 수정이 필요한 항목 수와 파일 형식별로 다른 오류 그래프도 포함됩니다. 자세한 내용은 다음을 참조하세요.

- [데이터를 처리할 때 오류 수정](error-remediation-when-processing-data-in-advanced-ediscovery.md)

- [단일 항목 오류 수정](single-item-error-remediation.md)

## <a name="updating-the-advanced-index-for-custodians"></a>수급자에 대한 고급 인덱스 업데이트

관리인이 사례에 추가될 Advanced eDiscovery 부분적으로 인덱싱된 항목은 모두 다시 처리됩니다. 그러나 시간이 지나면 부분적으로 인덱싱된 항목이 사용자의 사서함 또는 사용자 계정에 추가될 OneDrive 있습니다.  필요한 경우 특정관리자에 대한 인덱스를 업데이트할 수 있습니다. 자세한 내용은 [Manage custodians in an Advanced eDiscovery 참조하세요.](manage-new-custodians.md#re-index-custodian-data) 처리 탭에서 업데이트 인덱스를 클릭하여 사례에 있는 모든 정보주에 대한 인덱스를 업데이트할 **수** 있습니다. 

> [!NOTE]
> 양도인 인덱스를 업데이트하는 것은 긴 프로세스입니다. 경우에 한해 하루 두 번 이상 인덱스를 업데이트하지 않는 것이 좋습니다.