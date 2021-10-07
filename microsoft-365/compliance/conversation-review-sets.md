---
title: 2013에서 대화 Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Advanced eDiscovery 그룹에서 채팅 대화를 재구성, 검토 및 내보내기하기 위한 Advanced eDiscovery 재구성 기능에 대해 Microsoft Teams Yammer 대해 자세히 알아보습니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: c2638b2e89169560307cd32217532d4d5ce565e8
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60156525"
---
# <a name="conversation-threading-in-advanced-ediscovery"></a>Advanced eDiscovery

인스턴트 메시징은 질문을 하고, 아이디어를 공유하거나, 많은 대상을 통해 빠르게 의사소통할 수 있는 편리한 방법입니다. Microsoft Teams 및 Yammer 그룹과 같은 인스턴트 메시징 플랫폼이 엔터프라이즈 공동 작업에 핵심이 되기 때문에 조직은 eDiscovery 워크플로에서 이러한 새로운 형태의 통신 및 공동 작업을 사용하는 방법을 평가해야 합니다.

콘텐츠의 대화 재구성 기능은 Advanced eDiscovery 콘텐츠를 식별하고 고유한 대화 보기를 생성하는 데 도움이 하도록 디자인되어 있습니다. 이 기능을 사용하면 사용자와 같은 플랫폼에서 생성되는 전체 인스턴트 메시지 대화(스레드 대화라고도 하는)를 효율적이고 빠르게 검토할 수 Microsoft Teams.

대화 재구성에서는 기본 제공 기능을 사용하여 스레드된 대화를 재구성, 검토 및 내보낼 수 있습니다. 대화 Advanced eDiscovery 사용하여 다음을 할 수 있습니다.

- 대화 내의 모든 메시지에서 고유한 메시지 수준 메타데이터를 보존합니다.

- 검색 결과와 관련한 메시지를 수집합니다.

- 스레드된 대화를 검토, 주석 및 다시 시정합니다.

- 개별 메시지 또는 스레드된 대화 내보내기

## <a name="terminology"></a>용어

다음은 대화 재구성 사용을 시작하는 데 도움이 되는 몇 가지 정의입니다.

- **메시지:** 대화의 가장 작은 단위를 표현합니다. 메시지의 크기, 구조 및 메타데이터는 다를 수 있습니다.

- **대화:** 하나 이상의 메시지 그룹화 여러 응용 프로그램에서 대화는 서로 다른 방식으로 표현될 수 있습니다. 일부 응용 프로그램에서는 기존 메시지에 회신하여 수행한 명시적 작업이 있습니다. 대화는 이 사용자 작업의 결과로 명시적으로 구성됩니다. 예를 들어 여기에 채널 대화의 스크린샷이 Microsoft Teams.

   ![Microsoft Teams 채널 대화.](../media/threadedchat.png)

   다른 앱(예: Teams의 그룹 채팅 메시지)에는 공식적인 회신 체인이 없는 대신 메시지가 단일 스레드 내에서 "평평한 메시지 강"으로 표시됩니다. 이러한 유형의 앱에서는 특정 시간 내에 발생하는 메시지 그룹에서 대화가 유추됩니다. 이 "소프트 그룹화" 메시지는 회신 체인이 아니라 특정 관심 주제에 대한 "전방" 대화를 나타내고 있습니다.

## <a name="step-1-create-a-draft-collection"></a>1단계: 초안 컬렉션 만들기

관련 관리인 및 콘텐츠 위치를 확인한 후 검색을 만들어 관련성이 있는 콘텐츠를 찾을 수 있습니다. 새 **컬렉션을** 클릭하고 마법사를 Advanced eDiscovery 컬렉션 탭에서 컬렉션을  만들 수 있습니다. 컬렉션을 만들고, 검색 쿼리를 작성하고, 검색 결과를 미리 보는 방법에 대한 자세한 내용은 초안 컬렉션 [만들기를 참조하세요.](create-draft-collection.md)

## <a name="step-2-commit-a-draft-collection-to-a-review-set"></a>2단계: 검토 집합에 초안 컬렉션 커밋

컬렉션에서 검색 쿼리를 검토하고 마무리한 후 검색 결과를 검토 집합에 추가할 수 있습니다. 검색 결과를 검토 집합에 추가하면 검토 및 분석 프로세스가 용이하도록 원본 Azure Storage 영역으로 복사됩니다. 검토 집합에 검색 결과를 추가하는 데 대한 자세한 내용은 검토 집합에 초안 컬렉션 [커밋을 참조하세요.](commit-draft-collection.md)

