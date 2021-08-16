---
title: Canvas에서 Microsoft Teams 클래스 사용
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
description: Canvas Microsoft Teams 클래스 통합
ms.openlocfilehash: 8091d84e1d0f26c820979450001a1e0c9ad1cdec775ac9e34317f69c24bd2df6
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "53898710"
---
# <a name="use-microsoft-teams-classes-with-canvas"></a>Canvas에서 Microsoft Teams 클래스 사용

Microsoft Teams 클래스는 교사와 학생이 LMS(Learning Management System) 및 LMS(Learning 관리 시스템) 사이를 쉽게 탐색하는 데 도움이 되는 LTI(Learning 도구 상호 운영성) 앱입니다Teams. 사용자는 LMS 내에서 직접 과정과 연결된 수업 팀에 액세스할 수 있습니다.

## <a name="prerequisites-before-deployment"></a>배포 전의 선행 구성

> [!NOTE]
> 현재 클래스 Teams LTI는 Canvas 사용자와 제한된 범위의 AAD(Microsoft Azure Active Directory) 동기화만 지원됩니다. 
> - 테넌트는 Canvas 필드(전자 메일, 사용자 ID 또는 SIS ID)와 Microsoft AAD의 UPN 간에 정확히 일치해야 합니다. 동기화 기능에 대한 유연성을 확장하기 위해 작업 중이지만, 그 동안 Canvas의 사용자가 AAD의 UPN과 일치하지 않는 사용자는 Canvas와 동기화된 Teams 클래스에 추가되지 않습니다. 
> - Canvas와 Microsoft 간에 사용자를 매핑하는 데는 단일 Microsoft 테넌트만 사용할 수 있습니다.
> - 그룹이 중복되는 것을 방지하기 위해 Class Teams LTI를 사용하기 전에 SDS를 해제해야 합니다.

## <a name="microsoft-office-365-admin"></a>Microsoft Office 365 관리자

Instructure Canvas 내에서 Microsoft Teams 통합을 관리하기 전에 Canvas 관리자 설정을 완료하기 전에 캔버스의 **Microsoft-Teams-Sync-for-Canvas** Azure 앱을 Microsoft Office 365 Microsoft Azure 테넌트에서 승인해야 합니다.

1. Canvas에 로그인합니다.

2. 전역 **탐색에서** 관리자 링크를 선택한 다음 계정을 선택합니다.

3. 관리자 탐색에서 설정 **링크를** 선택한 다음 **통합 탭을** 선택합니다.

4. 토글을 Microsoft Teams 동기화를 사용하도록 설정

   ![teams-sync](media/teams-sync.png)

5. Microsoft 테넌트 이름 및 로그인 특성을 입력합니다.

   Login 특성은 Canvas 사용자를 사용자와 연결하기 위해 Azure Active Directory 사용됩니다.

6. 한 **번 설정** 업데이트를 선택합니다.

7. Canvas의 **Microsoft-Teams-Sync-for-Canvas** Azure 앱에 대한 액세스를 승인하려면 테넌트 액세스 권한 부여 **링크를** 선택합니다. Microsoft Identity Platform 관리자 동의 끝점으로 리디렉션됩니다.

   ![사용 권한](media/permissions.png)

8. **수락** 을 선택합니다.

## <a name="canvas-admin"></a>Canvas Admin

LTI Microsoft Teams 1.3 통합을 설치합니다.

Canvas 관리자는 사용자 환경 내에 Microsoft Teams 클래스 LTI 앱을 추가해야 합니다. 기본 계정의 개발자 키 목록에 액세스하고, 상속된 키로 전환하고, LTI 도구를 Teams 활성화합니다. 앱에 대한 LTI 클라이언트 ID를 메모합니다.

 - Microsoft Teams 클래스 - 170000000000570

1. 관리자 **설정 앱에**  >  **액세스합니다.**

2. **+ 앱을 선택하여** LTI Teams 추가합니다.

   ![external-apps](media/external-apps.png)

3. 구성 **유형으로 클라이언트 ID를** 선택합니다.

   ![앱 추가](media/add-app.png)

4. 제공된 클라이언트 ID를 입력한 다음 제출을 **선택합니다.**

   확인을 위해 클라이언트 Microsoft Teams 클래스 LTI 앱 이름을 알 수 있습니다.

5. **설치** 를 선택합니다.

   LTI Microsoft Teams 클래스가 외부 앱 목록에 추가됩니다.
   
## <a name="enabling-the-lti-app-for-canvas-courses"></a>Canvas에 대한 LTI 앱 사용 과정

과정 내에서 LTI 앱을 사용하려면 Canvas 과정의 강사는 통합 동기화를 사용하도록 설정해야 합니다. 각 강사는 해당 팀을 만들 수 있어야 합니다. 팀을 만들기 위한 전역 메커니즘은 있습니다. 이는 원치 않는 팀이 만들어지지 않도록 예방 조치로 디자인되었습니다.

각 과정에 대해 [](https://support.microsoft.com/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas) LTI 앱을 사용하도록 설정하고 통합 설정을 완료하려면 강사 설명서를 참조하세요.
