---
title: 데이터 분류 미리 보기 릴리스 정보(미리 보기)
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
description: 데이터 분류 공개 미리 보기에 대한 릴리스 정보입니다.
ms.openlocfilehash: fecf643d12cf544c16570c173b15bb1e0dc043f0
ms.sourcegitcommit: 3d17c1d6b80672719b1878e2f321f0de39595226
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41887343"
---
# <a name="data-classification-public-preview-release-notes-preview"></a>데이터 분류 공개 미리 보기 릴리스 정보(미리 보기)

이 공개 미리 보기에는 정책 만들기 *전에* 민감한 콘텐츠와 레이블이 지정된 콘텐츠의 스캔을 시작하는 새로운 기능이 도입되었습니다. 이를 **제로 변경 관리**라고 합니다. 이를 통해 모든 보존 및 민감도 레이블이 환경에 미치는 영향을 확인하고, 보호 및 관리 정책 요구 사항을 평가할 수 있습니다.

이 공개 미리 보기를 사용하여 최상의 환경을 활용하려면 이 릴리스 정보를 검토하세요. 저희는 지금과 GA(일반 가용성) 사이의 이러한 점을 해결하는 작업을 진행하고 있습니다.

## <a name="permissions-for-accessing-content-explorer"></a>콘텐츠 탐색기 액세스 권한

콘텐츠 탐색기에 대한 액세스는 검사된 파일의 내용을 읽을 수 있기 때문에 매우 제한적입니다. 콘텐츠 탐색기에 액세스하려면 **콘텐츠 탐색기 목록 뷰어**와 **콘텐츠 탐색기 콘텐츠 뷰어**에서 구성원 자격이 필요합니다. 기본적으로는 어떤 계정에서도 콘텐츠 탐색기에 액세스할 수 없습니다. [데이터 분류 콘텐츠 탐색기(미리 보기) 사용](data-classification-content-explorer.md#permissions)을 참조하세요. 전역 관리자, 준수 관리자 또는 데이터 관리자는 필요한 **콘텐츠 탐색기 목록 뷰어**와 **콘텐츠 탐색기 콘텐츠 뷰어** 역할 그룹 구성원 자격을 할당할 수 있습니다.

> [!TIP]
> **콘텐츠 탐색기 목록 뷰어**와 **콘텐츠 탐색기 콘텐츠 뷰어** 역할 그룹은 RBAC(역할 기반 엑세스 제어)가 세계적으로 배포되는 동안에는 사용 권한 페이지에 표시되지 않을 수 있습니다. 이들이 사용 권한 페이지에 표시되지 않는 경우 사용자 지정 역할 그룹을 만들고 사용자 지정 역할 그룹에 `data classification list viewer` 역할이나 `data classification content viewer` 역할을 할당해야 합니다.

## <a name="exchange-mailbox-count"></a>Exchange 사서함 수

Exchange 사서함을 드릴 다운하면 작은 도구 설명이 표시되는 것을 볼 수 있습니다. 중요한 정보 유형, 민감도 레이블 및 보존 레이블에 대해 표시되는 집계 수가 사서함 내에서 찾을 수 있는 항목 수와 정확히 일치하지 않을 수 있습니다. 이는 폴더로 드릴 다운하면 집계된 카운트가 계산되는 동안 분류된 콘텐츠의 라이브 뷰를 가져오기 때문입니다.

## <a name="seeing-guids-instead-of-label-names"></a>레이블 이름 대신 GUID 보기

개인 미리 보기 고객은 컨텐츠에 이미 스탬핑된 레이블을 삭제하면 콘텐츠 탐색기와 활동 탐색기에서 레이블 이름 대신 레이블 이름이 32비트 GUID로 해석되는 레이블이 있는 인스턴스를 보았습니다. 

## <a name="rendering-of-encrypted-documents"></a>암호화된 문서 렌더링

암호화되는 SharePoint, Exchange 및 OneDrive 파일은 콘텐츠 탐색기에서 렌더링되지 않습니다. 이는 콘텐츠 탐색기에서 파일 콘텐츠를 확인할 필요와 콘텐츠를 암호화된 상태로 유지할 필요 사이에 균형을 요구하는 중요한 문제입니다. **콘텐츠 탐색기 목록 뷰어** 및 **콘텐츠 탐색기 콘텐츠 뷰어** 역할 그룹에서 부여한 권한으로 파일, 파일, 메타 데이터, 웹 클라이언트를 통해 컨텐츠에 액세스하는 데 사용할 수 있는 링크의 목록 보기를 볼 수 있습니다.

## <a name="supported-characters-in-retention-label-names-in-sharepoint-search"></a>SharePoint 검색의 보존 레이블 이름에 지원되는 문자

SharePoint 검색은 `-` 또는 `_`이(가) 포함된 보존 레이블 이름을 지원하지 않습니다. 예를 들어 `Label-MIP` 및 `Label_MIP`은(는) 지원되지 않습니다. SharePoint 검색에서는 민감도 레이블 이름 및 중요한 정보 유형 이름의 문자를 지원합니다.

## <a name="see-also"></a>참고 항목

- [데이터 분류 시작(미리 보기)](data-classification-overview.md)
- [레이블 활동 보기(미리 보기)](data-classification-activity-explorer.md)
- [레이블이 지정된 콘텐츠 보기(미리 보기)](data-classification-content-explorer.md)
- [민감도 레이블](sensitivity-labels.md)
- [보존 레이블](labels.md)
- [중요한 정보 유형이 찾는 항목](what-the-sensitive-information-types-look-for.md)

