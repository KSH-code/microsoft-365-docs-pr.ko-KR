---
title: 모바일 장치에서 모바일 장치를 업데이트하는 방법을 Microsoft Defender 바이러스 백신
description: 랩톱과 같은 모바일 장치를 보호 업데이트로 업데이트하는 Microsoft Defender 바이러스 백신 관리합니다.
keywords: 업데이트, 보호, 업데이트 예약, 배터리, 모바일 장치, 노트북, 노트북, 옵트인, Microsoft 업데이트, wsus, override
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: d00c4a541951ee1c241a52a19b8ec27301b793a1
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59212075"
---
# <a name="manage-updates-for-mobile-devices-and-virtual-machines-vms"></a>모바일 장치 및 VM(가상 머신)에 대한 업데이트 관리

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

모바일 장치 및 VM의 경우 업데이트로 성능에 영향을 끼치지 않도록 더 많은 구성이 필요할 수 있습니다.

이러한 장치에 유용한 두 가지 설정이 있습니다.

- WSUS 연결 없이 모바일 컴퓨터에서 Microsoft 업데이트에 옵트인
- 배터리 전원으로 실행 시 보안 인텔리전스 업데이트 방지

다음 문서도 이러한 상황에서 유용할 수 있습니다.
- [예약된 검사 및 최대 검색 구성](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [최신이 지난 끝점에 대한 업데이트 관리](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [VDI(가상 데스크톱 인프라) 환경에서 Microsoft Defender 바이러스 백신의 배포 가이드](deployment-vdi-microsoft-defender-antivirus.md)

## <a name="opt-in-to-microsoft-update-on-mobile-computers-without-a-wsus-connection"></a>WSUS 연결 없이 모바일 컴퓨터에서 Microsoft 업데이트에 옵트인

Microsoft 업데이트를 사용하여 실행 중인 모바일 Microsoft Defender 바이러스 백신 회사 네트워크에 연결되지 않은 경우 또는 WSUS 연결이 없는 경우 보안 인텔리전스를 최신으로 유지할 수 있습니다.

즉, Microsoft 업데이트를 다시 적용하기 위해 WSUS를 설정한 경우에도 Microsoft 업데이트를 통해 보호 업데이트를 장치로 전달할 수 있습니다.

다음 방법 중 하나를 사용하여 모바일 장치에서 Microsoft 업데이트에 옵트인(opt in)할 수 있습니다.

- 그룹 정책을 사용하여 설정을 변경합니다.
- VBScript를 사용하여 스크립트를 만든 다음 네트워크의 각 컴퓨터에서 실행합니다.
- 사용자 설정 메뉴를 통해 네트워크의 모든 컴퓨터를 **설정** 옵트인합니다.

### <a name="use-group-policy-to-opt-in-to-microsoft-update"></a>그룹 정책을 사용하여 Microsoft 업데이트에 옵트인

1. 그룹 정책 관리 컴퓨터의 [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))그룹 정책 관리 콘솔을 열고 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집 을 **선택합니다.**

2. 그룹 정책 **관리 편집기에서** 컴퓨터 **구성으로 이동하십시오.**

3. 정책을 **선택한** 다음 **관리 템플릿을 선택합니다.**

4. 트리를 확장하여 **서명 Windows 구성** \> **Microsoft Defender 바이러스 백신** \> **확장합니다.**

5. Microsoft 업데이트의 보안 **인텔리전스** 업데이트 허용을 **사용으로** 설정하고 확인 을 **선택합니다.**

### <a name="use-a-vbscript-to-opt-in-to-microsoft-update"></a>VBScript를 사용하여 Microsoft 업데이트에 옵트인

1. MSDN 문서 [Microsoft 업데이트에 옵트인(Opt-In)의](/windows/win32/wua_sdk/opt-in-to-microsoft-update) 지침을 사용하여 VBScript를 만들 수 있습니다.

2. 네트워크의 각 컴퓨터에서 만든 VBScript를 실행합니다.

### <a name="manually-opt-in-to-microsoft-update"></a>Microsoft 업데이트에 수동으로 옵트인

1. **옵트인할**  Windows 컴퓨터의 & 업데이트에서 업데이트 업데이트를 하세요.

2. 고급 **옵션을** 선택합니다.

3. 다른 Microsoft 제품을 업데이트할 때 다른 Microsoft 제품에 대한 업데이트 제공 **확인란을** Windows.

## <a name="prevent-security-intelligence-updates-when-running-on-battery-power"></a>배터리 전원으로 실행 시 보안 인텔리전스 업데이트 방지

PC가 유선 전원에 Microsoft Defender 바이러스 백신 보호 업데이트만 다운로드하도록 구성할 수 있습니다.

### <a name="use-group-policy-to-prevent-security-intelligence-updates-on-battery-power"></a>그룹 정책을 사용하여 배터리 전원의 보안 인텔리전스 업데이트 방지

1. 그룹 정책 관리 컴퓨터의 그룹 정책 관리 콘솔을 [열고](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))구성할 그룹 정책 개체를 선택한 다음 편집할 수 있도록 를 니다.

2. 그룹 정책 **관리 편집기에서** 컴퓨터 **구성으로 이동하십시오.**

3. 정책을 **선택한** 다음 **관리 템플릿을 선택합니다.**

4. 트리를 확장하여 서명 **Windows 구성** Microsoft Defender 바이러스 백신 구성 요소를 확장한 다음 배터리 전원으로 실행 중일 때 보안 인텔리전스 업데이트 허용을 \>  \> 사용 **안 하도록 설정하십시오.**  그런 다음 **확인** 을 선택합니다.

이 작업을 수행하면 PC가 배터리 전원에 있는 경우 보호 업데이트가 다운로드되지 않습니다.

## <a name="related-articles"></a>관련 문서

- [업데이트 Microsoft Defender 바이러스 백신 관리하고 기준 적용](manage-updates-baselines-microsoft-defender-antivirus.md)
- [2016년 Microsoft Defender 바이러스 백신 업데이트 및 Windows 10](deploy-manage-report-microsoft-defender-antivirus.md)