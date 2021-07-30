---
title: Android의 끝점용 Microsoft Defender 문제 해결
description: Android의 끝점용 Microsoft Defender 문제 해결
keywords: Microsoft, defender, Endpoint용 Microsoft Defender, mde, android, cloud, connectivity, communication
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
ms.openlocfilehash: e5528311c3affc507009ba49ddf71f71179ad755
ms.sourcegitcommit: d817a3aecb700f7227a05cd165ffa7dbad67b09d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/29/2021
ms.locfileid: "53648462"
---
# <a name="troubleshooting-issues-on-microsoft-defender-for-endpoint-on-android"></a>Android의 끝점용 Microsoft Defender 문제 해결

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

장치를 등록할 때 앱이 설치된 후 로그인 문제가 표시될 수 있습니다.

등록하는 동안 장치에 앱을 설치한 후 로그인 문제가 발생할 수 있습니다.

이 문서에서는 로그인 문제를 해결하기 위한 해결법을 제공합니다.  

## <a name="sign-in-failed---unexpected-error"></a>로그인 실패 - 예기치 않은 오류
**로그인 실패:** *예기치 않은 오류, 나중에 시도*

![로그인 실패 오류의 이미지 예기치 않은 오류](images/f9c3bad127d636c1f150d79814f35d4c.png)

**메시지:**

예기치 않은 오류, 나중에 시도

**원인:**

이전 버전의 "Microsoft Authenticator" 앱이 장치에 설치되어 있습니다.

**해결 방법:**

Google Play 스토어에서 최신 [Microsoft Authenticator](https://play.google.com/store/apps/details?androidid=com.azure.authenticator) 설치하고 다시 시도

## <a name="sign-in-failed---invalid-license"></a>로그인 실패 - 잘못된 라이선스

**로그인 실패: 라이선스가** *잘못되었습니다. 관리자에게 문의하세요.*

![로그인 실패 이미지 관리자에게 문의하시기 바랍니다.](images/920e433f440fa1d3d298e6a2a43d4811.png)

**메시지:** *라이선스가 잘못되었습니다. 관리자에게 문의하세요.*

**원인:**

사용자에게 Microsoft 365 라이선스가 할당되지 않은 경우 또는 조직에 Microsoft 365 Enterprise 대한 라이선스가 없습니다.

**해결 방법:**

관리자에게 문의하십시오.

## <a name="report-unsafe-site"></a>안전하지 않은 사이트 보고

피싱 웹 사이트는 개인 또는 재무 정보를 얻기 위해 신뢰할 수 있는 웹 사이트를 가장합니다. 피싱 [](https://www.microsoft.com/wdsi/filesubmission/exploitguard/networkprotection) 사이트일 수 있는 웹 사이트를 보고하려는 경우 네트워크 보호에 대한 피드백 제공 페이지를 방문하세요.

## <a name="phishing-pages-arent-blocked-on-some-oem-devices"></a>일부 OEM 장치에서 피싱 페이지가 차단되지 않습니다.

**다음에 적용됩니다.** 특정 OEM만

-   **Xiaomi**

Android용 끝점용 Defender에서 감지한 피싱 및 유해한 웹 위협은 일부 Xiaomi 장치에서 차단되지 않습니다. 이러한 장치에서는 다음 기능이 작동하지 않습니다.

![안전하지 않은 것으로 보고된 사이트의 이미지](images/0c04975c74746a5cdb085e1d9386e713.png)


**원인:**

Xiaomi 장치에는 새로운 사용 권한 모델이 포함되어 있습니다. 이렇게 하면 Android용 Endpoint용 Defender가 백그라운드에서 실행되는 동안 팝업 창을 표시하지 못합니다.

Xiaomi 장치 권한: "백그라운드에서 실행되는 동안 팝업 창 표시"

![팝업 설정 이미지](images/6e48e7b29daf50afddcc6c8c7d59fd64.png)

**해결 방법:**

Xiaomi 디바이스에 대해 필요한 권한을 사용하도록 설정

- 백그라운드에서 실행되는 동안 팝업 창을 표시합니다.
