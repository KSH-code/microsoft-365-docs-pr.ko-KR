---
title: Office 365용 TLS 1.0 및 1.1 사용 중단
description: Office 365의 TLS 1.0 및 1.1 사용되지 않습니다.
author: workshay
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: shmehta
ms.reviewer: krowley
appliesto:
- Microsoft 365 Apps for enterprise
- Office 365 Business
- Office 365 Personal
- Office Online Server
- Office Web Apps
ms.openlocfilehash: 622d783011defcf9c84061087b7d05f2a117172e
ms.sourcegitcommit: 3bf4f1c0d3a8515cca651b2a520217195f89457f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2021
ms.locfileid: "49777060"
---
# <a name="tls-10-and-11-deprecation-for-office-365"></a>Office 365용 TLS 1.0 및 1.1 사용 중단
> [!IMPORTANT]
> COVID-19로 인해 상업 고객의 경우 TLS 1.0 및 1.1의 사용 중단이 일시적으로 중단되었습니다. 그러나 공급망이 조정되고 특정 국가가 백업될 때 TLS 적용이 2020년 10월 15일부터 다시 설정되고 있으며, 다음 주와 몇 개월 동안 롤아웃이 계속됩니다. 

2018년 10월 31일 현재, Office 365 서비스에 대해 TLS(전송 계층 보안) 1.0 및 1.1 프로토콜은 더 이상 사용되지 않습니다. 최종 사용자에게는 최소한의 영향이 있을 것으로 예상됩니다. 이 변경은 2년 이상 공개되고 2017년 12월에 첫 번째 공개 발표가 있습니다. 이 문서는 Office 365 서비스와 관련한 Office 365 로컬 클라이언트에 대해 다루기 위한 것일 뿐 아니라 Office 및 Office Online Server/Office Web Apps의 온라인 TLS 문제에도 적용할 수 있습니다.

## <a name="office-and-tls-overview"></a>Office 및 TLS 개요

Office 클라이언트는 WINHTTP(Windows 웹 서비스)를 사용하여 TLS 프로토콜을 통해 트래픽을 보내고 수신합니다. 로컬 컴퓨터의 웹 서비스가 TLS 1.2를 사용할 수 있는 경우 Office 클라이언트는 TLS 1.2를 사용할 수 있습니다. TLS 및 SSL 프로토콜은 Office 클라이언트와 관련이 없는 운영 체제의 일부이기에 따라 모든 Office 클라이언트는 TLS 프로토콜을 사용할 수 있습니다.

### <a name="on-windows-8-and-later-versions"></a>Windows 8 이상 버전

TLS 1.2 트래픽을 거부하도록 구성된 네트워크 장치가 없는 경우 기본적으로 TLS 1.2 및 1.1 프로토콜을 사용할 수 있습니다.

### <a name="on-windows-7"></a>Windows 7의 경우

KB [3140245 업데이트가 없는 경우 TLS 1.1 및 1.2 프로토콜을 사용할 수](https://support.microsoft.com/help/3140245) 없습니다. 업데이트는 이 문제를 해결하고 다음 레지스트리 하위 키를 추가합니다.

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> 이 업데이트가 없는 Windows 7 사용자는 2018년 10월 31일 현재 영향을 받을 수 있습니다. [KB 3140245에는](https://support.microsoft.com/help/3140245) TLS 프로토콜을 사용하도록 WINHTTP 설정을 변경하는 방법에 대한 세부 정보가 있습니다.

#### <a name="more-information"></a>추가 정보

KB 문서에서 설명하는 **DefaultSecureProtocols** 레지스트리 키의 값에 따라 사용할 수 있는 네트워크 프로토콜이 결정됩니다.

|DefaultSecureProtocols 값|프로토콜 사용|
|-|-|
|0x00000008|기본적으로 SSL 2.0 사용|
|0x00000020|기본적으로 SSL 3.0 사용|
|0x00000080|기본적으로 TLS 1.0 사용|
|0x00000200|기본적으로 TLS 1.1 사용|
|0x00000800|기본적으로 TLS 1.2 사용|

## <a name="office-clients-and-tls-registry-keys"></a>Office 클라이언트 및 TLS 레지스트리 키

[Office 365에서 TLS 1.2의 필수 사용을 준비하는 KB 4057306을](https://support.microsoft.com/help/4057306)참조할 수 있습니다. 이 문서는 IT 관리자를 위한 일반 문서로, TLS 1.2 변경에 대한 공식 설명서입니다.

다음 표에는 2018년 10월 31일 이후 Office 365 클라이언트의 적절한 레지스트리 키 값이 표시됩니다.

|2018년 10월 31일 이후 Office 365 서비스에 대한 프로토콜 사용|16진수 값|
|-|-|
|TLS 1.0 + 1.1 + 1.2|0x00000A80|
|TLS 1.1 + 1.2|0x00000A00|
|TLS 1.0 + 1.2|0x00000880|
|TLS 1.2|0x00000800|

> [!IMPORTANT]
> **DefaultSecureProtocols** 키를 사용하여 설정할 수도 있는 SSL 2.0 및 3.0 프로토콜은 사용하지 않는 것이 좋습니다. SSL 2.0 및 3.0은 사용되지 않습니다. 최상의 방법은 SSL 2.0 및 SSL 3.0 사용을 종료하는 것입니다. 그러나 이를 위한 결정은 궁극적으로 제품 요구 사항을 가장 잘 충족하는지 여부에 따라 결정됩니다. SSL 3.0 취약성에 대한 자세한 내용은 [KB 3009008을 참조하십시오.](https://support.microsoft.com/help/3009008)

프로그래머 모드에서 기본 Windows 계산기를 사용하여 동일한 참조 레지스트리 키 값을 설정할 수 있습니다. 자세한 내용은 [Windows의 WinHTTP에서 TLS 1.1 및 TLS 1.2를 기본 보안 프로토콜로 사용하도록 설정하려면 KB 3140245 업데이트를 참조하세요.](https://support.microsoft.com/help/3140245)

Windows 7[업데이트(KB 3140245)가](https://support.microsoft.com/help/3140245)설치되어 있어야 하는지와 관계없이 DefaultSecureProtocols 레지스트리 하위 키가 존재하지 않습니다. 수동으로 또는 GPO(그룹 정책 개체)를 통해 추가해야 합니다. 즉, 사용하도록 설정되거나 제한된 보안 프로토콜을 사용자 지정해야 하는 경우를 위해 이 키는 필요하지 않습니다. Windows 7[SP1(KB 3140245) 업데이트만](https://support.microsoft.com/help/3140245)필요합니다.
