---
title: TLS 1.0 및 1.1을 Microsoft 365
description: TLS 1.0 및 1.1 사용 중지 및 Microsoft 365.
author: workshay
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: fasqiu
ms.reviewer: krowley
appliesto:
- Microsoft 365 Apps for enterprise
- Office 365 Business
- Office 365 Personal
- Office Online Server
- Office Web Apps
ms.openlocfilehash: 870572a61c241d3d3c8ce6791cee77edba2a1956
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59216295"
---
# <a name="disabling-tls-10-and-11-for-microsoft-365"></a>TLS 1.0 및 1.1을 Microsoft 365

> [!IMPORTANT]
> COVID-19로 인해 상업 고객의 경우 TLS 1.0 및 1.1의 비활성화를 일시적으로 중지했습니다. 공급망이 조정되고 특정 국가가 백업을 시작하면 2020년 10월 15일 TLS 1.2 적용 롤아웃이 다시 시작됩니다. 몇 주와 몇 개월에 한해 출시가 계속됩니다.

2018년 10월 31일 현재 TLS(전송 계층 보안) 1.0 및 1.1 프로토콜은 Microsoft 365 사용되지 않습니다. 최종 사용자에게는 최소한의 영향만 미미합니다. 이 변경은 2017년 12월에 첫 번째 공개 발표와 함께 2년 넘게 공개되고 있습니다. 이 문서에서는 Office 365 서비스 관련 Office 365 로컬 클라이언트에 대해 다루고 Office 365 Web Apps 및 Office 및 Office Online Server/Office TLS 문제에도 적용할 수 있습니다.

이 SharePoint OneDrive TLS 1.2를 지원하도록 .NET을 업데이트하고 구성해야 합니다. 자세한 내용은 [클라이언트에서 TLS 1.2를 사용하도록 설정하는 방법을 참조하세요.](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)

## <a name="office-365-and-tls-overview"></a>Office 365 및 TLS 개요

Office 클라이언트는 WINHTTP(Windows 웹 서비스)를 사용하여 TLS 프로토콜을 통해 트래픽을 보내고 수신합니다. 로컬 Office 웹 서비스에서 TLS 1.2를 사용할 수 있는 경우 클라이언트에서 TLS 1.2를 사용할 수 있습니다. TLS Office SSL 프로토콜은 운영 체제의 일부가 아닌 운영 체제의 일부이기 때문에 모든 Office 사용할 수 있습니다.

### <a name="on-windows-8-and-later-versions"></a>On Windows 8 and later versions

TLS 1.2 트래픽을 거부하도록 구성된 네트워크 장치가 없는 경우 기본적으로 TLS 1.2 및 1.1 프로토콜을 사용할 수 있습니다.

### <a name="on-windows-7"></a>On Windows 7

