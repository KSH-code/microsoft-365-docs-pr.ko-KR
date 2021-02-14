---
title: Microsoft 365 검색에서 테넌트 격리
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: 이 문서에서는 Microsoft 365 Search에서 테넌트 데이터를 분리하기 위해 테넌트 분리가 작동하는 방식에 대한 설명을 찾아보는 것이 가장 까다로우며,
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3416afdeceaa7000b516ec89b4a2a1e59d8708d0
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332403"
---
# <a name="tenant-isolation-in-microsoft-365-search"></a>Microsoft 365 검색에서 테넌트 격리

SharePoint Online 검색은 공유 데이터 구조의 효율성과 테넌트 간의 정보 누출을 방지하는 테넌트 분리 모델을 사용 합니다. 이 모델을 사용하여 검색 기능은 다음을 방지합니다.

- 다른 테넌트의 문서가 포함된 쿼리 결과 반환
- 숙련된 사용자가 다른 테넌트에 대한 정보를 유추할 수 있는 쿼리 결과에 충분한 정보 노출
- 다른 테넌트의 Schema 또는 설정 표시
- 테넌트 간에 분석 처리 정보 혼합 또는 잘못된 테넌트의 결과 저장
- 다른 테넌트의 사전 항목 사용

각 테넌트 데이터 유형에 대해 코드에서 하나 이상의 보호 계층을 사용하여 실수로 정보가 누출되는 것을 방지합니다. 가장 중요한 데이터는 단일 결함으로 인해 실제 또는 인식된 정보 유출이 발생하지 않는 가장 중요한 보호 계층이 있습니다.

## <a name="tenant-separation-for-the-search-index"></a>검색 인덱스에 대한 테넌트 분리

검색 인덱스는 인덱스 구성 요소를 호스트하는 서버의 디스크에 저장되고 테넌트는 인덱스 파일을 공유합니다. 테넌트의 인덱싱된 문서는 해당 테넌트에 대한 쿼리에만 표시됩니다. 세 가지 독립적인 메커니즘으로 정보 유출을 방지합니다.

- 테넌트 ID 필터링
- 테넌트 ID 용어 prefixing
- ACL 검사

세 가지 메커니즘 모두 검색에서 잘못된 테넌트에 문서를 반환하는 데 실패해야 합니다.

## <a name="tenant-id-filtering-and-tenant-id-term-prefixing"></a>테넌트 ID 필터링 및 테넌트 ID 용어 Prefixing

검색에는 테넌트 ID가 있는 전체 텍스트 인덱스에서 인덱싱된 모든 용어가 미리 표시됩니다. 예를 들어 ID가 *"123"인* 테넌트에 대해 *"foo"라는* 용어가 인덱싱된 경우 전체 텍스트 인덱스의 항목은 *"123foo"입니다.*"

모든 쿼리는 테넌트 ID 필터링이라는 프로세스를 사용하여 테넌트 ID를 포함하기 위해 변환됩니다. 예를 들어 "*foo"* 쿼리는 "<*guid>.* *foo* AND *tenantID*:<*guid*>"입니다. 여기서 <*guid*> 쿼리를 수행하는 테넌트입니다. 이 쿼리 변환은 각 인덱스 노드 내에서 발생하며 쿼리와 콘텐츠 처리 모두 해당 노드에 영향을 줄 수 없습니다. 테넌트 ID는 모든 쿼리에 추가되는 것이기 때문에 한 테넌트에서 최상의 일치 순위를 보고 다른 테넌트의 용어 빈도를 유추할 수 없습니다.

테넌트 ID 용어 사전은 전체 텍스트 인덱스에서만 발생합니다. *"title:foo"와* 같은 필드로 입력된 검색은 용어에 테넌트 ID가 추가되지 않은 가상 검색 인덱스로 이동됩니다. 대신 필드 검색에는 필드 이름이 사전으로 추가됩니다. 예를 들어 *"title:foo"* 쿼리는 *"fields.title:foo AND fields.tenantID*:<*guid>."* 쿼리로 변환됩니다. 용어의 빈도는 가상 검색 인덱스의 적중 수 순위에 영향을 주지 않습니다. 따라서 용어의 사전순으로 테넌트 구분을 할 필요가 없습니다. *"title:foo"와* 같은 필드 검색의 경우 테넌트 콘텐츠 분리는 쿼리 변환을 통해 테넌트 ID 필터링에 따라 달라 집니다.

## <a name="document-access-control-list-checks"></a>문서 액세스 제어 목록 검사

검색은 검색 인덱스에 저장된 ACL을 통해 문서에 대한 액세스를 제어합니다. 모든 항목은 특수 ACL 필드의 용어 집합으로 인덱싱됩니다. ACL 필드에는 문서를 볼 수 있는 그룹 또는 사용자당 하나의 용어가 포함되어 있습니다. 모든 쿼리에는 인증된 사용자가 속한 각 그룹에 대해 하나씩 ACE(액세스 제어 항목) 용어 목록이 추가됩니다.

예를 들어 "<*guid>.* *foo AND tenantID*:<*guid>"* "<*guid>.* *foo AND tenantID*:<*guid* >  *AND* (*docACL:* < *ace1* OR >  *docACL*:<*ace2* OR >  *docACL*:<*ace3* >  *...*)"

사용자 및 그룹 식별자 및 따라서 AES는 고유하기 때문에 일부 사용자에게만 표시되는 문서의 테넌트 간에 추가 보안 수준을 제공합니다. 테넌트의 일반 사용자에게 액세스 권한을 부여하는 특수 "외부 사용자를 제외한 모든 사용자" ACE의 경우도 마찬가지입니다. 그러나 "모든 사용자"에 대한 AES는 모든 테넌트에 대해 동일하기 때문에 공용 문서에 대한 테넌트 분리는 테넌트 ID 필터링에 따라 달라 습니다. AES 거부도 지원됩니다. 쿼리 보강은 거부 ACE와 일치하는 일치가 있는 경우 결과에서 문서를 제거하는 절을 추가합니다.

Exchange Online 검색에서 인덱스는 SharePoint Online에서와 같은 테넌트 ID(구독 ID) 대신 개별 사용자 사서함의 사서함 ID로 분할됩니다. 분할 메커니즘은 SharePoint Online과 동일하지만 ACL 필터링은 없습니다.
