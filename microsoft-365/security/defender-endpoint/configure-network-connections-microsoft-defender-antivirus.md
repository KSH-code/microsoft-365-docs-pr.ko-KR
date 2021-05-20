---
title: Microsoft Defender 바이러스 백신 네트워크 연결 구성 및 유효성 검사
description: Microsoft Defender 바이러스 백신 클라우드 보호 서비스에 대한 연결을 구성하고 테스트합니다.
keywords: 바이러스 백신, Microsoft Defender 바이러스 백신, 맬웨어 방지, 보안, 수비수, 클라우드, 공격성, 보호 수준
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/17/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: ef5a9ffdf45a2f8e7f262ae7f969cd19e848b7a5
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572528"
---
# <a name="configure-and-validate-microsoft-defender-antivirus-network-connections"></a>Microsoft Defender 바이러스 백신 네트워크 연결 구성 및 유효성 검사

**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

클라우드로 배달된 보호 Microsoft Defender 바이러스 백신 제대로 작동하도록 하려면 엔드포인트와 특정 Microsoft 서버 간의 연결을 허용하도록 네트워크를 구성해야 합니다. 이 문서에서는 방화벽 규칙을 사용하여 허용해야 하는 연결을 나열하고 연결 유효성을 검사하기 위한 지침을 제공합니다. 보호를 올바르게 구성하면 클라우드에서 제공하는 보호 서비스에서 최상의 가치를 누릴 수 있습니다.

네트워크 연결에 대한 몇 가지 세부 정보는 블로그 게시물 [Microsoft 활성 보호 서비스 끝점에](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006) 대한 중요한 변경 사항을 참조하십시오.

