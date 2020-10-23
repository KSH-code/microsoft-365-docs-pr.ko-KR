---
title: Office 365용 TLS 1.0 및 1.1 사용 중단
description: Office 365에 대 한 TLS 1.0 및 1.1의 중단에 대해 설명 합니다.
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
ms.openlocfilehash: ab3685883ac08522ab9ea1ee0cf194ba263d9166
ms.sourcegitcommit: 554755bc9ce40228ce6e34bde6fc6e226869b6a1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2020
ms.locfileid: "48681692"
---
# <a name="tls-10-and-11-deprecation-for-office-365"></a>Office 365용 TLS 1.0 및 1.1 사용 중단
> [!IMPORTANT]
> Microsoft는 covid-19로 인해 상업용 고객에 대 한 TLS 1.0 및 1.1의 사용 중단을 일시적으로 중지 했지만, 공급망이 조정 되 고 일부 국가에서 백업이 진행 되는 동안 TLS 적용을 다시 설정 하는 경우에는 다음과 같은 주 및 달 동안, 즉, 2020가 다시 시작 됩니다. 

2018 년 10 월 31 일까 지, Office 365 서비스에 대해 TLS (전송 계층 보안) 1.0 및 1.1 프로토콜이 더 이상 사용 되지 않습니다. 최종 사용자에 대 한 영향은 최소한으로 예상 됩니다. 이 변경 내용은 2 년 이상에 게 공개 되었으며 12 월 2017에 첫 번째로 발생 한 공지를 포함 합니다. 이 문서는 office 365 서비스와 관련 하 여 Office 365 로컬 클라이언트에만 적용 되는 것이 좋지만 Office 및 Office Online Server/Office Web Apps에 온-프레미스 TLS 문제에도 적용할 수 있습니다.

## <a name="office-and-tls-overview"></a>Office 및 TLS 개요

Office 클라이언트는 WINHTTP (Windows web service)를 사용 하 여 TLS 프로토콜을 통해 트래픽을 주고 받습니다. 로컬 컴퓨터의 웹 서비스가 TLS 1.2를 사용할 수 있는 경우 Office 클라이언트에서 TLS 1.2을 사용할 수 있습니다. TLS 및 SSL 프로토콜은 Office 클라이언트와 관련 되지 않고 운영 체제에 포함 되므로 모든 Office 클라이언트에서 TLS 프로토콜을 사용할 수 있습니다.

### <a name="on-windows-8-and-later-versions"></a>Windows 8 이상 버전

Tls 1.2 트래픽을 거부 하도록 구성 된 네트워크 장치가 없으면 기본적으로 TLS 1.2 및 1.1 프로토콜을 사용할 수 있습니다.

### <a name="on-windows-7"></a>Windows 7

TLS 1.1 및 1.2 프로토콜은 [5003140245](https://support.microsoft.com/help/3140245) 업데이트 없이 사용할 수 없습니다. 이 업데이트는이 문제를 해결 하 고 다음 레지스트리 하위 키를 추가 합니다.

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> 이 업데이트가 없는 Windows 7 사용자는 2018 년 10 월 31 일의 영향을 받습니다. 이 [3140245](https://support.microsoft.com/help/3140245) 는 TLS 프로토콜을 사용 하도록 WINHTTP 설정을 변경 하는 방법에 대 한 세부 정보를 포함 합니다.

#### <a name="more-information"></a>추가 정보

기술 자료 문서에 설명 된 **Defaultsecureprotocols** 레지스트리 키의 값은 사용할 수 있는 네트워크 프로토콜을 결정 합니다.

|DefaultSecureProtocols 값|프로토콜 사용|
|-|-|
|0x00000008|기본적으로 SSL 2.0 사용|
|0x00000020|기본적으로 SSL 3.0 사용|
|0x00000080|기본적으로 TLS 1.0 사용|
|0x00000200|기본적으로 TLS 1.1 사용|
|0x00000800|기본적으로 TLS 1.2 사용|

## <a name="office-clients-and-tls-registry-keys"></a>Office 클라이언트 및 TLS 레지스트리 키

[Office 365에서 TLS 1.2의 필수 사용을 위해 4057306을 준비 하는](https://support.microsoft.com/help/4057306)것을 참조할 수 있습니다. 이 문서는 IT 관리자를 위한 일반적인 문서로, TLS 1.2 변경 사항에 대 한 공식적인 설명서입니다.

다음 표에서는 2018 년 10 월 31 일 이후에 Office 365 클라이언트의 해당 레지스트리 키 값을 보여 줍니다.

|설정 된 Office 365 서비스에 대 한 사용 프로토콜 (2018 년 10 월 31 일)|16 진수 값|
|-|-|
|TLS 1.0 + 1.1 + 1.2|0x00000A80|
|TLS 1.1 + 1.2|0x00000A00|
|TLS 1.0 + 1.2|0x00000880|
|TLS 1.2|0x00000800|

> [!IMPORTANT]
> **Defaultsecureprotocols** 키를 사용해 서도 설정할 수 있는 SSL 2.0 및 3.0 프로토콜은 사용 하지 않는 것이 좋습니다. SSL 2.0 및 3.0는 더 이상 사용 되지 않는 프로토콜로 간주 됩니다. SSL 2.0 및 SSL 3.0의 사용을 종료 하는 것이 가장 좋지만, 이러한 방법은 제품 요구 사항에 가장 적합 한 결정에 따라 달라 집니다. SSL 3.0 취약성에 대 한 자세한 내용은 [kb(3009008](https://support.microsoft.com/help/3009008)를 참조 하세요.

프로그래머용 모드에서 기본 Windows 계산기를 사용 하 여 동일한 참조 레지스트리 키 값을 설정할 수 있습니다. 자세한 내용은 [Windows의 WinHTTP에서 tls 1.1 및 tls 1.2을 기본 보안 프로토콜로 사용 하도록 설정 하려면-프로토콜 3140245 업데이트](https://support.microsoft.com/help/3140245)를 참조 하세요.

Windows 7 업데이트 ([KB 3140245](https://support.microsoft.com/help/3140245))가 설치 되어 있는지 여부에 관계 없이 DefaultSecureProtocols 레지스트리 하위 키가 존재 하지 않으므로 수동으로 또는 GPO (그룹 정책 개체)를 통해 추가 해야 합니다. 즉, 사용할 수 있거나 제한 되는 보안 프로토콜을 사용자 지정 해야 하는 경우가 아니면이 키가 필요 하지 않습니다. Windows 7 SP1 ([KB 3140245](https://support.microsoft.com/help/3140245)) 업데이트만 있으면 됩니다.
