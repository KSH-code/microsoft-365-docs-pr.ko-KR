---
title: Microsoft 365 보안 센터에서 사용자 조사
description: 보안 센터에서 Microsoft 365 조사
keywords: 보안, 맬웨어, Microsoft 365, M365, 보안 센터, 모니터링, 보고서, ID, 데이터, 장치, 앱, 인시던트, 분석, 응답
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
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
ms.openlocfilehash: c03e4d5bd94eb6105ffab91c6dad2b74d7159dde
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300064"
---
# <a name="investigate-users-in-microsoft-365-security-center"></a>Microsoft 365 보안 센터에서 사용자 조사

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**적용 대상:**

- Microsoft 365 Defender

인시던트 조사의 일부에는 사용자 계정이 포함됩니다. 사용자 탭에서 인시던트  및 인시던트 & 인시던트에 대한 사용자 >*>* **합니다.**  

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="인시던트에 대한 사용자 페이지의 예":::

인시던트에 대한 사용자 계정을 빠르게 요약하려면 사용자 계정 이름 옆의 확인 표시를 선택합니다. 다음은 예입니다.

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="보안 센터의 인시던트에 대한 사용자 계정 Microsoft 365 창의 예":::

> [!NOTE]
> 사용자 페이지에는 AZURE ACTIVE DIRECTORY(AD) 조직 및 그룹이 표시되어 사용자와 연결된 그룹 및 사용 권한을 이해할 수 있습니다.

이 플라이아웃 페이지에서 현재 인시던트, 활성 경고, 위험 수준, 사용자 노출, 계정, 장치 등을 비롯한 사용자 위협 정보를 검토할 수 있습니다.

또한 보안 센터에서 직접 Microsoft 365 조치를 취하여 손상된 사용자를 해결하고, 사용자가 손상된 것을 확인하거나 다시 로그인하도록 요구할 수 있습니다.

여기에서 사용자 페이지로  이동을 선택하여 사용자 계정의 세부 정보를 볼 수 있습니다. 다음은 예입니다.

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="보안 센터의 인시던트에 대한 사용자 계정 Microsoft 365 예":::

사용자 페이지의 목록에서 사용자 계정의 이름을 선택하여 이 페이지를 볼 **수** 있습니다.

Microsoft 365 보안 센터 사용자 페이지는 끝점용 Microsoft Defender, ID용 Microsoft Defender 및 Microsoft Cloud App Security 정보를 결합합니다(사용중인 라이선스에 따라 다를 수 있습니다). 

이 페이지에는 사용자 계정의 보안 위험과 관련한 정보가 표시됩니다. 여기에는 위험 및 최근 이벤트를 평가하는 데 도움이 되는 점수와 사용자의 전반적인 위험에 기여한 경고가 포함됩니다.

이 페이지에서는 다음 추가 작업을 수행할 수 있습니다. 

- 사용자 계정을 손상된 것으로 표시
- 사용자에게 다시 로그인하도록 요구
- 사용자 계정 일시 중단
- Azure AD(Azure Active Directory 계정 설정) 참조
- 사용자 계정이 소유한 파일 보기
- 이 사용자와 공유된 파일을 볼 수 있습니다. 

다음은 예입니다.

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="Microsoft 365 보안 센터에서 인시던트에 대한 사용자 계정에 대한 작업의 예":::


<!--
You can access this page from multiple areas in the Microsoft 365 security center. You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset. You can also search for users.  

Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).

--> 

## <a name="next-steps"></a>다음 단계

In-process 인시던트에 필요한 경우 조사를 [계속합니다.](investigate-incidents.md)

## <a name="see-also"></a>참고 항목

- [인시던트 개요](incidents-overview.md)
- [인시던트 우선 순위 지정](incident-queue.md)
- [인시던트 관리](manage-incidents.md)