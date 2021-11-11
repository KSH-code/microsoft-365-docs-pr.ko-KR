---
title: 사용자 조사에서 Microsoft 365 Defender
description: 사이트 포털에서 인시던트가 Microsoft 365 Defender 조사합니다.
keywords: 보안, 맬웨어, Microsoft 365, M365, 보안 센터, 모니터링, 보고서, ID, 데이터, 장치, 앱, 인시던트, 분석, 응답
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: dansimp
ms.date: ''
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: 165f1ccb1e0a059d61802e9a8e026b9dbef3efc2
ms.sourcegitcommit: 8410a49995a084e4cc9b3f7286c8d506b7a85d79
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/11/2021
ms.locfileid: "60914383"
---
# <a name="investigate-users-in-microsoft-365-defender"></a>사용자 조사에서 Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**적용 대상:**

- Microsoft 365 Defender

인시던트 조사의 일부에는 사용자 계정이 포함됩니다. **인시던트** 및 인시던트의 인시던트에 대한 사용자 탭에서 & _ 사용자  \> **_를_*\>* 선택합니다.**

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="인시던트에 대한 사용자 페이지의 예입니다." lightbox="../../media/investigate-incidents/incident-users.png":::

인시던트에 대한 사용자 계정을 빠르게 요약하려면 사용자 계정 이름 옆의 확인 표시를 선택합니다. 다음은 예입니다.

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="인시던트에 대한 사용자 계정 요약 창의 예입니다." lightbox="../../media/investigate-users/incidents-ss-user-pane.png":::

> [!NOTE]
> 사용자 페이지에 Azure Active Directory(Azure AD) 조직 및 그룹이 표시되어 사용자와 연결된 그룹 및 사용 권한을 이해하는 데 도움이 됩니다.

이 플라이아웃 페이지에서 현재 인시던트, 활성 경고, 위험 수준, 사용자 노출, 계정, 장치 등을 비롯한 사용자 위협 정보를 검토할 수 있습니다.

또한 노출된 사용자를 해결하거나 Microsoft 365 Defender 확인하거나 다시 로그인하도록 요구하기 위해 Microsoft 365 Defender 포털에서 직접 조치를 취할 수 있습니다.

여기에서 사용자 페이지로  이동을 선택하여 사용자 계정의 세부 정보를 볼 수 있습니다. 다음은 예입니다.

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="인시던트에 대한 사용자 계정 페이지의 예입니다." lightbox="../../media/investigate-users/incidents-ss-user-details.png":::

사용자 페이지의 목록에서 사용자 계정의 이름을 선택하여 이 페이지를 볼 **수** 있습니다.

그룹 에서 번호를 선택하여 사용자의 그룹 구성원 자격을 볼 **수 있습니다.**

:::image type="content" source="../../media/investigate-users/user-group-membership.png" alt-text="사용자에 대한 그룹 구성원의 예입니다." lightbox="../../media/investigate-users/user-group-membership.png":::

관리자에서 아이콘을 **선택하면** 사용자가 조직 트리의 위치를 볼 수 있습니다.

Microsoft 365 Defender 포털 사용자 페이지는 Microsoft Defender for Endpoint, Id용 Microsoft Defender 및 Microsoft Cloud App Security 정보를 결합합니다(사용한 라이선스에 따라 다를 수 있습니다).

이 페이지에는 사용자 계정의 보안 위험과 관련한 정보가 표시됩니다. 여기에는 위험 및 최근 이벤트를 평가하는 데 도움이 되는 점수와 사용자의 전반적인 위험에 기여한 경고가 포함됩니다.

이 페이지에서는 다음 추가 작업을 수행할 수 있습니다.

- 사용자 계정을 손상된 것으로 표시
- 사용자에게 다시 로그인하도록 요구
- 사용자 계정 일시 중단
- Azure AD(Azure Active Directory 계정 설정) 참조
- 사용자 계정이 소유한 파일 보기
- 이 사용자와 공유된 파일을 볼 수 있습니다.

다음은 예입니다.

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="인시던트에 대한 사용자 계정에 대한 작업의 예입니다." lightbox="../../media/investigate-users/incidents-ss-user-details-actions.png":::

<!--
You can access this page from multiple areas in the Microsoft 365 Defender portal. You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset. You can also search for users.  

Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).

-->

## <a name="view-lateral-movement-paths"></a>측면 이동 경로 보기

**측면** 이동 경로 탭을 선택하면 네트워크에 침투하는 데 사용할 수 있는 이 사용자와의 측면 이동 경로를 시각적으로 표현하는 완전히 동적이고 클릭 가능한 지도를 볼 수 있습니다.

이 맵은 공격자가 중요한 계정을 손상하기 위해 이 사용자와 연결해야 하는 컴퓨터 또는 사용자 간의 홉 수 목록을 제공합니다. 또한 사용자가 중요한 계정을 사용하는 경우 직접 연결된 리소스 및 계정의 수를 볼 수 있습니다.

지난 2일 동안 엔터티에 대해 잠재적인 측면 이동 경로가 검색되지 않은 경우 그래프가 표시되지 않습니다. 다른 날짜 보기를 사용하여 이 엔터티에 대해 검색된 이전 측면 이동 경로 그래프를 볼 수 있는 다른 날짜를 선택합니다. 측면 이동 경로 보고서는 검색된 잠재적인 측면 이동 경로에 대한 정보를 항상 제공할 수 있으며 시간별 사용자 지정이 가능합니다.

:::image type="content" source="../../media/investigate-users/lateral-movement-path.png" alt-text="사용자에 대한 측면 이동 경로의 예입니다." lightbox="../../media/investigate-users/lateral-movement-path.png":::

자세한 내용은 측면 이동 [경로를 참조하세요.](/defender-for-identity/use-case-lateral-movement-path)

## <a name="next-steps"></a>다음 단계

In-process 인시던트에 필요한 경우 조사를 [계속합니다.](investigate-incidents.md)

## <a name="see-also"></a>참고 항목

- [인시던트 개요](incidents-overview.md)
- [인시던트 우선 순위 지정](incident-queue.md)
- [인시던트 관리](manage-incidents.md)
