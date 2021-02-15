---
title: Microsoft 365 Defender를 끄는 경우 자주 묻는 질문과 대답
description: Microsoft 365 Defender 사용과 관련된 라이선싱, 사용 권한, 초기 설정 및 기타 제품 및 서비스에 대한 가장 일반적으로 묻는 질문에 대한 답변을 얻습니다.
keywords: 자주 묻는 질문, FAQ, GCC, 시작, MTP 사용, Microsoft Threat Protection, M365, 보안, 데이터 위치, 필요한 사용 권한, 라이선스 자격, 설정 페이지
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
ms.openlocfilehash: 2cb9aed070959644e3660188835386118d5f4d9b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930189"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a>Microsoft 365 Defender를 끄는 경우 자주 묻는 질문과 대답

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

필수 라이선스 및 사용 권한, 지원 서비스 배포 및 초기 설정을 포함하여 [Microsoft 365 Defender](microsoft-threat-protection.md)켜기와 관련한 가장 일반적인 질문과 대답을 읽어 읽습니다.

서비스를 켜는 방법에 대한 지침은 [Microsoft 365 Defender 켜기 를 읽어 읽습니다.](mtp-enable.md)

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a>Microsoft 365 E5 라이선스가 없습니다. Microsoft 365 Defender를 계속 사용할 수 있나요?

다음 비 E5 라이선스가 있는 고객은 Microsoft 365 Defender를 사용할 수 있습니다.

- 엔드포인트용 Microsoft Defender
- ID용 Microsoft Defender
- Microsoft Cloud App Security
- Office 365용 Defender(계획 2)
 
지원되는 라이선스의 전체 목록은 라이선스 [요구 사항을 읽어야 합니다.](prerequisites.md#licensing-requirements)

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a>Microsoft 365 Defender를 사용하려면 설치하거나 배포해야 하나요?

아니요. Microsoft 365 Defender는 이미 배포한 Microsoft 365 보안 서비스의 데이터를 통합합니다. 켜면 인시던트, 자동화 및 헌팅 환경이 배포된 제품의 범위 내에서 작동하기 시작하게 됩니다. 이러한 제품이 제대로 배포되지 않은 경우 Microsoft 365 Defender는 데이터를 표시하지 않습니다. 어떠한 조치도 취하지 못합니다.

Microsoft 365 Defender 환경을 최적화하기 위해  지원되는 [모든 Microsoft 365](deploy-supported-services.md)보안 제품 및 서비스를 배포하는 것이 좋습니다.

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a>Microsoft 365 Defender는 어디에서 데이터를 처리하고 저장하나요?
Microsoft 365 Defender는 통합 데이터가 처리되고 저장되는 데이터 센터에 대한 최적의 위치를 자동으로 선택합니다. 끝점용 Microsoft Defender가 있는 경우 끝점용 Defender에서 사용하는 동일한 위치를 선택합니다.

>[!NOTE]
>끝점용 Microsoft Defender는 Azure Defender를 통해 켜져 있는 경우 유럽 연합(EU) 데이터 센터에서 자동으로 프로비전합니다. Microsoft 365 Defender는 이 방식으로 끝점용 Microsoft Defender를 프로비전한 고객을 위해 동일한 EU 데이터 센터에서 자동으로 프로비전합니다. 

데이터 센터 위치는 Microsoft 365 Defender의 설정 페이지에 서비스가 프로비전되기 전과 후에 **표시됩니다(Microsoft 365 Defender의** 설정 >). 다른 데이터 센터 위치를 사용하려면 Microsoft 365 보안 센터에서 도움이 **필요하세요?** Microsoft 지원 센터에 문의하세요.

## <a name="where-can-i-access-microsoft-365-defender"></a>Microsoft 365 Defender는 어디에서 액세스할 수 있나요?

Microsoft 365 Defender는 Microsoft 365 보안 센터에서 사용할 수 있습니다. 보안 센터로 이동하기 위해 URL로 [https://security.microsoft.com](https://security.microsoft.com) 이동하십시오.

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a>Microsoft 365 보안 센터에서 Microsoft 365 Defender에 액세스하는 데 필요한 사용 권한은 무엇입니까?

다음 Azure AD(Active Directory) 역할이 할당된 계정은 Microsoft 365 Defender 기능 및 데이터에 액세스할 수 있습니다.

- 전역 관리자
- 보안 관리자
- 보안 운영자
- 전역 읽기 권한자
- 보안 읽기 권한자

>[!NOTE]
>끝점용 Microsoft Defender의 역할 기반 액세스 제어 설정은 데이터에 대한 액세스에 영향을 미치게 됩니다. 자세한 내용은 Microsoft [365 Defender에 대한 액세스 관리에 대해 읽어보아야 합니다.](mtp-permissions.md)

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a>Microsoft 365 Defender는 어떤 표준 시간대를 기본으로 하나요?
기본적으로 Microsoft 365 Defender는 UTC 표준 시간대에 시간 정보를 표시합니다. 이 설정을 변경하여 현지 표준 시간대를 사용할 수 있습니다. [표준 시간대 설정에 대해 자세히](mtp-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a>새로운 Microsoft 365 Defender 기능 및 UI 업데이트에 대해 어떻게 알 수 있나요?

Microsoft는 다음을 비롯한 다양한 채널을 통해 정보를 정기적으로 제공합니다.

- Microsoft [](../../admin/manage/message-center.md) 365 관리 센터의 메시지 센터
- [Microsoft 365](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance) 보안 및 규정 & 커뮤니티의 블로그

미리 보기 기능을 켜서 공개적으로 사용할 수 있는 최신 환경을 [얻습니다.](preview.md)

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a>Microsoft 365 Defender를 미국 GCC(정부 커뮤니티 클라우드) 또는 GCC High에서 사용할 수 있나요?
현재는 사용불가합니다. 

## <a name="related-topics"></a>관련 항목

- [Microsoft 365 Defender 개요](microsoft-threat-protection.md)
- [Microsoft 365 Defender 켜기.](mtp-enable.md)
- [라이선스 요구 사항 및 기타 필수 구성 요소](prerequisites.md)
- [지원 서비스 배포](deploy-supported-services.md)
- [미리 보기 기능 설정](preview.md)
