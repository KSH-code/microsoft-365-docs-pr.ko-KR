---
title: Microsoft Defender 바이러스 백신 네트워크 연결 구성 및 유효성 검사
description: Microsoft Defender 바이러스 백신 클라우드 보호 서비스에 대한 연결을 구성하고 테스트합니다.
keywords: 바이러스 백신, Microsoft Defender 바이러스 백신, 맬웨어 방지, 보안, defender, 클라우드, 적극성, 보호 수준
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/28/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 8c049a7301cc651dbf2621d0baa398117856b925
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274643"
---
# <a name="configure-and-validate-microsoft-defender-antivirus-network-connections"></a>Microsoft Defender 바이러스 백신 네트워크 연결 구성 및 유효성 검사

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

Microsoft Defender 바이러스 백신 클라우드 제공 보호가 제대로 작동하려면 끝점과 특정 Microsoft 서버 간의 연결을 허용하도록 네트워크를 구성해야 합니다.

이 문서에서는 방화벽 규칙을 사용하는 등 허용해야 하는 연결을 나열하고 연결 유효성을 검사하기 위한 지침을 제공합니다. 보호를 올바르게 구성하면 클라우드 제공 보호 서비스에서 최고의 가치를 받을 수 있습니다.

네트워크 연결에 대한 자세한 내용은 블로그 게시물 [Microsoft Active Protection Services](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) 끝점에 대한 중요한 변경 사항을 참조하세요.

