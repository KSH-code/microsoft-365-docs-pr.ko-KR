---
title: Microsoft Defender for Endpoint(iOS용)에 대한 업데이트 배포
ms.reviewer: ''
description: 엔터프라이즈 환경에서 Linux에서 끝점용 Microsoft Defender 업데이트를 배포하는 방법에 대해 설명
keywords: Microsoft, defender, Endpoint용 Microsoft Defender, linux, 업데이트, 배포
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 36783c3f00a38711489e85d60974888a96fff8aa
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60205430"
---
# <a name="deploy-updates-for-microsoft-defender-for-endpoint-on-linux"></a>Microsoft Defender for Endpoint(iOS용)에 대한 업데이트 배포

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

Microsoft는 성능, 보안을 개선하고 새로운 기능을 제공하기 위해 소프트웨어 업데이트를 정기적으로 게시합니다.

> [!WARNING]
> Linux의 각 Endpoint용 Defender 버전에는 만료 날짜가 있습니다. 그 이후에는 더 이상 디바이스를 보호하지 않습니다. 이 날짜 이전에 제품을 업데이트해야 합니다. 만료 날짜를 확인하기 위해 다음 명령을 실행합니다.
> ```bash
> mdatp health --field product_expiration
> ```


일반적으로 사용할 수 있는 끝점용 Microsoft Defender 기능은 배포에 사용되는 업데이트 채널(Beta(Insider), Preview(외부), 현재(프로덕션))에 관계없이 동일합니다.


Linux에서 Endpoint용 Defender를 수동으로 업데이트하려면 다음 명령 중 하나를 실행합니다.

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
