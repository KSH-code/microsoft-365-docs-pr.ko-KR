---
title: 게스트 계정에 대 한 필수 구성 요소
description: 게스트 계정에 대 한 구성 지침 및이를 조정 하는 방법
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: d8953e9f451daa02671a1e1544f2dfe6649ab1b3
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073227"
---
# <a name="prerequisites-for-guest-accounts"></a>게스트 계정에 대 한 필수 구성 요소

Microsoft Managed Desktop에는 게스트 계정 액세스를 위한 Azure AD 조직의 다음 설정이 필요 합니다. **외부 id/외부 공동 작업** 아래의 [Azure portal](https://portal.azure.com) 에서 이러한 설정을 조정할 수 있습니다.

-   **게스트 inviter 역할의 관리자 및 사용자가** **' 예 '** 로 설정할 수 있습니다.
-   **공동 작업 제한** 의 경우 다음 옵션 중 하나를 선택 합니다.
    -   **모든 도메인에 대해 초대 보내기 허용 (가장 많이 포함)** 을 선택 하는 경우에는 다른 구성이 필요 하지 않습니다.
    -   **지정 된 도메인에 대 한 초대 거부** 를 선택 하는 경우 Microsoft.com가 대상 도메인에 나열 되어 있지 않은지 확인 합니다.
    -   **지정한 도메인에만 초대 허용 (가장 제한적)** 을 선택 하는 경우에는 Microsoft.com *이* 대상 도메인에 나열 되어 있는지 확인 합니다.

이러한 설정과 상호 작용 하는 제한을 설정 하는 경우 Azure Active Directory **최신 작업 공간 서비스 계정을** 제외 해야 합니다. 예를 들어 게스트 계정이 Intune 포털에 액세스 하지 못하게 하는 조건부 액세스 정책이 있는 경우이 정책에서 **최신 직장의 서비스 계정** 그룹을 제외 합니다.

