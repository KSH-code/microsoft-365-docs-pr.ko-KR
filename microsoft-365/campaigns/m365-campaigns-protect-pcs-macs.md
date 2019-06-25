---
title: 관리 되지 않는 Windows 10 Pc 및 Mac 보호
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Microsoft 365 for 캠페인을 통해 피싱 및 기타 공격 으로부터 보호 합니다.
ms.openlocfilehash: 8b83fa9c145f2c17347fc4c2983c64d4003f46c8
ms.sourcegitcommit: c452413dff5d5388c9725f38871246237c313e65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/22/2019
ms.locfileid: "35183374"
---
# <a name="protect-unmanaged-windows-10-pcs-and-macs"></a>관리 되지 않는 Windows 10 Pc 및 Mac 보호

이를 Microsoft Intune에 등록 하 여 Windows 10 Pc 및 Mac을 관리할 수 있으며,이를 통해 해당 환경의 데이터에 액세스 하기 전에 이러한 장치를 안전 하 고 안전한 상태로 유지할 수도 있습니다. 그러나 많은 캠페인 및 소규모 기업에는 조직에서 관리할 수 없는 byod (자체 장치)를 제공 하는 인력이 포함 됩니다. 이러한 관리 되지 않는 Pc 및 Mac에 대해이 문서를 사용 하 여 최소 보안 기능이 구성 되어 있는지 확인 합니다. 

<!--A Windows 10 PC is considered managed after you have completed the following two steps:

1. You (or the admin) set up device and data protection policies in the [setup  wizard](../business/set-up.md).

2. You have [connected your computer to Azure Active Directory](../business/set-up-windows-devices.md) and use your Microsoft 365 Business username and password to sign in.
3. --> 

## <a name="protect-a-computer-running-windows-10-or-a-mac"></a>Windows 10 또는 Mac을 실행 하는 컴퓨터 보호

<!--If you have a PC that is running Windows 10 that is not connected to Microsoft 365 Business, or a Mac, the Microsoft 365 Business protections do not apply to it, but here are some things you can do to keep your data secure on these devices as well:
-->
조직에서 Windows 10 PC 또는 Mac을 관리 하지 않는 경우 이러한 보안 기능을 구성 해야 합니다.

## <a name="windows-10tabwindows10"></a>[Windows 10](#tab/Windows10)
**장치 암호화 켜기**<p>

다양 한 범위의 Windows 장치에서 장치 암호화를 사용할 수 있으며 암호화를 통해 데이터를 보호할 수 있습니다. 장치 암호화를 켜면 승인 된 사용자만 장치 및 데이터에 액세스할 수 있게 됩니다. 자세한 내용은 [장치 암호화 설정을](https://support.microsoft.com/en-us/help/4028713/windows-10-turn-on-device-encryption) 참조 하세요.

 장치에서 장치 암호화를 사용할 수 없는 경우 표준 [BitLocker 암호화](https://support.microsoft.com/en-us/help/4028713/windows-10-turn-on-device-encryption) 를 대신 켤 수 있습니다. BitLocker는 Windows 10 Home edition에서 사용할 수 없습니다. 



**Windows 보안을 사용 하 여 장치 보호**<p>
Windows 10이 있는 경우 Windows 보안을 사용 하 여 최신 바이러스 백신 보호를 사용할 수 있습니다. Windows 10을 처음 시작 하면 Windows 보안이 켜 지 며 맬웨어 (악의적인 소프트웨어), 바이러스 및 보안 위협을 검사 하 여 PC를 보호 하는 데 도움을 줍니다. Windows 보안에서는 실시간 보호를 사용 하 여 PC에서 다운로드 하거나 실행 한 모든 항목을 검사 합니다.

Windows Update는 Windows 보안 업데이트를 자동으로 다운로드 하 여 PC를 안전 하 게 유지 하 고 위협 으로부터 보호 합니다.

이전 버전의 Windows가 있고 Microsoft 보안 Essentials를 사용 하는 경우 Windows 보안으로 이동 하는 것이 좋습니다. 자세한 내용은 [Windows 보안으로 내 장치 보호를](https://support.microsoft.com/en-us/help/17464/windows-10-help-protect-my-device-with-windows-security) 참조 하세요.

**Windows 방화벽 설정**<p>
다른 방화벽이 설정 된 경우에도 항상 Windows 방화벽을 실행 해야 합니다. Windows 방화벽을 끄면 장치 (및 네트워크)가 무단으로 액세스 하는 데 더 취약 해질 수 있습니다. 지침은 [Windows 방화벽 켜기 또는 끄기](https://support.microsoft.com/en-us/help/4028544/windows-10-turn-windows-defender-firewall-on-or-off) 를 참조 하세요.

## <a name="mactabmac"></a>[Mac](#tab/Mac)
**FileVault을 사용 하 여 Mac 디스크 암호화**<p>
디스크 암호화는 장치를 분실 하거나 도난당 한 경우 데이터를 보호 합니다. FileVault 전체 디스크 암호화는 시작 디스크의 정보에 대 한 무단 액세스를 방지 하는 데 도움이 됩니다. 지침은 [FileVault을 사용 하 여 Mac에서 시동 디스크 암호화를](https://support.apple.com/HT204837) 참조 하세요.

**맬웨어 로부터 mac 보호**<p>
Mac에서 신뢰할 수 있는 바이러스 백신 소프트웨어를 설치 하 고 사용 하는 것이 좋습니다. 선택 사항 목록은 다음 문서를 참조 하십시오 ( [최상의 Mac 바이러스 백신 2019 ](https://www.macworld.co.uk/feature/mac-software/mac-antivirus-3672182/)).

신뢰할 수 있는 원본의 소프트웨어만 사용 하 여 맬웨어의 위험을 줄일 수도 있습니다. 보안 & 개인 정보 기본 설정의 설정을 사용 하 여 Mac에 설치 된 소프트웨어의 출처를 지정할 수 있습니다. 자세한 내용은 [맬웨어 로부터 Mac 보호](https://support.apple.com/kb/PH25087) 를 참조 하세요.

**방화벽 보호 설정**<p>
방화벽 설정을 사용 하 여 인터넷 이나 네트워크에 연결 되어 있을 때 다른 컴퓨터가 시작한 원치 않는 대화 상대 로부터 Mac을 보호 합니다. 이 보호를 사용 하지 않으면 Mac이 무단으로 액세스 하는 데 더 취약 해질 수 있습니다. 지침은 [응용 프로그램 방화벽 정보](https://support.apple.com/HT201642) 를 참조 하세요.
