---
title: Microsoft Threat Protection을 켤 때 자주 묻는 질문
description: Microsoft Threat Protection을 사용 하도록 설정 하는 것과 관련 된 라이선스, 사용 권한, 초기 설정 및 기타 제품 및 서비스에 대 한 가장 일반적인 질문과 대답을 볼 수 있습니다.
keywords: 자주 묻는 질문, FAQ, GCC, 시작, MTP 사용, Microsoft Threat Protection, M365, 보안, 데이터 위치, 필수 권한, 라이선스 자격, 설정 페이지
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 6b0d8d9be0cc84e61a3228f79fc14f1bfc9f8a83
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198842"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-threat-protection"></a>Microsoft Threat Protection을 켤 때 자주 묻는 질문

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 위협 방지

필수 라이선스 및 사용 권한, 지원 서비스 배포 및 초기 설정을 포함 하 여 [Microsoft Threat Protection](microsoft-threat-protection.md)을 설정 하는 방법에 대 한 가장 일반적인 질문에 대 한 답변을 제공 합니다.

서비스를 설정 하는 방법에 대 한 자세한 내용은 [Microsoft Threat Protection 사용을 참조](mtp-enable.md)하십시오.

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-threat-protection"></a>Microsoft 365 E5 라이선스가 없습니다. 여전히 Microsoft Threat Protection을 사용할 수 있나요?

다음과 같은 E5 이외의 라이선스를 가진 고객은 Microsoft Threat Protection을 사용할 수 있습니다.

- Microsoft Defender Advanced Threat Protection
- Azure Advanced Threat Protection
- Microsoft Cloud App Security
- Office 365 Advanced Threat Protection (계획 2)
 
지원 되는 라이선스의 전체 목록을 보려면 [라이선스 요구 사항을 참조](prerequisites.md#licensing-requirements)하세요.

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-threat-protection"></a>Microsoft Threat Protection을 사용 하 여 시작 하려면 모든 것을 설치 하거나 배포 해야 하나요?

아니요, Microsoft Threat Protection은 이미 배포한 Microsoft 365 보안 서비스의 데이터를 통합 합니다. 이 기능을 켜면 인시던트, 자동화 및 찾기 환경이 배포 된 제품의 범위 내에서 작동 하 게 됩니다. 이러한 제품이 제대로 배포 되지 않은 경우 Microsoft Threat Protection은 데이터를 표시 하지 않으며 어떤 작업을 수행할 수 없습니다.

Microsoft Threat Protection 환경을 최적화 하기 위해 지원 되는 *모든* [Microsoft 365 보안 제품 및 서비스](deploy-supported-services.md)를 배포 하는 것이 좋습니다.

## <a name="where-does-microsoft-threat-protection-process-and-store-my-data"></a>Microsoft Threat Protection에서 데이터를 처리 하 고 저장 하는 위치
Microsoft Threat Protection은 통합 데이터가 처리 되 고 저장 되는 데이터 센터에 대 한 최적의 위치를 자동으로 선택 합니다. Microsoft Defender ATP가 있으면 Microsoft Defender ATP에서 사용 하는 것과 동일한 위치를 선택 합니다.

>[!NOTE]
>Azure 보안 센터를 통해 설정 하는 경우 Microsoft Defender ATP는 EU (유럽 연합) 데이터 센터를 자동으로 프로 비전 합니다. Microsoft Threat Protection은 이러한 방식으로 Microsoft Defender ATP를 프로 비전 한 고객을 위해 동일한 EU 데이터 센터를 자동으로 프로 비전 합니다. 

데이터 센터 위치는 Microsoft Threat Protection (**설정 > Microsoft Threat protection**)에 대 한 설정 페이지에서 서비스가 프로 비전 되기 전과 후에 표시 됩니다. 다른 데이터 센터 위치를 사용 하려면 microsoft 365 보안 센터에서 Microsoft 지원 서비스에 문의 **하세요** .를 선택 합니다.

## <a name="where-can-i-access-microsoft-threat-protection"></a>Microsoft Threat Protection에 액세스할 수 있는 위치

Microsoft Threat Protection은 Microsoft 365 보안 센터에서 사용할 수 있습니다. 보안 센터로 이동 하 여 URL을 찾습니다 [https://security.microsoft.com](https://security.microsoft.com) .

##  <a name="what-permissions-do-i-need-to-access-microsoft-threat-protection-in-microsoft-365-security-center"></a>Microsoft 365 보안 센터에서 Microsoft 위협 보호에 액세스 하는 데 필요한 사용 권한은 무엇입니까?

다음 Azure AD(Active Directory) 역할이 할당 된 계정은 Microsoft 위협 방지 기능 및 데이터에 액세스할 수 있습니다.

- 전역 관리자
- 보안 관리자
- 보안 운영자
- 전역 읽기 권한자
- 보안 읽기 권한자

>[!NOTE]
>Microsoft Defender ATP의 역할 기반 액세스 제어 설정은 데이터에 대 한 액세스에 영향을 줍니다. 자세한 내용은 [Microsoft Threat Protection에 대 한 액세스 관리](mtp-permissions.md)를 참조 하세요.

## <a name="what-time-zone-does-microsoft-threat-protection-default-to"></a>Microsoft Threat Protection이 기본적으로 어떤 표준 시간대에 있습니까?
기본적으로 Microsoft Threat Protection은 시간 정보를 UTC 표준 시간대에 표시 합니다. 현지 표준 시간대를 사용 하도록이 설정을 변경할 수 있습니다. [표준 시간대 설정에 대 한 자세한 정보](mtp-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-threat-protection-feature-and-ui-updates"></a>새로운 Microsoft 위협 방지 기능 및 UI 업데이트에 대 한 자세한 내용은 어떻게 확인할 수 있나요?

Microsoft는 다음을 비롯 한 다양 한 채널을 통해 정보를 정기적으로 제공 합니다.

- Microsoft 365 관리 센터의 [메시지 센터](../../admin/manage/message-center.md)
- [Microsoft 365 보안 & 준수 기술 커뮤니티](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance) 의 blogposts

[미리 보기 기능](preview.md)을 설정 하 여 공개적으로 사용 가능한 최신 환경을 가져옵니다.

## <a name="is-microsoft-threat-protection-available-for-us-government-community-cloud-gcc-or-gcc-high"></a>GCC(미국 정부 커뮤니티 클라우드)나 GCC High에서 Microsoft Threat Protection을 사용할 수 있나요?
현재는 사용불가합니다. 

## <a name="related-topics"></a>관련 항목

- [Microsoft 위협 방지 개요](microsoft-threat-protection.md)
- [Microsoft Threat Protection을 사용 하도록 설정](mtp-enable.md)합니다.
- [라이선스 요구 사항 및 기타 필수 구성 요소](prerequisites.md)
- [지원 서비스 사용](deploy-supported-services.md)
- [미리 보기 기능 설정](preview.md)
