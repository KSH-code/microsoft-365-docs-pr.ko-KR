---
title: 인증에 대한 프로토콜 Microsoft Defender 바이러스 백신
description: 프로토콜 인식을 Microsoft Defender 바이러스 백신.
keywords: Microsoft Defender 바이러스 백신, 맬웨어 방지, 보안, defender, 프로토콜 인식
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 05/07/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.collection: m365-security-compliance
ms.openlocfilehash: da8b7c2949e594fc461ca6a8ac65467bb207aae4
ms.sourcegitcommit: 6968594dc8cf8b30a4c958df6d65dfd0cd2cfae1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2021
ms.locfileid: "59489620"
---
# <a name="turn-on-protocol-recognition"></a>프로토콜 인식 켜기 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

이 정책 설정을 통해 알려진 취약성 악용으로부터 네트워크 보호에 대한 프로토콜 인식을 구성할 수 있습니다. 이 설정을 사용하도록 설정하거나 구성하지 않은 경우 프로토콜 인식이 사용하도록 설정됩니다. 이 설정을 사용하지 않도록 설정하면 프로토콜 인식을 사용할 수 없습니다.

## <a name="use-group-policy-to-configure-protocol-recognition"></a>그룹 정책을 사용하여 프로토콜 인식 구성

1. 그룹 정책 관리 끝점에서 그룹 정책 관리 [콘솔 을 니다.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))

2. 컴퓨터 구성 **관리** 템플릿 Windows 네트워크 Microsoft Defender 바이러스 백신  >    >    >    >  **시스템으로 이동하십시오.** 

3. 프로토콜 **인식 을 선택합니다.** 기본적으로 이 정책은 사용하도록 설정됩니다. 구성되지 **않은 것으로 설정된 경우** 정의 사용 중지가 사용하도록 설정됩니다. 

4. 정책을 편집하려면 정책 설정 **편집 링크를** 선택합니다.

5. 사용 **을** 선택한 다음 확인 을 **선택합니다.**

6. 업데이트된 그룹 정책 개체를 배포합니다. 그룹 [정책 관리 콘솔을 참조합니다.](/windows/win32/srvnodes/group-policy)

> [!TIP]
> 그룹 정책 개체를 사용하는지 여부 클라우드에서 번역하는 방법을 참조합니다. 미리 보기에서 그룹 정책 분석을 사용하여 Microsoft Endpoint Manager 그룹 정책 개체를 [분석합니다.](/mem/intune/configuration/group-policy-analytics) 
  
## <a name="related-articles"></a>관련 문서

- [Windows 10의 Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-in-windows-10.md)
 
- [클라우드 제공 보호 사용](enable-cloud-protection-microsoft-defender-antivirus.md)

- [맬웨어 방지 정책을 만들고 배포하는 방법: 클라우드 보호 서비스](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)