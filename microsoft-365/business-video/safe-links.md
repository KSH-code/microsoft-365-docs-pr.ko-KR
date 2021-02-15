---
title: 안전한 링크 관리
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 안전한 링크를 관리하여 악의적인 사이트로부터 비즈니스를 보호하는 방법을 배워야 합니다.
ms.openlocfilehash: 1f5b3f61871e8d231029156631031dbb0ef4f2f5
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928021"
---
# <a name="manage-safe-links"></a>안전한 링크 관리

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWvdwy?autoplay=false]

이전의 Microsoft 365 ATP 또는 Advanced Threat Protection이라고 하는 Office 365용 Microsoft Defender는 사용자가 Office 앱에서 링크를 클릭할 때 악의적인 사이트로부터 비즈니스를 보호하는 데 도움이 됩니다.

## <a name="try-it"></a>사용해 보세요!

1. 관리 [센터로 이동하여 설치를](https://admin.microsoft.com) **선택합니다.**
1. 아래로 **스크롤하여 고급 위협으로부터 보호를 강화합니다.** **보기,** **관리** 및 **ATP 안전한 링크를 선택합니다.**
1. 전체 **조직에 적용되는** 정책에서 기본  정책을 선택한 다음 편집 **아이콘을** 선택합니다.
1. 차단할 URL을 입력합니다.
1. Select **Use safe links in Office apps, Office for iOS and Android**; 사용자가 **안전한 링크를 클릭하는 경우 추적 안 을 선택합니다.** 및 **사용자가 원래 URL에 대한** 안전한 링크를 클릭할 수 없습니다. 기본 정책을 설정한 경우 이러한 설정이 이미 선택되어 있을 수 있습니다. **저장** 을 선택합니다.
1. 특정 **받는 사람에게 적용되는** 정책에서 권장 안전한 링크 규칙을 선택한 다음 편집 **아이콘을** 선택합니다.
1. 설정을 **선택하고** 아래로 스크롤하고 확인하지 않을 URL을 입력한 다음 추가 **아이콘을** 선택합니다.
1. 적용 **대상을** 선택한 다음 도메인 이름을 선택합니다. 규칙을 적용할 추가 도메인을 선택합니다. Select **add**, **OK,** and then **Save.**

이제 ATP 안전한 링크가 구성됩니다. 변경 내용을 적용하는 데 최대 30분을 허용합니다.

사용자가 링크가 있는 전자 메일을 받으면 링크가 검색됩니다. 링크가 안전한 것으로 확인된 경우 클릭할 수 있습니다. 그러나 링크가 차단 목록에 있는 경우 차단된 메시지가 표시됩니다.