TLS 1.1 및 1.2 프로토콜은 [KB](https://support.microsoft.com/help/3140245) 업데이트가 없는 3140245 없습니다. 이 업데이트는 이 문제를 해결하고 다음 레지스트리 하위 키를 추가합니다.

```console
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings\WinHttp
```

> [!NOTE]
> Windows 이 업데이트가 없는 사용자 7명은 2018년 10월 31일 현재 영향을 받을 수 있습니다. [KB 3140245](https://support.microsoft.com/help/3140245) WINHTTP 설정을 변경하여 TLS 프로토콜을 사용하도록 설정하는 방법에 대한 세부 정보가 있습니다.

#### <a name="more-information"></a>추가 정보

KB 문서에서 설명하는 **DefaultSecureProtocols** 레지스트리 키의 값에 따라 사용할 수 있는 네트워크 프로토콜이 결정됩니다.

|DefaultSecureProtocols 값|프로토콜 사용|
|-|-|
|0x00000008|기본적으로 SSL 2.0 사용|
|0x00000020|기본적으로 SSL 3.0 사용|
|0x00000080|기본적으로 TLS 1.0 사용|
|0x00000200|기본적으로 TLS 1.1 사용|
|0x00000800|기본적으로 TLS 1.2 사용|

## <a name="office-clients-and-tls-registry-keys"></a>Office 및 TLS 레지스트리 키

에서 KB 4057306 [TLS 1.2의](https://support.microsoft.com/help/4057306)필수 사용 준비를 Office 365. 이 문서는 IT 관리자를 위한 일반 문서로, TLS 1.2 변경에 대한 공식 설명서입니다.

다음 표에는 2018년 10월 31일 이후의 Office 365 클라이언트의 적절한 레지스트리 키 값이 표시됩니다.

|2018년 10월 31일 이후 Office 365 서비스용 프로토콜 사용|16진수 값|
|-|-|
|TLS 1.0 + 1.1 + 1.2|0x00000A80|
|TLS 1.1 + 1.2|0x00000A00|
|TLS 1.0 + 1.2|0x00000880|
|TLS 1.2|0x00000800|

> [!IMPORTANT]
> **DefaultSecureProtocols** 키를 사용하여 설정할 수 있는 SSL 2.0 및 3.0 프로토콜을 사용하지 않습니다. SSL 2.0 및 3.0은 기한이 지난 비보안 프로토콜로 간주됩니다. 최상의 방법은 SSL 2.0 및 SSL 3.0 사용을 종료하는 것입니다. 그러나 이를 위한 결정은 궁극적으로 제품 요구 사항을 가장 잘 충족하는지 여부에 따라 결정됩니다. SSL 3.0 취약성에 대한 자세한 내용은 [KB](https://support.microsoft.com/help/3009008)3009008.

프로그래머 모드에서 기본 Windows 계산기를 사용하여 동일한 참조 레지스트리 키 값을 설정할 수 있습니다. 자세한 내용은 KB 3140245 업데이트를 참조하여 에서 WinHTTP의 기본 보안 프로토콜로 [TLS 1.1 및 TLS 1.2를 사용하도록 Windows.](https://support.microsoft.com/help/3140245)

Windows 7[업데이트(KB](https://support.microsoft.com/help/3140245)3140245)가 설치되어 있지 않은지와 관계없이 DefaultSecureProtocols 레지스트리 하위 키는 존재하지 않습니다. 수동으로 또는 GPO(그룹 정책 개체)를 통해 추가해야 합니다. 즉, 사용하도록 설정되거나 제한된 보안 프로토콜을 사용자 지정할 필요 없이 이 키가 필요하지 않습니다. 7 SP1(Windows) 업데이트만 3140245[](https://support.microsoft.com/help/3140245)필요합니다.

## <a name="update-and-configure-the-net-framework-to-support-tls-12"></a>TLS 1.2를 .NET Framework 업데이트 및 구성

TLS 1.2를 사용하려면 TLS Microsoft 365 또는 TLS 1.1을 통해 Microsoft 365 응용 프로그램을 업데이트해야 합니다. .NET 4.5는 기본적으로 TLS 1.1로 설정됩니다. .NET 구성을 업데이트하려면 [클라이언트에서 TLS(전송 계층 보안) 1.2를](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)사용하도록 설정하는 방법을 참조합니다.

## <a name="more-information"></a>추가 정보

자세한 내용은 에서 [TLS 1.2의](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)필수 사용 준비를 Office 365.

## <a name="references"></a>참조

다음 리소스는 클라이언트가 TLS 1.2 이상 버전을 사용하고 있는지와 TLS 1.0 및 1.1을 사용하지 않도록 설정하는 데 도움이 되는 지침을 제공합니다.

- Office 365에 연결하는 Windows 7 클라이언트의 경우 Windows의 WinHTTP에서 TLS 1.2가 기본 보안 프로토콜인지 확인하세요. 자세한 내용은 KB 3140245 - 업데이트 - 에서 WinHTTP의 기본 보안 프로토콜로 [TLS 1.1 및 TLS 1.2를 사용하도록](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in)Windows.
- TLS 1.0 및 1.1 종속성 제거를 통해 약한 TLS 사용을 해결 방법은 [Microsoft에서 TLS 1.2 지원을 참조하세요.](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)
- [새로운 IIS 기능](https://cloudblogs.microsoft.com/microsoftsecure/2017/09/07/new-iis-functionality-to-help-identify-weak-tls-usage/)을 사용하면 취약한 보안 프로토콜로 서비스에 연결하는 [Windows Server 2012 R2](https://support.microsoft.com/help/4025335/windows-8-1-windows-server-2012-r2-update-kb4025335) 및 [Windows Server 2016](https://support.microsoft.com/help/4025334/windows-10-update-kb4025334)에서 클라이언트를 쉽게 찾을 수 있습니다.
- [TLS 1.0](https://www.microsoft.com/download/details.aspx?id=55266)문제를 해결하는 방법에 대한 자세한 정보를 얻습니다.
- 보안에 접근하는 방식에 대한 일반적인 정보는 [Office 365 Trust Center](https://www.microsoft.com/trustcenter/cloudservices/office365)로 이동하십시오.
- [TLS 1.0/1.1 사용 중단 준비 - Office 365 비즈니스용 Skype](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/ba-p/222247)
- [Exchange Server TLS 지침, 1부: TLS 1.2 준비](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/ba-p/607649)
- [Exchange Server TLS 지침 2부: TLS 1.2 사용 및 이를 사용하지 않는 클라이언트 식별](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-2-enabling-tls-1-2-and/ba-p/607761)
- [Exchange Server TLS 지침 3부: TLS 1.0/1.1 끄기](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-3-turning-off-tls-1-0-1-1/ba-p/607898)
- [Office Online Server에서 TLS 1.1 및 TLS 1.2 지원 사용](/officeonlineserver/enable-tls-1-1-and-tls-1-2-support-in-office-online-server)