대화의 항목을 검토 집합에 추가할 때 스레드된 대화 옵션을 사용하여 컬렉션의 검색 조건과 일치하는 항목이 포함된 대화에서 상황에 맞는 메시지를 수집할 수 있습니다. 스레드 대화 옵션을 선택한 후 다음과 같은 상황이 발생 할 수 있습니다.

  ![Conversation Retrieval.](../media/messagesandconversations.png)

1. 키워드 및 날짜 범위 쿼리를 사용하여 메시지 3에서 검색이 *적중을 반환했습니다.* 이 메시지는 CRC1에 의해 설명된 대규모 *대화의 일부입니다.*

2. 검토 집합에 데이터를 추가하고 대화 검색 옵션을 사용하도록 설정하면 Advanced eDiscovery *돌아가서 CRC1에서* 다른 항목을 수집합니다.

3. 검토 집합에 항목이 추가된 후 *CRC1의* 모든 개별 메시지를 검토할 수 있습니다.

스레드된 대화 옵션을 사용하도록 설정하려면 검토 집합에 초안 컬렉션 [커밋을 참조하세요.](commit-draft-collection.md#commit-a-draft-collection-to-a-review-set)

## <a name="step-3-review-and-export-threaded-conversations"></a>3단계: 스레드된 대화 검토 및 내보내기

콘텐츠가 처리되고 검토 집합에 추가된 후 검토 집합의 데이터 검토를 시작할 수 있습니다. 개별 메시지는 함께 스레드로 처리된 후 대화로 표시됩니다. 이를 통해 상황에 맞는 대화를 검토하고 내보낼 수 있습니다.

  ![대화 검토 집합.](../media/ConversationRSOptions.PNG)

다음 섹션에서는 대화 검토 및 내보내기에 대해 설명합니다.

### <a name="reviewing-conversations"></a>대화 검토

검토 집합에서 다음 옵션을 사용하여 검토 프로세스를 용이하게 할 수 있습니다.

- **대화로 그룹화:** 동일한 대화 내의 메시지를 그룹화하여 사용자가 검토 프로세스를 간소화하고 더 쉽게 진행할 수 있도록 합니다.

- **요약 보기:** 스레드된 대화를 나타냅니다. 이 보기에서 전체 대화를 볼 수 있으며 각 개별 메시지의 메타데이터에 액세스할 수도 있습니다.

   - 개별 메시지에 대한 메타데이터 보기

   - 개별 메시지 다운로드

- **텍스트 보기:** 전체 대화에 대해 추출된 텍스트를 입력합니다.

- **보기에 주석을 추가합니다.** 스레드된 대화 보기를 마크업할 수 있습니다. 대화의 모든 메시지는 동일한 주석이 있는 문서를 공유합니다.

- **태그 지정:** 검토 집합에서 대화를 볼 때 코딩 패널에서 태그  지정 패널을 클릭하여 태그를 보고 적용할 수 있습니다.

- **대화 변환 다시 시작:** 메시지를 대화 검토 집합에 추가하면 변환 작업이 자동으로 실행되어 스레드된 요약을 만들고 보기에 주석을 추가합니다. 대화 재구성 작업이 실패하면 작업 및 검토 집합에 대화 > 만들기를 클릭하여 이 작업을 **다시 실행할** 수 있습니다.

### <a name="exporting-conversations"></a>대화 내보내기

검토 집합에서 대화를 내보낼 때 선택할 수 있는 옵션은 검토 집합에서 문서 [내보내기 를 참조하세요.](export-documents-from-review-set.md#export-options)

특히 전체 채팅 대화를 단일 PDF 파일로 내보내거나 대화의 각 채팅 메시지를 개별 파일로 내보낼 수 있습니다.

## <a name="more-information"></a>추가 정보

사례 데이터를 검토하는 방법에 대한 자세한 내용은 Advanced eDiscovery 문서를 참조합니다.

- [검토 집합의 콘텐츠 쿼리 및 필터링](review-set-search.md)
- [검토 집합에서 문서 태그 지정](tagging-documents.md)
- [사례 데이터 보기](view-documents-in-review-set.md)
- [대/소문자 데이터 분석](analyzing-data-in-review-set.md)
- [사례 데이터 내보내기](exporting-data-ediscover20.md)
