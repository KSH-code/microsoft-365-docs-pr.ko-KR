---
title: 즉시 차단을 사용하여 몇 초 만에 맬웨어 감지
description: 몇 초 이내에 맬웨어를 감지하고 차단하는 모든 시 차단 기능을 켜세요.
keywords: 검사, BAFS, 맬웨어, 최초, 최초, 클라우드, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: priority
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.date: 10/22/2020
ms.technology: mde
ms.openlocfilehash: 1baa770da677ec755bd56db9b92c071680efae7b
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765758"
---
# <a name="turn-on-block-at-first-sight"></a>첫 번째 차단 켜기

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/) 

차단은 몇 초 이내에 새 맬웨어를 검색하고 차단하는 방법을 제공합니다. 이 보호는 특정 선행 조건 설정을 사용할 때 기본적으로 사용됩니다. 이러한 설정에는 클라우드 제공 보호, 지정된 샘플 제출 시간 제한(예: 50초) 및 높은 파일 차단 수준이 포함됩니다. 대부분의 엔터프라이즈 조직에서 이러한 설정은 기본적으로 Microsoft Defender 바이러스 백신 배포에서 사용하도록 설정됩니다. 

클라우드 기반 [보호](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) 서비스가 파일을 분석하는 동안 파일 실행을 차단할 기간을 지정할 수 있습니다. 또한 파일이 [차단될](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) 때 사용자의 데스크톱에 표시되는 메시지를 사용자 지정할 수 있습니다. 회사 이름, 연락처 정보 및 메시지 URL을 변경할 수 있습니다.

