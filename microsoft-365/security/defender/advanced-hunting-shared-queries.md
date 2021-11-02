---
title: 고급 헌팅에서 Microsoft 365 Defender 쿼리 사용
description: 미리 정의된 쿼리 및 공유 쿼리를 사용하여 위협 요소를 즉시 헌팅합니다. 쿼리를 공용 또는 조직에 공유합니다.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 365 Defender, microsoft 365, m365, 검색, 쿼리, 원격 분석, 사용자 지정 검색, schema, kusto, github 리포지터, 내 쿼리, 공유 쿼리
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 843d81664ce3f9b88d5de6fe742aab123df75a4f
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2021
ms.locfileid: "60643198"
---
# <a name="use-shared-queries-in-advanced-hunting"></a>고급 헌팅에서 공유 쿼리 사용

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender
- 끝점용 Microsoft Defender



[고급 헌팅](advanced-hunting-overview.md) 쿼리는 동일한 조직에 있는 사용자들 간에 공유될 수 있습니다. GitHub에서 공개적으로 공유되는 쿼리를 찾을 수도 있습니다. 이러한 쿼리를 사용하여 쿼리를 처음부터 작성하지 않고도 특정 위협 요소를 신속하게 파악할 수 있습니다.

![공유 쿼리의 이미지입니다.](../../media/advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a>쿼리 저장, 수정 및 공유
새로운 쿼리나 기존 쿼리를 저장하여 조직의 다른 사용자와 공유하거나 해당 쿼리를 액세스하도록 할 수 있습니다. 

1. 쿼리 만들기 또는 수정 

2. **쿼리 저장** 드롭다운 단추를 클릭하고 **다른 이름으로 저장** 을 선택합니다.
    
3. 쿼리 이름을 입력합니다. 

   ![쿼리 저장 이미지입니다.](../../media/advanced-hunting-save-query.png)

4. 쿼리를 저장할 폴더를 선택합니다.
    - **공유 쿼리** — 조직에 있는 모든 사용자에게 공유합니다.
    - **나의 쿼리** — 사용자 본인만 액세스 가능합니다.
    
5. **저장** 을 선택합니다. 

## <a name="delete-or-rename-a-query"></a>쿼리 삭제 또는 이름 바꾸기
1. 이름을 바꾸거나 삭제하려는 쿼리를 마우스 오른쪽 단추로 클릭합니다.

    ![삭제 쿼리의 이미지입니다.](../../media/advanced_hunting_delete_rename.png)

2. **삭제** 선택하고 삭제를 확인합니다. 또는 **이름 바꾸기** 를 선택하고 쿼리의 새 이름을 입력합니다.

## <a name="create-a-direct-link-to-a-query"></a>쿼리에 대한 직접 링크 만들기
고급 헌팅 쿼리 편집기에서 쿼리를 직접 여는 링크를 생성하려면 쿼리를 마무리하고 링크 **공유 를 선택합니다.**

## <a name="access-queries-in-the-github-repository"></a>GitHub 리포지토리의 쿼리에 액세스  
Microsoft 보안 연구원은 [GitHub의 지정된 공용 저장소](https://aka.ms/hunting-queries)에서 고급 헌팅 쿼리를 정기적으로 공유 합니다. 이 리포지토리는 참가 기회가 열려 있습니다. 참가하려면 [무료로 GitHub에 가입](https://github.com/)하세요.

>[!tip]
>또한 Microsoft 보안 연구원들은 최신 위협과 관련 된 활동과 지표를 찾는 데 사용할 수 있는 고급 검색 쿼리를 제공합니다. 이러한 쿼리는 Microsoft Defender 보안 센터의 [위협 분석](/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) 보고서의 일부로 제공됩니다.

>[!NOTE]
>이 문서의 일부 테이블은 끝점용 Microsoft Defender에서 사용할 수 없습니다. [더 많은 Microsoft 365 Defender](m365d-enable.md) 사용하여 위협을 헌팅할 수 있습니다. Endpoint용 Microsoft Defender에서 고급 헌팅 Microsoft 365 Defender [Microsoft Defender에서](advanced-hunting-migrate-from-mde.md)고급 헌팅 쿼리 마이그레이션의 단계를 수행하여 고급 헌팅 워크플로를 끝점으로 이동할 수 있습니다.

## <a name="related-topics"></a>관련 항목
- [지능형 헌팅 개요](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [쿼리 결과로 작업](advanced-hunting-query-results.md)
- [장치, 전자 메일, 앱 및 ID를 검색합니다.](advanced-hunting-query-emails-devices.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
- [쿼리 모범 사례 적용](advanced-hunting-best-practices.md)