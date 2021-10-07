---
title: 전자 메일 스레딩 Advanced eDiscovery
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
description: 전자 메일 Advanced eDiscovery 수행하면 전자 메일 스레딩이 전자 메일 대화를 구문 분석하고 각 메시지를 서로 다른 범주로 구분합니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 788858d6acaccbe07f3190b5adaaa05fe95c33a5
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60159793"
---
# <a name="email-threading-in-advanced-ediscovery"></a>전자 메일 스레딩 Advanced eDiscovery

한 동안 진행된 전자 메일 대화를 고려합니다. 대부분의 경우 전자 메일 스레드의 마지막 메시지에는 이전의 모든 메시지의 내용이 포함됩니다. 따라서 마지막 메시지를 검토하면 스레드에서 실행된 대화의 전체 컨텍스트가 제공될 수 있습니다. 전자 메일 스레딩은 검토자가 컨텍스트를 잃지 않고 수집된 일부 문서를 검토할 수 있도록 이러한 메시지를 식별합니다.

## <a name="what-does-email-threading-do"></a>전자 메일 스레딩은 어떻게 하나요?

전자 메일 스레딩은 각 전자 메일 스레드를 구문 분석하고 개별 메시지로 해지합니다. 각 전자 메일 스레드는 개별 메시지의 체인입니다. Advanced eDiscovery 집합의 모든 전자 메일 messaes를 분석하여 전자 메일 메시지에 고유한 콘텐츠가 있는지 또는 체인(상위 메시지)이 전자 메일 스레드의 최종 메시지에 전체적으로 포함되어 있는지 여부를 확인할 수 있습니다. 전자 메일 메시지는 네 가지 포함 값으로 나뉘어 있습니다.

- **포함:** *포괄* 전자 메일은 전자 메일 스레드의 최종 전자 메일 메시지로, 해당 전자 메일 스레드의 이전 콘텐츠를 모두 포함 합니다.

- **포괄** 마이너스: 전자 메일 스레드  내에서 특정 메시지와 연결된 첨부 파일이 하나 이상 있는 경우 전자 메일 메시지는 포괄 제외로 지정됩니다. 검토자는 Inclusive minus 값을 사용하여 스레드 내의 특정 전자 메일 메시지에 첨부 파일이 연결되어 있는지 확인할 수 있습니다. 

- **포괄** 복사본: 전자 메일 메시지는  포괄 또는 포괄 제외 메시지의 정확한 복사본인 경우 포괄 복사본으로 간주됩니다. 

- **없음:** *None* 값은 메시지 콘텐츠가 포괄 또는 포괄 이수로 표시된 다른 전자 메일 메시지 하나 이상에 전적으로 포함되어 있습니다.

## <a name="how-is-it-different-from-conversations-in-outlook"></a>이 대화와 다른 Outlook?

이 소리는 한 눈에 보기에서 대화 그룹화와 Outlook. 그러나 몇 가지 중요한 차이점이 있습니다. 두 개의 대화로 포크된 전자 메일 대화를 고려합니다. 예를 들어, 대화의 마지막 두 전자 메일에 고유한 콘텐츠가 있도록 누군가가 대화의 최신 전자 메일이 아닌 전자 메일에 응답했습니다.

Outlook 전자 메일을 단일 대화로 그룹화합니다. 마지막 전자 메일만 읽으면 고유한 콘텐츠가 포함된 두 번째 전자 메일의 컨텍스트가 누락됩니다. 전자 메일 스레딩은 각 전자 메일을 개별 구성 요소로 구문 분석하고 비교하기 때문에 전자 메일 스레딩은 마지막 두 전자 메일을 모두 포함으로 표시하여 포괄으로 표시된 모든 전자 메일을 읽는 한 컨텍스트를 누락하지 않습니다.
