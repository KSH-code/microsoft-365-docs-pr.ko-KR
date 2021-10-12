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
ms.localizationpriority: medium
ROBOTS: NOINDEX, NOFOLLOW
description: Canvas Microsoft Teams 클래스 통합
ms.openlocfilehash: 77f17e8d64fe2bf565eff6c66aa00e9b566cf796
ms.sourcegitcommit: df1ad7118c4a95a310a4f17124322a6ae6ace26f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/11/2021
ms.locfileid: "60268733"
---
# <a name="use-microsoft-teams-classes-with-canvas"></a>Canvas에서 Microsoft Teams 클래스 사용

Microsoft Teams 클래스는 교사와 학생이 LMS(Learning Management System) 및 LMS(Learning 관리 시스템) 사이를 쉽게 탐색하는 데 도움이 되는 LTI(Learning 도구 상호 운영성) 앱입니다Teams. 사용자는 LMS 내에서 직접 과정과 연결된 수업 팀에 액세스할 수 있습니다.

## <a name="prerequisites-before-deployment"></a>배포 전의 선행 구성

> [!NOTE]
> 현재 Teams 클래스 LTI는 Canvas 사용자와 제한된 범위의 Microsoft Azure Active Directory(AAD)를 동기화하는 것만 지원됩니다. 
> - 테넌트에 Microsoft Education 라이선스(A1 이상)가 있어야 합니다.
> - Canvas와 Microsoft 간에 사용자를 매핑하는 데는 단일 Microsoft 테넌트만 사용할 수 있습니다.
> - 테넌트는 Canvas 필드(전자 메일, 고유 사용자 ID, SIS ID 또는 통합 ID)와 AAD(UPN(사용자 계정 이름), 기본 전자 메일 주소(메일) 또는 전자 메일 별칭(mailNickname) 필드 간에 정확히 일치해야 합니다.
> - SDS를 사용하여 클래스 및 그룹을 만드는 경우 SDS에서 팀 만들기 옵션을 사용하지 [](/schooldatasync/group-cleanup) 않도록 설정하고 그룹 정리를 수행하여 수업이 중복된 것을 방지하는 것이 좋습니다. SDS를 사용하여 조직 및 사용자 데이터를 동기화할 수 있습니다.


## <a name="enable-the-microsoft-teams-app-in-canvas"></a>Canvas에서 Microsoft Teams 앱 사용
통합을 시작하려면 개발자 키를 사용하도록 설정하고, Microsoft Teams 동기화를 사용하도록 설정하고, Microsoft-Teams-Sync-for-Canvas 앱을 인가하여 Canvas에서 앱을 사용하도록 설정해야 합니다. 앱 승인은 앱을 승인할 수 있는 Microsoft 테넌트 관리자만 수행할 수 있습니다.

**동기화를 Microsoft Teams 앱에 대한 액세스를 승인하려면**

1. 캔버스에 관리자로 로그인합니다.

2. 전역 **탐색에서** 관리자 링크를 선택한 다음 계정을 선택합니다.
3. 관리자 탐색에서 개발자 키 링크를 **선택한** 다음 상속된 **탭을** 선택합니다.
4. 각 해당 앱에 대해 **ON** 상태를 선택하여 배포할 LTI 앱을 사용하도록 설정할 수 있습니다.

5. 관리자 탐색에서 설정 **링크를** 선택한 다음 **통합 탭을** 선택합니다.

6. 토글을 Microsoft Teams 동기화를 사용하도록 설정 이 동기화를 통해 강의 등록에 따라 Teams 클래스를 만들 수 있습니다.
   
   ![Canvas Teams 동기화 업데이트된 png입니다.](https://user-images.githubusercontent.com/87142492/128225881-abdfc52d-dc9e-48ad-aec5-f6617c6436f3.png)

7. 적절한 정보로 다음 필드를 작성합니다. 이러한 필드는 Canvas의 사용자와 캔버스의 사용자 일치에 AAD. 
   * **테넌트 이름은** Microsoft 테넌트 이름입니다.
   * **Login 특성은** 매핑에 사용되는 다음 Canvas 사용자 특성 중 하나입니다.
      * **전자** 메일은 Canvas 사용자의 기본 전자 메일 주소입니다. 사용자가 Canvas에서 기본 전자 메일 주소를 변경하는 경우 과정의 등록이 앱과 동기화되지 Teams.
      * **고유 사용자 ID는** 사용자의 Canvas 로그인 ID입니다.
      * **SIS 사용자 ID는** SIS(학생 정보 시스템)에서 채워지는 ID 값으로, 사용자의 프로필 페이지에서 볼 수 있습니다.
      * **통합 ID는** SIS 가져오기를 통해서만 채워지며 사용자의 프로필 페이지에서 볼 수 있습니다. 일반적으로 이 고유 식별자는 기관에서 제공하며 계정 트러스트 또는 컨소시엄 상황에서 여러 계정에서 사용자를 식별하는 데 사용됩니다.

   * **접미사** 필드는 선택 사항이며 Canvas 특성과 Microsoft AAD 정확히 매핑되지 않는 경우 도메인을 지정할 수 있습니다. 예를 들어 Canvas 전자 메일이 'name@example.edu'인 경우 Microsoft AAD UPN이 '이름'인 경우 접미사 필드에 '@example.edu'를 입력하여 사용자를 일치할 수 있습니다. 도메인은 이 필드에 앞에 @와 함께 입력해야 합니다.
   * Active Directory Lookup Attribute는 Canvas 특성이 AAD 필드입니다. UPN, 기본 전자 메일 주소 또는 전자 메일 별칭 사이에서 선택합니다.

8. 업데이트 **설정.**

9. Canvas의 **Microsoft-Teams-Sync-for-Canvas** Azure 앱에 대한 액세스를 승인하려면 테넌트 액세스 권한 부여 **링크를** 선택합니다. Microsoft Identity Platform 관리자 동의 끝점으로 리디렉션됩니다.

   ![사용 권한.](media/permissions.png)
> [!NOTE] 
> 이 단계는 앱을 승인할 수 있는 Microsoft 테넌트 관리자가 수행해야 합니다.

10. **수락** 을 선택합니다.

## <a name="integrate-teams-classes-lti-in-canvas"></a>Canvas에서 Teams 클래스 LTI 통합

동기화를 사용하도록 설정하고 Azure 앱을 활성화한 후 Canvas 관리자는 이제 Canvas 사용자 인터페이스의 탐색에 표시될 Teams 클래스 LTI 앱을 Canvas 환경에 추가할 수 있습니다.

**Canvas 환경에 Teams 클래스 LTI 앱을 추가합니다.**

1. 관리 **설정의 앱** **탭에서** **+** 앱을 선택하여 LTI 앱을 Teams 추가합니다.

   ![external-apps.](media/external-apps.png)

3. 구성 **유형 의** 경우 클라이언트 **ID 를 선택합니다.**

   ![앱을 추가합니다.](media/add-app.png)

4. 클라이언트 **ID의** 경우 170000000000570 클래스 **LTI에** Microsoft Teams 를 입력한 다음 제출을 **선택합니다.**

5. 확인 메시지가 나타나면 앱 이름(Microsoft Teams 클래스)을 확인한 다음 설치를 **선택합니다.**

   이제 Microsoft Teams 클래스 LTI 앱이 외부 앱 목록에 추가됩니다.
   
## <a name="enabling-the-lti-app-for-canvas-courses"></a>Canvas에 대한 LTI 앱 사용 과정

과정 내에서 LTI 앱을 사용하려면 Canvas 과정의 강사는 통합 동기화를 사용하도록 설정해야 합니다. 각 강사는 해당 팀을 만들 수 있어야 합니다. 팀을 만들기 위한 전역 메커니즘은 있습니다. 이는 원치 않는 팀이 만들어지지 않도록 예방 조치로 디자인되었습니다.

각 과정에 대해 [](https://support.microsoft.com/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas) LTI 앱을 사용하도록 설정하고 통합 설정을 완료하려면 강사 설명서를 참조하세요.
