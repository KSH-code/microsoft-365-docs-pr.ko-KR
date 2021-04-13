---
title: Linux용 Microsoft Defender ATP용 업데이트 배포
ms.reviewer: ''
description: 엔터프라이즈 환경에서 Linux용 Microsoft Defender ATP용 업데이트를 배포하는 방법에 대해 설명
keywords: microsoft, defender, atp, linux, 업데이트, 배포
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 2e4ea4942446317aef90288da9fb181935503fa9
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687469"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-on-linux"></a>Linux에서 끝점용 Microsoft Defender 업데이트 배포

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037) 
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Microsoft는 성능, 보안을 개선하고 새로운 기능을 제공하기 위해 소프트웨어 업데이트를 정기적으로 게시합니다.

> [!WARNING]
> Linux용 끝점용 Defender의 각 버전에는 만료 날짜가 있습니다. 그 이후에는 더 이상 디바이스를 보호하지 않습니다. 이 날짜 이전에 제품을 업데이트해야 합니다. 만료 날짜를 확인하기 위해 다음 명령을 실행합니다.
> ```bash
> mdatp health --field product_expiration
> ```

Linux용 끝점용 Defender를 수동으로 업데이트하려면 다음 명령 중 하나를 실행합니다.

## <a name="rhel-and-variants-centos-and-oracle-linux"></a>RHEL 및 변형(CentOS 및 Oracle Linux)

```bash
sudo yum update mdatp
```

## <a name="sles-and-variants"></a>SLES 및 변형

```bash
sudo zypper update mdatp
```

## <a name="ubuntu-and-debian-systems"></a>Ubuntu 및 데비안 시스템

```bash
sudo apt-get install --only-upgrade mdatp
```
