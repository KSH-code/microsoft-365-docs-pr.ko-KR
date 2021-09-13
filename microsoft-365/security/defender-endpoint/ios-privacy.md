---
title: 개인 정보 보호 정보 - iOS의 끝점용 Microsoft Defender
ms.reviewer: ''
description: iOS의 끝점용 Microsoft Defender에 대한 개인 정보 보호 정보 설명
keywords: Microsoft, defender, Endpoint용 Microsoft Defender, ios, 정책, 개요
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: e1983e023a0236ea1e0ad9ac82b8d089e120cd7d
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59220540"
---
# <a name="privacy-information---microsoft-defender-for-endpoint-on-ios"></a>개인 정보 보호 정보 - iOS의 끝점용 Microsoft Defender

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

> [!NOTE]
> iOS의 끝점용 Defender는 VPN을 사용하여 웹 보호 기능을 제공합니다. 이는 일반 VPN이 아니며 장치 외부에서 트래픽을 취하지 않는 로컬 또는 자체 루프 VPN입니다. **Microsoft 또는 조직은 사용자의 검색 활동을 볼 수 없습니다.**

iOS의 Endpoint용 Defender는 구성된 iOS 장치에서 정보를 수집하고 Endpoint용 Defender가 있는 동일한 테넌트에 저장합니다. 이 정보는 iOS에서 끝점에 대한 Defender를 안전하고 최신으로 유지하며 예상대로 수행하고 서비스를 지원하기 위해 수집됩니다.

데이터 저장소에 대한 자세한 내용은 끝점 데이터 저장소 및 개인 정보 보호를 위한 [Microsoft Defender를 참조하세요.](data-storage-privacy.md)

Android 및 iOS 모바일 장치의 끝점용 Microsoft Defender에 대한 가장 일반적인 개인 정보 보호 질문에 대한 자세한 내용은 Android 및 iOS 모바일 장치에서 [끝점용 Microsoft Defender](https://support.microsoft.com/topic/microsoft-defender-for-endpoint-and-your-privacy-on-android-and-ios-mobile-devices-4109bc54-8ec5-4433-9c33-d359b75ac22a)및 개인 정보를 참조하세요.

## <a name="required-data"></a>필수 데이터

필수 데이터는 iOS의 끝점에 대한 Defender가 예상대로 작동하게 하는 데 필요한 데이터로 구성됩니다. 이 데이터는 서비스 운영에 필수적으로 사용하며 최종 사용자, 조직, 장치 및 앱과 관련된 데이터를 포함할 수 있습니다.

수집되는 데이터 형식 목록은 다음과 같습니다.

### <a name="web-page-or-network-information"></a>웹 페이지 또는 네트워크 정보

- 악의적인 연결 또는 웹 페이지가 검색된 웹 사이트의 도메인 이름 및 IP 주소입니다.

### <a name="device-and-account-information"></a>장치 및 계정 정보

- 날짜 및 &, iOS 버전, CPU 정보 및 장치 식별자와 같은 장치 정보입니다. 여기서 장치 식별자는 다음 중 하나입니다.
  - Wi-Fi 어댑터 MAC 주소
  - 임의로 생성된 GUID(Globally Unique Identifier)
- 테넌트, 장치 및 사용자 정보
  - Azure Active Directory(AD) 장치 ID 및 Azure 사용자 ID - Azure Active Directory에서 각각 장치를 고유하게 식별합니다.
  - Azure 테넌트 ID - 조직 내에서 조직을 식별하는 Azure Active Directory.
  - Microsoft Defender for Endpoint org ID - 장치가 속한 엔터프라이즈와 연결된 고유 식별자. Microsoft에서 선택한 엔터프라이즈 집합 및 영향을 받는 엔터프라이즈 수에 영향을 주는 문제가 있는지 식별할 수 있습니다.
  - 사용자 계정 이름 - 사용자의 전자 메일 ID입니다.

### <a name="product-and-service-usage-data"></a>제품 및 서비스 사용 현황 데이터

다음 정보는 장치에 설치된 끝점용 Microsoft Defender 앱에만 수집됩니다.

- 이름, 버전 및 앱 업그레이드 상태를 포함한 앱 패키지 정보입니다.
- 앱에서 수행된 작업입니다.
- iOS에서 생성된 크래시 보고서 로그입니다.
- 메모리 사용량 데이터입니다.

## <a name="optional-data"></a>선택적 데이터

선택적 데이터에는 클라이언트의 진단 데이터 및 피드백 데이터가 포함됩니다. 선택적 진단 데이터는 제품을 개선하고 향상된 정보를 제공하여 문제를 감지, 진단, 해결하는 데 도움이 되는 추가 데이터입니다. 이 데이터는 진단 목적으로만 사용하며 서비스 자체에 필요하지 않습니다.

선택적 진단 데이터에는 다음이 포함됩니다.

- 끝점용 Defender에 대한 앱, CPU 및 네트워크 사용.
- 관리자가 끝점용 Defender에 대해 구성한 기능입니다.

피드백 데이터는 사용자가 제공한 앱 내 피드백을 통해 수집됩니다.

- 사용자의 전자 메일 주소(제공하도록 선택한 경우)
- 피드백 유형(스마일, 희미한, 아이디어) 및 사용자가 제출한 피드백 설명입니다.

자세한 내용은 개인 정보 [보호에 대한 자세한 정보를 참조하세요.](https://aka.ms/mdatpiosprivacystatement)