> [!TIP]
> 또한 다음과 같은 기능이 작동하는지 확인하기 위해 [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 엔드 포인트 데모 웹 사이트에 대한 Microsoft Defender를 방문할 수 있습니다.
>
> - 클라우드 제공 보호
> - 빠른 학습 (첫눈에 블록 포함)
> - 잠재적으로 원치 않는 응용 프로그램 차단

## <a name="allow-connections-to-the-microsoft-defender-antivirus-cloud-service"></a>Microsoft Defender 바이러스 백신 클라우드 서비스에 대한 연결 허용

Microsoft Defender 바이러스 백신 클라우드 서비스는 엔드포인트에 대한 빠르고 강력한 보호를 제공합니다. 클라우드 제공 보호 서비스를 사용하도록 설정하는 것은 선택 사항이지만 엔드포인트와 네트워크 전체에서 맬웨어에 대한 중요한 보호를 제공하기 때문에 매우 권장됩니다.

> [!NOTE]
> Microsoft Defender 바이러스 백신 클라우드 서비스는 네트워크 및 끝점에 업데이트된 보호를 제공하는 메커니즘입니다. 클라우드 서비스라고 불리지만 단순히 클라우드에 저장된 파일을 보호하는 것이 아니라 분산 리소스와 머신 러닝을 사용하여 기존 보안 인텔리전스 업데이트보다 훨씬 빠른 속도로 엔드포인트에 보호를 제공합니다.

intune, Microsoft Endpoint Configuration Manager, 그룹 정책, PowerShell cmdlets 또는 Windows 보안 앱의 개별 클라이언트에서 서비스를 사용하도록 설정하는 방법에 대한 자세한 내용은 클라우드 제공 [보호 활성화를](enable-cloud-protection-microsoft-defender-antivirus.md) 참조하십시오. 

서비스를 활성화한 후 네트워크 또는 방화벽을 구성하여 서비스를 종료점과 끝점 간의 연결을 허용해야 할 수 있습니다.

보호는 클라우드 서비스이므로 컴퓨터는 인터넷에 액세스할 수 있어야 하며 컴퓨터 학습 서비스를 Office 365 Microsoft Defender에 도달해야 합니다. 어떤 종류의 네트워크 `*.blob.core.windows.net` 검사에서URL을 제외하지 마십시오. 

아래 표에는 서비스 및 관련 URL이 나열되어 있습니다. 이러한 URL에 대한 액세스를 거부하는 방화벽 또는 네트워크 필터링 규칙이 없거나 URL 을 제외한 방화벽에 대한 허용 규칙을 만들어야 할 수 `*.blob.core.windows.net` 있습니다. 아래 언급 URL은 통신을 위해 포트 443을 사용하고 있습니다.


| **서비스**| **설명** |**URL** |
| :--: | :-- | :-- |
| Microsoft 활성 보호 서비스 Microsoft Defender 바이러스 백신 클라우드 제공 보호 서비스(MAPS)라고도 합니다.|Microsoft Defender 바이러스 백신 사용하여 클라우드 전달 보호 기능을 제공합니다.|`*.wdcp.microsoft.com` <br/> `*.wdcpalt.microsoft.com` <br/> `*.wd.microsoft.com`|
| 마이크로소프트 업데이트 서비스 (MU) <br/> Windows 업데이트 서비스(WU)|  보안 인텔리전스 및 제품 업데이트   |`*.update.microsoft.com` <br/> `*.delivery.mp.microsoft.com`<br/> `*.windowsupdate.com` <br/><br/> 자세한 내용은 [Windows 업데이트에 대한 연결 끝점을 참조하십시오.](/windows/privacy/manage-windows-1709-endpoints#windows-update)|
|보안 인텔리전스 업데이트 대체 다운로드 위치(ADL)|   설치된 보안 인텔리전스가 오래된 경우 Microsoft Defender 바이러스 백신 보안 인텔리전스 업데이트의 대체 위치(7일 이상 뒤)|    `*.download.microsoft.com`  </br> `*.download.windowsupdate.com`</br>  `go.microsoft.com`</br> `https://fe3cr.delivery.mp.microsoft.com/ClientWebService/client.asmx`|
| 맬웨어 제출 스토리지|제출 양식 또는 자동 샘플 제출을 통해 Microsoft에 제출된 파일의 업로드 위치    | `ussus1eastprod.blob.core.windows.net` <br/>    `ussus2eastprod.blob.core.windows.net` <br/>    `ussus3eastprod.blob.core.windows.net` <br/>    `ussus4eastprod.blob.core.windows.net` <br/>    `wsus1eastprod.blob.core.windows.net` <br/>    `wsus2eastprod.blob.core.windows.net` <br/>    `ussus1westprod.blob.core.windows.net` <br/>    `ussus2westprod.blob.core.windows.net` <br/>    `ussus3westprod.blob.core.windows.net` <br/>    `ussus4westprod.blob.core.windows.net` <br/>    `wsus1westprod.blob.core.windows.net` <br/>    `wsus2westprod.blob.core.windows.net` <br/>    `usseu1northprod.blob.core.windows.net` <br/>    `wseu1northprod.blob.core.windows.net` <br/>    `usseu1westprod.blob.core.windows.net` <br/>    `wseu1westprod.blob.core.windows.net` <br/>    `ussuk1southprod.blob.core.windows.net` <br/>    `wsuk1southprod.blob.core.windows.net` <br/>    `ussuk1westprod.blob.core.windows.net` <br/>    `wsuk1westprod.blob.core.windows.net` |
| 인증서 해지 목록(CRL)|CRL 을 업데이트하기 위해 MAPS에 SSL 연결을 만들 때 Windows 사용   | `http://www.microsoft.com/pkiops/crl/` <br/> `http://www.microsoft.com/pkiops/certs` <br/>   `http://crl.microsoft.com/pki/crl/products` <br/> `http://www.microsoft.com/pki/certs` |
| 심볼 스토어|Microsoft Defender 바이러스 백신 사용하여 수정 흐름 중에 특정 중요한 파일을 복원하는 데 사용됩니다.  | `https://msdl.microsoft.com/download/symbols` |
| 범용 원격 분석 클라이언트| Windows 클라이언트 진단 데이터를 전송하는 데 사용; Microsoft Defender 바이러스 백신 제품 품질 모니터링을 위해 원격 분석을 사용합니다.   | 이 업데이트는 SSL(TCP 포트 443)을 사용하여 매니페스트를 다운로드하고 진단 데이터를 Microsoft에 업로드합니다.   `vortex-win.data.microsoft.com` <br/>   `settings-win.data.microsoft.com`|

## <a name="validate-connections-between-your-network-and-the-cloud"></a>네트워크와 클라우드 간의 연결 유효성 검사

위에 나열된 URL을 허용한 후 Microsoft Defender 바이러스 백신 클라우드 서비스에 연결되어 있고 정보를 올바르게 보고하고 수신하여 완전히 보호되는지 테스트할 수 있습니다.

**cmdline 도구를 사용하여 클라우드 제공 보호의 유효성을 검사합니다.**

Microsoft Defender 바이러스 백신 명령줄 유틸리티()와 다음 인수를 사용하여 `mpcmdrun.exe` 네트워크가 Microsoft Defender 바이러스 백신 클라우드 서비스와 통신할 수 있는지 확인합니다.

```console
"%ProgramFiles%\Windows Defender\MpCmdRun.exe" -ValidateMapsConnection
```

> [!NOTE]
> 명령 프롬프트의 관리자 수준 버전을 열어야 합니다. 시작 메뉴에서 항목을 마우스 오른쪽 **단추로** 클릭하고 관리자로 실행을 클릭하고 사용 권한 프롬프트에서 **예를** 클릭합니다. 이 명령은 Windows 10 버전 1703 이상에서만 작동합니다.

자세한 내용은 [mpcmdrun.exe 명령줄 도구를 사용하여 Microsoft Defender 바이러스 백신 관리를](command-line-arguments-microsoft-defender-antivirus.md)참조하십시오.

**Microsoft에서 가짜 악성 코드 파일을 다운로드하려고 시도합니다.**

클라우드에 제대로 연결되어 있는 경우 Microsoft Defender 바이러스 백신 감지하고 차단하는 샘플 파일을 다운로드할 수 있습니다.

를 방문하여 파일을 [https://aka.ms/ioavtest](https://aka.ms/ioavtest) 다운로드합니다.

> [!NOTE]
> 이 파일은 실제 맬웨어가 아닙니다. 클라우드에 제대로 연결되어 있는지 테스트하도록 설계된 가짜 파일입니다.

제대로 연결되어 있으면 알림 Microsoft Defender 바이러스 백신 경고가 표시됩니다.

Microsoft Edge 사용하는 경우 알림 메시지도 표시됩니다.

![Microsoft Edge 사용자에게 맬웨어가 발견되었다는 사실을 알려줍니다.](images/defender/wdav-bafs-edge.png)

Internet Explorer를 사용하는 경우 비슷한 메시지가 발생합니다.

![Microsoft Defender 바이러스 백신 사용자에게 맬웨어가 발견되었다는 알림](images/defender/wdav-bafs-ie.png)

또한 Windows 보안 앱의 **스캔 기록** 섹션에서 **격리된 위협** 아래에서 탐지가 표시됩니다.

1. 작업 표시줄의 쉴드 아이콘을 클릭하거나 보안에 대한 시작 메뉴를 검색하여 Windows 보안 앱을 **엽니다.**

2. **위협 보호 & 바이러스를** 선택한 다음 보호 기록을 **선택합니다.**

3. **격리된 위협** 섹션에서 **전체 기록 보기를** 선택하여 검색된 가짜 맬웨어를 확인합니다.

   > [!NOTE]
   > 버전 1703 전에 Windows 10 버전은 다른 사용자 인터페이스를 가지고 있습니다. [Windows 보안 앱에서 Microsoft Defender 바이러스 백신](microsoft-defender-security-center-antivirus.md)참조하십시오.

   Windows 이벤트 로그는 [클라이언트 이벤트 ID 1116 Windows Defender](troubleshoot-microsoft-defender-antivirus.md)표시됩니다.

## <a name="related-articles"></a>관련 문서

- [Windows 10의 Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-in-windows-10.md)

- [클라우드 제공 보호 사용](enable-cloud-protection-microsoft-defender-antivirus.md)

- [명령줄 인수](command-line-arguments-microsoft-defender-antivirus.md)

- [Microsoft 활성 보호 서비스 끝점에 대한 중요한 변경 사항](https://techcommunity.microsoft.com/t5/Configuration-Manager-Archive/Important-changes-to-Microsoft-Active-Protection-Service-MAPS/ba-p/274006)
