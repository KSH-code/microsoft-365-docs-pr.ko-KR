---
title: Microsoft Defender 바이러스 백신 클라우드 차단 제한 시간 구성
description: 클라우드 확인을 기다리는 동안 Microsoft Defender 바이러스 백신에서 파일이 실행되지 못하도록 차단하는 기간을 구성할 수 있습니다.
keywords: Microsoft Defender 바이러스 백신, 맬웨어 방지, 보안, defender, 클라우드, 시간 제한, 차단, 기간, 초
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 372d679f45d6f87392b612f757e6bdf1c6c6b9ad
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765806"
---
# <a name="configure-the-cloud-block-timeout-period"></a>클라우드 차단 시간 제한 기간 구성

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/) 

Microsoft Defender 바이러스 백신이 의심스러운 파일을 발견하면 Microsoft Defender 바이러스 백신 클라우드 서비스를 쿼리하는 동안 파일이 실행되지 [않도록 할 수 있습니다.](cloud-protection-microsoft-defender-antivirus.md)

파일이 차단될 기본 기간은 10초입니다. [](configure-block-at-first-sight-microsoft-defender-antivirus.md) 파일을 실행할 수 있도록 허용되기 전에 대기할 시간을 추가로 지정할 수 있습니다. 이를 통해 Microsoft Defender 바이러스 백신 클라우드 서비스에서 적절한 확인을 받을 충분한 시간을 확보할 수 있습니다.

## <a name="prerequisites-to-use-the-extended-cloud-block-timeout"></a>확장된 클라우드 차단 시간 제한을 사용하기 위한 선행 준비

[제한 시간을](configure-block-at-first-sight-microsoft-defender-antivirus.md) 연장하려면 먼저 차단 및 해당 선행 조건이 활성화되어야 합니다.

## <a name="specify-the-extended-timeout-period"></a>연장된 제한 시간 지정

그룹 정책을 사용하여 클라우드 검사에 대한 연장된 시간 제한을 지정할 수 있습니다.

1. 그룹 정책 관리 컴퓨터에서 그룹 [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))정책 관리 콘솔을 열고 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집을 **클릭합니다.**

2. 그룹 정책 **관리 편집기에서** 컴퓨터 **구성으로 이동하여** 관리 템플릿 **을 클릭합니다.**

3. **Microsoft Defender** 바이러스 백신 > Windows 구성 > 확장

4. 확장된 클라우드 확인 구성을 두 **번 클릭하고** 옵션이 사용하도록 설정되어 있는지 확인합니다. 클라우드 확인을 기다리는 동안 파일이 실행되지 않도록 추가 시간을 지정합니다. 추가 시간을 초당 1초에서 50초로 지정할 수 있습니다. 이 시간은 기본값인 10초에 추가됩니다.

5. **확인** 을 클릭합니다.

## <a name="related-topics"></a>관련 항목

- [Windows 10의 Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-in-windows-10.md)
- [클라우드 제공 보호를 통해 차세대 바이러스 백신 기술 사용](cloud-protection-microsoft-defender-antivirus.md)
- [최초 차단 구성](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [클라우드 제공 보호 사용](enable-cloud-protection-microsoft-defender-antivirus.md)