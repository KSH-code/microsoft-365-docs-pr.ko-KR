---
title: Microsoft Defender for Endpoint(Android용) - 개인 정보
description: 개인 정보 제어, Android의 끝점용 Microsoft Defender에서 수집된 진단 데이터에 대한 개인 정보 및 정보에 영향을 미치는 정책 설정을 구성하는 방법입니다.
keywords: Microsoft, defender, Endpoint용 Microsoft Defender, android, 개인 정보, 진단
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
ms.openlocfilehash: 185ffab8d4fb67040d11dbf8b36459b94341a0d2
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60176910"
---
# <a name="microsoft-defender-for-endpoint-on-android---privacy-information"></a>Microsoft Defender for Endpoint(Android용) - 개인 정보

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Android의 Endpoint용 Defender는 구성된 Android 장치에서 정보를 수집하고 Endpoint용 Defender가 있는 동일한 테넌트에 저장합니다. 이 정보는 Android용 Endpoint용 Defender를 안전하고 최신으로 유지하며 예상대로 수행하고 서비스를 지원하기 위해 수집됩니다.

데이터 저장소에 대한 자세한 내용은 끝점 데이터 저장소 및 개인 정보 보호를 위한 [Microsoft Defender를 참조하세요.](data-storage-privacy.md)

Android용 Endpoint용 Defender를 예상대로 안전하게 최신으로 유지하고 서비스를 지원하기 위해 수집된 정보입니다.

Android 및 iOS 모바일 장치의 끝점용 Microsoft Defender에 대한 가장 일반적인 개인 정보 보호 질문에 대한 자세한 내용은 Android 및 iOS 모바일 장치에서 [끝점용 Microsoft Defender](https://support.microsoft.com/topic/microsoft-defender-for-endpoint-and-your-privacy-on-android-and-ios-mobile-devices-4109bc54-8ec5-4433-9c33-d359b75ac22a)및 개인 정보를 참조하세요.

## <a name="required-data"></a>필수 데이터

필수 데이터는 Android용 Endpoint용 Defender가 예상대로 작동하게 하는 데 필요한 데이터로 구성됩니다. 이 데이터는 서비스 운영에 필수적으로 사용하며 최종 사용자, 조직, 장치 및 앱과 관련된 데이터를 포함할 수 있습니다. 수집되는 데이터의 유형 목록은 다음과 같습니다.

### <a name="app-information"></a>앱 정보

디바이스의  악성 Android 응용 프로그램 패키지(APK)에 대한 정보 포함

- 원본 설치
- Storage 위치(파일 경로)입니다.
- 설치 시간, APK 크기 및 사용 권한

### <a name="web-page--network-information"></a>웹 페이지/네트워크 정보

- 악의적인 연결 또는 웹 페이지가 검색된 웹 사이트의 전체 URL입니다.
- 연결 정보
- 프로토콜 유형(예: HTTP, HTTPS 등)

### <a name="device-and-account-information"></a>장치 및 계정 정보

- 날짜 및 &, Android 버전, OEM 모델, CPU 정보 및 장치 식별자와 같은 장치 정보입니다.
- 장치 식별자는 다음 중 하나입니다.
  - Wi-Fi 어댑터 MAC 주소
  - [Android](https://developer.android.com/reference/android/provider/Settings.Secure#ANDROID_ID) ID(디바이스를 처음 부팅할 때 Android에서 생성)
  - 임의로 생성된 GUID(Globally Unique Identifier)입니다.

- 테넌트, 장치 및 사용자 정보
  - Azure Active Directory(AD) 장치 ID 및 Azure 사용자 ID: Azure Active Directory에서 각각 장치를 고유하게 식별합니다.
  - Azure 테넌트 ID: 조직 내에서 조직을 식별하는 Azure Active Directory.
  - Microsoft Defender for Endpoint org ID: 장치가 속한 엔터프라이즈와 연결된 고유 식별자입니다. Microsoft에서 문제가 선택한 엔터프라이즈 집합에 영향을 미치는지 여부와 영향을 미치는 엔터프라이즈 수를 식별할 수 있도록 합니다.
  - 사용자 계정 이름: 사용자의 전자 메일 ID

### <a name="product-and-service-usage-data"></a>제품 및 서비스 사용 현황 데이터

다음 정보는 장치에 설치된 끝점용 Microsoft Defender 앱에만 수집됩니다. 

- 이름, 버전 및 앱 업그레이드 상태를 포함한 앱 패키지 정보입니다.
- 앱에서 수행된 작업입니다.
- 위협 감지 정보(예: 위협 이름, 범주 등)
- Android에서 생성된 크래시 보고서 로그입니다.

## <a name="optional-data"></a>선택적 데이터

선택적 데이터에는 진단 데이터 및 피드백 데이터가 포함됩니다. 선택적 진단 데이터는 제품을 개선하고 향상된 정보를 제공하여 문제를 감지, 진단, 해결하는 데 도움이 되는 추가 데이터입니다. 선택적 진단 데이터에는 다음이 포함됩니다.

- 앱, CPU 및 네트워크 사용.
- 검사 상태, 검사 시간, 부여된 앱 권한 및 업그레이드 상태를 포함하여 앱 관점에서 장치의 상태입니다.
- 관리자가 구성한 기능입니다.
- 장치의 브라우저에 대한 기본 정보입니다.

**피드백 데이터는** 사용자가 제공한 앱 내 피드백을 통해 수집됩니다.

- 사용자의 전자 메일 주소(제공하도록 선택한 경우)
- 피드백 유형(스마일, 희미한, 아이디어) 및 사용자가 제출한 피드백 설명입니다.
