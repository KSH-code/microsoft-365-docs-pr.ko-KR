---
title: Microsoft 365 수비수를 켜면 자주 묻는 질문
description: Microsoft 365 Defender를 활성화하는 데 관련된 라이선스, 사용 권한, 초기 설정 및 기타 제품 및 서비스에 대해 가장 일반적으로 묻는 질문에 대한 답변을 얻으십시오.
keywords: 자주 묻는 질문, FAQ, GCC, 시작, Microsoft 365 수비수, Microsoft 365 수비수, M365, 보안, 데이터 위치, 필요한 권한, 라이센스 자격, 설정 페이지를 활성화
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 008e3cc6ee65597a032aa932b74a64ac591927f2
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572768"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a>Microsoft 365 수비수를 켜면 자주 묻는 질문

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

필요한 라이선스 및 사용 권한, 지원 서비스 배포 및 초기 설정을 포함하여 [Microsoft 365 Defender를](microsoft-365-defender.md)켜는 것에 대해 가장 일반적으로 묻는 질문에 대한 답변을 읽어보십시오.

서비스를 켜는 방법에 대한 지침은 [Microsoft 365 수비수를 켜십시오.](m365d-enable.md)

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a>Microsoft 365 E5 라이선스가 없습니다. Microsoft 365 수비수를 사용할 수 있습니까?

다음과 같은 비 E5 라이선스를 사용하는 고객은 Microsoft 365 Defender를 사용할 수 있습니다.

- 끝점용 Microsoft Defender
- ID용 Microsoft Defender
- Microsoft Cloud App Security
- Office 365용 Defender(플랜 2)
 
지원되는 라이선스의 전체 목록은 [라이선스 요구 사항을 참조하십시오.](prerequisites.md#licensing-requirements)

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a>Microsoft 365 수비수를 사용하기 위해 설치하거나 배포해야 합니까?

아니요, Microsoft 365 Defender는 이미 배포한 Microsoft 365 보안 서비스의 데이터를 통합합니다. 이를 켜면 인시던트, 자동화 및 사냥 경험이 배포된 제품의 범위 내에서 작업을 시작합니다. 이러한 제품이 제대로 배포되지 않으면 Microsoft 365 Defender는 데이터를 표시하지 않으며 조치를 취할 수 없습니다.

Microsoft 365 Defender 환경을 최적화하려면 지원되는 *모든* [Microsoft 365 보안 제품 및 서비스를](deploy-supported-services.md)배포하는 것이 좋습니다.

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a>Microsoft 365 Defender는 데이터를 처리하고 저장하는 곳은 어디입니까?
Microsoft 365 Defender는 통합 된 데이터가 처리되고 저장되는 데이터 센터에 대한 최적의 위치를 자동으로 선택합니다. 엔드포인트에 대한 Microsoft Defender가 있는 경우 끝점에 대한 Defender에서 사용하는 동일한 위치를 선택합니다.

>[!NOTE]
>엔드포인트에 대한 Microsoft Defender는 Azure Defender를 통해 켜지면 유럽 연합(EU) 데이터 센터에서 자동으로 규정을 제공합니다. Microsoft 365 Defender는 이러한 방식으로 엔드포인트에 대한 Microsoft Defender를 프로비전한 고객을 위해 동일한 EU 데이터 센터에서 자동으로 프로비저닝됩니다. 

데이터 센터 위치는 서비스가 Microsoft 365 **Defender(설정 > Microsoft 365 Defender)의** 설정 페이지에 프로비전되기 전과 후에 표시됩니다. 다른 데이터 센터 위치를 사용하려면 Microsoft 365 보안 센터에서 **도움말 필요를** 선택하여 Microsoft 지원에 문의하십시오.

## <a name="where-can-i-access-microsoft-365-defender"></a>수비수 Microsoft 365 어디에서 액세스할 수 있습니까?

Microsoft 365 수비수는 Microsoft 365 보안 센터에서 사용할 수 있습니다. 보안 센터로 이동하려면 URL을 [https://security.microsoft.com](https://security.microsoft.com) 찾아봅타보겠습니다.

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a>보안 센터에서 Microsoft 365 Defender에 액세스하려면 Microsoft 365 어떤 권한이 필요합니까?

다음 Azure Active Directory(Azure AD) 역할이 할당된 계정은 Microsoft 365 Defender 기능 및 데이터에 액세스할 수 있습니다.

- 전역 관리자
- 보안 관리자
- 보안 운영자
- 전역 읽기 권한자
- 보안 읽기 권한자

>[!NOTE]
>엔드포인트에 대한 Microsoft Defender의 역할 기반 액세스 제어 설정은 데이터에 대한 액세스에 영향을 미칩니다. 자세한 내용은 Microsoft 365 [Defender에 대한 액세스 관리에](m365d-permissions.md)대해 읽어보십시오.

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a>Microsoft 365 어떤 시간대에 수비수가 기본값으로 지정합니까?
기본적으로 Microsoft 365 Defender는 UTC 표준 시간대에 시간 정보를 표시합니다. 로컬 표준 시간대를 사용하도록 이 설정을 변경할 수 있습니다. [표준 시간대 설정에 대해 알아보기](m365d-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a>새로운 Microsoft 365 Defender 기능 및 UI 업데이트에 대해 어떻게 알아보세요.

Microsoft는 정기적으로 다음과 같은 다양한 채널을 통해 정보를 제공합니다.

- Microsoft 365 관리 센터의 [메시지 센터](../../admin/manage/message-center.md)
- Microsoft 365 보안 [& 규정 준수 기술 커뮤니티의](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance) 블로그 포스트

[미리 보기 기능을](preview.md)켜서 공개적으로 사용할 수 있는 최신 환경을 가져옵니다.

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a>Microsoft 365 수비수는 미국 정부 커뮤니티 클라우드 (GCC) 또는 GCC 높음에 사용할 수 있습니까?
현재는 사용불가합니다. 

## <a name="related-topics"></a>관련 항목

- [Microsoft 365 수비수 개요](microsoft-365-defender.md)
- [Microsoft 365 수비수를 켭니다.](m365d-enable.md)
- [라이선스 요구 사항 및 기타 필수 구성 요소](prerequisites.md)
- [지원 서비스 배포](deploy-supported-services.md)
- [미리 보기 기능 설정](preview.md)
