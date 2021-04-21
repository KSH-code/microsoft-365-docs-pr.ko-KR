---
title: Linux에서 끝점용 Microsoft Defender를 통해 잠재적으로 원치 않는 응용 프로그램 검색 및 차단
description: Linux에서 끝점용 Microsoft Defender를 사용하여 잠재적으로 원치 않는 응용 프로그램(PUA)을 검색하고 차단합니다.
keywords: microsoft, defender, atp, linux, pua, pus
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 9631fc2eb1cb791f48f107482474d1bb8e2fd62b
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903861"
---
# <a name="detect-and-block-potentially-unwanted-applications-with-microsoft-defender-for-endpoint-on-linux"></a>Linux에서 끝점용 Microsoft Defender를 통해 잠재적으로 원치 않는 응용 프로그램 검색 및 차단

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Linux용 Endpoint용 Defender의 PUA(사용자 가능성이 원치 않는 응용 프로그램) 보호 기능은 네트워크의 끝점에서 PUA 파일을 검색하고 차단할 수 있습니다.

이러한 응용 프로그램은 바이러스, 맬웨어 또는 기타 유형의 위협으로 간주되지 않지만 성능이나 사용에 부정적인 영향을 주는 끝점에서 작업을 수행할 수 있습니다. PUA는 신뢰도가 낮은 것으로 간주되는 응용 프로그램을 참조할 수 있습니다.

이러한 응용 프로그램은 네트워크가 맬웨어에 감염될 위험을 높이고, 맬웨어 감염을 식별하기 더 어렵게 할 수 있으며, 응용 프로그램을 정리하는 데 IT 리소스를 낭비할 수 있습니다.

## <a name="how-it-works"></a>작동 방식

Linux용 끝점용 Defender는 PUA 파일을 검색하고 보고할 수 있습니다. 차단 모드에서 구성하면 PUA 파일이 검지로 이동됩니다.

끝점에서 PUA가 감지되면 Linux용 Endpoint용 Defender는 위협 기록에 감염 기록을 보관합니다. 기록은 Microsoft Defender 보안 센터 포털 또는 명령줄 도구를 통해 `mdatp` 시각화할 수 있습니다. 위협 이름에는 "Application"이라는 단어가 포함되어 있습니다.

## <a name="configure-pua-protection"></a>PUA 보호 구성

Linux용 끝점용 Defender의 PUA 보호는 다음 방법 중 하나에서 구성할 수 있습니다.

- **Off**: PUA 보호를 사용할 수 없습니다.
- **감사**: PUA 파일이 제품 로그에 보고되지만 Microsoft Defender 보안 센터에는 보고되지 않습니다. 감염에 대한 기록은 위협 기록에 저장되지 않습니다. 제품에 의해 수행된 조치가 없습니다.
- **차단:** PUA 파일이 제품 로그 및 Microsoft Defender 보안 센터에 보고됩니다. 감염 레코드는 위협 기록에 저장되고 제품이 조치를 취합니다.

>[!WARNING]
>기본적으로 PUA 보호는 감사 모드에서 **구성됩니다.**

명령줄 또는 관리 콘솔에서 PUA 파일이 처리되는 방법을 구성할 수 있습니다.

### <a name="use-the-command-line-tool-to-configure-pua-protection"></a>명령줄 도구를 사용하여 PUA 보호를 구성합니다.

터미널에서 다음 명령을 실행하여 PUA 보호를 구성합니다.

```bash
mdatp threat policy set --type potentially_unwanted_application --action [off|audit|block]
```

### <a name="use-the-management-console-to-configure-pua-protection"></a>관리 콘솔을 사용하여 PUA 보호를 구성합니다.

기업에서는 다른 제품 설정 구성 방법과 마찬가지로 Puppet 또는 Ansible과 같은 관리 콘솔에서 PUA 보호를 구성할 수 있습니다. 자세한 내용은 Linux용 [끝점용](linux-preferences.md#threat-type-settings) Defender에 대한 기본 설정 설정 문서의 위협 유형 설정 [섹션을 참조하세요.](linux-preferences.md)

## <a name="related-articles"></a>관련 문서

- [Linux용 끝점에 대한 Defender 기본 설정 설정](linux-preferences.md)
