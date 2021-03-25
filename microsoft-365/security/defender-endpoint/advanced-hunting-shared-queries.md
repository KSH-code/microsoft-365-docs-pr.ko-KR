---
title: 고급 헌팅에서 공유 쿼리 사용
description: 미리 정의된 쿼리 및 공유 쿼리를 사용하여 위협 요소를 즉시 헌팅합니다. 쿼리를 공용 또는 조직에 공유합니다.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, mdatp, microsoft defender atp, wdatp 검색, 쿼리, 원격 분석, 사용자 지정 검색, schema, kusto, github 리포지타이저, 내 쿼리, 공유 쿼리
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 9788594eaab29aba54c634e79c7aa00d6148aacd
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51075468"
---
# <a name="use-shared-queries-in-advanced-hunting"></a>고급 헌팅에서 공유 쿼리 사용

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)

>Endpoint용 Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

[고급 헌팅](advanced-hunting-overview.md) 쿼리는 동일한 조직에 있는 사용자들 간에 공유될 수 있습니다. GitHub에서 공개적으로 공유되는 쿼리를 찾을 수도 있습니다. 이러한 쿼리를 사용하여 쿼리를 처음부터 작성하지 않고도 특정 위협 요소를 신속하게 파악할 수 있습니다.

![공유 쿼리 이미지](images/atp-advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a>쿼리 저장, 수정 및 공유
새로운 쿼리나 기존 쿼리를 저장하여 조직의 다른 사용자와 공유하거나 해당 쿼리를 액세스하도록 할 수 있습니다.

1. 새 쿼리를 입력하거나 공유 쿼리 또는 내 **쿼리에서** 기존 쿼리를 **로드합니다.**

2. 저장 **옵션에서** **다른 사용자로** 저장 또는 저장을 선택합니다. 기존 쿼리를 덮어 작성하지 않도록 방지하기 위해 다른 로 **저장을 선택하십시오.**

3. 쿼리 이름을 입력합니다.

   ![쿼리 저장의 이미지](images/advanced-hunting-save-query.png)

4. 쿼리를 저장할 폴더를 선택합니다.
    - **공유 쿼리** - 조직의 모든 사용자에게 공유
    - **나의 쿼리** — 사용자 본인만 액세스 가능합니다.
    
5. **저장** 을 선택합니다.

## <a name="delete-or-rename-a-query"></a>쿼리 삭제 또는 이름 바꾸기
1. 이름을 바꾸거나 삭제하려는 쿼리를 마우스 오른쪽 단추로 클릭합니다.

    ![쿼리 삭제의 이미지](images/atp_advanced_hunting_delete_rename.png)

2. **삭제** 선택하고 삭제를 확인합니다. 또는 **이름 바꾸기** 를 선택하고 쿼리의 새 이름을 입력합니다.

## <a name="create-a-direct-link-to-a-query"></a>쿼리에 대한 직접 링크 만들기
고급 헌팅 쿼리 편집기에서 쿼리를 직접 여는 링크를 생성하려면 쿼리를 마무리하고 링크 **공유 를 선택합니다.**

## <a name="access-queries-in-the-github-repository"></a>GitHub 리포지토리의 쿼리에 액세스  
Microsoft 보안 연구원은 [GitHub의 지정된 공용 저장소](https://github.com/Microsoft/WindowsDefenderATP-Hunting-Queries)에서 고급 헌팅 쿼리를 정기적으로 공유 합니다. 이 리포지토리는 참가 기회가 열려 있습니다. 참가하려면 [무료로 GitHub에 가입](https://github.com/)하세요. 

>[!TIP]
>또한 Microsoft 보안 연구원들은 최신 위협과 관련 된 활동과 지표를 찾는 데 사용할 수 있는 고급 검색 쿼리를 제공합니다. 이러한 쿼리는 Microsoft Defender 보안 센터의 [위협 분석](threat-analytics.md) 보고서의 일부로 제공됩니다.

## <a name="related-topics"></a>관련 항목
- [고급 헌팅 개요](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [쿼리 결과 작업](advanced-hunting-query-results.md)
- [스키마의 이해](advanced-hunting-schema-reference.md)
- [쿼리 모범 사례 적용](advanced-hunting-best-practices.md)
- [사용자 지정 검색 개요](overview-custom-detections.md)
