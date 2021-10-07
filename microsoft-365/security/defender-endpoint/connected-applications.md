---
title: 끝점용 Microsoft Defender의 연결된 응용 프로그램
ms.reviewer: ''
description: 표준 OAuth 2.0 프로토콜을 사용하여 Microsoft Defender for Endpoint API와 함께 사용할 토큰을 인증하고 제공하는 연결된 파트너 응용 프로그램을 볼 수 있습니다.
keywords: 파트너, 응용 프로그램, 타사, 연결, sentinelone, lookout, bitdefender, corrata, morphisec, paloalto, ziften, 더 나은 모바일
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: d9ac6593df3d06b9a8bd3ff91d5f6b7395659297
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60208544"
---
# <a name="connected-applications-in-microsoft-defender-for-endpoint"></a>끝점용 Microsoft Defender의 연결된 응용 프로그램

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

연결된 응용 프로그램은 API를 사용하여 끝점용 Defender 플랫폼과 통합됩니다.

응용 프로그램은 표준 OAuth 2.0 프로토콜을 사용하여 끝점 API용 Microsoft Defender에서 사용할 토큰을 인증하고 제공합니다. 또한 Azure AD(Azure Active Directory) 응용 프로그램을 통해 테넌트 관리자는 해당 앱을 사용하여 액세스할 수 있는 API에 대한 명시적 컨트롤을 설정할 수 있습니다.

연결된 응용 프로그램에서 [](/microsoft-365/security/defender-endpoint/apis-intro) API를 사용하려면 다음 단계를 따라야 합니다.

왼쪽 탐색 메뉴에서  파트너 & **API(끝점** 아래) > **선택합니다.**

## <a name="view-connected-application-details"></a>연결된 응용 프로그램 세부 정보 보기

연결된 응용 프로그램 페이지에서는 조직의 끝점용 Microsoft Defender에 연결된 Azure AD 응용 프로그램에 대한 정보를 제공합니다. 마지막으로 확인한 응용 프로그램, 지난 24시간 동안의 요청 수 및 지난 30일 동안의 추세 요청과 같은 연결된 응용 프로그램의 사용을 검토할 수 있습니다.

![연결된 앱의 이미지입니다.](images/connected-apps.png)
 
## <a name="edit-reconfigure-or-delete-a-connected-application"></a>연결된 응용 프로그램 편집, 다시 구성 또는 삭제

응용 **프로그램 설정 열기 링크를** 클릭하면 Azure Portal에서 해당 Azure AD 응용 프로그램 관리 페이지가 열립니다. Azure Portal에서 연결된 응용 프로그램을 관리하거나, 다시 구성하거나, 삭제할 수 있습니다.
