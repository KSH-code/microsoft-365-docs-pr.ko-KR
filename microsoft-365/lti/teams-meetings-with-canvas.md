---
title: Canvas에서 Microsoft Teams 모임 사용
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: sovaish
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: 캔버스 Microsoft Teams 통합
ms.openlocfilehash: 946abaec52cb1c5060d5490b409758cf230a4e5a
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256882"
---
# <a name="use-microsoft-teams-meetings-with-canvas"></a>Canvas에서 Microsoft Teams 모임 사용

> [!IMPORTANT]
> 일부 정보는 상용으로 출시되기 전에 실질적으로 수정될 수 있는 사전 릴리스된 제품과 관련이 있습니다. Microsoft는 여기에서 제공하는 정보와 관련하여 명시적이거나 묵시적인 어떠한 보증도 제공하지 않습니다.

Microsoft Teams 모임은 교육자 및 학생이 LMS(Learning Management System) 및 LMS(Learning 관리 시스템) 사이를 쉽게 탐색하는 데 도움이 되는 LTI(Learning 도구 상호 운영성) Teams. 사용자는 LMS 내에서 직접 과정과 연결된 수업 팀에 액세스할 수 있습니다.

## <a name="microsoft-office-365-admin"></a>Microsoft Office 365 관리자

Instructure Canvas 내에서 Microsoft Teams 통합을 관리하기 전에 Canvas 관리자 설정을 완료하기 전에 캔버스의 **Microsoft-Teams-Sync-for-Canvas** Azure 앱을 Microsoft Office 365 Microsoft Azure 테넌트에서 승인해야 합니다.

1. Canvas에 로그인합니다.

2. 전역 **탐색에서** 관리자 링크를 선택한 다음 계정을 선택합니다.

3. 관리자 탐색에서 설정 **링크를** 선택한 다음 **통합 탭을** 선택합니다.

4. Microsoft 테넌트 이름 및 로그인 특성을 입력합니다.

   Login 특성은 Canvas 사용자를 사용자와 연결하기 위해 Azure Active Directory 사용됩니다.

5. 한 **번 설정** 업데이트를 선택합니다.

6. Canvas의 **Microsoft-Teams-Sync-for-Canvas** Azure 앱에 대한 액세스를 승인하려면 테넌트 액세스 권한 부여 **링크를** 선택합니다. Microsoft Identity Platform 관리자 동의 끝점으로 리디렉션됩니다.

   ![사용 권한](media/permissions.png)

7. **수락을 선택합니다.**

8. 토글을 Microsoft Teams 동기화할 수 있도록 합니다.

   ![teams-sync](media/teams-sync.png)

## <a name="canvas-admin"></a>Canvas Admin

LTI Microsoft Teams 1.3 통합을 설치합니다.

Canvas 관리자는 사용자 환경 내에서 Microsoft Teams 모임 LTI 앱을 추가해야 합니다. 앱에 대한 LTI 클라이언트 ID를 메모합니다.

 - Microsoft Teams 모임 - 1700000000000703

1. 관리자 **설정 앱에**  >  **액세스합니다.**

2. **+ 앱을 선택하여** LTI Teams 추가합니다.

   ![external-apps](media/external-apps.png)

3. 구성 **유형으로 클라이언트 ID를** 선택합니다.

   ![앱 추가](media/add-app.png)

4. 제공된 클라이언트 ID를 입력한 다음 제출을 **선택합니다.**

   확인을 위해 Microsoft Teams 모임 LTI 앱 이름을 알 수 있습니다.

5. **설치** 를 선택합니다.

   모임 Microsoft Teams LTI 앱이 외부 앱 목록에 추가됩니다.
