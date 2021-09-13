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
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 전자 메일 Advanced eDiscovery 수행하면 전자 메일 스레딩이 전자 메일 대화를 구문 분석하고 각 메시지를 서로 다른 범주로 구분합니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b087bfc84175f80daaf1c0d2f1394584a70757ac
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59218945"
---
# <a name="email-threading-in-advanced-ediscovery"></a>전자 메일 스레딩 Advanced eDiscovery

한 동안 진행된 전자 메일 대화를 고려합니다. 대부분의 경우 스레드의 마지막 전자 메일에는 이전의 모든 전자 메일의 내용이 포함됩니다. 마지막 전자 메일을 검토하면 스레드에서 발생된 대화의 전체 컨텍스트가 제공될 것입니다. 전자 메일 스레딩은 검토자가 컨텍스트를 잃지 않고 수집된 문서의 일부를 검토할 수 있도록 이러한 전자 메일을 식별합니다.

## <a name="what-does-email-threading-do"></a>전자 메일 스레딩은 어떻게 하나요?

전자 메일 스레딩은 각 전자 메일을 구문 분석하고 개별 메시지로 해지합니다. 각 전자 메일은 개별 메시지의 체인입니다. 그런 다음 검토 집합의 모든 전자 메일을 분석하여 전자 메일에 고유한 콘텐츠가 있는지 또는 체인이 다른 전자 메일에 전체적으로 포함되어 있는지 여부를 파악합니다. 최종 전자 메일은 다음과 같은 네 가지 범주로 구분됩니다.

- **포괄**: 전자 메일의 마지막 메시지에 고유한 콘텐츠가 있으며 전자 메일에는 다른 전자 메일에 포함된 모든 첨부 파일이 있으며 이 전자 메일에 콘텐츠가 전체적으로 포함되어 있습니다.

- **일부 제외 포괄**: 전자 메일의 마지막 메시지에 고유한 콘텐츠가 있지만 해당 콘텐츠가 이 전자 메일에 전부 포함되어 있는 다른 전자 메일에 포함된 일부 첨부 파일은 전자 메일에 포함되어 있지 않습니다.

- **사본 포괄**: 포괄/일부 제외 포괄 전자 메일의 정확한 복사본

- **미포괄**: 이 전자 메일의 콘텐츠는 하나 이상의 포괄/일부 제외 포괄로 표시된 전자 메일에 모두 포함되어 있습니다.

## <a name="how-is-it-different-from-conversations-in-outlook"></a>이 대화와 다른 Outlook?

이 소리는 한 눈에 보기에서 대화 그룹화와 Outlook. 그러나 몇 가지 중요한 차이점이 있습니다. 두 개의 대화로 포크된 전자 메일 대화를 고려합니다. 예를 들어, 대화의 마지막 두 전자 메일에 고유한 콘텐츠가 있도록 누군가가 대화의 최신 전자 메일이 아닌 전자 메일에 응답했습니다.

Outlook 전자 메일을 단일 대화로 그룹화합니다. 마지막 전자 메일만 읽으면 고유한 콘텐츠가 포함된 두 번째 전자 메일의 컨텍스트가 누락됩니다. 전자 메일 스레딩은 각 전자 메일을 개별 구성 요소로 구문 분석하고 비교하기 때문에 전자 메일 스레딩은 마지막 두 전자 메일을 모두 포함으로 표시하여 포괄으로 표시된 모든 전자 메일을 읽는 한 컨텍스트를 누락하지 않습니다.
