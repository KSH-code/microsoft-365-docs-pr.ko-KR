---
title: 단일 항목 오류 수정
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
description: 고급 eDiscovery의 검토 집합에 포함 된 문서에서 대량 오류 업데이트 관리 프로세스를 수행 하지 않고도 처리 오류를 해결할 수 있습니다.
ms.openlocfilehash: 3c50f9dcd1448ee36edd0e82e5b2c2879c11d6b5
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42069697"
---
# <a name="single-item-error-remediation"></a>단일 항목 오류 수정

오류 수정을 통해 고급 eDiscovery 사용자는 고급 eDiscovery가 콘텐츠를 제대로 처리 하지 못하게 하는 데이터 문제를 해결할 수 있습니다. 예를 들어 암호로 보호 된 파일은 잠겨 있거나 암호화 되어 처리할 수 없습니다. 이전에는 [이 워크플로](error-remediation-when-processing-data-in-advanced-ediscovery.md)를 사용 하 여 대량 으로만 오류를 수정할 수 있었습니다. 그러나 조사 중인 사례에 대응 되는 파일이 있는지 확실 하지 않은 경우에는 여러 파일의 오류를 수정 하는 것이 좋을 수 있습니다. 또한 파일 위치 또는 액세스 권한이 있는 파일 메타 데이터를 검토 하 여 응답성에 대 한 사전 결정을 내리는 데 도움이 되도록 오류를 수정 하는 것은 바람직하지 않을 수 있습니다. *단일 항목 오류 수정* 프로그램 이라는 새로운 기능을 통해 eDiscovery 관리자는 처리 오류가 발생 한 파일의 메타 데이터를 볼 수 있으며, 필요한 경우 검토 집합에서 오류를 직접 수정 하는 기능이 제공 됩니다. 이 문서에서는 검토 집합에서 처리 오류가 발생 한 파일을 식별, 무시 및 수정 하는 방법에 대해 설명 합니다.

## <a name="identify-documents-with-errors"></a>오류가 있는 문서 확인

검토 집합에서 처리 오류가 발생 한 문서가 배너를 통해 식별 됩니다. 오류를 수정 하거나 무시할 수 있습니다. 다음 스크린샷은 검토 중에 암호로 보호 된 Word 문서에 대 한 처리 오류 배너를 보여 줍니다. 또한 처리 오류가 있는 문서의 파일 메타 데이터를 볼 수 있습니다.

![처리 오류가 있는 문서에 대해 표시 되는 배너](../media/SIERimage1.png)

[검토 집합에서 문서를 쿼리할](review-set-search.md)때 **처리 상태** 조건을 사용 하 여 처리 오류가 있는 문서를 검색할 수도 있습니다.

![처리 상태 조건을 사용 하 여 오류 문서 검색](../media/SIERimage2.png)

### <a name="ignore-errors"></a>오류 무시

처리 오류 배너에서 **건너뛰기를** 클릭 하 여 처리 오류를 무시할 수 있습니다. 오류를 무시 하면 문서가 [대량 오류 수정 워크플로](error-remediation-when-processing-data-in-advanced-ediscovery.md)에서 제거 됩니다. 오류가 무시 되 면 문서 배너가 색이 변경 되 고 처리 오류가 무시 됨을 나타냅니다. 언제 든 지 **되돌리기를**클릭 하 여 오류를 무시 하도록 결정을 되돌릴 수 있습니다.

![처리 오류를 무시 하려면 Ignore를 클릭 합니다.](../media/SIERimage3.png)

검토 집합에서 문서를 쿼리할 때 *처리 오류 무시* 조건을 사용 하 여 처리 오류가 발생 한 모든 문서를 검색할 수도 있습니다.

![무시 된 오류 문서를 검색 하는 데 필요한 문제 처리 오류 조건을 사용 합니다.](../media/SIERimage4.png)

## <a name="remediate-a-document-with-errors"></a>오류가 있는 문서 수정

경우에 따라 문서에서 암호를 제거 하 고 암호화 된 파일의 암호를 해독 하거나 손상 된 문서를 복구 하는 방법으로 처리 오류를 수정 하 고 검토 집합에 재구성 된 문서를 추가할 수 있습니다. 이를 통해 오류 문서를 검토 하 고 검토 집합의 다른 문서와 함께 내보낼 수 있습니다. 

단일 문서를 수정 하려면 다음 단계를 수행 합니다.

1. **원본 다운로드** **다운로드** > 를 클릭 하 여 로컬 컴퓨터에 파일의 복사본을 다운로드 합니다.

   ![처리 오류와 함께 문서 다운로드](../media/SIERimage5.png)

2. 오프 라인 파일에서 오류를 수정 합니다. 암호화 된 파일의 경우 암호 보호를 제거 하려면 암호를 입력 하 고 파일을 저장 하거나 암호 해독을 사용 해야 합니다. 파일을 수정 했으면 다음 단계로 이동 합니다.

3. 검토 집합에서 재구성 한 처리 오류가 있는 파일을 선택 하 고 **수정을**클릭 합니다.

   ![처리 오류가 있는 문서의 배너에서 업데이트를 클릭 합니다.](../media/SIERimage6.png)


4. **찾아보기를**클릭 하 고 로컬 컴퓨터에서 재구성 된 파일 위치로 이동한 다음 파일을 선택 합니다.

   ![찾아보기를 클릭 하 고 로컬 컴퓨터에서 재구성 한 파일을 선택 합니다.](../media/SIERimage7.png)

    재구성 된 파일을 선택 하면 해당 파일이 검토 집합에 자동으로 업로드 됩니다. 파일의 처리 상태를 추적할 수 있습니다.

    ![업데이트 관리 프로세스의 상태가 표시 됩니다.](../media/SIERimage8.png)

   처리가 완료 되 면 재구성 된 문서를 볼 수 있습니다.

    ![재구성 한 파일을 검토 집합의 기본 형식으로 볼 수 있습니다.](../media/SIERimage9.png)

문서를 수정 하는 경우 수행 되는 작업에 대 한 자세한 내용은 파일을 수정 [했을 때 수행 되는 작업](error-remediation.md#what-happens-when-files-are-remediated)을 참조 하십시오.

## <a name="search-for-remediated-documents"></a>재구성 한 문서 검색

**키워드** 조건을 사용 하 고 값 쌍: **Isfromerrorremediation: true**속성을 지정 하 여 검토 집합에서 재구성 된 모든 문서를 검색할 수 있습니다. 이 속성은 문서를 검토 집합에서 내보낼 때 내보내기 로드 파일 에서도 사용할 수 있습니다.
