---
title: 끝점 계획 1에 대한 Microsoft Defender 설정 및 구성(미리 보기)
description: 끝점 계획 1에 대한 Defender를 설정하고 구성하는 방법을 알아보습니다. 요구 사항을 검토하고, 롤아웃을 계획하고, 환경을 설정할 수 있습니다.
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: ITPro
ms.topic: overview
ms.date: 10/01/2021
ms.prod: m365-security
ms.technology: mdep1
ms.localizationpriority: medium
ms.reviewer: inbadian
f1.keywords: NOCSH
ms.collection: M365-security-compliance
ms.openlocfilehash: ceda29b0e4ad17cfd9a6d9ad43a42f0ee31323ea
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60205330"
---
# <a name="set-up-and-configure-microsoft-defender-for-endpoint-plan-1-preview"></a>끝점 계획 1에 대한 Microsoft Defender 설정 및 구성(미리 보기)

> [!TIP]
> If you have Microsoft 365 E3 or A3 but not Microsoft 365 E5 or A5, visit [https://aka.ms/mdep1trial](https://aka.ms/mdep1trial) to sign up for the preview program!

이 문서에서는 끝점 계획 1(미리 보기)에 대한 Defender를 설정하고 구성하는 방법을 설명합니다. 지원이 있는 경우 또는 직접 수행하고 있는 경우 이 문서를 배포 전반에 대한 가이드로 사용할 수 있습니다.  

## <a name="the-setup-and-configuration-process"></a>설치 및 구성 프로세스

:::image type="content" source="images/mde-p1-deploymentflow.png" alt-text="끝점 계획 1용 Microsoft Defender의 설치 및 배포 흐름":::

Endpoint Plan 1(미리 보기)에 대한 일반적인 설치 및 구성 프로세스는 다음과 같습니다. <br/><br/>


| 숫자  | 단계  | 설명  |
|:---------:|:---------|:---------|
| 1 | [요구 사항 검토](#review-the-requirements)  | 라이선스, 브라우저, 운영 체제 및 데이터 센터 요구 사항 나열   |
| 2 | [배포 계획](#plan-your-deployment) | 고려할 여러 배포 방법을 나열하고 사용할 방법을 결정하는 데 도움이 되는 추가 리소스에 대한 링크를 포함합니다.  |
| 3  | [테넌트 환경 설정](#set-up-your-tenant-environment) | 테넌트 환경 설정에 대한 작업 나열 |
| 4  | [역할 및 사용 권한 할당](#assign-roles-and-permissions) | 보안 팀에 대해 고려할 역할 및 사용 권한 나열 <br/><br/>**팁:** 역할 및 사용 권한이 할당되는 즉시 보안 팀이 보안 포털을 사용하여 시작할 Microsoft 365 Defender 있습니다. 자세한 내용은 [시작을 참조합니다.](mde-plan1-getting-started.md) |
| 5 | [끝점용 Defender에 온보딩](#onboard-to-defender-for-endpoint) | Endpoint Plan 1용 Defender에 온보딩할 운영 체제의 여러 방법을 나열하고 각 방법에 대한 자세한 정보에 대한 링크를 포함합니다.  |
| 6  | [차세대 보호 구성](#configure-next-generation-protection) | 2013에서 차세대 보호 설정을 구성하는 Microsoft Endpoint Manager  |
| 7  | [공격 표면 감소 기능 구성](#configure-your-attack-surface-reduction-capabilities)        | 구성할 수 있는 공격 표면 감소 기능 유형을 나열하고 추가 리소스에 대한 링크가 포함된 절차를 포함합니다.  |

> [!IMPORTANT]
> 이 문서의 일부 정보는 상업적으로 출시되기 전에 상당수 수정될 수 있는 미리 시판된 제품/서비스와 관련이 있습니다. Microsoft는 여기에 제공된 정보에 대해 표현적 또는 암시적 보증을하지 않습니다. 이 문서에는 Defender for Endpoint Plan 1(미리 보기)에 포함되지 않은 일부 기능을 설명할 수 있는 온라인 콘텐츠에 대한 링크가 포함되어 있습니다.
 
## <a name="review-the-requirements"></a>요구 사항 검토

다음 표에는 Endpoint Plan 1(미리 보기)에 대한 기본 요구 사항이 나열됩니다.<br/><br/>

| 요구 사항 | 설명 |
|:---|:---|
| 라이선스 요구사항 | 엔드포인드용 Defender 플랜 1(미리 보기) <br/><br/>*If you have Microsoft 365 E3 or A3, you can join the preview program.* |
| 브라우저 요구 사항 | Microsoft Edge <br/> Internet Explorer 버전 11 <br/> Google Chrome |
| 운영 체제 | Windows 10 버전 1709 이상 <br/>macOS: 11.5(큰 수르), 10.15.7(카탈로니아) 또는 10.14.6(모자베) <br/>iOS <br/>Android OS  |
| Datacenter | 다음 데이터 센터 위치 중 하나: <br/>- 유럽 연합 <br/>- 영국 <br/>- 미국 |


## <a name="plan-your-deployment"></a>배포 계획

배포를 계획할 때 여러 가지 아키텍처 및 배포 방법 중 선택할 수 있습니다. 조직마다 고유하기 때문에 다음 표에 나와 있는 몇 가지 옵션을 고려해야 합니다. <br/><br/>

| 방법 | 설명 |
|:---|:---|
| [Microsoft Intune(Microsoft Endpoint Manager)](/mem/intune/fundamentals/what-is-intune) | Intune을 사용하여 클라우드 기본 환경에서 끝점 관리 |
| [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) [및 Configuration Manager(Microsoft Endpoint Manager)](/mem/configmgr/core/understand/introduction) | Intune 및 Configuration Manager를 사용하여 사내 및 클라우드 환경에 걸쳐 있는 끝점 및 워크로드 관리 |
| [Configuration Manager](/mem/configmgr/core/understand/introduction) | Configuration Manager를 사용하여 끝점용 Defender의 클라우드 기반 기능으로 사내 끝점 보호 |
| 사이트 포털에서 다운로드한 Microsoft 365 Defender 스크립트 | 끝점에서 로컬 스크립트를 사용하여 파일럿을 실행하거나 몇 대의 장치만 온보딩 |

배포 옵션에 대한 자세한 내용은 [Plan your Defender for Endpoint deployment을 참조하세요.](deployment-strategy.md) 그리고 다음 포스터를 다운로드합니다. 

[:::image type="content" source="../../media/defender-endpoint/mde-deployment-strategy.png" alt-text="배포 전략 포스터 축소판 그림":::](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.pdf)

**[배포 포스터를 받을 수 있습니다.](https://download.microsoft.com/download/5/6/0/5609001f-b8ae-412f-89eb-643976f6b79c/mde-deployment-strategy.pdf)**

> [!TIP]
> 배포 계획에 대한 자세한 내용은 [Plan your Microsoft Defender for Endpoint deployment을 참조하세요.](deployment-strategy.md)

## <a name="set-up-your-tenant-environment"></a>테넌트 환경 설정

테넌트 환경 설정에는 다음과 같은 작업이 포함됩니다.

- 라이선스 확인
- 테넌트 구성
- 프록시 설정 구성(필요한 경우만 해당)
- 센서가 올바르게 작동하고 끝점용 Defender에 데이터를 보고하는지 확인 

이러한 작업은 Endpoint용 Defender의 설정 단계에 포함됩니다. [끝점에 대한 Defender 설정 을 참조합니다.](production-deployment.md)

## <a name="assign-roles-and-permissions"></a>역할 및 사용 권한 할당

Microsoft 365 Defender 포털에 액세스하거나 끝점에 대한 Defender 설정을 구성하거나 감지된 위협에 대한 대응 조치를 취하는 등의 작업을 수행하려면 적절한 사용 권한을 할당해야 합니다. Endpoint용 Defender는 에서 기본 제공 [역할을 Azure Active Directory.](/azure/active-directory/roles/permissions-reference) 

사용자에게 작업을 수행하는 데 필요한 권한 수준만 할당하는 것이 좋습니다. 기본 사용 권한 관리 또는 RBAC(역할 [](rbac.md) 기반 액세스 제어)를 사용하여 권한을 할당할 수 있습니다. 

- 기본 사용 권한 관리를 통해 전역 관리자와 보안 관리자는 모든 권한을 가지지만 보안 읽기 전용 권한자입니다.
- RBAC를 사용하면 더 많은 역할을 통해 보다 세부적인 사용 권한을 설정할 수 있습니다. 예를 들어 보안 읽기 권한자, 보안 운영자, 보안 관리자, 끝점 관리자 등을 사용할 수 있습니다.


다음 표에서는 조직의 Endpoint용 Defender에 대해 고려해야 하는 주요 역할에 대해 설명하고 있습니다. <br/><br/>

| 역할 | 설명 |
|:---|:---|
| 전역 관리자(전역 관리자라고도 지칭) <br/><br/> *최상의 방법은 전역 관리자 수를 제한하는 것입니다.* | 전역 관리자는 모든 종류의 작업을 수행할 수 있습니다. Microsoft Defender for Endpoint Microsoft 365 또는 Microsoft Defender for Endpoint Plan 1에 회사에 등록한 사람은 기본적으로 전역 관리자입니다. <br/><br/> 전역 관리자는 모든 웹 사이트 포털에서 설정에 액세스하여 Microsoft 365 수 있습니다. <br/>- Microsoft 365 관리 센터( [https://admin.microsoft.com](https://admin.microsoft.com) ) <br/>- Microsoft 365 Defender 포털( [https://security.microsoft.com](https://security.microsoft.com) ) <br/>- Microsoft Endpoint Manager 관리 센터( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) )  |
| 보안 관리자(보안 관리자라고도 지칭) | 보안 관리자는 보안 운영자 작업과 다음 작업을 수행할 수 있습니다. <br/>- 보안 관련 정책 모니터링 <br/>- 보안 위협 및 경고 관리 <br/>- 보고서 보기 |
| 보안 운영자 | 보안 운영자는 보안 읽기 작업과 다음 작업을 수행할 수 있습니다. <br/>- 감지된 위협에 대한 정보 보기 <br/>- 감지된 위협 조사 및 대응  |
| 보안 읽기 권한자 | 보안 읽기는 다음 작업을 수행할 수 있습니다. <br/>- 여러 서비스에서 보안 관련 Microsoft 365 보기 <br/>- 보안 위협 및 경고 보기 <br/>- 보고서 보기  |


> [!TIP]
> Azure Active Directory 역할에 대한 자세한 내용은 다음을 통해 사용자에게 관리자 및 비 관리자 역할 [할당을 Azure Active Directory.](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal) 또한 끝점용 Defender의 역할에 대한 자세한 내용은 역할 기반 [액세스 제어를 참조하세요.](prepare-deployment.md#role-based-access-control)

## <a name="onboard-to-defender-for-endpoint"></a>끝점용 Defender에 온보딩

조직의 끝점을 온보드할 준비가 된 경우 다음 표에 나열된 여러 가지 방법 중 선택할 수 있습니다. <br/><br/>

|끝점 운영 체제 | 온보더링 방법|
|---|---|
| Windows 10 | [로컬 스크립트(최대 10대의 장치)](configure-endpoints-script.md) <br>  [그룹 정책](configure-endpoints-gp.md) <br>  [Microsoft Endpoint Manager/ 모바일 장치 관리자](configure-endpoints-mdm.md) <br> [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) <br> [VDI 스크립트](configure-endpoints-vdi.md)  |
| macOS | [로컬 스크립트](mac-install-manually.md) <br> [Microsoft Endpoint Manager ](mac-install-with-intune.md) <br> [JAMF Pro](mac-install-with-jamf.md) <br> [모바일 장치 관리](mac-install-with-other-mdm.md) |
| iOS |[앱 기반](ios-install.md) |
| Android | [Microsoft Endpoint Manager ](android-intune.md) |

그런 다음 차세대 보호 및 공격 표면 축소 기능을 구성합니다.

## <a name="configure-next-generation-protection"></a>차세대 보호 구성

다음 이미지와 [Microsoft Endpoint Manager](/mem) 사용하여 조직의 장치 및 보안 설정을 관리하는 것이 좋습니다.
 
:::image type="content" source="../../media/mde-p1/endpoint-policies.png" alt-text="MEM의 끝점 보안 정책":::

2016에서 차세대 보호를 Microsoft Endpoint Manager 다음 단계를 따르세요.

1. Microsoft Endpoint Manager 관리 센터()로 이동하여 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 로그인합니다.

2. **끝점 보안 바이러스 백신** 을 선택한 다음 기존 정책을  >  선택합니다. 기존 정책이 없는 경우 새 정책을 만들어야 합니다.

3. 바이러스 백신 구성 설정을 설정하거나 변경합니다. 도움이 필요하신가요? 다음 리소스를 참조합니다. <br/>

   - [설정 Windows 10 Microsoft Defender 바이러스 백신 정책에 대한 Microsoft Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-windows)
   - [iOS 기능에서 끝점에 대한 Defender 구성](ios-configure-features.md)

4. 설정 지정이 끝나면 검토 + 저장 **을 선택합니다.**

## <a name="configure-your-attack-surface-reduction-capabilities"></a>공격 표면 감소 기능 구성

공격 표면 감소는 조직이 공격에 열려 있는 장소와 방법을 줄이는 것입니다. Defender for Endpoint Plan 1(미리 보기)에는 끝점 전체에서 공격 표면을 줄이는 데 도움이 되는 몇 가지 기능이 포함되어 있습니다. 다음 표에는 이러한 기능이 나와 있습니다. <br/><br/>

| 기능 | 설명 |
|:---|:---|
| [공격 표면 감소 규칙](#attack-surface-reduction-rules) | 공격 표면 감소 규칙을 구성하여 소프트웨어 기반의 위험한 동작을 제한하고 조직을 안전하게 유지할 수 있습니다. 공격 표면 감소 규칙은 다음과 같은 특정 소프트웨어 동작을 대상으로 합니다.<br/>- 파일 다운로드 또는 실행을 시도하는 실행 파일 및 스크립트 실행 <br/>- 난동 또는 기타 의심스러운 스크립트 실행 <br/>- 앱이 일반적인 일과의 작업 중에 일반적으로 시작되지 않는 동작 수행 <br/><br/>이러한 소프트웨어 동작은 경우에 따라 합법적인 응용 프로그램에서 볼 수 있습니다. 그러나 이러한 동작은 일반적으로 맬웨어를 통해 공격자에 의해 악용되는 위험한 동작으로 간주됩니다.  |
| [랜섬웨어 완화](#ransomware-mitigation) | 제어된 폴더 액세스를 구성하여 랜섬웨어 완화를 설정하면 랜섬웨어와 같은 악성 앱 및 위협으로부터 조직의 중요한 데이터를 보호할 수 있습니다. | 
| [장치 제어](#device-control) | 이동식 장치(예: USB 드라이브)를 허용하거나 차단하도록 조직의 장치 제어 설정을 구성합니다. | 
| [네트워크 보호](#network-protection) | 조직의 사용자가 인터넷에서 위험한 도메인 또는 악의적인 콘텐츠에 액세스하는 응용 프로그램을 사용하지 못하게 하는 네트워크 보호를 설정하세요. |
| [웹 보호](#web-protection) | 웹 위협 방지를 설정하여 피싱 사이트, 악용 사이트 및 기타 신뢰도 수준이 낮은 사이트로부터 조직의 장치를 보호합니다. 웹 콘텐츠 필터링을 설정하여 콘텐츠 범주(예: 분할, 높은 대역폭, 성인 콘텐츠 또는 법적 책임)에 따라 웹 사이트에 대한 액세스를 추적하고 규제합니다. |
| [네트워크 방화벽](#network-firewall) | 조직 장치에서 들어오거나 나가도록 허용되는 네트워크 트래픽을 결정하는 규칙을 사용하여 네트워크 방화벽을 구성합니다. |
| [응용 프로그램 제어](#application-control)  | 신뢰할 수 있는 응용 프로그램 및 프로세스만 해당 장치에서 실행하도록 허용하려는 경우 응용 프로그램 제어 Windows 구성합니다.    |

### <a name="attack-surface-reduction-rules"></a>공격 노출 영역 축소 규칙

공격 표면 감소 규칙은 공격 표면 감소 규칙을 실행하는 장치에서 사용할 Windows. 다음 이미지와 Microsoft Endpoint Manager 를 사용하는 것이 좋습니다.

:::image type="content" source="../../media/mde-p1/mem-asrpolicies.png" alt-text="공격 표면 감소 규칙 Microsoft Endpoint Manager":::

1. Microsoft Endpoint Manager 관리 센터()로 이동하여 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 로그인합니다.

2. 끝점 **보안 공격 표면**  >  **감소**+ 정책  >  **만들기 를 선택 합니다.**

3. **플랫폼에서** 에 대해 Windows 10 **이상을 선택합니다.**

4. 프로필에서 공격 **표면 감소 규칙을 선택한** 다음 만들기 를 **선택합니다.** 

5. 기본 **탭에서** 정책의 이름과 설명을 지정하고 다음 을 **선택합니다.**

6. 구성 **설정 탭에서** 공격 **표면 감소 규칙을 확장합니다.**

7. 각 규칙에 대한 설정을 지정하고 다음 을 **선택합니다.** 각 규칙의 작동에 대한 자세한 내용은 공격 표면 감소 [규칙을 참조하세요.](attack-surface-reduction.md) 

8. 범위 **태그 탭에서** 조직에서 범위 태그를 사용하는 경우 **+** 범위 태그 선택을 선택한 다음 사용할 태그를 선택합니다. 그런 다음 다음 **을 선택.** 
   
   범위 태그에 대한 자세한 내용은 [분산 IT에 RBAC(역할](/mem/intune/fundamentals/scope-tags)기반 액세스 제어) 및 범위 태그 사용을 참조합니다.

9. 할당 **탭에서** 정책을 적용할 사용자 및 그룹을 지정하고 다음 을 **선택합니다.** 할당에 대한 자세한 내용은 에서 사용자 및 장치 프로필 [할당을 Microsoft Intune.](/mem/intune/configuration/device-profile-assign)

10. 검토 **+ 만들기 탭에서** 설정을 검토한 다음 만들기 를 **선택합니다.**

> [!TIP]
> 공격 표면 감소 규칙에 대한 자세한 내용은 다음 리소스를 참조합니다.
> - [공격 표면 감소 규칙을 사용하여 맬웨어 감염 방지](attack-surface-reduction.md)
> - [공격 표면 감소 규칙 목록 보기](attack-surface-reduction-rules.md)
> - [공격 표면 감소 규칙 사용자 지정](customize-attack-surface-reduction.md)

### <a name="ransomware-mitigation"></a>랜섬웨어 완화

제어된 폴더 액세스를 통해 랜섬웨어 완화를 통해 신뢰할 수 있는 앱만 끝점의 보호된 폴더에 액세스할 수 있습니다. [](controlled-folders.md#what-is-controlled-folder-access) 

제어된 폴더 Microsoft Endpoint Manager 구성하는 것이 좋습니다.

:::image type="content" source="../../media/mde-p1/mem-asrpolicies.png" alt-text="Microsoft Endpoint Manager":::

1. Microsoft Endpoint Manager 관리 센터()로 이동하여 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 로그인합니다. 

2. **끝점 보안 을 선택한** 다음 공격 **표면 감소 를 선택합니다.**

3. **+ 정책 만들기 를 선택 합니다.** 

4. **플랫폼의** 경우 Windows 10 **이상을** 선택하고 **프로필에** 대해 공격 표면 감소 규칙을 **선택합니다.** 그런 다음 만들기 **를 선택.** 

5. 기본 **탭에서** 정책 이름을 지정하고 설명을 추가합니다. **다음** 을 선택합니다. 

6. 구성 **설정 탭의** 공격 **표면** 감소 규칙 섹션에서 아래쪽으로 스크롤합니다. 폴더 보호 **사용 드롭다운에서** 사용 을 **선택합니다.** 선택적으로 이러한 다른 설정을 지정할 수 있습니다.

   - 보호해야 하는 추가 폴더 목록 옆의 드롭다운 메뉴를 선택한 다음 보호해야 하는 폴더를 추가합니다.
   - 보호된 폴더에 액세스할 수 있는 앱 목록 옆의 드롭다운 메뉴를 선택한 다음 보호된 폴더에 액세스할 수 있는 앱을 추가합니다.
   - 공격 **표면** 축소 규칙에서 파일 및 경로 제외 옆에 있는 드롭다운 메뉴를 선택한 다음 공격 표면 감소 규칙에서 제외해야 하는 파일 및 경로를 추가합니다.

   그런 후 **다음** 을 선택합니다.

7. 범위 **태그 탭에서** 조직에서 범위 태그를 사용하는 경우 **+** 범위 태그 선택을 선택한 다음 사용할 태그를 선택합니다. 그런 다음 다음 **을 선택.** 
   
   범위 태그에 대한 자세한 내용은 [분산 IT에 RBAC(역할](/mem/intune/fundamentals/scope-tags)기반 액세스 제어) 및 범위 태그 사용을 참조합니다.

8. 할당 **탭에서** 모든  사용자 추가 및 + 모든 장치 **추가를** 선택하고 다음 을 **선택합니다.** (또는 특정 사용자 또는 장치 그룹을 지정할 수 있습니다.)

9. 검토 **+ 만들기 탭에서** 정책의 설정을 검토한 다음 만들기 를 **선택합니다.** 정책은 곧 끝점용 Defender에 온보딩된 모든 끝점에 적용됩니다.

### <a name="device-control"></a>디바이스 컨트롤

이동식 장치에서 이동식 장치 및 파일을 차단하거나 허용하도록 끝점에 대한 Defender를 구성할 수 있습니다. 디바이스 제어 Microsoft Endpoint Manager 구성하는 것이 좋습니다.

:::image type="content" source="../../media/mde-p1/mem-admintemplates.png" alt-text="Microsoft Endpoint Manager 서식 파일 관리":::

1. Microsoft Endpoint Manager 관리 센터()로 이동하여 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 로그인합니다. 

2. 장치 **구성**  >  **프로필 프로필**  >  **만들기를 선택합니다.**

3. **플랫폼의** 경우 Windows 10 이상을 선택하고 프로필 유형 **에** **대해** 템플릿 **을 선택합니다.** 

   템플릿 **이름에서** 관리 템플릿 **을** 선택한 다음 만들기 를 **선택합니다.** 

4. 기본 **탭에서** 정책 이름을 지정하고 설명을 추가합니다. **다음** 을 선택합니다. 

5. 구성 **설정 탭에서** 모든 설정을 **설정.** 그런 다음 검색 상자에 이동식 장치와 연결된 모든 설정을 `Removable` 표시하려면 을 입력합니다.

6. 목록에서 모든 이동식 Storage **클래스:** 모든 액세스 거부 등 목록에서 항목을 선택하여 플라이아웃 창을 열 수 있습니다. 각 설정에 대한 플라이아웃은 설정, 비활성화 또는 구성되지 않은 경우 발생하는 일에 대해 설명합니다. 설정을 선택한 다음 확인 을 **선택합니다.** 

7. 구성할 각 설정에 대해 6단계를 반복합니다. 그런 후 **다음** 을 선택합니다.

8. 범위 **태그 탭에서** 조직에서 범위 태그를 사용하는 경우 **+** 범위 태그 선택을 선택한 다음 사용할 태그를 선택합니다. 그런 다음 다음 **을 선택.** 
   
   범위 태그에 대한 자세한 내용은 [분산 IT에 RBAC(역할](/mem/intune/fundamentals/scope-tags)기반 액세스 제어) 및 범위 태그 사용을 참조합니다.

9. 할당 **탭에서** 모든  사용자 추가 및 + 모든 장치 **추가를** 선택하고 다음 을 **선택합니다.** (또는 특정 사용자 또는 장치 그룹을 지정할 수 있습니다.)

10. 검토 **+ 만들기 탭에서** 정책의 설정을 검토한 다음 만들기 를 **선택합니다.** 정책은 곧 끝점용 Defender에 온보딩된 모든 끝점에 적용됩니다.

> [!TIP]
> 자세한 내용은 [Endpoint용 Microsoft Defender를](control-usb-devices-using-intune.md)사용하여 USB 장치 및 기타 이동식 미디어를 제어하는 방법을 참조하세요.

### <a name="network-protection"></a>네트워크 보호

네트워크 보호 기능을 사용하면 인터넷에서 피싱 사기, 악용 및 기타 악성 콘텐츠를 호스팅할 수 있는 위험한 도메인으로부터 조직을 보호할 수 있습니다. 네트워크 보호를 켜기 위해 Microsoft Endpoint Manager 사용하는 것이 좋습니다.

:::image type="content" source="../../media/mde-p1/mem-endpointprotectionprofile.png" alt-text="Microsoft Endpoint Manager":::

1. Microsoft Endpoint Manager 관리 센터()로 이동하여 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 로그인합니다. 

2. 장치 **구성**  >  **프로필 프로필**  >  **만들기를 선택합니다.**

3. **플랫폼의** 경우 Windows 10 이상을 선택하고 프로필 유형 **에** **대해** 템플릿 **을 선택합니다.** 

   템플릿 **이름에서** **끝점 보호를** 선택한 다음 만들기를 **선택합니다.** 

4. 기본 **탭에서** 정책 이름을 지정하고 설명을 추가합니다. **다음** 을 선택합니다. 

5. 구성 **설정 탭에서** 를 Microsoft Defender Exploit Guard 네트워크 **필터링을 확장합니다.**

   네트워크 **보호를 사용으로** **설정** (감사를 **선택해** 처음에 작업 환경에서 네트워크 보호가 어떻게 작동할지 볼 수 있습니다.)

   그런 후 **다음** 을 선택합니다.

6. 할당 **탭에서** 모든  사용자 추가 및 + 모든 장치 **추가를** 선택하고 다음 을 **선택합니다.** (또는 특정 사용자 또는 장치 그룹을 지정할 수 있습니다.)

7. 적용 **가능성 규칙 탭에서** 규칙을 설정합니다. 구성하는 프로필은 지정한 결합 조건을 충족하는 디바이스에만 적용됩니다. 

   예를 들어 특정 OS 버전만 실행 중인 끝점에 정책을 할당할 수 있습니다.

   그런 후 **다음** 을 선택합니다. 

8. 검토 **+ 만들기 탭에서** 정책의 설정을 검토한 다음 만들기 를 **선택합니다.** 정책은 곧 끝점용 Defender에 온보딩된 모든 끝점에 적용됩니다.

> [!TIP]
> 네트워크 보호를 사용하도록 설정하려면 Windows PowerShell 그룹 정책과 같은 다른 방법을 사용할 수 있습니다. 자세한 내용은 네트워크 보호 [켜기 를 참조합니다.](enable-network-protection.md)

### <a name="web-protection"></a>웹 보호

웹 보호를 사용하면 웹 위협 및 원치 않는 콘텐츠로부터 조직의 장치를 보호할 수 있습니다. 웹 보호에는 [웹 위협 방지](#configure-web-threat-protection) 및 웹 [콘텐츠](#configure-web-content-filtering) 필터링(미리 보기)이 포함됩니다. 두 기능 집합을 모두 구성합니다. 웹 보호 Microsoft Endpoint Manager 구성하는 것이 좋습니다.

#### <a name="configure-web-threat-protection"></a>웹 위협 방지 구성

1. Microsoft Endpoint Manager 관리 센터()로 이동하여 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 로그인합니다.
 
2. 끝점 **보안 공격**  >  **표면 감소를 선택한** 다음 + 정책 만들기 **를 선택 합니다.**

3. 플랫폼(예: Windows 10 **이상)을** 선택하고  웹 보호 프로필을 선택한 다음 만들기를 **선택합니다.** 

4. 기본 **탭에서** 이름과 설명을 지정하고 다음 을 **선택합니다.**

5. 구성 **설정 탭에서** 웹 보호를 **확장하고** 다음 표에 설정을 지정한 후 다음 을 **선택합니다.** <br/><br/>

   | 설정 | 권장 사항 |
   |:---|:---|
   | **네트워크 보호 사용** | 사용으로 **설정합니다.** 사용자가 악성 사이트 또는 도메인을 방문하지 못하게 합니다. <br/><br/>또는 네트워크 보호를 감사  모드로 설정하여 해당 환경에서 네트워크 보호가 어떻게 작동할지 볼 수 있습니다. 감사 모드에서 네트워크 보호는 사용자가 사이트 또는 도메인을 방문하는 것을 차단하지는 않지만 검색을 이벤트로 추적합니다. |
   | **이 기능을 사용하려면 SmartScreen Microsoft Edge 레거시** | 예로 **설정** 잠재적인 피싱 사기 및 악성 소프트웨어로부터 사용자를 보호합니다. |
   | **악의적인 사이트 액세스 차단** | 예로 **설정** 사용자가 잠재적으로 악의적인 사이트에 대한 경고를 무시하지 못하게 합니다. |
   | **미확인 파일 다운로드 차단** | 예로 **설정** 사용자가 경고를 무시하고 미확인 파일을 다운로드하지 못하게 합니다. |

6. 범위 **태그 탭에서** 조직에서 범위 태그를 사용하는 경우 **+** 범위 태그 선택을 선택한 다음 사용할 태그를 선택합니다. 그런 다음 다음 **을 선택.** 
   
   범위 태그에 대한 자세한 내용은 [분산 IT에 RBAC(역할](/mem/intune/fundamentals/scope-tags)기반 액세스 제어) 및 범위 태그 사용을 참조합니다.

7. 할당 **탭에서** 웹 보호 정책을 받을 사용자 및 장치를 지정하고 다음 을 **선택합니다.**

8. 검토 **+ 만들기 탭에서** 정책 설정을 검토한 다음 만들기 를 **선택합니다.**

> [!TIP]
> 웹 위협 방지에 대한 자세한 내용은 웹 위협으로부터 [조직 보호를 참조합니다.](web-threat-protection.md)

#### <a name="configure-web-content-filtering"></a>웹 콘텐츠 필터링 구성

> [!NOTE]
> 웹 콘텐츠 필터링은 현재 미리 보기 상태입니다.

1. Microsoft 365 Defender 포털()로 [https://security.microsoft.com/](https://security.microsoft.com/) 이동하여 로그인합니다.

2. 끝점 **설정**  >  **를 선택 합니다.**

3. 규칙에서 웹 콘텐츠 **필터링 을 선택한** 다음 + 정책 추가 **를 선택 합니다.** 

4. 정책 **추가** 플라이아웃의 일반 **탭에서** 정책의 이름을 지정하고 다음 을 **선택합니다.**

5. 차단된 **범주에서** 차단할 하나 이상의 범주를 선택하고 다음 을 **선택합니다.**

6. 범위 **탭에서** 이 정책을 받을 장치 그룹을 선택하고 다음 을 **선택합니다.**

7. 요약 **탭에서** 정책 설정을 검토한 다음 저장 을 **선택합니다.**

> [!TIP]
> 웹 콘텐츠 필터링 구성에 대한 자세한 내용은 웹 콘텐츠 필터링 [을 참조하세요.](web-content-filtering.md)

### <a name="network-firewall"></a>네트워크 방화벽

네트워크 방화벽은 네트워크 보안 위협의 위험을 줄이는 데 도움이 됩니다. 보안 팀은 조직의 장치로 또는 해당 장치에서 흐르기 위해 허용되는 트래픽을 결정하는 규칙을 설정할 수 있습니다. 네트워크 방화벽을 Microsoft Endpoint Manager 구성하는 것이 좋습니다. 

:::image type="content" source="../../media/mde-p1/mem-firewallpolicy.png" alt-text="Microsoft Endpoint Manager":::

기본 방화벽 설정을 구성하려면 다음 단계를 수행합니다.

1. Microsoft Endpoint Manager 관리 센터()로 이동하여 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 로그인합니다.

2. 끝점 **보안 방화벽**  >  **을** 선택한 다음 **+ 정책 만들기 를 선택 합니다.**

3. Select a platform, such as **Windows 10 and later**, select the Microsoft **Defender Firewall profile,** and then choose **Create**. 

4. 기본 **탭에서** 이름과 설명을 지정하고 다음 을 **선택합니다.**

5. **Microsoft Defender 방화벽을 확장한** 다음 목록 맨 아래로 스크롤합니다.

6. 다음 설정을 각각 예로 **설정하십시오.**

   - **도메인 네트워크에 대해 Microsoft Defender 방화벽 켜기** 
   - **개인 네트워크에 대해 Microsoft Defender 방화벽 켜기**
   - **공용 네트워크에 대해 Microsoft Defender 방화벽 켜기**
   
   각 도메인 네트워크, 개인 네트워크 및 공용 네트워크에서 설정 목록을 검토합니다. 구성되지 않은 으로 설정하거나 조직의 요구에 맞게 변경할 수 있습니다. 

   그런 후 **다음** 을 선택합니다.

7. 범위 **태그 탭에서** 조직에서 범위 태그를 사용하는 경우 **+** 범위 태그 선택을 선택한 다음 사용할 태그를 선택합니다. 그런 다음 다음 **을 선택.** 
   
   범위 태그에 대한 자세한 내용은 [분산 IT에 RBAC(역할](/mem/intune/fundamentals/scope-tags)기반 액세스 제어) 및 범위 태그 사용을 참조합니다.

8. 할당 **탭에서** 모든  사용자 추가 및 + 모든 장치 **추가를** 선택하고 다음 을 **선택합니다.** (또는 특정 사용자 또는 장치 그룹을 지정할 수 있습니다.)

9. 검토 **+ 만들기 탭에서** 정책 설정을 검토한 다음 만들기 를 **선택합니다.**

> [!TIP]
> 방화벽 설정이 자세히 설명된 후 복잡해 보일 수 있습니다. 방화벽을 [구성하기 위한 모범 Windows Defender 참조합니다.](/windows/security/threat-protection/windows-firewall/best-practices-configuring)

### <a name="application-control"></a>응용 프로그램 제어

Windows Defender WDAC(응용 프로그램 제어)는 신뢰할 수 있는 응용 프로그램 및 프로세스만 Windows 끝점을 보호하는 데 도움이 됩니다. 대부분의 조직에서는 WDAC의 단계적 배포를 사용했습니다. 즉, 대부분의 조직에서는 처음에 모든 끝점에서 WDAC를 Windows 않습니다. 실제로 조직의 Windows 끝점이 완전히 관리되고, 약간 관리되는지 또는 "장치 가져오기" 끝점인지에 따라 모든 끝점 또는 일부 끝점에 WDAC를 배포할 수 있습니다.

WDAC 배포 계획을 지원하기 위해 다음 리소스를 참조합니다.

- [Windows용 응용 프로그램 제어](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)

- [Windows Defender 응용 프로그램 제어 정책 디자인 결정](/windows/security/threat-protection/windows-defender-application-control/understand-windows-defender-application-control-policy-design-decisions)

- [Windows Defender 다양한 시나리오에서 응용 프로그램 제어 배포: 장치 유형](/windows/security/threat-protection/windows-defender-application-control/types-of-devices)

## <a name="next-steps"></a>다음 단계

이제 설정 및 구성 프로세스를 거쳤습니다. 다음 단계는 끝점용 Defender 사용을 시작하는 것입니다. 

- [Endpoint Plan 1용 Defender 시작(미리 보기)](mde-plan1-getting-started.md)