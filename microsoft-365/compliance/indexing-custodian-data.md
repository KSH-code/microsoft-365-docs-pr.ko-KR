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
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Advanced eDiscovery 경우, 부분적으로 인덱싱된 것으로 확인된 모든 콘텐츠는 완전히 검색할 수 있도록 다시 처리됩니다.
ms.openlocfilehash: 205594031bcfb65b882d10217ccdcd10e4ed014d
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60201052"
---
# <a name="advanced-indexing-of-custodian-data"></a>보유자 데이터의 고급 인덱싱

Advanced eDiscovery 사례에 추가된 경우 부분적으로 인덱싱되거나 인덱싱 오류가 있는 모든 콘텐츠는 완전히 검색할 수 있도록 다시 인덱싱됩니다.  이 다시 인덱싱 프로세스를 *고급 인덱싱이라고 합니다.* 콘텐츠가 부분적으로 인덱싱되거나 인덱싱 오류가 발생하는 이유는 여러 가지가 있습니다. 여기에는 이미지 파일 또는 파일의 이미지 존재, 지원되지 않는 파일 형식 또는 파일 크기 인덱싱 제한이 포함됩니다. 파일 SharePoint 고급 인덱싱은 부분적으로 인덱싱된 것으로 표시되거나 인덱싱 오류가 있는 항목에서만 실행됩니다. Exchange 첨부 파일이 있는 전자 메일 메시지는 부분적으로 인덱싱되거나 인덱싱 오류가 있는 것으로 표시되지 않습니다. 즉, 이러한 파일은 고급 인덱싱 프로세스에서 다시 인덱싱되지 않습니다.

지원 및 부분적으로 인덱싱된 항목 처리에 대한 자세한 내용은 다음을 참조합니다.

- [지원되는 Advanced eDiscovery](supported-filetypes-ediscovery20.md)

- [eDiscovery에서 부분적으로 인덱싱된 항목](partially-indexed-items-in-content-search.md)

- [Exchange 검색에서 인덱싱하는 파일 형식](/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [SharePoint Server의 크롤링되는 기본 파일 이름 확장명 및 구문 분석되는 파일 형식](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a>고급 인덱싱 결과 보기

고급 인덱싱 프로세스가 완료되면 다시 처리의 효율성을 이해할 수 있습니다.  사례에 대한 처리 탭의  고급 인덱싱 결과 보기에서 하이브리드 인덱스에 추가된 항목 수를 *그래프에 나열합니다.*  하이브리드 인덱스는 Advanced eDiscovery에서 다시 처리된 콘텐츠를 저장합니다.

이 보기에는 수정이 필요한 항목 수와 파일 형식별로 다른 오류 그래프도 포함됩니다. 자세한 내용은 다음을 참조하세요.

- [데이터를 처리할 때 오류 수정](error-remediation-when-processing-data-in-advanced-ediscovery.md)

- [단일 항목 오류 수정](single-item-error-remediation.md)

## <a name="updating-the-advanced-index-for-custodians"></a>수급자에 대한 고급 인덱스 업데이트

관리인이 사례에 추가될 Advanced eDiscovery 부분적으로 인덱싱된 항목은 모두 다시 처리됩니다. 그러나 시간이 지나면 부분적으로 인덱싱된 항목이 사용자의 사서함 또는 사용자 계정에 추가될 OneDrive 있습니다.  필요한 경우 특정관리자에 대한 인덱스를 업데이트할 수 있습니다. 자세한 내용은 [Manage custodians in an Advanced eDiscovery 참조하세요.](manage-new-custodians.md#re-index-custodian-data) 처리 탭에서 업데이트 인덱스를 클릭하여 사례에 있는 모든 정보주에 대한 인덱스를 업데이트할 **수** 있습니다. 

> [!NOTE]
> 양도인 인덱스를 업데이트하는 것은 긴 프로세스입니다. 경우에 한해 하루 두 번 이상 인덱스를 업데이트하지 않는 것이 좋습니다.
