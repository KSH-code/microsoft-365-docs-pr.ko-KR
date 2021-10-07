---
title: 이 기능을 켜면 자주 묻는 Microsoft 365 Defender
description: 라이선스, 사용 권한, 초기 설정 및 라이선스 사용과 관련된 기타 제품 및 서비스에 대한 가장 일반적으로 Microsoft 365 Defender
keywords: 질문과 대답, FAQ, GCC, 시작, Microsoft 365 Defender, Microsoft 365 Defender, M365, 보안, 데이터 위치, 필요한 사용 권한, 라이선스 자격, 설정 페이지
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: ac26e2528698cc671c5cb45eb507d01900a77ec4
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60162329"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a>이 기능을 켜면 자주 묻는 Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

필요한 라이선스 및 사용 권한, 지원 서비스 [배포 및](microsoft-365-defender.md)초기 설정을 포함하여 Microsoft 365 Defender 설정과 관련한 가장 일반적으로 묻는 질문에 대한 응답을 읽습니다.

서비스를 켜는 방법에 대한 지침은 켜기 를 [Microsoft 365 Defender.](m365d-enable.md)

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a>I don't have a Microsoft 365 E5. 계속 사용할 수 Microsoft 365 Defender?

다음과 같은 비 E5 라이선스를 사용하는 고객은 다음을 사용할 수 Microsoft 365 Defender.

- 엔드포인트용 Microsoft Defender
- ID용 Microsoft Defender
- Microsoft Cloud App Security
- Office 365용 Defender(플랜 2)

지원되는 라이선스의 전체 목록은 라이선스 [요구 사항을 읽어 보아야 합니다.](prerequisites.md#licensing-requirements)

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a>설치 또는 배포를 통해 시작하려면 Microsoft 365 Defender?

아니요. Microsoft 365 Defender 배포한 Microsoft 365 보안 서비스의 데이터를 통합합니다. 켜면 인시던트, 자동화 및 헌팅 환경이 배포된 제품의 범위 내에서 작동하기 시작하게 됩니다. 이러한 제품이 제대로 배포되지 않은 경우 Microsoft 365 Defender 데이터가 표시되지 않습니다. 작업을 수행하지 못합니다.

보안 Microsoft 365 Defender 환경을 최적화하기 위해 지원되는  모든 보안 제품 및 Microsoft 365 [배포하는 것이 좋습니다.](deploy-supported-services.md)

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a>데이터를 Microsoft 365 Defender 저장하는 위치

Microsoft 365 Defender 통합 데이터가 처리되고 저장되는 데이터 센터에 대한 최적의 위치를 자동으로 선택합니다. 끝점용 Microsoft Defender가 있는 경우 Endpoint용 Defender에서 사용하는 동일한 위치를 선택합니다.

>[!NOTE]
>끝점용 Microsoft Defender는 Azure Defender를 통해 켜져 있는 경우 유럽 연합(EU) 데이터 센터에서 자동으로 프로비전합니다. Microsoft 365 Defender Microsoft Defender for Endpoint를 이 방식으로 프로비전한 고객을 위해 동일한 EU 데이터 센터에서 자동으로 프로비전합니다.

데이터 센터 위치는 서비스를 프로비전하기 전과 후에 **Microsoft 365 Defender(설정 > Microsoft 365 Defender).** 다른 데이터 센터 위치를 사용하려면 microsoft 지원 센터에 문의하려면 Microsoft 365 Defender 포털에서 도움이 **필요하세요?를** 선택합니다.

## <a name="where-can-i-access-microsoft-365-defender"></a>어디에서 액세스할 수 Microsoft 365 Defender?

Microsoft 365 Defender 에서 사용할 수 <https://security.microsoft.com> 있습니다.

## <a name="what-permissions-do-i-need-to-access-microsoft-365-defender"></a>어떤 사용 권한에 액세스해야 Microsoft 365 Defender?

다음 Azure AD(Azure Active Directory) 역할이 할당된 계정은 Microsoft 365 Defender 데이터에 액세스할 수 있습니다.

- 전역 관리자
- 보안 관리자
- 보안 운영자
- 전역 읽기 권한자
- 보안 읽기 권한자

> [!NOTE]
> 엔드포인트용 Microsoft Defender의 역할 기반 액세스 제어 설정은 데이터에 대한 액세스에 영향을 미칩니다. 자세한 내용은 [Microsoft 365 Defender에 대한 액세스 관리](m365d-permissions.md)를 참조하세요.

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a>기본 표준 시간대는 Microsoft 365 Defender 표준 시간대는 무엇입니까?

기본적으로 Microsoft 365 Defender UTC 표준 시간대에 시간 정보가 표시됩니다. 이 설정을 변경하여 로컬 표준 시간대를 사용할 수 있습니다. [표준 시간대 설정에 대해 자세히](m365d-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a>새로운 업데이트 기능 및 UI Microsoft 365 Defender 어떻게 알 수 있나요?

Microsoft는 다음을 비롯한 다양한 채널을 통해 정기적으로 정보를 제공합니다.

- 메시지 [센터의](../../admin/manage/message-center.md) Microsoft 365 관리 센터
- 보안 및 규정 [Microsoft 365 커뮤니티의](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance) 블로그 & 커뮤니티

미리 보기 기능을 켜서 공개적으로 사용할 수 있는 최신 [환경을 얻습니다.](preview.md)

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a>US Microsoft 365 Defender(us 정부 커뮤니티 클라우드) 또는 GCC 사용할 GCC 있습니까?

현재는 사용불가합니다. 

## <a name="related-topics"></a>관련 항목

- [Microsoft 365 Defender 개요](microsoft-365-defender.md)
- [를 Microsoft 365 Defender.](m365d-enable.md)
- [라이선스 요구 사항 및 기타 필수 구성 요소](prerequisites.md)
- [지원 서비스 배포](deploy-supported-services.md)
- [미리 보기 기능 설정](preview.md)
