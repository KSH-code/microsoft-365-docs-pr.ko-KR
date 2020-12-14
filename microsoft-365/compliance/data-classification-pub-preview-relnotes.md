---
title: 데이터 분류 릴리스 정보
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 데이더 분류에 대한 릴리스 정보입니다.
ms.openlocfilehash: 2b9302cfa49f9445d3cbeb5109aef70e0c8d8f7f
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663043"
---
# <a name="data-classification-release-notes"></a>데이터 분류 릴리스 정보


## <a name="exchange-mailbox-count"></a>Exchange 사서함 수

Exchange 사서함을 드릴 다운하면 작은 도구 설명이 표시되는 것을 볼 수 있습니다. 중요한 정보 유형, 민감도 레이블 및 보존 레이블에 대해 표시되는 집계 수가 사서함 내에서 찾을 수 있는 항목 수와 정확히 일치하지 않을 수 있습니다. 이는 폴더로 드릴다운하면 집계된 수가 계산되는 동안 분류된 콘텐츠의 라이브 뷰를 가져오기 때문입니다.


## <a name="rendering-of-encrypted-documents"></a>암호화된 문서 렌더링

암호화되는 SharePoint, Exchange 및 OneDrive 파일은 콘텐츠 탐색기에서 렌더링되지 않습니다. 이는 콘텐츠 탐색기에서 파일 콘텐츠를 확인할 필요와 콘텐츠를 암호화된 상태로 유지할 필요 사이에 균형을 요구하는 중요한 문제입니다. **콘텐츠 탐색기 목록 뷰어** 및 **콘텐츠 탐색기 콘텐츠 뷰어** 역할 그룹에서 부여한 권한으로 파일, 파일, 메타 데이터, 웹 클라이언트를 통해 컨텐츠에 액세스하는 데 사용할 수 있는 링크의 목록 보기를 볼 수 있습니다.

## <a name="supported-characters-in-retention-label-names-in-sharepoint-search"></a>SharePoint 검색의 보존 레이블 이름에 지원되는 문자

SharePoint 검색은 `-` 또는 `_`가 포함된 보존 레이블 이름을 지원하지 않습니다. 예를 들어 `Label-MIP` 및 `Label_MIP`은 지원되지 않습니다. SharePoint 검색에서는 민감도 레이블 이름 및 중요한 정보 유형 이름의 문자를 지원합니다.

## <a name="onedrive-remains-in-preview"></a>OneDrive가 미리 보기에 남아 있음

미리 보기 프로그램 중 OneDrive 통합에 대한 유용한 피드백에 대해 감사드립니다. 세부 사항을 통해 작업할 때 일치하지 않는 데이터/흐름이 실행될 수 있습니다. 모든 수정 사항이 적용될 때까지 OneDrive를 미리 보기로 계속해서 제공할 것입니다. 귀하의 지속적인 지원에 감사드립니다.


## <a name="see-also"></a>참고 항목

- [데이터 분류 시작(미리 보기)](data-classification-overview.md)
- [레이블 활동 보기(미리 보기)](data-classification-activity-explorer.md)
- [레이블이 지정된 콘텐츠 보기(미리 보기)](data-classification-content-explorer.md)
- [민감도 레이블에 대해 알아보기](sensitivity-labels.md)
- [보존 정책 및 보존 레이블에 대해 알아보기](retention.md)
- [중요한 정보 유형 엔터티 정의](sensitive-information-type-entity-definitions.md)