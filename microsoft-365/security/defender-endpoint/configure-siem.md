---
title: 끝점용 Microsoft Defender에서 SIEM 도구로 검색 끌어오기
description: REST API를 사용하는 방법을 알아보고 검색을 수신하고 끌어오도록 지원되는 보안 정보 및 이벤트 관리 도구를 구성합니다.
keywords: siem 구성, 보안 정보 및 이벤트 관리 도구, splunk, arcsight, 사용자 지정 표시기, rest api, 경고 정의, 손상 표시기
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
ms.openlocfilehash: 80a56ac33b11962028e6735a28d8a4692226d306
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60209960"
---
# <a name="pull-detections-to-your-siem-tools"></a>SIEM 도구로 검색 끌어오기

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configuresiem-abovefoldlink)

## <a name="pull-detections-using-security-information-and-events-management-siem-tools"></a>SIEM(보안 정보 및 이벤트 관리) 도구를 사용하여 검색 끌어오기

> [!NOTE]
>
> - [끝점용 Microsoft Defender 경고는](alerts.md) 하나 이상의 검색으로 구성됩니다.
> - [끝점 검색을 위한 Microsoft Defender는](api-portal-mapping.md) 장치 및 관련 경고 세부 정보에서 발생한 의심스러운 이벤트로 구성됩니다.
> -The Microsoft Defender for Endpoint Alert API는 경고 소비를 위한 최신 API로, 각 경고에 대한 자세한 관련 증거 목록을 제공합니다. 자세한 내용은 [Alert 메서드](alerts.md) 및 속성 및 목록 [경고를 참조하세요.](get-alerts.md)

Endpoint용 Defender는 검색을 끌어오기 위한 SIEM(보안 정보 및 이벤트 관리) 도구를 지원합니다. Endpoint용 Defender는 Azure에서 호스트된 HTTPS 끝점을 통해 경고를 노출합니다. 환경에 설치된 특정 SIEM 커넥터를 나타내는 AAD 응용 프로그램에 대해 OAuth 2.0 인증 프로토콜을 사용하여 AAD(Azure Active Directory)의 엔터프라이즈 테넌트에서 검색을 끌어오도록 끝점을 구성할 수 있습니다.

Endpoint용 Defender는 현재 전용 SIEM 통합 모델을 통해 다음과 같은 특정 SIEM 솔루션 도구를 지원합니다.

- IBM QRadar
- 마이크로 포커스 ArcSight

Splunk, RSA NetWitness 등의 다른 SIEM 솔루션은 새로운 경고 API를 기반으로 하는 다른 통합 모델을 통해 지원됩니다. 자세한 내용은 파트너 [](https://securitycenter.microsoft.com/interoperability/partners) 응용 프로그램 페이지를 보고 전체 세부 정보를 확인하려면 보안 정보 및 분석 섹션을 선택합니다.

지원되는 SIEM 도구 중 하나를 사용하려면 다음을 해야 합니다.

- [Endpoint용 Defender에서 SIEM 통합 사용](enable-siem-integration.md)
- 지원되는 SIEM 도구를 구성합니다.
  - [엔드포인트 감지를 위해 Defender를 끌어오도록 마이크로 포커스 ArcSight 구성](configure-arcsight.md)
  - 끝점 검색을 위해 Defender를 끌어오도록 IBM QRadar 구성 자세한 내용은 [IBM 기술 센터를 참조하세요.](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/com.ibm.dsm.doc/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1)

검색 API에 노출된 필드 목록에 대한 자세한 내용은 Endpoint 검색 [필드에 대한 Defender를 참조하세요.](api-portal-mapping.md)