>[!TIP]
>Microsoft Defender for Endpoint 데모 웹 [사이트를](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 방문하여 demo.wd.microsoft.com 작동을 확인할 수 있습니다.
>
>- 클라우드 제공 보호
>- 빠른 학습(차단 시 차단 포함)
>- 잠재적으로 원치 않는 응용 프로그램 차단

## <a name="allow-connections-to-the-microsoft-defender-antivirus-cloud-service"></a>Microsoft Defender 바이러스 백신 클라우드 서비스에 대한 연결 허용

Microsoft Defender 바이러스 백신 클라우드 서비스는 끝점을 빠르고 강력하게 보호합니다. 클라우드 제공 보호 서비스를 사용하도록 설정하는 것은 선택 사항이지만 끝점 및 네트워크 전체에서 맬웨어에 대한 중요한 보호 기능을 제공하기 때문에 이 서비스를 사용하도록 설정하는 것이 좋습니다.

>[!NOTE]
>Microsoft Defender 바이러스 백신 클라우드 서비스는 네트워크 및 끝점에 업데이트된 보호를 제공하는 메커니즘입니다. 클라우드 서비스라고 하지만 단순히 클라우드에 저장된 파일을 보호하는 것이 아니라 분산 리소스와 기계 학습을 사용하여 기존 보안 인텔리전스 업데이트보다 훨씬 빠른 속도로 끝점에 보호 기능을 제공합니다.

Intune, Microsoft Endpoint Configuration Manager, 그룹 정책, PowerShell cmdlet 또는 Windows 보안 앱의 개별 클라이언트에서 서비스를 사용하도록 설정하는 데 대한 자세한 내용은 클라우드 제공 보호 사용을 참조하세요. [](enable-cloud-protection-microsoft-defender-antivirus.md) 

서비스를 사용하도록 설정한 후 네트워크 또는 방화벽과 끝점 간의 연결을 허용하도록 구성해야 할 수 있습니다.

보호는 클라우드 서비스이기 때문에 컴퓨터는 인터넷에 액세스할 수 있어야 합니다. Microsoft Defender for Office 365 기계 학습 서비스에 연결해야 합니다. 모든 종류의 네트워크 검사에서 URL을 `*.blob.core.windows.net` 제외하지 않습니다. 

아래 표에는 서비스 및 해당 관련 URL이 나열됩니다. 이러한 URL에 대한 액세스를 거부하는 방화벽 또는 네트워크 필터링 규칙이 없는지 확인하거나 해당 URL에 대해 특별히 허용 규칙을 만들어야 할 수 있습니다(URL `*.blob.core.windows.net` 제외). 아래 언급 URL은 통신에 포트 443을 사용하고 있습니다.


| **서비스**| **설명** |**URL** |
| :--: | :-- | :-- |
| MICROSOFT Defender 바이러스 백신 클라우드 제공 보호 서비스(MAPS(Microsoft Active Protection Service)라고도 합니다.|Microsoft Defender 바이러스 백신에서 클라우드 제공 보호를 제공하는 데 사용됩니다.|`*.wdcp.microsoft.com` <br/> `*.wdcpalt.microsoft.com` <br/> `*.wd.microsoft.com`|
| MICROSOFT 업데이트 서비스(MU) <br/> WU(Windows 업데이트 서비스)|  보안 인텔리전스 및 제품 업데이트   |`*.update.microsoft.com` <br/> `*.delivery.mp.microsoft.com`<br/> `*.windowsupdate.com` <br/><br/> 자세한 내용은 [Windows 업데이트용 연결 끝점을 참조합니다.](/windows/privacy/manage-windows-1709-endpoints#windows-update)|
|보안 인텔리전스 업데이트 ADL(대체 다운로드 위치)|   설치된 보안 인텔리전스가 최신 상태로 유지된 경우 Microsoft Defender 바이러스 백신 보안 인텔리전스 업데이트의 대체 위치(7일 이상 후)|    `*.download.microsoft.com`  </br> `*.download.windowsupdate.com`</br> `https://fe3cr.delivery.mp.microsoft.com/ClientWebService/client.asmx`|
| 맬웨어 제출 저장소|제출 양식 또는 자동 샘플 제출을 통해 Microsoft에 제출된 파일의 업로드 위치    | `ussus1eastprod.blob.core.windows.net` <br/>    `ussus2eastprod.blob.core.windows.net` <br/>    `ussus3eastprod.blob.core.windows.net` <br/>    `ussus4eastprod.blob.core.windows.net` <br/>    `wsus1eastprod.blob.core.windows.net` <br/>    `wsus2eastprod.blob.core.windows.net` <br/>    `ussus1westprod.blob.core.windows.net` <br/>    `ussus2westprod.blob.core.windows.net` <br/>    `ussus3westprod.blob.core.windows.net` <br/>    `ussus4westprod.blob.core.windows.net` <br/>    `wsus1westprod.blob.core.windows.net` <br/>    `wsus2westprod.blob.core.windows.net` <br/>    `usseu1northprod.blob.core.windows.net` <br/>    `wseu1northprod.blob.core.windows.net` <br/>    `usseu1westprod.blob.core.windows.net` <br/>    `wseu1westprod.blob.core.windows.net` <br/>    `ussuk1southprod.blob.core.windows.net` <br/>    `wsuk1southprod.blob.core.windows.net` <br/>    `ussuk1westprod.blob.core.windows.net` <br/>    `wsuk1westprod.blob.core.windows.net` |
| CRL(인증서 해지 목록)|CRL을 업데이트하기 위해 MAPS에 대한 SSL 연결을 만들 때 Windows에서 사용됩니다.   | `http://www.microsoft.com/pkiops/crl/` <br/> `http://www.microsoft.com/pkiops/certs` <br/>   `http://crl.microsoft.com/pki/crl/products` <br/> `http://www.microsoft.com/pki/certs` |
| 기호 저장소|Microsoft Defender 바이러스 백신에서 수정 흐름 중에 중요한 특정 파일을 복원하는 데 사용됩니다.  | `https://msdl.microsoft.com/download/symbols` |
| 유니버설 원격 분석 클라이언트| Windows에서 클라이언트 진단 데이터를 전송하는 데 사용됩니다. Microsoft Defender 바이러스 백신은 제품 품질 모니터링을 위해 원격 분석 사용   | 이 업데이트는 SSL(TCP 포트 443)을 사용하여 매니페스트를 다운로드하고 다음 DNS 끝점을 사용하는 진단 데이터를 Microsoft에 업로드합니다.   `vortex-win.data.microsoft.com` <br/>   `settings-win.data.microsoft.com`|

## <a name="validate-connections-between-your-network-and-the-cloud"></a>네트워크와 클라우드 간의 연결 유효성 검사

위에 나열된 URL을 허용한 후 Microsoft Defender 바이러스 백신 클라우드 서비스에 연결되어 있으며 완전히 보호되도록 정보를 올바르게 보고하고 받는지 테스트할 수 있습니다.

**cmdline 도구를 사용하여 클라우드 제공 보호의 유효성을 검사합니다.**

Microsoft Defender 바이러스 백신 명령줄 유틸리티()와 함께 다음 인수를 사용하여 네트워크가 Microsoft Defender 바이러스 백신 클라우드 서비스와 통신할 수 있는지 `mpcmdrun.exe` 확인합니다.

```console
"%ProgramFiles%\Windows Defender\MpCmdRun.exe" -ValidateMapsConnection
```

> [!NOTE]
> 명령 프롬프트의 관리자 수준 버전을 열 필요가 있습니다. 시작 메뉴에서 항목을 마우스 오른쪽  단추로 클릭하고 관리자 권한으로 실행을 클릭한 다음 사용 권한 프롬프트에서 **예를** 클릭합니다. 이 명령은 Windows 10 버전 1703 이상에서만 작동됩니다.

자세한 내용은 명령줄 도구를 사용하여 Microsoft Defender 바이러스 mpcmdrun.exe [관리를 참조하세요.](command-line-arguments-microsoft-defender-antivirus.md)

**Microsoft에서 위조된 맬웨어 파일을 다운로드하려고 시도합니다.**

클라우드에 제대로 연결되어 있는 경우 Microsoft Defender 바이러스 백신에서 검색하고 차단하는 샘플 파일을 다운로드할 수 있습니다.

를 방문하여 파일을 [https://aka.ms/ioavtest](https://aka.ms/ioavtest) 다운로드합니다.

>[!NOTE]
>이 파일은 실제 맬웨어 조각이 아니기 때문에 클라우드에 제대로 연결되어 있는지 테스트하도록 설계된 위조 파일입니다.

제대로 연결된 경우 Microsoft Defender 바이러스 백신 알림이 표시됩니다.

Microsoft Edge를 사용하는 경우 알림 메시지도 표시됩니다.

![사용자에게 맬웨어가 발견된 경우를 알리는 Microsoft Edge](images/defender/wdav-bafs-edge.png)

다음을 사용하는 경우 유사한 메시지가 Internet Explorer.

![사용자에게 맬웨어가 발견된 경우를 알리는 Microsoft Defender 바이러스 백신 알림](images/defender/wdav-bafs-ie.png)

또한 Windows 보안 앱의 검사 기록 섹션에서  **Quarantined threats** 아래에 검색이 표시됩니다.

1. 작업 표시줄에서 방패 아이콘을 클릭하거나 **Defender의** 시작 메뉴를 검색하여 Windows 보안 앱을 열 수 있습니다.

2. 바이러스 & **보호** 타일(또는 왼쪽 메뉴 표시줄의 방패 아이콘)을 선택한 다음 검사 기록 **레이블을** 선택합니다.

    ![Windows 보안 앱의 검사 기록 레이블 스크린샷](images/defender/wdav-history-wdsc.png)

3. **Quarantined threats(Quarantined threats)** 섹션에서 **전체** 기록 보기를 선택하여 검색된 가짜 맬웨어를 표시합니다.

   > [!NOTE]
   > 버전 1703 이전의 Windows 10 버전에는 다른 사용자 인터페이스가 있습니다. [Windows 보안 앱에서 Microsoft Defender 바이러스 백신을 참조하세요.](microsoft-defender-security-center-antivirus.md)

   Windows 이벤트 로그에는 클라이언트 [Windows Defender ID 1116도 표시됩니다.](troubleshoot-microsoft-defender-antivirus.md)

## <a name="related-articles"></a>관련 문서

- [Windows 10의 Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-in-windows-10.md)

- [클라우드 제공 보호 사용](enable-cloud-protection-microsoft-defender-antivirus.md)

- [명령줄 인수](command-line-arguments-microsoft-defender-antivirus.md)

- [Microsoft Active Protection Services 끝점에 대한 중요한 변경 사항](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006)