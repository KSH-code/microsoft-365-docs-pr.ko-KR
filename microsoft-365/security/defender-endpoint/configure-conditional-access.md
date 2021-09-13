---
title: 끝점용 Microsoft Defender에서 조건부 액세스 구성
description: 조건부 액세스를 구현하기 위해 Intune, Microsoft 365 Defender Azure에서 수행해야 하는 단계에 대해 자세히 알아보십시오.
keywords: 조건부 액세스, 조건부, 액세스, 장치 위험, 위험 수준, 통합, intune 통합
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 0a0be19a974f7a065333ff0a5045512a2eb98a85
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59222980"
---
# <a name="configure-conditional-access-in-microsoft-defender-for-endpoint"></a>끝점용 Microsoft Defender에서 조건부 액세스 구성

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

이 섹션에서는 조건부 액세스를 올바르게 구현하기 위해 필요한 모든 단계를 안내합니다.

## <a name="before-you-begin"></a>시작하기 전에

> [!WARNING]
> 이 시나리오에서는 Azure AD 등록 장치가 지원되지 않는다는 점에 유의해야 합니다.</br>
> Intune 등록 장치만 지원됩니다.

모든 장치가 Intune에 등록된지 확인해야 합니다. 다음 옵션 중 원하는 옵션을 사용하여 Intune에서 장치를 등록할 수 있습니다.