>[!TIP]
>Microsoft Defender for Endpoint 데모 웹 [사이트(demo.wd.microsoft.com)를](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 방문하여 기능이 작동하고 작동 방법을 확인하세요.

## <a name="how-it-works"></a>작동 방식

Microsoft Defender 바이러스 백신이 의심스러우지만 검색되지는 않지만 파일을 발견하면 클라우드 보호 백엔드를 쿼리합니다. 클라우드 백end는 파일에 대한 지론, 기계 학습 및 자동화된 분석을 적용하여 파일이 악성인지 아니면 위협이 아닌지 판단합니다.

Microsoft Defender 바이러스 백신은 여러 감지 및 방지 기술을 사용하여 정확하고 지능적인 실시간 보호를 제공합니다. 자세한 내용은 다음 블로그를 참조하세요. Endpoint 차세대 보호를 위한 Microsoft Defender의 핵심에 있는 고급 기술에 [대해 알아보세요.](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)
![Microsoft Defender AV 엔진 목록](images/microsoft-defender-atp-next-generation-protection-engines.png)  

Windows 10 버전 1803 이상에서 즉석에서 차단은 이식할 수 없는 실행 파일(예: JS, VBS 또는 매크로)과 실행 파일을 차단할 수 있습니다.

즉 차단은 인터넷에서 다운로드되거나 인터넷 영역에서 시작된 실행 파일 및 이식할 수 없는 실행 파일에만 클라우드 보호 백드를 사용 합니다. .exe 파일의 해시 값은 클라우드 백엔드를 통해 확인하여 파일이 이전에는 확인되지 않았다는 파일을 확인하는 것입니다.

클라우드 백디드에서 판단할 수 없는 경우 Microsoft Defender 바이러스 백신은 파일을 잠그고 클라우드에 복사본을 업로드합니다. 클라우드는 추가 분석을 수행하여 파일이 악의적인지 안전한지 여부에 따라 향후 발생할 모든 발생 시 파일을 실행하거나 차단하기 전에 결정에 도달합니다.

대부분의 경우 이 프로세스는 새 맬웨어에 대한 응답 시간을 시간에서 초로 줄일 수 있습니다.

## <a name="turn-on-block-at-first-sight-with-microsoft-intune"></a>Microsoft Intune을 통해 즉시 차단 켜기

> [!TIP]
> Microsoft Intune은 이제 Microsoft Endpoint Manager의 일부입니다.

1. Microsoft Endpoint Manager 관리 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 센터()에서 장치 구성   >  **프로필로 이동합니다.**

2. 장치 제한 프로필 유형을 사용하여 **프로필을 선택하거나** 만들 수 있습니다.

3. 장치 제한 **프로필의** 구성 설정에서 Microsoft Defender 바이러스 백신에서 다음 설정을 **설정하거나 확인합니다.**

   - **클라우드 제공 보호**: 사용
   - **파일 차단 수준**: 높음
   - **클라우드에서 파일 검색을 위한 시간 확장명:** 50
   - **샘플 제출 전에** 사용자에게 확인 : 메시지를 표시하지 않고 모든 데이터 보내기

   ![Intune 구성](images/defender/intune-block-at-first-sight.png)

4. 설정을 저장합니다.

> [!TIP]
> - 파일 차단 수준을 **높음으로** 설정하면 강력한 검색 수준이 적용됩니다. 파일 차단으로 인해 합법적인 파일이 가의 긍정 검색을 발생하게 하는 가능성은 낮지만, 검지된 파일을 복원할 [수 있습니다.](./restore-quarantined-files-microsoft-defender-antivirus.md)
> - Intune에서 Microsoft Defender 바이러스 백신 장치 제한을 구성하는 데 대한 자세한 내용은 Microsoft Intune에서 장치 제한 설정 [구성을 참조하세요.](/intune/device-restrictions-configure)
> - Intune의 Microsoft Defender 바이러스 백신 장치 제한 목록은 [Intune의 Windows 10](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)및 최신 설정에 대한 장치 제한을 참조하세요.

## <a name="turn-on-block-at-first-sight-with-microsoft-endpoint-manager"></a>Microsoft Endpoint Manager를 통해 첫 번째 차단 켜기

> [!TIP]
> Microsoft Endpoint Configuration Manager를 찾고 있는 경우 이제 Microsoft Endpoint Manager의 일부입니다.

1. Microsoft Endpoint Manager( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) 에서 **Endpoint 보안 바이러스 백신으로**  >  **이동 합니다.**

2. 기존 정책을 선택하거나 **Microsoft Defender 바이러스** 백신 프로필 유형을 사용하여 새 정책을 만들 수 있습니다.

3. 다음 구성 설정을 설정하거나 확인합니다.

   - **클라우드 제공 보호 켜기**: 예
   - **클라우드 제공 보호 수준:** 높음
   - **Defender 클라우드 확장 시간 제한(초)**: 50

   :::image type="content" source="images/endpointmgr-antivirus-cloudprotection.png" alt-text="엔드포인트 관리자에서 즉시 설정 차단":::

4. 모든 사용자, 모든 장치 또는 모든 사용자 및 장치와 같은 그룹에 Microsoft Defender 바이러스 백신 **프로필을 적용합니다.**

## <a name="turn-on-block-at-first-sight-with-group-policy"></a>그룹 정책을 통해 첫 번째 차단 켜기

> [!NOTE]
> Intune 또는 Microsoft Endpoint Manager를 사용하여 즉시 차단을 켜는 것이 좋습니다. 

1. 그룹 정책 관리 컴퓨터에서 그룹 정책 관리 콘솔을 [열고](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집을 **선택합니다.** 

2. 그룹 정책 **관리 편집기를 사용하여** **컴퓨터** 구성 관리 템플릿 Windows 구성 요소  >    >    >  **Microsoft Defender 바이러스 백신** MAPS 로  >  **이동하세요.** 

3. MAPS 섹션에서 '즉각적 **차단'** 기능 구성을 두 번 클릭하고 사용으로 **설정한** 다음 확인 을 **선택합니다.**

    > [!IMPORTANT]
    > 항상 **메시지 표시(0)로** 설정하면 장치의 보호 상태가 낮아지게 됩니다. 보내지 **않습니다(2)로** 설정하면 즉시 차단이 작동하지 않습니다.

4. MAPS 섹션에서 추가 분석이 필요한 경우 파일 샘플 보내기 를 두 번 클릭하고 사용으로 **설정합니다.**  추가 **분석이 필요한** 경우 파일 샘플 보내기에서 모든 샘플 보내기 **를** 선택하고 확인을 **클릭합니다.**

5. 설정을 변경한 경우 네트워크 전체에 그룹 정책 개체를 다시 재배포하여 모든 끝점이 적용되도록 합니다.

## <a name="confirm-block-at-first-sight-is-enabled-on-individual-clients"></a>개별 클라이언트에서 최초 차단이 사용하도록 설정되어 있는지 확인

Windows 보안 설정을 사용하여 개별 클라이언트에서 즉시 차단이 사용하도록 설정되어 있는지 확인할 수 있습니다.

클라우드 제공 보호 및 자동  샘플 제출이 모두 켜져 있는 한, 모든 시야 **차단이** 자동으로 활성화됩니다.

1. Windows 보안 앱을 열 수 있습니다.

2. 바이러스 **& 위협** 방지를 선택한 다음 바이러스 & **보호** 설정에서 설정 **관리를 선택합니다.**

   ![Windows 보안 앱의 바이러스 & 보호 설정 레이블 스크린샷](images/defender/wdav-protection-settings-wdsc.png)

3. 클라우드 제공 **보호 및** 자동 샘플 제출이 **모두** 켜져 있는지 확인

> [!NOTE]
> - 그룹 정책을 사용하여 선행 구성 설정이 구성 및 배포된 경우 이 섹션에 설명된 설정은 회색으로 표시됩니다. 개별 끝점에서 사용할 수 없습니다. 
> - 그룹 정책 개체를 통해 변경한 내용은 먼저 개별 끝점에 배포해야 설정이 Windows 설정에서 업데이트됩니다.

## <a name="validate-block-at-first-sight-is-working"></a>모든 시 차단이 작동하고 있는지 확인

기능이 작동하고 있는지 확인을 위해 네트워크와 클라우드 간의 연결 유효성 검사의 지침을 [따르하세요.](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)

## <a name="turn-off-block-at-first-sight"></a>첫 번째 차단 끄기

> [!CAUTION]
> 차단을 끄면 디바이스와 네트워크의 보호 상태가 낮아집니다.

실제로 차단을 사용하지 않고 선행 설정을 유지하려는 경우 모든 시 차단을 사용하지 않도록 선택할 수 있습니다. 대기 시간 문제가 발생하거나 기능이 네트워크에 미치는 영향을 테스트하려는 경우 일시적으로 차단을 해제할 수 있습니다. 그러나 최초 보호를 영구적으로 차단하지 않는 것이 좋습니다.

### <a name="turn-off-block-at-first-sight-with-microsoft-endpoint-manager"></a>Microsoft Endpoint Manager를 통해 중단 시 차단 끄기

1. Microsoft Endpoint Manager 관리 센터()로 이동하여 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 로그인합니다.

2. 끝점 보안 **바이러스 백신으로**  >  **이동한** 다음 Microsoft Defender 바이러스 백신 정책을 선택합니다.

3. 관리에서 속성을 **선택 합니다.** 

4. 구성 설정 **옆에 있는** 편집 **을 선택합니다.**

5. 다음 설정 중 하나 이상을 변경합니다.

   - 클라우드 **제공 보호 켜기 를** **구성** 안 되거나 **구성되지 않습니다.로 설정**
   - 클라우드 **제공 보호 수준을 구성되지** 않은 **으로 설정**
   - **Defender 클라우드 확장 시간 제한(초) 상자의 선택을 취소합니다.**

6. 설정을 검토하고 저장합니다.

### <a name="turn-off-block-at-first-sight-with-group-policy"></a>그룹 정책을 통해 한시 차단 끄기

1. 그룹 정책 관리 컴퓨터에서 그룹 [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))정책 관리 콘솔을 열고 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭한 다음 편집을 **클릭합니다.**

2. 그룹 정책 **관리 편집기를 사용하여** **컴퓨터 구성으로 이동하여** 관리 템플릿 **을 클릭합니다.**

3. Windows 구성 요소 **Microsoft** Defender 바이러스 백신  >  **MAPS를 통해 트리를**  >  **확장합니다.**

4. **'최초 차단'** 기능 구성을 두 번 클릭하고 옵션을 사용 안 **하도록 설정 합니다.**

    > [!NOTE]
    > 차단을 최초로 사용하지 않도록 설정하면 선행 그룹 정책이 비활성화되거나 변경되지 않습니다.

## <a name="see-also"></a>참고 항목

- [Windows 10의 Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-in-windows-10.md)

- [클라우드 제공 보호 사용](enable-cloud-protection-microsoft-defender-antivirus.md)