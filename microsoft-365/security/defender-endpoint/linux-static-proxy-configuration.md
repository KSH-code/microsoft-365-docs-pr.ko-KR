---
title: Linux 정적 프록시 검색의 끝점용 Microsoft Defender
ms.reviewer: ''
description: 정적 프록시 검색을 위해 Linux에서 끝점용 Microsoft Defender를 구성하는 방법을 설명 합니다.
keywords: microsoft, defender, atp, linux, 설치, 프록시
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
ms.openlocfilehash: e59727b6bb5fca58595764fc003009891546d8f6
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903849"
---
# <a name="configure-microsoft-defender-for-endpoint-on-linux-for-static-proxy-discovery"></a>정적 프록시 검색을 위해 Linux에서 끝점에 대한 Microsoft Defender 구성

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Microsoft Defender for Endpoint는 환경 변수를 사용하여 프록시 서버를 ```HTTPS_PROXY``` 검색할 수 있습니다. 이 설정은 설치  시와 제품이 설치된 후에 모두 구성해야 합니다.

## <a name="installation-time-configuration"></a>설치 시간 구성

설치하는 동안 ```HTTPS_PROXY``` 환경 변수를 패키지 관리자에게 전달해야 합니다. 패키지 관리자는 다음 방법 중 한 가지 방법으로 이 변수를 읽을 수 있습니다.

- 변수는 ```HTTPS_PROXY``` 다음 ```/etc/environment``` 줄로 정의됩니다.

    ```bash
    HTTPS_PROXY="http://proxy.server:port/"
    ```

- 변수는 패키지 관리자 전역 `HTTPS_PROXY` 구성에 정의되어 있습니다. 예를 들어 Ubuntu 18.04에서 다음 줄을 추가할 수 `/etc/apt/apt.conf.d/proxy.conf` 있습니다.
  
    ```bash
    Acquire::https::Proxy "http://proxy.server:port/";
    ```

    > [!CAUTION]
    > 위의 두 메서드는 시스템의 다른 응용 프로그램에 사용할 프록시를 정의할 수 있습니다. 이 방법은 일반적으로 전역 구성인 경우 또는 주의하여 사용하십시오.
  
- 변수가 설치 또는 제거 명령에 `HTTPS_PROXY` 추가됩니다. 예를 들어 APT 패키지 관리자를 통해 끝점용 Microsoft Defender를 설치할 때 변수를 다음과 같이 추가합니다. 

    ```bash  
    HTTPS_PROXY="http://proxy.server:port/" apt install mdatp
    ```

    > [!NOTE]
    > 환경 변수 정의와 apt 사이에 sudo를 추가하지 말고, 그렇지 않으면 변수가 전파되지 않습니다.

제거 중에 환경 변수도 비슷하게 `HTTPS_PROXY` 정의될 수 있습니다.

프록시가 필요하지만 구성되지 않은 경우 설치 및 제거가 반드시 실패할 필요는 없습니다. 그러나 원격 분석은 제출되지 않습니다. 네트워크 시간 제한으로 인해 작업이 훨씬 오래 걸릴 수 있습니다.

## <a name="post-installation-configuration"></a>설치 후 구성
  
설치 후 `HTTPS_PROXY` 환경 변수는 Endpoint 서비스용 Defender 파일에 정의되어야 합니다. 이렇게 하도록 루트 사용자로 실행 하는 동안 텍스트 `/lib/systemd/system/mdatp.service` 편집기에서 를 여는 합니다. 그런 다음 다음 두 가지 방법 중 하나를 사용하여 변수를 서비스에 전파할 수 있습니다.

- 줄의 줄의 줄을 `#Environment="HTTPS_PROXY=http://address:port"` 지우고 정적 프록시 주소를 지정합니다.

- 선을 `EnvironmentFile=/path/to/env/file` 추가합니다. 이 경로는 다음 줄을 추가해야 하는 사용자 지정 파일 또는 사용자 지정 파일을 `/etc/environment` 지정합니다.
  
    ```bash
    HTTPS_PROXY="http://proxy.server:port/"
    ```

파일을 수정한 `mdatp.service` 후 저장한 후 닫습니다. 변경 내용을 적용할 수 있도록 서비스를 다시 시작합니다. Ubuntu에서 이 명령에는 다음 두 가지 명령이 있습니다.  

```bash
systemctl daemon-reload; systemctl restart mdatp
```
