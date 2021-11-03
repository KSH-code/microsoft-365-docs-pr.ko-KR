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
ms.openlocfilehash: 820c93804615e9aafcb34052d65f09bbd3e3d1c9
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2021
ms.locfileid: "60717519"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-android"></a>Android의 끝점용 Microsoft Defender의 새로운

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="upcoming-permission-changes-for-microsoft-defender-for-endpoint-running-android-11-or-later"></a>Android 11 이상을 실행하는 끝점용 Microsoft Defender에 대한 예정된 권한 변경 사항

11월에는 [Google에서](https://developer.android.com/distribute/play-policies#APILevel30) Android API 30으로 이동하기 위해 끝점용 Microsoft Defender가 필요합니다. 이 이동은 Android [](https://developer.android.com/training/data-storage/manage-all-files#all-files-access-google-play) 11 이상을 실행하는 장치에 대한 새 저장소 권한을 묻는 메시지를 표시합니다. 사용자는 11월 버전의 끝점용 Microsoft Defender로 업데이트한 후 이 새 저장소 권한을 수락해야 합니다. 이렇게 하면 장치에서 Defender의 '앱 보안' 기능이 계속됩니다. 자세한 내용은 다음 섹션의 세부 정보를 참조하세요.

**조직에 미치는 영향:**

이러한 변경 내용은 Android 11 이상을 실행하고 11월 앱으로 업데이트된 장치에서 끝점용 Microsoft Defender를 사용하는 경우에만 영향을 미치게 됩니다. 이 설정은 다음 설정을 통해 구성할 Microsoft Endpoint Manager. 사용자가 앞서 수행한 Google API 변경으로 인해 조치를 취해야 합니다.

- **사용자 환경:** 사용자는 앱 보안에 대한 사용 권한이 누락되었음을 나타내는 알림을 받게 됩니다. 사용자가 이 권한을 거부하면 장치에서 '앱 보안' 기능이 꺼집니다. 사용자가 권한을 수락하거나 거부하지 않는 경우 디바이스 잠금을 해제하거나 승인될 때까지 앱을 열 때 메시지가 계속 표시됩니다.

>[!NOTE] 
> 조직에서 '변조 방지' 기능을 미리 보고 있으며 최신 버전으로 업데이트한 후 7일 이내에 사용자가 새 저장소 권한을 부여하지 않은 경우 사용자는 회사 리소스에 액세스할 수 없습니다.

**준비에 필요한 작업:**

끝점용 Microsoft Defender 앱의 11월 버전으로 업데이트한 후 메시지가 표시될 때 사용자에게 새 사용 권한을 수락해야 하다는 사실을 사용자 및 기술 지원팀에 알릴 수 있습니다. 사용 권한을 수락하려면 사용자는 다음을 해야 합니다.

1. Defender 앱 내 알림을 탭하거나 끝점용 Microsoft Defender 앱을 하세요. 사용자에게 필요한 사용 권한이 나열된 화면이 표시됩니다. 사용 권한 옆에 녹색 확인 표시가 Storage 있습니다.

2. 시작 **을 탭합니다.**

3. 모든 파일을 관리할 수 있도록 허용 **토글을 탭합니다.** 

  >[!NOTE] 
  >이 사용 권한은 끝점용 Microsoft Defender가 사용자 장치의 저장소에 액세스할 수 있도록 하여 악의적이지 않은 원치 않는 앱을 검색하고 제거하는 데 도움이 됩니다. 끝점용 Microsoft Defender는 Android 앱 패키지 파일(.apk)만 액세스하고 검색하며, 작업 프로필이 있는 장치에서는 작업 관련 파일만 검색합니다.

4. 이제 장치가 보호됩니다.





