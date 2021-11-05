---
title: Android의 끝점용 Microsoft Defender의 새로운
description: Android용 끝점용 Microsoft Defender의 이전 버전에 대한 주요 변경 내용에 대해 자세히 알아보습니다.
keywords: Microsoft, defender, Endpoint용 Microsoft Defender, mac, 설치, macos, whatsnew
ms.prod: m365-security
ms.mktglfcycl: security
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: reference
ms.technology: mde
ms.openlocfilehash: c29570668f6fcf542ef3336c8053b395331fcce2
ms.sourcegitcommit: 27bf284b3bfe334eb98847798734625bd2ffafb1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/05/2021
ms.locfileid: "60792547"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-android"></a>Android의 끝점용 Microsoft Defender의 새로운

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="upcoming-permission-changes-for-microsoft-defender-for-endpoint-running-android-11-or-later-nov-2021"></a>Android 11 이상을 실행하는 끝점용 Microsoft Defender의 예정된 사용 권한 변경 사항(2021년 11월)
릴리스 빌드: 1.0.3501.0301 릴리스 월: 2021년 11월

끝점용 Microsoft Defender는 [Google이 Android](https://developer.android.com/distribute/play-policies#APILevel30) API 30으로 업그레이드할 수 있도록 합니다. 이 변경은 Android [](https://developer.android.com/training/data-storage/manage-all-files#all-files-access-google-play) 11 이상을 실행하는 장치에 대한 새 저장소 권한을 묻는 메시지를 표시합니다. 사용자는 릴리스 빌드 1.0.3501.0301 이상으로 Defender 앱을 업데이트한 후 이 새 저장소 권한을 수락해야 합니다. 이렇게 하면 중단 없이 Defender의 '앱 보안' 기능이 작동할 수 있습니다. 자세한 내용은 다음 섹션의 세부 정보를 참조하세요.

**조직에 미치는 영향:**

Android 11 이상을 실행하는 장치에서 끝점용 Microsoft Defender를 사용하고 빌드 1.0.3501.0301 이상을 릴리스하기 위해 Defender를 업데이트한 경우 이러한 변경 내용이 영향을 미치게 됩니다. 이 설정은 관리자를 통해 구성할 수 Microsoft Endpoint Manager. 위에서 언급한 Google API 변경으로 인해 사용자는 조치를 취해야 합니다.

- **사용자 환경:** 사용자는 앱 보안에 대한 사용 권한이 누락되었음을 나타내는 알림을 받게 됩니다. 사용자가 이 권한을 거부하면 장치에서 '앱 보안' 기능이 꺼집니다. 사용자가 권한을 수락하거나 거부하지 않는 경우 승인될 때까지 디바이스 잠금을 해제하거나 앱을 열 때 메시지가 계속 표시됩니다.

>[!NOTE] 
> 조직에서 '변조 방지' 기능을 미리 보고 있으며 최신 버전으로 업데이트한 후 7일 이내에 사용자가 새 저장소 권한을 부여하지 않은 경우 사용자는 회사 리소스에 액세스할 수 없습니다.

**준비에 필요한 작업:**

1.0.3501.0301 이상 버전을 빌드할 수 있도록 Defender를 업데이트한 후 메시지가 표시될 때 사용자에게 새 사용 권한을 수락해야 하다는 사실을 사용자 및 헬프데스크에 알릴 수 있습니다. 사용 권한을 수락하려면 사용자는 다음을 해야 합니다.

1. Defender 앱 내 알림을 탭하거나 끝점용 Microsoft Defender 앱을 하세요. 사용자에게 필요한 사용 권한이 나열된 화면이 표시됩니다. 사용 권한 옆에 녹색 확인 표시가 Storage 있습니다.

2. 시작 **을 탭합니다.**

3. 모든 파일을 관리할 수 있도록 허용 **토글을 탭합니다.** 

4. 이제 장치가 보호됩니다.

  >[!NOTE] 
  >이 사용 권한은 끝점용 Microsoft Defender가 사용자 장치의 저장소에 액세스할 수 있도록 하여 악의적이지 않은 원치 않는 앱을 검색하고 제거하는 데 도움이 됩니다. 끝점용 Microsoft Defender는 Android 앱 패키지 파일(.apk)만 액세스하고 검색합니다. 작업 프로필이 있는 장치에서 Denender는 작업 관련 파일만 검색합니다.







