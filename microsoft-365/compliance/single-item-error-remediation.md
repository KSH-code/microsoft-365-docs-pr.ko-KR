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
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 대량 오류 수정 프로세스를 수행하지 않고도 문서의 검토 집합에서 Advanced eDiscovery 오류를 수정할 수 있습니다.
ms.openlocfilehash: c816ef1e3fd28299bb316e51aa434a8f08d544a0
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60200380"
---
# <a name="single-item-error-remediation-in-advanced-ediscovery"></a>단일 항목 오류 수정 Advanced eDiscovery

오류 수정을 Advanced eDiscovery 사용자가 콘텐츠가 제대로 처리되지 않도록 하는 데이터 문제를 Advanced eDiscovery 수 있습니다. 예를 들어 암호로 보호된 파일은 잠기거나 암호화되어 있기 때문에 처리될 수 없습니다. 이전에는 이 워크플로를 사용하여 대량으로만 오류를 [수정할 수 있습니다.](error-remediation-when-processing-data-in-advanced-ediscovery.md) 그러나 조사하고 있는 사례에 응답하는 파일이 없는 경우 여러 파일의 오류를 수정하는 것이 타당하지 않은 경우도 있습니다. 또한 파일 메타데이터(예: 파일 위치 또는 액세스 권한이 있는 사용자)를 검토하기 전에 오류를 수정하여 응답성에 대한 선행 결정을 내리는 데 도움이 될 수 있습니다. 단일 항목  오류 수정이라는 새로운 기능을 통해 eDiscovery 관리자는 처리 오류가 있는 파일의 메타데이터를 보고 필요한 경우 검토 집합에서 직접 오류를 수정하는 기능을 사용할 수 있습니다. 이 문서에서는 검토 집합에서 오류를 처리하여 파일을 식별, 무시 및 수정하는 방법에 대해 논의합니다.

## <a name="identify-documents-with-errors"></a>오류가 있는 문서 식별

이제 검토 집합에서 오류를 처리하는 문서가 배너로 식별됩니다. 오류를 수정하거나 무시할 수 있습니다. 다음 스크린샷은 암호로 보호된 검토 집합의 Word 문서에 대한 처리 오류 배너를 보여줍니다. 또한 처리 오류와 함께 문서의 파일 메타데이터를 볼 수 있습니다.

![처리 오류와 함께 문서에 표시되는 배너입니다.](../media/SIERimage1.png)

검토 집합의 문서를 쿼리할 때 처리 상태  조건을 사용하여 처리 오류가 있는 문서를 검색할 [수도 있습니다.](review-set-search.md)

![처리 상태 조건을 사용하여 오류 문서를 검색합니다.](../media/SIERimage2.png)

### <a name="ignore-errors"></a>오류 무시

처리 오류 배너에서 **무시를** 클릭하여 처리 오류를 무시할 수 있습니다. 오류를 무시하면 문서가 대량 오류 수정 [워크플로에서 제거됩니다.](error-remediation-when-processing-data-in-advanced-ediscovery.md) 오류가 무시되면 문서 배너의 색이 변경되고 처리 오류가 무시된 것입니다. 원하는 경우 되전을 클릭하여 오류를 무시하기로 결정한 시간을 **되전할 수 있습니다.**

![처리 오류를 무시하려면 무시를 클릭합니다.](../media/SIERimage3.png)

검토 집합에서 문서를 쿼리할 때 무시된 처리 오류 조건을  사용하여 처리 오류가 무시된 모든 문서를 검색할 수도 있습니다.

![무시된 처리 오류 조건을 사용하여 무시된 오류 문서를 검색합니다.](../media/SIERimage4.png)

## <a name="remediate-a-document-with-errors"></a>오류로 문서 수정

경우에 따라 암호 제거, 암호화된 파일 암호 해독 또는 손상된 문서 복구를 통해 문서의 처리 오류를 수정한 다음 수정된 문서를 검토 집합에 추가해야 할 수 있습니다. 이렇게 하면 오류 문서를 검토하고 검토 집합의 다른 문서와 함께 내보낼 수 있습니다. 

단일 문서를 수정하기 위해 다음 단계를 수행합니다.

1. 원본 **다운로드를** 클릭하여 파일 복사본을 로컬 컴퓨터에  >   다운로드합니다.

   ![처리 오류와 함께 문서를 다운로드합니다.](../media/SIERimage5.png)

2. 파일을 오프라인으로 수정합니다. 암호 보호를 제거하려면 암호 해독 소프트웨어가 필요한 암호화된 파일의 경우 암호를 제공하고 파일을 저장하거나 암호 크래커를 사용하세요. 파일을 수정한 후 다음 단계로 이동하십시오.

3. 검토 집합에서 수정한 처리 오류가 있는 파일을 선택하고 수정 **을 클릭합니다.**

   ![처리 오류로 문서 배너에서 수정을 클릭합니다.](../media/SIERimage6.png)


4. **찾아보기를** 클릭하고 로컬 컴퓨터에서 수정된 파일의 위치로 이동한 다음 파일을 선택합니다.

   ![찾아보기를 클릭하고 로컬 컴퓨터에서 수정된 파일을 선택합니다.](../media/SIERimage7.png)

    수정된 파일을 선택한 후 검토 집합에 자동으로 업로드됩니다. 파일의 처리 상태를 추적할 수 있습니다.

    ![재구성 프로세스의 상태가 표시됩니다.](../media/SIERimage8.png)

   처리가 완료되면 수정된 문서를 볼 수 있습니다.

    ![수정된 파일은 검토 집합에서 기본 형식으로 볼 수 있습니다.](../media/SIERimage9.png)

문서가 수정되는 경우 발생하는 일에 대한 자세한 내용은 파일이 수정되는 경우 발생하는 [일 을 참조하세요.](error-remediation-when-processing-data-in-advanced-ediscovery.md#what-happens-when-files-are-remediated)

## <a name="search-for-remediated-documents"></a>수정된 문서 검색

키워드 조건을 사용하고 **IsFromErrorRemediation:true** 속성  쌍을 지정하여 수정된 검토 집합의 모든 문서를 검색할 수 있습니다. 이 속성은 검토 집합에서 문서를 내보낼 때 로드 파일 내보내기에서도 사용할 수 있습니다.
