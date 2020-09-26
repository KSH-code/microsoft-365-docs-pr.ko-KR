---
title: 테마-eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 고급 eDiscovery에서 테마를 사용 하 여 각 문서에서 기준 테마를 찾아서 검토 집합을 구성 합니다.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3dfc0dca0c6ed62e3ce8384efa2fd3ea407c3ce8
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285534"
---
# <a name="themes-in-advanced-ediscovery"></a>고급 eDiscovery의 테마

사용자가 문서를 작성 하는 방법은 무엇 인가요? 일반적으로 문서에서 전달 하려는 하나 이상의 아이디어를 시작 하 고 아이디어와 일치 하는 단어를 사용 하 여 작성 합니다. 가장 많이 알려진 개념은 해당 아이디어와 관련 된 단어의 빈도가 가장 많습니다. 사용자가 문서를 사용 하는 방법에 대해 알려 줍니다. 문서를 읽을 때 이해 해야 하는 중요 한 사항은 문서에서 전달을 시도 하는 내용, 해당 위치에 표시 되는 개념 및 아이디어 간의 관계입니다.

이를 통해 사용자가 문서 집합을 사용 하는 방법으로 확장할 수 있습니다. 이러한 사용자는 집합에 있는 아이디어와 이러한 아이디어에 대해 어떤 문서를 말하고 있는지 확인 하고자 합니다. 또한 관심 있는 특정 문서를 찾으면 비슷한 내용을 설명 하는 문서를 볼 수 있습니다.

고급 eDiscovery의 테마 기능은 검토 집합에 설명 되어 있는 *테마* 를 분석 하 고 검토 집합의 문서에 테마를 지정 하 여 문서에 대 한 이유를 모방 합니다. 고급 eDiscovery에서 테마는 한 단계 더 나아가 각 문서에서 *기준 테마* 를 식별 합니다. 주요 테마는 문서에서 가장 자주 표시 되는 항목입니다.

## <a name="how-does-themes-work"></a>테마는 어떻게 작동 하나요?

테마 기능은 검토 집합의 텍스트를 사용 하 여 문서를 분석 하 여 검토 집합의 모든 문서에 표시 되는 일반적인 테마를 구문 분석 합니다. Advanced eDiscovery는 해당 테마를 표시 되는 문서에 할당 합니다. 또한 테마를 대표 하는 문서에 사용 된 단어와 각 테마에 레이블을 붙입니다. 문서에는 다양 한 유형의 주제가 포함 될 수 있으므로 고급 eDiscovery에서는 문서에 여러 테마를 할당 하는 경우가 많습니다. 문서에서 가장 두드러지게 표시 되는 테마는 기준 테마로 지정 됩니다.
