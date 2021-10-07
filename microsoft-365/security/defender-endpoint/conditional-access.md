---
title: 조건부 액세스를 사용하도록 설정하여 사용자, 장치 및 데이터를 보다 잘 보호
description: 조건부 액세스를 사용하도록 설정하여 장치가 위험 상태인 것으로 간주되고 응용 프로그램이 호환되지 않는 것으로 결정된 경우 응용 프로그램이 실행되지 않도록 합니다.
keywords: 조건부 액세스, 응용 프로그램 차단, 보안 수준, intune,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 93b547718bca2fb157c3b4e0a4b08d383ec92e4f
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60196996"
---
# <a name="enable-conditional-access-to-better-protect-users-devices-and-data"></a>조건부 액세스를 사용하도록 설정하여 사용자, 장치 및 데이터를 보다 잘 보호

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-conditionalaccess-abovefoldlink)

조건부 액세스는 보안 장치만 응용 프로그램에 액세스할 수 있도록 하여 사용자 및 엔터프라이즈 정보를 보다 잘 보호하는 데 도움이 되는 기능입니다.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4byD1]

조건부 액세스를 사용하면 장치의 위험 수준에 따라 엔터프라이즈 정보에 대한 액세스를 제어할 수 있습니다. 이렇게 하면 신뢰할 수 있는 사용자가 신뢰할 수 있는 응용 프로그램을 사용하여 신뢰할 수 있는 디바이스를 유지하는 데 도움이 됩니다.

장치 및 응용 프로그램이 실행되고 네트워크의 정보에 액세스할 수 있는 보안 조건을 정의하려면 장치가 규격 상태로 돌아올 때까지 응용 프로그램 실행을 중지하는 정책을 적용합니다.

끝점용 Defender의 조건부 액세스 구현은 Microsoft Intune(Intune) 장치 준수 정책 및 Azure AD(Azure Active Directory 액세스 정책)를 기반으로 합니다.

준수 정책은 조건부 액세스와 함께 하나 이상의 장치 준수 정책 규칙을 충족하는 장치만 응용 프로그램에 액세스할 수 있도록 허용하는 데 사용됩니다.

## <a name="understand-the-conditional-access-flow"></a>조건부 액세스 흐름 이해

조건부 액세스는 장치에 위협이 있는 경우 위협이 수정될 때까지 중요한 콘텐츠에 대한 액세스가 차단될 수 있도록 설정됩니다.

흐름은 낮은, 보통 또는 높은 위험을 지고 있는 장치로 시작됩니다. 이러한 위험 결정은 Intune으로 전송됩니다.

Intune에서 정책을 구성하는 방법에 따라 특정 조건이 충족될 때 정책이 적용될 수 있도록 조건부 액세스를 설정할 수 있습니다.

예를 들어 위험이 높은 장치에 조건부 액세스를 적용하도록 Intune을 구성할 수 있습니다.

Intune에서 장치 준수 정책은 Azure AD 조건부 액세스와 함께 사용하여 응용 프로그램에 대한 액세스를 차단합니다. 동시에 자동화된 조사 및 수정 프로세스가 실행됩니다.

 사용자는 자동화된 조사 및 수정이 진행되는 동안에도 장치를 사용할 수 있지만 위협이 완전히 해결될 때까지 엔터프라이즈 데이터에 대한 액세스는 차단됩니다.

장치에서 발견되는 위험을 해결하려면 장치를 규격 상태로 되찾아야 합니다. 장치가 위험에 노출될 위험이 없는 경우 규격 상태로 돌아올 수 있습니다.

위험을 해결할 수 있는 방법에는 세 가지가 있습니다.

1. 수동 또는 자동화된 수정을 사용 합니다.
2. 장치에서 활성 경고를 해결합니다. 이렇게 하면 장치에서 위험이 제거됩니다.
3. 활성 정책에서 장치를 제거할 수 있으며 결과적으로 조건부 액세스가 장치에 적용되지 않습니다.

수동 수정을 위해서는 보안 관리자가 경고를 조사하고 장치에 표시될 위험을 해결해야 합니다. 자동화된 수정은 Configure Conditional Access 섹션에 제공된 구성 설정을 [통해 구성됩니다.](configure-conditional-access.md)

수동 또는 자동화된 수정을 통해 위험을 제거하면 장치가 규격 상태로 돌아와 응용 프로그램에 대한 액세스 권한이 부여됩니다.

다음 이벤트 시퀀스 예제에서는 조건부 액세스의 실행에 대해 설명합니다.

1. 사용자가 악성 파일을 열고 Endpoint용 Defender가 디바이스에 높은 위험으로 플래그를 지정합니다.
2. 높은 위험 평가는 Intune을 따라 전달됩니다. 동시에 식별된 위협을 수정하기 위해 자동화된 조사가 시작됩니다. 식별된 위협을 수정하기 위해 수동 수정을 할 수도 있습니다.
3. Intune에서 만든 정책에 따라 장치가 규격이 아닌 것으로 표시됩니다. 그런 다음 평가는 Intune 조건부 액세스 정책에 의해 Azure AD에 전달됩니다. Azure AD에서는 응용 프로그램에 대한 액세스를 차단하기 위해 해당 정책이 적용됩니다.
4. 수동 또는 자동화된 조사 및 수정이 완료되고 위협이 제거됩니다. Endpoint용 Defender는 장치에 위험이 없음을 보고 Intune은 장치가 규격 상태인 것으로 평가합니다. Azure AD는 응용 프로그램에 대한 액세스를 허용하는 정책을 적용합니다.
5. 이제 사용자가 응용 프로그램에 액세스할 수 있습니다.

## <a name="related-topic"></a>관련 항목

- [끝점용 Microsoft Defender에서 조건부 액세스 구성](configure-conditional-access.md)