- IT 관리자: 자동 등록을 사용하도록 설정하는 방법에 대한 자세한 내용은 Windows [등록을 참조하세요.](/intune/windows-enroll#enable-windows-10-automatic-enrollment)
- 최종 사용자: Intune에서 Windows 10 장치를 등록하는 방법에 대한 자세한 내용은 [Intune에서 Windows 10 장치 등록을 참조하세요.](/intune/quickstart-enroll-windows-device)
- 최종 사용자 대체: Azure AD 도메인에 가입하는 방법에 대한 자세한 내용은 방법: Azure AD 조인 구현 계획을 [참조하세요.](/azure/active-directory/devices/azureadjoin-plan)

Intune 포털, Microsoft 365 Defender Azure AD 포털에서 수행해야 하는 단계가 있습니다.

이러한 포털에 액세스하고 조건부 액세스를 구현하는 데 필요한 역할을 주의해야 합니다.

- **Microsoft 365 Defender** - 통합을 설정하려면 전역 관리자 역할로 포털에 로그인해야 합니다.
- **Intune** - 관리 권한이 있는 보안 관리자 권한으로 포털에 로그인해야 합니다.
- **Azure AD 포털** - 전역 관리자, 보안 관리자 또는 조건부 액세스 관리자로 로그인해야 합니다.

> [!NOTE]
> Intune 관리 Microsoft Intune Azure AD가 연결된 장치와 함께 Windows 10 필요합니다.

조건부 액세스를 사용하도록 설정하려면 다음 단계를 수행합니다.

- 1단계: Microsoft Intune 연결 Microsoft 365 Defender
- 2단계: Intune에서 끝점에 대한 Defender 통합 켜기
- 3단계: Intune에서 준수 정책 만들기
- 4단계: 정책 할당 
- 5단계: Azure AD 조건부 액세스 정책 만들기

### <a name="step-1-turn-on-the-microsoft-intune-connection"></a>1단계: 연결 Microsoft Intune 켜기

1. 탐색 창에서 연결 **설정** \> **끝점** 일반 고급 Microsoft Intune \>  \>  \> **선택합니다.**
2. 설정의 Microsoft Intune 으로 **전환합니다.**
3. 기본 **설정 저장을 클릭합니다.**

### <a name="step-2-turn-on-the-defender-for-endpoint-integration-in-intune"></a>2단계: Intune에서 끝점에 대한 Defender 통합 켜기

1. [Azure Portal](https://portal.azure.com)에 로그인합니다.
2. 장치 **준수** \> **Microsoft Defender ATP를 선택합니다.**
3. **커넥트 Windows 10.0.15063+ 장치를 Microsoft Defender Advanced Threat Protection으로** **설정 .**
4. **저장** 을 클릭합니다.

### <a name="step-3-create-the-compliance-policy-in-intune"></a>3단계: Intune에서 준수 정책 만들기

1. Azure [Portal에서](https://portal.azure.com)모든 **서비스를** 선택하고 **Intune을** 필터링하고 를 **Microsoft Intune.**
2. 장치 **준수 정책** \> **정책** 만들기 정책을 \> **선택합니다.**
3. 이름 및 **설명을** **입력합니다.**
4. **플랫폼에서** 를 선택하고 Windows 10 **이상을 선택합니다.**
5. 장치 **상태 설정에서**  장치 위협 수준에 또는 장치 위협 수준 아래에 있도록 요구를 기본 설정 수준으로 설정합니다.

   - **보안 :** 이 수준이 가장 안전합니다. 장치에 기존 위협이 없는 경우 회사 리소스에 계속 액세스할 수 없습니다. 위협이 발견되는 경우 장치는 비호조로 평가됩니다.
   - **낮음:** 낮은 수준의 위협만 존재하는 경우 장치가 규격입니다. 중간 또는 높은 위협 수준이 있는 장치는 규정을 준수하지 않습니다.
   - **보통:** 장치에서 발견되는 위협이 낮거나 중간인 경우 장치가 규격입니다. 높은 수준의 위협이 감지되면 장치가 비준수로 결정됩니다.
   - **높음:** 이 수준은 최소 보안 수준으로, 모든 위협 수준을 허용합니다. 따라서 높은, 중간 또는 낮은 위협 수준이 있는 장치는 규격으로 간주됩니다.

6. 확인 **및** **만들기를 선택하여** 변경 내용을 저장하고 정책을 생성합니다.

### <a name="step-4-assign-the-policy"></a>4단계: 정책 할당

1. Azure [Portal에서](https://portal.azure.com)모든 **서비스를** 선택하고 **Intune을** 필터링하고 를 **Microsoft Intune.**
2. 장치 **준수 정책을>** Microsoft \>  Defender 준수 정책을 선택합니다.
3. **과제** 를 선택합니다.
4. Azure AD 그룹을 포함하거나 제외하여 정책을 할당합니다.
5. 그룹에 정책을 배포하려면 저장 을 **선택합니다.** 정책이 대상으로 하는 사용자 장치는 규정 준수로 평가됩니다.

### <a name="step-5-create-an-azure-ad-conditional-access-policy"></a>5단계: Azure AD 조건부 액세스 정책 만들기

1. Azure [Portal에서](https://portal.azure.com) **조건부 Azure Active Directory** \> **새 정책 을 열** 수 \> **있습니다.**
2. 정책 이름 **을 입력하고** 사용자 및 **그룹을 선택합니다.** 포함 또는 제외 옵션을 사용하여 정책에 대한 그룹을 추가하고 완료 를 **선택합니다.**
3. 클라우드 **앱 을** 선택하고 보호할 앱을 선택합니다. 예를 들어 앱 **선택 을** 선택하고 Office 365 SharePoint **Online을** **선택하고** Office 365 Exchange Online. **완료** 를 선택하여 변경 내용을 저장합니다.

4. 조건 **클라이언트** 앱을 선택하여 앱 및 \>  브라우저에 정책을 적용합니다. 예를 들어 **예, 를** 선택한 다음 **브라우저** 및 모바일 앱 및 데스크톱 클라이언트를 **사용하도록 설정할 수 있습니다.** **완료** 를 선택하여 변경 내용을 저장합니다.

5. 장치 **준수에** 따라 조건부 액세스를 적용하려면 허용을 선택합니다. 예를 들어 **액세스 허용 디바이스를** \> **규격으로 표시해야 합니다.를 선택합니다.** **선택을** 선택하여 변경 내용을 저장합니다.

6. 정책 **사용 을** 선택한 다음 **만들기를 선택하여** 변경 내용을 저장합니다.

자세한 내용은 Intune에서 조건부 액세스를 통해 [끝점에 대한 Microsoft Defender 준수 적용을 참조하세요.](/intune/advanced-threat-protection)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-conditionalaccess-belowfoldlink)
